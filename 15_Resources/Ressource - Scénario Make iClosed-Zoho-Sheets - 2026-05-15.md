---
type: ressource-automation
source: debug + extension session Boris ×Claude — 15 mai 2026 + 18 mai 2026
date-build: pré-existant (avant la session du 12-13 mai)
date-analyzed: 2026-05-18 (J17)
status: V1.2 — production stabilisée (dédup + Tally Lookup + backfill historique)
participants: "Boris Arduy"
context: "scénario Make iClosed → Sheets + Zoho CRM pour gérer les bookings de calls. Crée Compte, Contact et Affaire dans Zoho selon que le contact existe déjà ou non (Router avec Search Contact). Préexistant avant le projet Kelly Launch V1.3 mais critique pour le funnel."
sensitivity: confidential
tags: [iclosed, make, zoho, automation, bookings, dedup, tally, backfill, J17, kelly-launch, debugging]
related: "[[Ressource - Automation Zoho-DocuSign Contrats BOSS-ENERGY - 2026-05-13]] (note V1.3 — scénarios complémentaires en aval), [[Kelly Launch]]"
---

# 🔁 Scénario Make iClosed → Sheets + Zoho — V1.2 (dédup + Tally Lookup)

> **Contexte** : scénario Make pré-existant qui ingère les bookings iClosed pour les enregistrer dans Google Sheets et créer/lier Compte + Contact + Affaire dans Zoho CRM. C'est le scénario **amont** du funnel Kelly Launch (avant les scénarios Zoho → DocuSign et Fermé Gagné → log Ventes documentés dans la note V1.3).
>
> **Pourquoi cette note** : 2 sessions de debug majeures (15 mai et 18 mai) ont permis de :
> - V1.1 (15 mai) : éliminer les doublons Sheets + Zoho via Data Store
> - V1.2 (18 mai) : remonter les réponses Tally dans les Affaires Zoho (backfill 4533 lignes + fix flow pour nouveaux bookings)

---

## ⚡ Synthèse en 30 secondes

### Session 15 mai (V1.1)
- 🟢 **Problème 1 résolu** : doublons Sheets + Zoho éliminés via module **Data Store Make** en position #2 du flow
- 🟡 **Problème 2 partiellement résolu** : les modules de création Compte (9) et Contact (10) dans la branche "Contact found" plantent quand le contact existe déjà (DUPLICATE_DATA), mais les error handlers **Resume** rattrapent → fonctionnellement OK mais pas optimal
- 🔴 **Cause racine du doublon** : iClosed émet **2 webhooks identiques** par booking malgré une config qui n'a que `Call booked` coché (retry interne ou comportement non-documenté)

### Session 18 mai (V1.2)
- 🟢 **Problème 3 résolu** : 5 champs Tally (Entreprise, Site web/LinkedIn, CA actuel, Pain points, Déjà coaché) absents des fiches Deal Zoho → ajoutés comme champs custom + remontés automatiquement à la création de l'Affaire
- 🟢 **Backfill historique exécuté** : ~4533 lignes Tally synchronisées vers les ~1015 Affaires Zoho existantes via un scénario Make dédié + script Apps Script (~30 min de tournage cumulé sur 7-8 runs Apps Script)
- 🟢 **Embeds iClosed ClickFunnels corrigés** : les 3 funnels (Momentum, Tip Talent, Next Sales) pointaient vers des slugs invalides → tous repassés sur le slug workspace `CGM` (le bon)

---

## 🏗️ Architecture actuelle V1.2

```
[1] iClosed (Watch Call Booked, webhook trigger)
      │
      ▼
[19] Data Store: Add/replace a record  ← FIX DÉDUP V1.1
      │
      ├──[error: Duplicate key]──▶ [20] Commit (stoppe proprement)
      │
      ▼ (succès — premier webhook reçu pour ce booking)
[15] Google Sheets: Search Rows (avec filter "Booking valide uniquement")
      │
      ▼
[2] Google Sheets: Add a Row (sur le sheet Bookings)
      │
      ▼
[4] Tools: Set multiple variables
      │
      ▼
[NEW] Google Sheets: Search Rows sur onglet "Tally"  ← AJOUTÉ V1.2
       filter email = booking email
       sort timestamp_received DESC, limit 1
       "Continue even if no result" = YES
      │
      ▼
[5] Zoho CRM: Search Objects (Contacts par email)
      │
      ▼
[7] Router (2 branches selon résultat du Search)
      │
      ├── Route 1 "Contact found" ─▶ [13] Zoho API Call (/v3/users) ─▶ [14] Iterator ─▶ [9] Create Compte → [Resume]
      │                                                                                    │
      │                                                                                    ▼
      │                                                                              [10] Create Contact → [Resume]
      │                                                                                    │
      │                                                                                    ▼
      │                                                                              [11] Create Affaire (avec 5 champs Tally  ← V1.2)
      │
      └── Route 2 "Contact not found" ──────────────────────────────────────▶ [11] Create Affaire (avec 5 champs Tally  ← V1.2)
```

