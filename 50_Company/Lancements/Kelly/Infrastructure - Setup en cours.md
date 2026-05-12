---
type: technical-setup-log
project: "[[_Index|Lancement Kelly]]"
owner: "[[Boris Arduy]]"
created: 2026-05-08
last-updated: 2026-05-10
status: en-cours
tags: [lancement, kelly, infrastructure, technical-setup, zoho, short-io, tally, make]
sensitivity: confidential
---

# Infrastructure Lancement Kelly — Log de setup

> Document de suivi du build de l'infrastructure technique du funnel parallèle Kelly. Mise à jour au fur et à mesure de la construction des briques.

## État global au 10 mai 2026

| Brique | Statut | Notes |
|---|---|---|
| Tally → Google Sheets (Make A1) | ✅ Fonctionnel | Scenario Make en place, données stockées dans Sheet de tracking |
| Google Sheet de tracking | ✅ Créé | ID : `1XTVJvuabrKtScKaLNFl9bBo3n-75Gz7O2C3WyU0H0aI` — onglet `Kelly Bookings` ajouté le 9 mai |
| Zoho CRM — compte | ✅ Créé | Plan Professional Trial 30 jours, expire ~7 juin 2026 |
| Zoho CRM — Profiles (4) | ✅ Créés | Administrator, Manager, Team Leader, Sales External |
| Zoho CRM — Roles (7) | ✅ Créés + renommés (10 mai) | Hiérarchie 4 niveaux. Renommage `Sales Axel` → `Sales Next Sales` + `Manager Axel` → `Manager Next Sales` effectué. |
| Zoho CRM — Data Sharing | ✅ Configuré | Tous modules critiques en mode Privé |
| Zoho CRM — Custom fields Contacts | ✅ Créés (9 mai) | Email_Domain, LinkedIn_URL, Agence_Assignee |
| Zoho CRM — Custom fields Accounts | ✅ Créés (9 mai) | Plage_revenus, Secteur_activite, Problematiques (multi), Accompagnement_existant, LinkedIn_entreprise |
| Zoho CRM — Custom fields Deals | ✅ Créés (9 mai) | Agence_Assignee, Origine_du_lead, Format, Code_Produit, Modalites_paiement, Duree_prestation, Nb_mensualites, Date_demarrage, Statut_contrat, Etat_paiements |
| Zoho CRM — Pipeline Deal | ✅ Créé (9 mai) | `Kelly Launch — Agences Externes` avec 6 stages : Appel Réservé → R1 → R2 → R3 → Engagé → Fermé Gagné |
| Zoho CRM — User boris@ | ✅ Créé (9 mai) | 2e user Pro, User ID `983392000000615324`, distinct de l'admin `drive@entrepreneurs.com` |
| Zoho CRM — Users closers (42) | ✅ Importés (10 mai) | 42/42 importés en 2 batches. Batch 1 = 38 users. Batch 2 = 4 users Next Sales (Nabil, Guilian, Axel SH, Walid) après upgrade licences Zoho. Cf. [[Closers - Liste opérationnelle Kelly]] |
| Short.io — compte | ✅ Créé | Plan Free, domaine `kelly-ec.short.gy` |
| Short.io — Splitter | ✅ Créé et testé | Lien `kelly-ec.short.gy/kelly-route`, routing 25/50/25 |
| Short.io — URLs cibles définitives | ✅ Mises à jour (9 mai) | Pointent vers les 3 pages ClickFunnels avec embed iClosed (cf. ci-dessous) |
| Short.io — Forward parameters | ✅ Validé | UTMs préservés end-to-end (Tally → Short.io → CF → iClosed → Zoho) |
| iClosed — events Kelly (3) | ✅ Créés (9 mai) | `kelly-tiptalent`, `kelly-momentum`, `kelly-nextsales` (NB: Axel renommé Next Sales) |
| iClosed — embed sur ClickFunnels | ✅ Live | 3 pages CF entrepreneurs.com avec embed iClosed correspondant |
| iClosed — hosts closers (42) | 🟡 Ajoutés (10 mai) | 10 TT + 21 Momentum + 11 Next Sales, configurés en Round Robin sur l'event de leur agence. Walid Mellal (Next Sales) en attente d'activation iClosed. Cf. [[Closers - Liste opérationnelle Kelly]] |
| Emails @entrepreneurs.com closers (42) | ✅ Créés (10 mai) | Convention `prenom.nom@entrepreneurs.com`. MDP provisoires distribués aux closers via leurs managers d'agence. |
| **Make scenario A2 (booking → Zoho)** | ✅ **Production-ready (9 mai)** | Cf. [[Scenario A2 - iClosed vers Zoho]] — 11 modules, dédup, owner dynamique. Toggle OFF en attente du go-live. |
| Make scenario A2bis (cancellations) | 🔴 À faire | Roadmap V2 |
| Make scenario A2ter (reschedule) | 🔴 À faire | Roadmap V2 |
| Make scenario A3 (notif Slack closer) | 🔴 À faire | Dépend des canaux Slack par agence |
| Make scenario A5 (Zoho → HubSpot) | 🔴 À faire | Dépend de l'audit HubSpot et de l'intégration DocuSign |
| Brief Tally au créateur | ⏳ En attente | Diagramme prêt + URL `kelly-route` ; manque les 3 URLs Calendly (Incubateur / Accélérateur / Scaling) |
| Stratégie users Zoho closers externes | ✅ Tranchée (10 mai) | Licences Pro pour les 38 closers. Coordination via emails `@entrepreneurs.com` unifiés iClosed/Zoho. |
| Adresses mail dédiées (~70) | 🟡 Partiel (10 mai) | 38 emails closers créés. Reste : managers, setters Momentum backup, admin. |

