---
type: ressource-automation
source: debug session Boris ×Claude — 15 mai 2026
date-build: pré-existant (datant d'avant la session du 12-13 mai)
date-analyzed: 2026-05-15 (J14)
status: V1.1 — en production avec dédup Data Store (anti-doublon iClosed)
participants: "Boris Arduy"
context: "scénario Make iClosed → Sheets + Zoho CRM pour gérer les bookings de calls. Crée Compte, Contact et Affaire dans Zoho selon que le contact existe déjà ou non (Router avec Search Contact). Préexistant avant le projet Kelly Launch V1.3 mais critique pour le funnel."
sensitivity: confidential
tags: [iclosed, make, zoho, automation, bookings, dedup, J14, kelly-launch, debugging]
related: "[[Ressource - Automation Zoho-DocuSign Contrats BOSS-ENERGY - 2026-05-13]] (note V1.3 — scénarios complémentaires en aval), [[Kelly Launch]]"
---

# 🔁 Scénario Make iClosed → Sheets + Zoho — V1.1 avec dédup

> **Contexte** : scénario Make pré-existant qui ingère les bookings iClosed pour les enregistrer dans Google Sheets et créer/lier Compte + Contact + Affaire dans Zoho CRM. C'est le scénario **amont** du funnel Kelly Launch (avant les scénarios Zoho → DocuSign et Fermé Gagné → log Ventes documentés dans la note V1.3).
>
> **Pourquoi cette note** : debug session du 15 mai a révélé 2 problèmes (doublons Sheets + doublons Zoho) et apporté un fix par dédup via Data Store Make. Documenter pour traçabilité et runbook.

---

## ⚡ Synthèse en 30 secondes

- 🟢 **Problème 1 résolu (15 mai)** : doublons Sheets + Zoho éliminés via module **Data Store Make** en position #2 du flow
- 🟡 **Problème 2 partiellement résolu** : les modules de création Compte (9) et Contact (10) dans la branche "Contact found" plantent quand le contact existe déjà (DUPLICATE_DATA), mais les error handlers **Resume** rattrapent → fonctionnellement OK mais pas optimal
- 🟢 **Test validé** : 1 booking iClosed = 1 ligne Sheets + 1 Compte + 1 Contact + 1 Affaire dans Zoho
- 🔴 **Cause racine du doublon** : iClosed émet **2 webhooks identiques** par booking malgré une config qui n'a que `Call booked` coché (probablement retry interne ou comportement non-documenté de l'API iClosed)

---

## 🏗️ Architecture actuelle

```
[1] iClosed (Watch Call Booked, webhook trigger)
      │
      ▼
[19] Data Store: Add/replace a record  ← FIX DÉDUP — ajouté 15 mai
      │
      ├──[error: Duplicate key]──▶ [20] Commit (stoppe proprement le scénario)
      │
      ▼ (succès — premier webhook reçu pour ce booking)
[15] Google Sheets: Search Rows (avec filter "Booking valide uniquement")
      │
      ▼
[2] Google Sheets: Add a Row (sur le sheet Bookings, avec filter "Pas de duplicate")
      │
      ▼
[4] Tools: Set multiple variables
      │
      ▼
[5] Zoho CRM: Search Objects (cherche le Contact par email)
      │
      ▼
[7] Router (2 branches selon résultat du Search)
      │
      ├── Route 1 "Contact found" ─▶ [13] Zoho API Call (/v3/users) ─▶ [14] Iterator (match closer email)
      │                                                                      │
      │                                                                      ▼
      │                                                              [9] Zoho Create Compte ──▶ [Resume si DUPLICATE]
      │                                                                      │
      │                                                                      ▼
      │                                                              [10] Zoho Create Contact ──▶ [Resume si DUPLICATE]
      │                                                                      │
      │                                                                      ▼
      │                                                              [11] Zoho Create Affaire (toujours créée)
      │
      └── Route 2 "Contact not found" ──────────────────────────────▶ [11] Zoho Create Affaire (avec création implicite Compte + Contact)
```

---

## 🔑 Composants critiques

### Module Data Store (#19) — Garde-fou anti-doublon

| Paramètre | Valeur |
|---|---|
| Data store name | `iClosed Bookings Dedup` |
| Data structure | `Booking dedup structure` (1 field : `booking_id` Text) |
| Key utilisée | `{{1.callPreviewId}}` (ou équivalent — ID unique du booking iClosed) |
| Overwrite existing record | **No** ⚠️ critique |
| Storage size | 1 MB (largement suffisant) |

**Mécanique** : à chaque webhook iClosed reçu, on tente d'ajouter un record dans le store avec la key = booking ID. Si l'ID existe déjà (= 2ème webhook du même booking), le module renvoie une erreur "duplicate key". L'error handler **Commit** (#20) attrape cette erreur et arrête le scénario proprement, sans propager aux modules en aval.

**Résultat** : seul le 1er webhook par booking déclenche le flow complet.

### Module Commit (#20) — Branche d'erreur