---

## 🔑 Composants critiques

### Module Data Store (#19) — Garde-fou anti-doublon (V1.1)

| Paramètre | Valeur |
|---|---|
| Data store name | `iClosed Bookings Dedup` |
| Data structure | `Booking dedup structure` (1 field : `booking_id` Text) |
| Key utilisée | `{{1.callPreviewId}}` (ou équivalent — ID unique du booking iClosed) |
| Overwrite existing record | **No** ⚠️ critique |
| Storage size | 1 MB (largement suffisant) |

**Mécanique** : à chaque webhook iClosed reçu, on tente d'ajouter un record dans le store avec la key = booking ID. Si l'ID existe déjà (= 2ème webhook du même booking), le module renvoie une erreur "duplicate key". L'error handler **Commit** (#20) attrape cette erreur et arrête le scénario proprement.

### Module Tally Lookup (NEW V1.2) — Sheets Search Rows

Inséré entre le Module 4 (Tools: Set Variables) et le Module 5 (Zoho Search Contact).

| Paramètre | Valeur |
|---|---|
| Connection | `Boris (boris@entrepreneurs.com)` |
| Spreadsheet | `Stockage Tally` |
| Sheet | `Tally` |
| Table contains headers | Yes |
| Filter | `email` Equal to `{{1.payload.email}}` |
| Sort order | Descending |
| Sort column | `timestamp_received` |
| Maximum number of returned rows | **1** |
| Continue execution even if no result | **Yes** ⚠️ critique (sinon scénario stoppe si booking sans Tally) |

**Renommé** : `Tally Lookup` pour clarté du mapping.

### Modules Create Affaire (#11) — Mapping V1.2

Les 5 champs custom Affaires Zoho à mapper depuis le module `Tally Lookup` :

| Champ Zoho Affaire | Source Make | Wrap recommandé |
|---|---|---|
| Entreprise | `{{TallyLookup.company}}` | `ifempty(...; "")` |
| Site web / LinkedIn | `{{TallyLookup.website_or_linkedin}}` | `ifempty(...; "")` |
| CA actuel | `{{TallyLookup.revenue_range}}` | `ifempty(...; "")` |
| Pain points | `{{TallyLookup.pain_points}}` | `ifempty(...; "")` |
| Déjà coaché | `{{TallyLookup.previous_coaching}}` | `ifempty(...; "")` |

⚠️ Le mapping doit être présent dans **les 2 modules Create Affaire** (branche "Contact found" et branche "Contact not found").

---

## 📊 Champs Zoho custom ajoutés (Module Affaires) — V1.2

| Label affiché | Type | Usage |
|---|---|---|
| Entreprise | Une seule ligne | Nom de l'entreprise du lead (réponse Tally) |
| Site web / LinkedIn | URL | Site web ou LinkedIn (réponse Tally) |
| CA actuel | Une seule ligne | Tranche de CA (réponse Tally — typiquement `0 - 5K€/mois`, `5K - 20K€/mois`, etc.) |
| Pain points | Multi-ligne (petit) | Pain points sélectionnés (réponse Tally, multi-valeurs comma-separated) |
| Déjà coaché | Une seule ligne | Statut historique de coaching (réponse Tally) |

⚠️ **Choix design** : single line / multi-line (pas picklist) pour le backfill safe — accepte 100% des valeurs sans validation stricte. Possibilité de basculer en picklist V2 si volonté de segmentation BI.

---

## 🔄 Backfill historique V1.2 (18 mai) — Process exécuté

### Scénario Make `Backfill Tally → Zoho Deals`

URL webhook : `https://hook.eu2.make.com/5dji26h167u3dczyuo3x4ufr150kp3o5`

6 modules :
1. **Webhook trigger** — reçoit `{email, company, website, ca, pain, coache, row}`
2. **Zoho Search Records** sur Contacts par Email = `{{1.email}}`, limit 1
3. **Zoho Search Records** sur Deals par `Contact Name` = `{{2.id}}`, limit 10
4. **Router** :
   - Route 1 "Deals found" : bundles M3 > 0
   - Route 2 "No deals found" : bundles M3 = 0 (fallback)
5. **Zoho Update Record** (Route 1) — itère auto sur tous les bundles M3 (Scénario A multi-Deals)
6. **Sheets Add Row** dans onglet `Backfill Log` (succès)
7. **Sheets Add Row** dans onglet `Backfill Log` (échec, Route 2)

### Script Apps Script (dans Stockage Tally → Extensions → Apps Script)