## Détail Zoho CRM

### Configuration générale
- **URL d'accès** : compte Zoho EU (zoho.eu)
- **Édition** : Professional Trial 30 jours
- **Devise** : EUR
- **Fuseau horaire** : Europe/Paris
- **Format date** : DD/MM/YYYY
- **Format heure** : 24h
- **Business Hours** : Lundi-Samedi 06:00-23:00

### Profiles créés

| Profile | Description | Cible utilisateurs |
|---|---|---|
| Administrator | Tous droits (par défaut Zoho) | Boris uniquement |
| Manager | Voit tout son périmètre, mass actions, exports, rapports | Aziz, Lucas, Romain, Axel, Hélène |
| Team Leader | Voit son équipe, modifications individuelles, pas de mass actions | Team leaders agences, Closer Success Manager, Julien (EC) |
| Sales External | Voit ses propres deals uniquement, restrictions fortes (pas d'export, pas de mass action, pas de suppression, pas de sync contacts persos) | Tous les closers et setters externes |

### Hiérarchie de Roles

```
Entrepreneurs.com
└── Boris (Operating Partner)
    └── Aziz (Head of Sales EC)
        ├── Manager Tip Talent
        │   └── Sales Tip Talent
        ├── Manager Momentum
        │   └── Sales Momentum
        └── Manager Axel
            └── Sales Axel
```

### Data Sharing Settings

| Module | Mode |
|---|---|
| Prospects | Privé |
| Comptes | Privé |
| Contacts | Privé |
| Affaires | Privé |
| Tâches | Privé |
| Réunions | Privé |
| Appels | Privé |
| Visites | Privé |
| E-mails | Privé |
| Produits | Public (lecture seule) — catalogue partagé |

## Détail Short.io

### Configuration

- **URL d'accès** : app.short.io
- **Compte** : boris@entrepreneurs.com
- **Plan** : Gratuit (à upgrader vers Team avant le 14 mai)
- **Domaine** : `kelly-ec.short.gy` (gratuit fourni par Short.io)
- **Domaine custom prévu** : à configurer plus tard via DNS entrepreneurs.com

### Lien splitter principal

- **URL** : `https://kelly-ec.short.gy/kelly-route`
- **Type** : Test A/B (3 destinations)
- **Pondération configurée** :
  - Page d'origine (Tip Talent) : 25%
  - Variante 1 (Momentum) : 50%
  - Variante 2 (Axel) : 25%

### URLs cibles actuelles (live au 9 mai 2026)

| Destination | URL Short.io variant | URL ClickFunnels cible | Event iClosed embarqué |
|---|---|---|---|
| Tip Talent (25%) | Page d'origine | `https://www.entrepreneurs.com/closer-equipe-no-activity-tiptalent` | `kelly-tiptalent` |
| Momentum (50%) | Variante 1 | `https://www.entrepreneurs.com/closer-equipe-no-activity-momentum` | `kelly-momentum` |
| Next Sales (25%) | Variante 2 | `https://www.entrepreneurs.com/closer-equipe-no-activity-next-sales` | `kelly-nextsales` |

**UTMs propagés** : `utm_source=tally`, `utm_medium=routing`, `utm_campaign=kelly_launch`, `utm_content={agence}`. Validés end-to-end Tally → Short.io → CF → iClosed → fiche contact iClosed (capture des UTMs sur les 7 contacts test du 9 mai).

### Tests effectués

**Test 1 — Routing pondéré (8 mai 2026)**
- 20 clics manuels en navigation
- Résultat : 5 Tip Talent / 7 Momentum / 8 Axel
- Conclusion : routing fonctionnel, écart cohérent avec variance statistique sur petit échantillon. Convergence attendue vers 25/50/25 sur volumes >100.

**Test 2 — Forward des paramètres URL (8 mai 2026)**
- URL test : `https://kelly-ec.short.gy/kelly-route?email=test@example.com&name=Boris+Test&phone=%2B33624847394`
- Résultat httpbin.org confirmé : tous les paramètres (`email`, `name`, `phone`) sont transmis intacts à l'URL cible
- Conclusion : forward fonctionne **par défaut**, aucune activation manuelle nécessaire

### Observations

- Lors du premier test, les URLs cibles entrepreneurs.com (`/kelly-test-tiptalent` etc.) déclenchaient une redirection serveur 302 vers `/welcome` ou `/` (pages 404 redirigées). Ce comportement faisait perdre les paramètres URL et empêchait de valider le forward.
- Solution adoptée : utilisation temporaire de httpbin.org comme URLs cibles pour valider le forward proprement. À remplacer par les vraies URLs iCloseit dès qu'elles seront créées.

## Décisions prises pendant le setup

| Date | Décision | Rationale |
|---|---|---|
| 8 mai | Approche "copie absolue HubSpot → Zoho" pour custom fields et pipeline | Évite les erreurs de mapping lors du push Zoho → HubSpot |
| 8 mai | Profiles Zoho construits par clonage en cascade (Standard → Manager → Team Leader → Sales External) | Préserve les ajustements de sécurité à chaque niveau |
| 8 mai | Désactivation des sync Google Contacts + Microsoft Contact sur tous profiles externes | Éviter fuite de données client dans les outils persos des sales partenaires |
| 8 mai | Sales External : pas de droit de suppression, ni d'export, ni de mass actions, ni de sync agenda perso | Sécurité maximale sur le profile le plus diffusé |
| 8 mai | Short.io plan Gratuit pour setup et tests, upgrade Team avant 14 mai | Pas de besoin Team avant les tests à blanc et le go-live |
| 9 mai | Scope MVP custom fields (10 Deal + 5 Account + 3 Contact) plutôt que duplication exhaustive HubSpot | Évite la complexité de répliquer 50+ propriétés dont la moitié sont liées à de l'intégration interne (Pennylane, OneFlow, Skool, Platform learning). Phase 2 si besoin. |
| 9 mai | Account placeholder `[À compléter] - {Nom}` à la création | iClosed ne donne pas le nom d'entreprise. Le closer enrichit après le call. Signal visuel clair dans la liste Accounts. |
| 9 mai | Création d'un 2e user Zoho `boris@entrepreneurs.com` (distinct de l'admin `drive@`) | Permet le matching dynamique entre l'email iClosed du closer et le user Zoho. Coût : ~30€/mois. |
| 9 mai | Owner dynamique via API Call `/v3/users` + Iterator + Filter sur `closerEmail` (Solution B) plutôt que Switch hardcoded (Solution A) | Aucune modification du scenario quand un closer arrive/part — il suffit de créer/supprimer le user Zoho. |
| 9 mai | Dédup par `callPreviewId` via Sheets Search Rows | Bloque les retries iClosed (observation : iClosed a renvoyé 2 webhooks à la même seconde sur 1 booking). |
| 9 mai | Renommage `Axel` → `Next Sales` partout (page CF, UTM, slug iClosed) | Cohérence avec le nom commercial de l'agence d'Axel. |
| 10 mai | Convention emails closers : `prenom.nom@entrepreneurs.com` unique pour iClosed + Zoho + Google Workspace | Évite le mismatch entre les systèmes et garantit le matching Deal Owner dynamique du scenario A2. Plus simple opérationnellement. |
| 10 mai | 38 closers ajoutés en host iClosed avant la création des users Zoho | Permet de capter les emails exacts et de tester le Round Robin en amont. Import Zoho préparé en CSV mais pas encore exécuté. |
| 10 mai | Renommage des roles Zoho `Sales Axel` → `Sales Next Sales` et `Manager Axel` → `Manager Next Sales` | Cohérence avec le rename global Axel → Next Sales. |
| 10 mai | Pas de users Zoho pour les managers d'agence (Romain, Lucas, Hélène, Axel, Aziz) en V1 | Scope minimal pour le go-live. Focus closers qui prennent les calls. Manager users à ajouter post-event si besoin. |
| 10 mai | Upgrade Zoho au-dessus du seuil trial (>40 users) | Nécessaire pour importer les 42 closers. Souscription Pro payante anticipée par rapport à l'expiration trial du 7 juin. |

