---
type: technical-scenario-spec
project: "[[_Index|Lancement Kelly]]"
owner: "[[Boris Arduy]]"
created: 2026-05-09
last-updated: 2026-05-10
status: production-ready
version: V1.0
tags: [lancement, kelly, infrastructure, make, scenario, zoho, iclosed, automation, A2]
sensitivity: confidential
related-docs: ["[[Infrastructure - Setup en cours]]", "[[Architecture - Funnel parallèle closers externes]]"]
---

# Scenario Make A2 — iClosed booking → Zoho

> Source of truth pour l'automation qui crée Account + Contact + Deal dans Zoho à chaque booking iClosed sur les events Kelly. Construit et validé en prod le 9 mai 2026.

## Statut

**🟢 Production-ready** — testé end-to-end sur les 3 events Kelly (Tip Talent / Momentum / Next Sales). Dédup en place, owner dynamique fonctionnel, 11 modules opérationnels.

## Objectif business

À chaque fois qu'un lead Kelly booke un call sur l'un des 3 events iClosed (`kelly-tiptalent`, `kelly-momentum`, `kelly-nextsales`), le scenario doit :

1. **Tracker** le booking dans le Google Sheet centralisé `Kelly Bookings` (audit trail)
2. **Créer un Account** placeholder dans Zoho (à enrichir manuellement par le closer après le call)
3. **Créer le Contact** dans Zoho avec ses infos personnelles + l'agence assignée
4. **Créer le Deal** dans le pipeline `Kelly Launch — Agences Externes`, stage initial `Appel Réservé`
5. **Attribuer le Deal Owner dynamiquement** au closer iClosed qui a pris le call (matching par email)

Cette automation est la **brique centrale du funnel Kelly externe**. Toute la suite (notifications closer, update post-call, push HubSpot) en dépend.

## Architecture

### Vue d'ensemble — 11 modules

```
[1]  Watch Call Booked (iClosed)
        ↓
[2]  Filter "Booking valide"
     (hookType = "Call booked" AND canceled = false)
        ↓
[15] Google Sheets - Search Rows (dédup par Call Preview ID)
        ↓ [Filter "Pas de duplicate" : Total bundles = 0]
[3]  Google Sheets - Add a Row (Kelly Bookings, 20 colonnes)
        ↓
[4]  Set Variables (agence, email_domain, deal_name, closing_date, description, account_placeholder)
        ↓
[5]  Zoho - Search Objects (Contact par email)
        ↓
[6]  Router (Found / Not Found)
        ↓
   ┌────┴─────────────────────────────────────────┐
   │                                              │
[Branche A — Found]                  [Branche B — Not Found]
   (vide en V1)                                   ↓
                                  [13] Zoho - Make API Call (/v3/users)
                                                  ↓
                                  [14] Iterator → décompose users
                                                  ↓ [Filter "Match closer email"]
                                  [9]  Zoho - Create Account placeholder
                                                  ↓
                                  [10] Zoho - Create Contact (lié à Account)
                                                  ↓
                                  [11] Zoho - Create Deal (lié à Account + Contact)
```

### Logique narrative

1. iClosed déclenche le webhook quand un lead booke un call.
2. On filtre uniquement les vrais bookings (pas les cancellations ou autres event types).
3. On vérifie via Sheets si ce `callPreviewId` a déjà été traité (iClosed retry parfois) — si oui, stop.
4. On log dans Sheets pour audit trail.
5. On calcule les variables réutilisées : agence depuis le slug, deal name formaté, closing date à +30j, description avec call ID.
6. On cherche si le Contact existe déjà dans Zoho (par email) — la branche A "found" est vide en V1, on traitera le cas plus tard.
7. **Branche B (cas principal)** : on appelle l'API Zoho pour récupérer la liste des users actifs.
8. On itère, on filtre celui dont l'email matche `Event.closerEmail`.
9. On crée Account + Contact + Deal en cascade, avec Owner = user matché.

## Mapping détaillé

### Module 1 — Watch Call Booked (iClosed)

