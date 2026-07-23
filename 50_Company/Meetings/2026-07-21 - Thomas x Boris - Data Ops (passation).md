---
type: meeting
date: 2026-07-21
date_call: "21/07/2026, 11:31–11:45 (Google Meet) — horodatage confirmé par l'export Sembly « Thomas X Boris - Data Ops »."
participants: ["[[Boris Arduy]]", "[[Thomas Baeumlin]] (data — départ début août)"]
contexte: "ENT — Point de passation Thomas (data, départ début août) : état des projets en cours (intégration Customer.io/webhook BigQuery pour les leads, dashboard marketing, dashboard finance & réconciliation Penny Lane↔Odoo), récupération des accès (Stitch, Fivetran, BigQuery, GitHub, Looker), et cadrage de la documentation d'architecture data pour la reprise en main."
source: "Export Sembly AI (PDF, archivé via Claude) — speakers renormalisés"
sensitivity: confidential
tags: [meeting, ent, data, dataops, passation, thomas-baeumlin, customer-io, bigquery, hubspot, penny-lane, odoo, finance, stitch, fivetran, looker, github, documentation, wiki, q3-2026]
status: inbox
---

# Data Ops — Passation Thomas × Boris (21/07/2026)

> [!warning] **Sensibilité.** Passation d'un poste data sensible (accès à toute la data). Détails d'accès/architecture → cercle direction / IT.

> [!note] **Normalisations transcription.** « Customer.io » = outil d'emailing/automatisation. · « Penny Lane ↔ Odoo » = réconciliation facturation/ERP. · « Stitch » / « Fivetran » = connecteurs d'ingestion de data (sources différentes). · « BigQuery » = data warehouse. · « Uber » = personne ayant un accès Stitch (usage marketing/Facebook Ads, à confirmer). · « Works / entrepreneurs.org » = wiki interne. · Ce call est **la passation technique annoncée par Boris dans le 1:1 Alec du 20/07** (« je fais la passation demain avec Thomas »).