Code complet conservé dans le projet Apps Script. Fonctions clés :
- `testBackfill5Rows()` — test initial sur 5 lignes pour valider le pipeline
- `backfillTallyToZoho()` — run complet, s'arrête à 4min40 (limite 6min Apps Script) puis à relancer manuellement
- `resetAllStatus()` — reset complet de la colonne Backfill Status (avec confirmation UI)

Constants :
- `WEBHOOK_URL` : URL du scénario Make backfill
- `SHEET_NAME` : `Tally`
- `PROGRESS_CELL` : `Z1` (cellule de progression live)
- `SLEEP_MS` : `150` (pause entre requêtes — rate limit Zoho safe)
- `MAX_RUNTIME_SEC` : `280` (s'arrête à 4min40)
- `FLUSH_EVERY` : `20` (refresh affichage tous les 20 lignes)

### Throughput observé
- ~475ms par ligne (Make + Zoho + Sheets cumulés)
- ~632 lignes par run Apps Script de 5 min
- ~7-8 runs nécessaires pour 4533 lignes
- ~30-40 min cumulé en tournage actif

### Coût Make réel
- ~5 ops par ligne (Webhook + Search Contact + Search Deals + Update + Log) 
- + multiplicateur Update si plusieurs Deals par Contact
- ~25K ops total pour 4533 lignes
- Plan Make Enterprise/custom Boris : 1.84M ops/mois, donc 1.4% du quota

### Colonne tracking
- Colonne `Backfill Status` ajoutée au sheet Tally
- Valeurs : `✅ Sent`, `⚠️ Skipped (no email)`, `❌ HTTP X`, `❌ [erreur]`
- Permet skip auto des lignes déjà traitées au relance

---

## 🐛 Pièges rencontrés & solutions (cumulé V1.1 + V1.2)

| # | Symptôme | Cause | Solution |
|---|---|---|---|
| 1 | 2 lignes apparaissent dans le sheet Bookings pour chaque booking iClosed | iClosed émet 2 webhooks par booking (retry interne ou comportement non-documenté) | Module Data Store en position #2 + error handler Commit |
| 2 | DUPLICATE_DATA `$.data[0].Email` sur module Create Contact (#10) | Contact existe déjà dans Zoho (re-booking) | Error handler **Resume** avec output `{}` (vide) |
| 3 | Webhook iClosed config "Call booked" seul mais quand même 2 émissions | Comportement non-documenté d'iClosed | Solution = dédup côté Make (cf. piège #1) |
| 4 | Backfill : match Affaire via `Email_du_signataire` (initial) | Email du signataire n'est pas renseigné au booking (rempli par closer en R3) | Match par Email côté Contact → puis Contact_Name côté Deals |
| 5 | Embed iClosed ClickFunnels "This iClosed link is not valid" | Slug workspace dans l'URL incorrect (avait `axel/`, `entrepreneurs/` au lieu de `CGM/`) | Mettre tous les embeds en `https://app.iclosed.io/e/CGM/[event-slug]` |
| 6 | Apps Script kill auto à 6 min | Limite max d'exécution Google Apps Script | Boucle interne qui s'arrête à 4min40 + relance manuelle (ou trigger time-based) |
| 7 | Boris ne veut pas désactiver le webhook iClosed (utilisé par d'autres automatisations) | Pas modifiable côté source | Dédup côté Make obligatoire |

---

## 📖 Runbook opérationnel

### "Les doublons reviennent dans le sheet Bookings"
1. Vérifier que le module Data Store (#19) est toujours en place
2. Vérifier que l'error handler Commit (#20) est connecté
3. Vérifier dans History qu'on voit bien 2 exécutions (1ère verte, 2ème stoppée par Commit)

### "Le scénario plante en cascade sur les modules 9 ou 10"
1. Vérifier que les error handlers Resume sont toujours en place
2. Si oui mais flow stoppé : Resume probablement configuré avec un output qui casse un module en aval — repasser sur output `{}` simple

### "Un nouveau booking n'a pas ses réponses Tally"
1. Vérifier que le module `Tally Lookup` (post-Module 4) est toujours en place
2. Vérifier qu'il a bien "Continue execution even if no result" = Yes
3. Vérifier que les 5 mappings sont présents sur les modules Create Affaire (les 2 occurrences dans les 2 branches Router)
4. Vérifier que le lead a bien rempli Tally avant de booker (lookup par email)

### "Backfill : retry uniquement les lignes en erreur"
Si certaines lignes Tally sont restées en `❌` après le backfill complet, il suffit de :
1. Filtrer le sheet Tally sur `Backfill Status` = "❌ *"
2. Effacer manuellement la valeur dans la colonne pour ces lignes (ou via filtre + delete content)
3. Relancer `backfillTallyToZoho()` — il reprendra uniquement les lignes vides

### "Régénérer le Data Store en cas de pollution"
1. Make → Data Stores → `iClosed Bookings Dedup` → Browse → sélectionner records → Delete
2. ⚠️ Attention : pendant ~5-10 min après reset, les éventuels doublons iClosed re-passeront

---

## 🔧 IDs critiques V1.2

| Élément | Valeur |
|---|---|
| Webhook scénario iClosed → Sheets+Zoho | `https://hook.eu2.make.com/im3bm6usbr8ywk8y0ayromociboehgcc` |
| Webhook scénario Backfill Tally → Zoho | `https://hook.eu2.make.com/5dji26h167u3dczyuo3x4ufr150kp3o5` |
| Data Store dédup | `iClosed Bookings Dedup` |
| Sheet ID Stockage Tally | `1XTVJvuabrKtScKaLNFl9bBo3n-75Gz7O2C3WyU0H0aI` |
| Slug workspace iClosed | `CGM` |
| Event link Momentum | `https://app.iclosed.io/e/CGM/kelly-momentum` |
| Event link Tip Talent | `https://app.iclosed.io/e/CGM/kelly-tiptalent` |
| Event link Next Sales | `https://app.iclosed.io/e/CGM/kelly-axel` |

---

## 🔄 Backlog V2 — Améliorations à arbitrer

### Priorité moyenne
- [ ] **Nettoyer la branche "Contact found"** : supprimer les modules 9 (Create Compte) et 10 (Create Contact) qui sont systématiquement en erreur Resume. Garder uniquement le module 11 (Create Affaire) qui lie l'Affaire au Contact + Compte existants via leur ID. Économie : 2 ops Make par booking sur contact existant.
- [ ] **Search Affaires avant Create dans branche "Contact found"** : éviter de créer une nouvelle Affaire si une Affaire active existe déjà (Stage ≠ Fermé Gagné/Perdu) dans les 30 derniers jours pour ce Contact.
- [ ] **Renommer slug `kelly-axel`** en `kelly-nextsales` côté iClosed quand Axel partira (juin 2026) — synchroniser avec mise à jour embed ClickFunnels et update template emails iClosed.

### Priorité basse
- [ ] **TTL sur le Data Store dédup** : purger les records de booking plus vieux que 7 jours (sinon store grossit indéfiniment — pas un problème immédiat sur 1MB)
- [ ] **Migrer sur Upsert au lieu de Resume** pour branche "Contact found" : remplacer les Create + Resume par Upsert (Search → Update or Create)
- [ ] **Trigger Apps Script time-based pour le backfill** : auto-relance toutes les 6 min en background (pour ne pas avoir à cliquer Exécuter manuellement) — uniquement utile si on a un autre backfill volumineux à faire un jour
- [ ] **Bascule slug workspace iClosed** `CGM` → `entrepreneurs` (cosmétique, à coordonner avec support iClosed — implique mise à jour de toutes les URLs sortantes)

---

## 📝 Méta

- **Construction V1** : pré-existante (avant 12 mai 2026), créateur initial inconnu
- **Refonte V1.1 (15 mai 2026, 18h40)** — session Boris × Claude, ~30 min
  - Ajout Data Store dédup + Commit handler
  - Doublons éliminés
- **Refonte V1.2 (18 mai 2026, 08h-10h)** — session Boris × Claude, ~2h
  - Création 5 champs custom Zoho (Module Affaires)
  - Création scénario Make dédié `Backfill Tally → Zoho Deals` (7 modules)
  - Création script Apps Script `backfillTallyToZoho` avec resume auto
  - Exécution backfill complet 4533 lignes (~30 min cumulé)
  - Ajout module Tally Lookup au scénario iClosed → Zoho pour les nouveaux bookings
  - Mapping 5 champs Tally dans modules Create Affaire (2 occurrences)
  - Fix des 3 embeds iClosed ClickFunnels (Momentum, Tip Talent, Next Sales)
- **Tests réussis** :
  - 15 mai 18h32 — Booking test avec email frais : 1 ligne Sheets + 1 Compte + 1 Contact + 1 Affaire
  - 18 mai 08h13 — Test Make backfill Run Once sur `borisarduy42@gmail.com` : 5 champs Tally remontés dans Affaire
  - 18 mai 08h26 — Test 5 lignes backfill : 5 fiches Zoho mises à jour (ex: Skin Cartography validé)
  - 18 mai ~10h00 — Backfill complet 4533 lignes terminé
  - 18 mai — Test fix flow iClosed → Zoho avec Tally Lookup : nouveau booking remonte les 5 champs Tally correctement
- **Next steps** :
  - Surveiller sur 24-48h en prod réelle que tout tient sur les vrais bookings live
  - Au départ d'Axel (juin) : reconfigurer les events `kelly-momentum` et `kelly-axel` côté iClosed pour router vers le successeur