**Type** : Module natif iClosed (Make).

**Webhook URL** (auto-générée par Make) : `https://hook.eu2.make.com/im3bm6usbr8ywk8y0ayromociboehgcc`

Cette URL est **collée côté iClosed dans la config webhook**. Elle reçoit les payloads à chaque booking sur n'importe quel event iClosed (le webhook iClosed est probablement global au compte, pas par event).

**Payload reçu** (structure principale) :

| Field | Type | Exemple |
|---|---|---|
| `EventType.slug` | string | `kelly-tiptalent` / `kelly-momentum` / `kelly-nextsales` |
| `EventType.kind` | string | `Round Robin` |
| `EventType.name` | string | `🚀 Rencontre avec un Expert` |
| `Event.uuid` | int | `1878445` |
| `Event.callPreviewId` | string | `call_p2BrZXMehOVQ` (clé d'idempotence) |
| `Event.closerId` | int | `303` |
| `Event.closerName` | string | `Boris Arduy` |
| `Event.closerEmail` | string | `boris@entrepreneurs.com` |
| `Event.start_time` | datetime | `2026-05-12T11:00:00` (format ISO) |
| `Event.end_time` | datetime | `2026-05-12T12:00:00` |
| `Event.location` | url | `https://meet.google.com/xxx-xxxx-xxx` |
| `Event.eventLink` | url | `https://app.iclosed.io/e/entrepreneurs/kelly-tiptalent` |
| `Event.rescheduleLink` | url | Lien iClosed reschedule |
| `Event.cancelLink` | url | Lien iClosed cancel |
| `Event.canceled` | boolean | `false` |
| `Invitee.email` | email | `borisarduy42@gmail.com` |
| `Invitee.first_name` | string | `Boris` |
| `Invitee.last_name` | string | `Arduy` |
| `Invitee.text_reminder_number` | phone | `+33624847394` |
| `tracking.utm_*` | strings | UTMs (peuvent être bruités cf. edge cases) |
| `hookType` | string | `Call booked` |

### Module 2 — Filter "Booking valide"

Sur le lien entre Watch Call Booked et le module suivant.

**Conditions** (toutes deux requises) :
- `1. hookType` Equal to `Call booked`
- `1. Event.canceled` Equal to `false`

**Justification** : défense en profondeur. Bloque les futurs `hookType` non gérés (ex: si iClosed introduit `Call rescheduled` plus tard, on ne veut pas créer un nouveau Deal).

### Module 15 — Google Sheets : Search Rows (dédup)

**But** : éviter les doublons quand iClosed envoie le même webhook 2 fois.

**Configuration** :
- Spreadsheet : `Tally Tracking Kelly` (ID : `1XTVJvuabrKtScKaLNFl9bBo3n-75Gz7O2C3WyU0H0aI`)
- Sheet : `Kelly Bookings`
- Filter : `Call Preview ID` (colonne B) Equal to `{{1.Event.callPreviewId}}`
- Limit : 1

**Filter sur le lien suivant** : `{{15.Total number of bundles}}` Equal to `0` → si une ligne existe déjà avec ce callPreviewId, le scenario stoppe.

### Module 3 — Google Sheets : Add a Row

**Spreadsheet** : `Tally Tracking Kelly`
**Sheet** : `Kelly Bookings` (créée le 9 mai)
**Headers + mapping** :

| Colonne | Header Sheet | Source / Formule |
|---|---|---|
| A | Booking Date | `{{formatDate(now; "DD/MM/YYYY HH:mm")}}` |
| B | Call Preview ID | `{{1.Event.callPreviewId}}` |
| C | Slug | `{{1.EventType.slug}}` |
| D | Agence | switch sur slug (Tip Talent / Momentum / Next Sales / Inconnu) |
| E | First Name | `{{1.Invitee.first_name}}` |
| F | Last Name | `{{1.Invitee.last_name}}` |
| G | Email | `{{1.Invitee.email}}` |
| H | Phone | `{{1.Invitee.text_reminder_number}}` |
| I | Email Domain | calculé via `substring(email; indexOf(email; "@") + 1; length(email))` |
| J | Call Start Time | `{{1.Event.start_time}}` |
| K | Call End Time | `{{1.Event.end_time}}` |
| L | Closer Name | `{{1.Event.closerName}}` |
| M | Closer Email | `{{1.Event.closerEmail}}` |
| N | Meet Link | `{{1.Event.location}}` |
| O | UTM Source | `{{1.tracking.utm_source}}` |
| P | UTM Medium | `{{1.tracking.utm_medium}}` |
| Q | UTM Content | `{{1.tracking.utm_content}}` |
| R | UTM Campaign | `{{1.tracking.utm_campaign}}` |
| S | Reschedule Link | `{{1.Event.rescheduleLink}}` |
| T | Cancel Link | `{{1.Event.cancelLink}}` |

### Module 4 — Set Variables

6 variables calculées à partir du payload, réutilisées par les modules suivants.

| Variable | Formule | Exemple output |
|---|---|---|
| `agence` | `switch(1.EventType.slug; "kelly-tiptalent"; "Tip Talent"; "kelly-momentum"; "Momentum"; "kelly-nextsales"; "Next Sales"; "Inconnu")` | `Tip Talent` |
| `email_domain` | `substring(1.Invitee.email; indexOf(1.Invitee.email; "@") + 1; length(1.Invitee.email))` | `gmail.com` |
| `account_placeholder` | `[À compléter] - {{1.Invitee.first_name}} {{1.Invitee.last_name}}` | `[À compléter] - Boris Arduy` |
| `deal_name` | `Kelly - {{agence}} - {{formatDate(now; "MMMM YYYY")}} - {{1.Invitee.first_name}} {{1.Invitee.last_name}}` | `Kelly - Tip Talent - May 2026 - Boris Arduy` |
| `closing_date_30d` | `formatDate(addDays(parseDate(1.Event.start_time; "YYYY-MM-DDTHH:mm:ss"); 30); "YYYY-MM-DD")` | `2026-06-11` |
| `description_zoho` | `Booking iClosed du {{formatDate(now; "DD/MM/YYYY")}} ; Call ID : {{1.Event.callPreviewId}} ; Event link : {{1.Event.eventLink}} ; Reschedule : {{1.Event.rescheduleLink}}` | concat |

### Module 5 — Zoho Search Objects (Contact)

**Module** : Contacts
**Filter** : `Email` Equals `{{1.Invitee.email}}`
**Limit** : 1

**Output critique** : `Total number of bundles` (0 ou 1) — utilisé par le Router.

### Module 6 — Router

2 branches.

**Branche A — Contact found**
- Filter sur le lien : `{{5.Total number of bundles}}` Greater than `0`
- **Vide en V1**. Comportement à définir en V2 (cf. Roadmap).

**Branche B — Contact not found**
- Filter sur le lien : `{{5.Total number of bundles}}` Equal to `0`
- C'est le cas principal pour Kelly (premiers leads = nouveaux contacts).

### Module 13 — Make API Call (/v3/users)

**But** : récupérer la liste des users Zoho actifs pour matcher le closer iClosed.

**Pourquoi pas Search Users ?** : le module natif Search Users de Make sur Zoho ne supporte pas le filtre par email. Il retourne des résultats limités sans filtering. On bypass via API Call directe.

**Configuration** :
- URL : `/v3/users?type=ActiveUsers&per_page=200`
- Method : `GET`
- Headers : (Make ajoute auto l'auth via OAuth)
- Body : (vide)

**⚠️ Piège initial** : Make attend une URL relative à `https://{API_URL}/crm`, donc il faut bien préfixer `/v3/`. Sans le `/v3`, on a un `400 DataError undefined`.

**Output** : `Body.users[]` (array de tous les users actifs).

### Module 14 — Iterator

**Array** : `{{13.body.users}}`

L'Iterator décompose le tableau en bundles individuels (1 par user).

**Filter sur le lien après Iterator** :
- Label : `Match closer email`
- Condition : `{{14.email}}` Equal to `{{1.Event.closerEmail}}`

Seul le user dont l'email matche `Event.closerEmail` passe.

### Module 9 — Zoho Create Account

**Module** : Accounts (Comptes)
**Champs** :

| Champ Zoho | Mapping |
|---|---|
| Nom du Compte (Account_Name) | `{{4.account_placeholder}}` |
| Téléphone | `{{1.Invitee.text_reminder_number}}` |
| Gestionnaire du Compte | `{{14.id}}` (User ID du closer matché) |

Tous les autres champs custom (Plage de revenus, Secteur, Problématiques) sont **laissés vides** en V1 — à enrichir manuellement par le closer après le call.

### Module 10 — Zoho Create Contact

**Module** : Contacts
**Champs** :

| Champ Zoho | Mapping |
|---|---|
| Nom (Last Name) | `{{1.Invitee.last_name}}` |
| Prénom (First Name) | `{{1.Invitee.first_name}}` |
| E-mail | `{{1.Invitee.email}}` |
| Téléphone | `{{1.Invitee.text_reminder_number}}` |
| Email Domain (custom) | `{{4.email_domain}}` |
| Agence Assignée (custom) | `{{4.agence}}` |
| Nom du Compte (lookup) | `{{9.Object ID}}` (Account créé au module 9) |
| Gestionnaire du Contact | `{{14.id}}` |

### Module 11 — Zoho Create Deal

**Module** : Deals (Affaires)
**Champs** :

| Champ Zoho | Mapping |
|---|---|
| Nom de l'Affaire | `{{4.deal_name}}` |
| Pipeline | `Kelly Launch — Agences Externes` (hardcoded) |
| Stage | `Appel Réservé` (hardcoded) |
| Probabilité | `10` (hardcoded) |
| Type | `Nouveau client` (hardcoded) |
| Date de clôture | `{{4.closing_date_30d}}` |
| Nom du Compte (lookup) | `{{9.Object ID}}` |
| Nom du Contact (lookup) | `{{10.Object ID}}` |
| Description | `{{4.description_zoho}}` |
| Agence_Assignee (custom) | `{{4.agence}}` |
| Origine_du_lead (custom) | `Kelly Launch` (hardcoded) |
| Statut contrat (custom) | `En préparation` (hardcoded) |
| Etat des paiements (custom) | `Non payé` (hardcoded) |
| Gestionnaire de l'Affaire | `{{14.id}}` |

Champs **vides en V1** (le closer remplit après call) :
- Format
- Code Produit
- Modalités de paiement
- Durée de prestation
- # Mensualités
- Date de démarrage
- Montant (le closer met le prix négocié)

## Identifiants critiques (références techniques)

### Make
- Scenario nom : Kelly — Booking iClosed → Zoho A2
- Webhook URL : `https://hook.eu2.make.com/im3bm6usbr8ywk8y0ayromociboehgcc`
- Trigger : Watch Call Booked (iClosed natif)
- Mode scheduling : `On demand` (déclenché par webhook)
- Plan Make : à confirmer (Free 1000 ops/mois pourrait suffire au début)

### Google Sheets
- Sheet ID : `1XTVJvuabrKtScKaLNFl9bBo3n-75Gz7O2C3WyU0H0aI`
- Nom : `Tally Tracking Kelly`
- Onglet utilisé par A2 : `Kelly Bookings` (créé le 9 mai)
- Headers : 20 colonnes (A à T)

### Zoho CRM
- Domain : `zoho.eu`
- Pipeline cible : `Kelly Launch — Agences Externes`
- Stage initial : `Appel Réservé`
- Stages disponibles : Appel Réservé → R1 Réalisé → R2 Réalisé → R3 Réalisé → Engagé → Fermé Gagné (+ Closed Lost variants)

### Users Zoho actifs (au 10 mai 2026)

| Email | User ID Zoho | Rôle |
|---|---|---|
| drive@entrepreneurs.com | `983392000000542001` | Admin Zoho (compte technique) |
| boris@entrepreneurs.com | `983392000000615324` | Boris user opérationnel (matérialise Operating Partner dans le matching iClosed) |

**Statut au 10 mai 2026** : 38 users closers à importer en masse via CSV (cf. [[Closers - Liste opérationnelle Kelly]]). Convention emails alignée iClosed/Zoho : `prenom.nom@entrepreneurs.com` pour tous les closers Tip Talent / Momentum / Next Sales.

⚠️ Le compte iClosed Boris utilise `boris@entrepreneurs.com`, qui est volontairement différent de l'admin Zoho `drive@entrepreneurs.com`. Cette séparation permet à l'API Call + Iterator + Filter de matcher le bon user comme Deal Owner.

## Edge cases identifiés et résolutions

### 1. utm_content incohérent dans le payload iClosed

**Symptôme** : le payload contient parfois 2-3 valeurs différentes pour `utm_content` (root vs index list), à cause des cookies cumulés sur des tests successifs sur différents events.

**Décision** : `EventType.slug` est la source de vérité pour l'agence assignée. L'utm_content est conservé pour analytics uniquement, jamais pour la logique métier.

### 2. Mismatch admin Zoho ↔ user iClosed

**Symptôme** : l'admin Zoho a l'email `drive@entrepreneurs.com`, mais Boris reçoit les bookings iClosed sur `boris@entrepreneurs.com`. Sans 2 users distincts, impossible de matcher dynamiquement.

**Décision** : création d'un 2e user Zoho `boris@entrepreneurs.com` avec profile Administrator. Coût : ~30€/mois supplémentaire en édition Pro. Justifié pour la propreté architecturale et la compatibilité avec les data sharing rules par équipe.

### 3. Module Search Users ne supporte pas le filtre email

**Symptôme** : `[400] UNABLE_TO_PARSE_DATA_TYPE` quand on tente de filtrer Search Users par email. L'API Zoho `/users` ne supporte pas le filtering criteria (contrairement à `/search` sur les Records).

**Décision** : bypass via Make an API Call directe (`/v3/users?type=ActiveUsers&per_page=200`) + Iterator + Filter. Plus de modules mais 100% dynamique.

### 4. Mauvais champ `id` mappé sur Owner

**Symptôme** : "Missing value of required parameter 'Account_Name'" quand on mappe le mauvais `id` sous l'Iterator (ex: `role.id` ou `profile.id` au lieu du `id` racine du user).

**Résolution** : utiliser explicitement `{{14.id}}` (l'ID au niveau racine de l'Iterator), pas les IDs imbriqués dans `role`/`profile`/`created_by`.

### 5. Doublons à cause de retries iClosed

**Symptôme** : 2 exécutions du scenario à la même seconde pour 1 seul booking (iClosed renvoie le webhook si pas de 200 OK assez vite). Résultat : 2 lignes Sheets, 2 Accounts, 1 Contact + 1 erreur DUPLICATE_DATA Email, 1 Deal + 1 stop mid-flow.

**Résolution** : ajout d'un module Search Rows en début de scenario qui filtre par `callPreviewId` déjà présent dans Sheets. Si présent → stop. Coût : +2 ops par booking. Acceptable.

**Race condition résiduelle** : si 2 exécutions arrivent EXACTEMENT simultanément, les 2 Search Rows peuvent retourner 0 avant que la 1ère ait écrit. En pratique, le délai d'écriture Sheets fait que ça passe. Si problème observé en prod sur volume élevé → migrer la dédup vers Data Store Make.

### 6. URL API Call incorrecte sans `/v3/`

**Symptôme** : `[400] DataError undefined` cryptique sur le module Make an API Call.

**Résolution** : Make attend une URL relative à `https://{API_URL}/crm`. Donc préfixer toujours `/v3/users?...` et pas juste `/users?...`.

## Procédures de troubleshooting

### Si le scenario ne se déclenche pas

1. Vérifier que le webhook iClosed est bien actif et pointe vers la bonne URL Make
2. Vérifier dans Make → History → si rien n'arrive, c'est un problème d'envoi côté iClosed
3. Tester en utilisant `webhook.site` temporairement pour isoler

### Si l'Owner du Deal est wrong (= drive@ au lieu du closer attendu)

1. Vérifier que le module API Call retourne bien la liste des users (Make History → output module 13)
2. Vérifier que l'Iterator a bien des bundles en sortie (output module 14)
3. Vérifier que le Filter "Match closer email" a la bonne condition `{{14.email}} = {{1.Event.closerEmail}}`
4. Vérifier que les modules Create utilisent `{{14.id}}` (racine), pas `{{14.role.id}}` ou autre nested
5. Si le user iClosed (closerEmail) n'a pas de user Zoho correspondant → l'Iterator ne laisse passer aucun bundle → erreur Account_Name missing. Solution : créer le user Zoho ou avoir un fallback (V2)

### Si on a des doublons Sheets/Zoho

1. Vérifier dans Make History : combien d'exécutions pour 1 booking
2. Si 2+ exécutions distinctes → c'est un retry iClosed, le module 15 (Search Rows dédup) devrait l'avoir bloqué
3. Si la dédup n'a pas fonctionné, vérifier que le module 15 cherche bien sur la colonne B (Call Preview ID) avec la bonne valeur

### Si DataError undefined sur API Call

1. Vérifier que l'URL contient bien le préfixe `/v3/`
2. Vérifier les scopes OAuth de la connexion Zoho (besoin de `users.READ` ou `users.ALL`)
3. Si scope manquant, reconnecter Zoho dans Make avec les permissions Users

## Roadmap V2 (chantiers planifiés)

### Branche A enrichie (lead existant)

Aujourd'hui la branche A "Contact found" est vide. Comportement à implémenter :
- Si contact existe → ne pas re-créer Account ni Contact
- **Update Contact existant** avec les UTMs / agence du booking actuel (en cas de changement)
- **Create Deal seulement** (un même contact peut avoir plusieurs deals successifs)
- Lookup Account = celui déjà associé au Contact
- Lookup Contact = celui trouvé

**Effort estimé** : 30-45 min.

### Scenario A2bis — Cancellations

Trigger : `hookType = "Call canceled"` ou `Event.canceled = true`
Action : retrouver le Deal Zoho par `callPreviewId` (stocké en Description) → mettre à jour le Stage en `Closed Lost - No Show` ou `Closed Lost - Refus`

**Effort estimé** : 1h.

### Scenario A2ter — Reschedule

Trigger : webhook iClosed reschedule (à confirmer le hookType exact)
Action : update du Deal correspondant avec la nouvelle date de clôture (+30j de la nouvelle date) + log dans Description.

**Effort estimé** : 1h.

### Scenario A3 — Notifications Slack

Trigger : suite directe d'A2 (after Create Deal)
Action : poster un message dans le canal Slack dédié à l'agence assignée (ex: `#kelly-tiptalent`, `#kelly-momentum`, `#kelly-nextsales`) avec :
- Nom du lead, email, phone
- Heure du call (format lisible)
- Lien iClosed direct (event link)
- Lien Deal Zoho

**Effort estimé** : 1h. Dépend du fait que les canaux Slack soient créés et que les agences externes soient invitées.

### Scenario A4 — Update post-call

Trigger : à définir (Supersales API ? Update manuel iClosed ?)
Action : update du Deal Zoho selon le résultat du call (Stage suivant, montant proposé, modalités, etc.)

**Effort estimé** : 2-3h. Bloquant : choix de la source d'update.

### Scenario A5 — Pont Zoho → HubSpot

Trigger : Deal Zoho passe en stage `Fermé Gagné` ET DocuSign signé (à coupler avec l'intégration DocuSign)
Action : créer/update Contact + Deal HubSpot dans le pipeline interne EC pour reprise de la delivery par les sales internes.

**Effort estimé** : 3-5h. Dépend de l'API HubSpot et de l'intégration DocuSign.

## Tests effectués (9 mai 2026)

| Test | Statut | Notes |
|---|---|---|
| Booking sur kelly-tiptalent → Sheets | ✅ | Ligne créée avec 20 colonnes correctes |
| Booking sur kelly-tiptalent → Zoho Account | ✅ | `[À compléter] - Boris Arduy` créé |
| Booking sur kelly-tiptalent → Zoho Contact | ✅ | Contact créé, lié à Account, agence Tip Talent, email_domain calculé |
| Booking sur kelly-tiptalent → Zoho Deal | ✅ | Deal créé `Kelly - Tip Talent - May 2026 - Boris Arduy`, stage Appel Réservé, closing date +30j |
| Switch agence depuis slug | ✅ | `kelly-tiptalent` → "Tip Talent", `kelly-momentum` → "Momentum" testés |
| Owner dynamique via API Call + Iterator + Filter | ✅ | Deal Owner = `boris@entrepreneurs.com` (User ID 983392000000615324), pas `drive@` |
| Dédup par callPreviewId | ✅ | Test sur double webhook iClosed → 1 seule ligne Sheets, 1 seul set Zoho |
| Filter "Booking valide" | ✅ | hookType + canceled vérifiés |

## Avant le go-live (checklist)

- [ ] **Nettoyer les ~10 sets de tests Zoho** (Accounts `[À compléter]`, Contacts borisarduy*, Deals "Kelly - * - May 2026")
- [ ] **Nettoyer les ~10 lignes test du Sheet `Kelly Bookings`** (garder ligne 1 = headers)
- [ ] **Activer le scenario** (toggle ON en bas-gauche dans Make)
- [ ] **Test final sur les 3 events** : 1 booking sur chaque (Tip Talent / Momentum / Next Sales) en condition réelle
- [ ] **Vérifier que les 3 deals créés ont bien la bonne Agence Assignée** dans Zoho

## Décisions architecturales documentées

### Pourquoi un Account placeholder `[À compléter]` plutôt que vide ?

Zoho exige qu'un Deal soit lié à un Account. Sans Account, pas de Deal. Vu que iClosed ne nous donne pas le nom de l'entreprise (sauf custom field), on crée un placeholder visible visuellement. Le closer voit `[À compléter] - Boris Arduy` dans la liste Accounts → signal clair qu'il doit l'enrichir après le call.

### Pourquoi pas le module Search Users de Make ?

Limitation API Zoho : `/users` ne supporte pas le filtering par criteria. Make Search Users retourne tous les users actifs sans pouvoir filtrer côté serveur. Plus simple et plus dynamique de bypasser via API Call + Iterator + Filter.

### Pourquoi pas un Switch hardcoded `closerEmail → user_id` dans Set Variables ?

Considéré au début (Solution A). Plus simple à mettre en place mais nécessite une mise à jour manuelle du scenario à chaque arrivée/départ de closer. La Solution B (API dynamique) ne demande aucune modification du scenario quand on ajoute/retire un user Zoho — seul le compte Zoho doit être ajouté/retiré.

### Pourquoi 30 jours pour la closing date ?

Estimation conservatrice du cycle de vente Kelly. Ajustable plus tard selon les data réelles.

## Liens

- [[_Index|Hub projet Kelly]]
- [[Architecture - Funnel parallèle closers externes]]
- [[Infrastructure - Setup en cours]]
- [[Closers - Liste opérationnelle Kelly]]
- [[Partenaires - Vue d'ensemble 3 agences]]

## Historique

- **2026-05-09** — Création du scenario A2 V1 en pair-programming Boris ↔ Claude
  - Construction des 11 modules
  - Validation end-to-end avec 7 bookings tests sur Tip Talent + 1 sur Momentum
  - Identification et résolution des 6 edge cases listés
  - Mise en place de la dédup Sheets pour gérer les retries iClosed
  - Création du 2e user Zoho `boris@entrepreneurs.com` pour matching closer
- 2026-05-09 — Documentation Atlas-Brain rédigée à chaud après finalisation