## Points en attente

### Sujets ouverts (au 9 mai 2026)

1. **Brief Tally au créateur** — diagramme de routing + URL `kelly-route` prêts ; manque les 3 URLs Calendly (Incubateur / Accélérateur / Scaling) à fournir avant transmission
2. **Stratégie users Zoho closers externes** — décision à prendre : licences Pro à 30€/user/mois pour les ~40 closers, ou Portal Users (moins chers mais accès limité), ou autre mécanisme
3. **Setup ~70 adresses mail dédiées** (40 closers + 20 setters + 3 head of sales + 3 managers + ~5 admin)
4. **Configuration domaine custom Short.io** via DNS entrepreneurs.com (transmettre les valeurs DNS à la personne qui gère le domaine)
5. **Audit HubSpot** plus complet pour V2 du custom fields Zoho (Phase 2 — pas urgent vu que MVP fonctionne)
6. **Activation numéro de téléphone Short.io** (warning affiché, non bloquant pour l'instant)

### Roadmap V2 scenarios Make

- Branche A enrichie du A2 (lead existant → create deal seulement)
- A2bis (cancellations → update Deal stage Closed Lost)
- A2ter (reschedule → update Deal closing date)
- A3 (notif Slack closer assigné, par canal d'agence)
- A4 (update Deal post-call via Supersales ou autre)
- A5 (push Zoho → HubSpot quand Deal won + DocuSign signé)

## Prochaine étape immédiate

**Le scenario A2 V1 est en prod, les 38 closers sont en host iClosed.** Les chantiers suivants prioritaires :

1. **Import CSV des 38 users Zoho** (~5 min, cf. [[Closers - Liste opérationnelle Kelly]] pour le CSV prêt)
2. **Suivi des activations Zoho** avant dimanche 17 mai 20h (les closers doivent cliquer sur leur invitation et créer leur MDP)
3. **Calendar sync iClosed** à demander à chaque closer (à inclure dans coaching 12 mai)
4. **Activer le scenario A2** (toggle ON dans Make) une fois tous les users Zoho créés
5. **Transmettre le brief Tally au créateur** (besoin des 3 URLs Calendly avant)
6. **Construire le scenario A3** (notif Slack closer) une fois les canaux Slack par agence créés

## Liens

- [[_Index|Hub projet Kelly]]
- [[Architecture - Funnel parallèle closers externes]]
- [[Scenario A2 - iClosed vers Zoho]]
- [[Closers - Liste opérationnelle Kelly]]
- [[Partenaires - Vue d'ensemble 3 agences]]