Aucune config nécessaire. Rôle : finaliser proprement le scénario en cas d'erreur sur le Data Store sans logger l'erreur comme un crash.

⚠️ **Pourquoi Commit et pas Resume** : Resume continuerait le flow (créerait des doublons en aval). Commit arrête tout immédiatement = ce qu'on veut pour un doublon.

### Modules 9, 10, 11 — Création Zoho (branche Contact found)

Configuration actuelle = "force la création même si existant", avec error handlers Resume pour rattraper les erreurs DUPLICATE_DATA. Pas optimal mais fonctionnel.

---

## 🐛 Pièges rencontrés & solutions (15 mai)

| # | Symptôme | Cause | Solution |
|---|---|---|---|
| 1 | 2 lignes apparaissent dans le sheet Bookings pour chaque booking iClosed | iClosed émet 2 webhooks par booking (retry interne ou comportement non-documenté) | Module Data Store en position #2 + error handler Commit pour stopper le 2ème webhook |
| 2 | DUPLICATE_DATA `$.data[0].Email` sur module Create Contact (#10) | Contact existe déjà dans Zoho (re-booking) | Error handler **Resume** avec output `{}` (vide) |
| 3 | Webhook iClosed config "Call booked" seul mais quand même 2 émissions | Comportement non-documenté d'iClosed, retry probable, pas modifiable côté config | Solution = dédup côté Make (cf. piège #1) |
| 4 | Tentative initiale de demander à iClosed de désactiver les events superflus | Pas d'autres events activés dans la config, impossible de réduire à la source | Dédup côté Make obligatoire |

---

## 📖 Runbook opérationnel

### "Les doublons reviennent dans le sheet Bookings"

1. Vérifier que le module Data Store (#19) est toujours en place
2. Vérifier que l'error handler Commit (#20) est connecté
3. Vérifier dans History qu'on voit bien 2 exécutions :
   - 1ère : tout vert
   - 2ème : Data Store rouge + Commit vert + reste gris
4. Si les 2 exécutions ne sont plus jointes (ne se déclenchent plus simultanément à la seconde près), iClosed a peut-être changé son comportement — ré-investiguer

### "Le scénario plante en cascade sur les modules 9 ou 10 (Create Compte/Contact)"

1. Vérifier que les error handlers Resume sont toujours en place sur ces modules
2. Si oui mais flow stoppé : Resume probablement configuré avec un output qui casse un module en aval — repasser sur output `{}` simple

### "Régénérer le Data Store en cas de pollution"

Si le Data Store accumule trop de records ou si on veut reset :
1. Make → Data Stores → `iClosed Bookings Dedup`
2. Browse → sélectionner records à supprimer (ou tous)
3. Delete

⚠️ Attention : reset complet = pendant ~5-10 min après le reset, les éventuels doublons iClosed re-passeront. À faire en heure creuse.

---

## 🔄 Backlog V2 — Améliorations à arbitrer

### Priorité moyenne

- [ ] **Nettoyer la branche "Contact found"** : supprimer les modules 9 (Create Compte) et 10 (Create Contact) qui sont systématiquement en erreur Resume. Garder uniquement le module 11 (Create Affaire) qui doit lier l'Affaire au Contact + Compte existants via leur ID. Économie : 2 operations Make par booking sur contact existant.
- [ ] **Ajouter un Search Affaires avant le Create Affaire dans la branche "Contact found"** : éviter de créer une nouvelle Affaire si une Affaire active existe déjà (Stage ≠ Fermé Gagné/Perdu) dans les 30 derniers jours pour ce Contact. Évite les vrais doublons d'Affaires sur re-booking court terme.
- [ ] **Documenter le payload iClosed exact** : pour pouvoir reconstruire le scénario from scratch, capturer un payload type dans la note

### Priorité basse

- [ ] **TTL sur le Data Store** : ajouter une logique pour purger les records de booking plus vieux que 7 jours (sinon le store grossit indéfiniment, même si 1MB est largement suffisant pour le volume actuel)
- [ ] **Migrer sur Upsert au lieu de Resume** : pour la branche "Contact found", remplacer les 2 modules Create + Resume par des modules Upsert (Search Records → Update or Create) qui sont l'idiome propre Make pour ce cas

---

## 📝 Méta

- **Diagnostic & fix** : session Boris × Claude, 15 mai 2026 (matin)
- **Durée debug + fix** : ~30 min
- **Versions** :
  - V1 (avant 15 mai) — flow original avec Router + Resume sur création Compte/Contact, doublons systématiques
  - **V1.1 (15 mai 18h40) — ajout Data Store dédup + Commit, doublons éliminés**
- **Tests réussis** :
  - 15 mai 18h32 UTC — booking test avec email frais : 1 ligne Sheets + 1 Compte + 1 Contact + 1 Affaire
  - 15 mai 18h33 UTC — confirmation pas de doublon dans Zoho après test
- **Next steps immédiats** : surveiller sur 24-48h en prod réelle qu'aucun doublon ne réapparaît