## TL;DR
Point de passation court (14 min) avec **Thomas (départ début août)**. Trois chantiers restent ouverts : **(1) marketing** — nouvelle intégration pour **ne plus passer par HubSpot pour les leads** mais **directement par Customer.io via un webhook vu dans BigQuery** (paramétré au départ pour la seule campagne **Bootstrap/Bourbon**, désormais **répliqué sur les autres lancements** — actif même après son départ, remonte au dashboard) ; **(2) dashboard finance (Jordan)** — le gros reste la **réconciliation Penny Lane ↔ Odoo** (toujours galère côté tables) : Thomas lance la réconciliation via un fichier dédié, les cas en écart nécessitent un **check manuel** ; le dashboard existe **sans la partie Penny Lane** (back à ajouter) + un **Google Sheet de gestion** à côté (on ne peut pas laisser l'utilisateur agir sur les tables depuis le dashboard) ; **(3) documentation** — pas commencée, mais courte (la doc intrinsèque est dans les technos/GitHub) → l'attendu de Boris = **schémas & architecture de données** (quelle data va où, comment elle est traitée) pour une **reprise en main**, pas un PDF de 30 pages, publié sur le **wiki (avec Wassim)**. **Accès à sécuriser** : **Stitch, Fivetran, BigQuery, GitHub, Looker** (Fabrice a accès à tout sur BigQuery). **Mohamed n'a pas encore contacté Thomas** pour l'audit IT → à débloquer. Thomas attaque la doc **après avoir bouclé la finance avec Jordan** (début/milieu de semaine prochaine).

---

## 1 — Marketing : intégration Customer.io (sortie HubSpot pour les leads)
- Nouvelle intégration (avec **[[Fabrice Jaeger]]** & **[[Adil]]**) : **ne plus utiliser HubSpot pour les leads**, passer **directement par Customer.io** avec le **webhook vu dans BigQuery**.
- Paramétré au départ **uniquement pour la campagne Bootstrap** (Bourbon) → **décision : répliquer sur les autres lancements** (Thomas a ouvert le dispositif) → fonctionnera **même après son départ**, les leads apparaissent dans le dashboard.
- Reste des demandes d'ajout d'éléments dans le **dashboard marketing** qu'il a fait.

## 2 — Dashboard finance (Jordan) & réconciliation Penny Lane ↔ Odoo
- Chantier principal : **réconcilier les deals Penny Lane ↔ Odoo** (« toujours aussi galère en termes de table »). Thomas lance la **réconciliation via un fichier dédié** ; pour les cas en problème → **check manuel** requis.
- Le dashboard remonte tous les **écarts** ; la finance checke chaque écart et le marque (« done » / « à checker »), avec possibilité de corriger / d'ajouter une info.
- **Dashboard fait sans la partie Penny Lane** → il faut **ajouter le back Penny Lane** + un **Google Sheet de gestion** à côté (impossible de laisser l'utilisateur impacter les tables depuis le dashboard).
- Point avec **[[Jordan Leroux]]** en fin/début de semaine prochaine (rien de bloquant).

## 3 — Documentation d'architecture data
- Pas commencée, mais **pas très longue** : la doc intrinsèque à chaque techno est **dans la techno** (GitHub, etc.).
- Attendu **Boris** : **pas un PDF de 30 pages** → comprendre les **schémas de données et l'architecture** (quelle data va où, par quoi elle passe, comment elle est traitée) pour permettre une **reprise en main**.
- **Format** : markdown / PDF sur le **wiki (entrepreneurs.org / Works)** → à voir avec **[[Wassim]]** (qui implémente dans le wiki). Thomas partage ses **logs/versions au fur et à mesure** pour visibilité.

## 4 — Accès à récupérer / angles morts
- **Stitch** (ingestion de sources) : quelqu'un doit avoir l'accès ; « Uber » y a accès (besoin marketing/Facebook Ads, à confirmer).
- **Fivetran** : similaire à Stitch mais **pas les mêmes infos** qui partent.
- **BigQuery** : quelques personnes ont accès ; **[[Fabrice Jaeger]] a accès à tout**.
- **GitHub / Looker** : à récupérer (cf. weekly Mohamed).
- ⚠️ **[[Mohamed]] n'a pas encore contacté Thomas** pour l'audit IT → Boris met une note pour le déclencher.

---

## Actions consolidées

| # | Action | Owner | Échéance |
|---|---|---|---|
| 1 | Confirmer la **réplication Customer.io** sur tous les lancements + ajouts dashboard marketing | [[Thomas Baeumlin]] (+ [[Adil]]) | En cours |
| 2 | Finir le **dashboard finance** : back Penny Lane + Google Sheet de gestion + réconciliation | **[[Thomas Baeumlin]]** | Après point Jordan |
| 3 | Point **réconciliation / écarts** avec Jordan | Thomas ↔ [[Jordan Leroux]] | Fin/début sem. pro |
| 4 | **Déclencher le check Mohamed** (audit IT / récupération accès) | Boris → [[Mohamed]] | Immédiat |
| 5 | Rédiger la **doc d'architecture data** (schémas, flux) sur le wiki | Thomas (+ [[Wassim]]) | Début/milieu sem. pro |
| 6 | Sécuriser les accès **Stitch · Fivetran · BigQuery · GitHub · Looker** | Boris + Mohamed | Avant départ (début août) |
| 7 | **Partager les logs/versions** de doc au fil de l'eau | Thomas → Boris | Continu |

## Décisions clés
- **Intégration Customer.io répliquée sur tous les lancements** (sortie HubSpot pour les leads), pérenne après le départ de Thomas.
- **Doc = schémas & architecture data** (reprise en main), pas de la doc textuelle exhaustive → sur le wiki via Wassim.
- **Séquence** : finir la **finance** (priorité), **puis** attaquer la doc.

## Points de vigilance
- **Poste data sensible qui part début août** : la doc d'architecture + la récupération des accès sont **critiques** (risque de disparition de valeur — cf. weekly Mohamed).
- **Réconciliation Penny Lane ↔ Odoo** = nœud récurrent (impayés non visibles côté plateforme, cf. point Sabrina / crise Odoo) : les cas en écart resteront **manuels**.
- **Mohamed pas encore en lien avec Thomas** → ne pas laisser filer avant le départ.

## Liens
- [[Boris Arduy]] · [[Thomas Baeumlin]] · [[Jordan Leroux]] · [[Fabrice Jaeger]] · [[Adil]] · [[Mohamed]] · [[Wassim]] · [[Quentin]]
- Réunions liées : [[2026-07-21 - Mohamed x Boris - Cybersécurité, NAS Shade & cockpit SaaS]] (récupération accès Thomas) · [[2026-07-20 - Point hebdo 1-1 (Boris x Alec)]] (passation Thomas annoncée) · [[2026-07-20 - Réunion Hebdo Core Team (Core Team)]] (§ finance / réconciliation Odoo)
- Ressource : [[Ressource - Cartographie Data Thomas Baeumlin 28 mai 2026]]
- Projets : [[Refonte verticale Data-IA-Tech-Ops]] · [[Audit SaaS-IT — économies]] · [[Trésorerie & Finance]] · [[🗼 Tour de contrôle - Projets en cours]]
