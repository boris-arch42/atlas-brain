---
type: meeting
date: 2026-07-21
date_call: "21/07/2026, 12:04–12:44 (Google Meet) — horodatage confirmé par l'export Sembly « Mohamed X Boris - Cybersecurity »."
participants: ["[[Boris Arduy]]", "[[Mohamed]] (Mohamed Guendouzi)"]
contexte: "ENT — Weekly cybersécurité/IT : arbitrage stockage vidéo (migration NAS vers Shade Enterprise vs Frame.io+AWS), rationalisation des licences Google Workspace (215 licences), outil Riot (accès en attente), nettoyage des drives (top 3 : Grégoire/Charlotte/Samuel), 2FA généralisé, passation & récupération des accès de Thomas Baeumlin (départ début août), et avancement du cockpit SaaS (dashboard coûts/accès/utilisateurs)."
source: "Export Sembly AI (PDF, archivé via Claude) — speakers renormalisés"
sensitivity: confidential
tags: [meeting, ent, cybersecurite, it, nas, stockage, shade, frame-io, aws-s3, google-workspace, licences, cout-optimisation, riot, 2fa, mfa, data-cleanup, thomas-baeumlin, passation, dashboard, cockpit-saas, q3-2026]
status: inbox
---

# Cybersécurité / IT — NAS Shade, licences Google & cockpit SaaS — Mohamed × Boris (21/07/2026)

> [!warning] **Sensibilité.** Contient des devis fournisseurs, des chiffres d'économies, un départ non annoncé (Thomas Baeumlin) et des données de posture sécurité (comptes, MFA, accès sensibles). Cercle direction / IT uniquement.

> [!note] **Normalisations transcription.** « Shake / Shane / Shate » → **Shade** (DAM vidéo avec IA, ex. reconnaissance faciale sur les rushs). · « Frame » → **Frame.io** (impose **AWS S3** en stockage). · « TwiFi » → **2FA / MFA**. · « Riot » = outil cybersécurité/phishing (accès en attente). · « Anti-matter (David Gurley) » = solution alternative écartée (pas de connexion AWS S3). · « KLAP / clap » = demande de droits de **[[Quentin]]**. · Montants en USD sauf indication. · « l'heure de vie » (fin de call) = artefact de transcription.

## TL;DR
Weekly IT/cybersécurité à fort enjeu coûts. **(1) NAS / stockage vidéo** : comparatif **Shade Enterprise ≈ 33 000 $/an** vs **Frame.io ≈ 46-53 000 $** (Frame impose AWS S3, ~21-35 k$ de stockage). Shade règle le **problème de download** (visualisation, recherche par visage, bibliothèques de visages) et **prend en charge la migration de la data**. Une fois **les licences Google rationalisées** (voir §2), le coût **net** de Shade tombe à ~**12-13 k$** → **orientation retenue : passer sur Shade Enterprise**, **sous réserve de validation finance ([[Jordan Leroux]]) + Alec**. **(2) Google Workspace** : **215 licences à 16,80 $** ≈ **3 612 $/mois** → bascule des non-critiques en **Starter (7,77 $)** en gardant ~10 en Business → ≈ **1 570-1 670 $/mois**, soit **~2 000 $/mois (~24 k$/an) d'économie**. **(3) Riot** : contrat signé, **rien payé, aucun accès livré** → on temporise le paiement. **(4) Nettoyage drives** : relances Grégoire/Charlotte/Samuel — ça décroît (Samuel 24 756 → 3 015 ; Grégoire 3 579 → 2 573 ; Charlotte 2 225 → 1 686). **(5) 2FA** : 100 % déployé. **(6) Passation Thomas Baeumlin** (départ **début août**) : récupérer **GitHub, Looker, BigQuery, Stitch** ; réflexion sur l'**internalisation** des postes data sensibles ; compte **archivé, pas remplacé** dans l'immédiat. **(7) Cockpit SaaS** : V1 sous **~2 semaines** — licences, 186 comptes actifs, 34 à examiner, ~33 SaaS, accès/collaborateurs, dépenses, comptes dormants, risques ; basé sur les **5 SaaS les plus chers via API** (HubSpot, Slack, Airtable…) + Google Workspace ; bouton de refresh API + lien dans Works.

---

## 1 — NAS / stockage vidéo : Shade Enterprise vs Frame.io ✅ orientation
- Problème actuel : **download lourd** ; le reste (visualisation, recherche par visage) est bon.
- Comparatif : **Shade Enterprise ≈ 33 000 $/an** vs **Frame.io ≈ 46-53 000 $** (le poste cher = **stockage AWS S3**, ~21 120 $, jusqu'à 25-35 k$).
- Shade **centralise stockage/révision/approbation/édition à distance/recherche**, exploite **active storage + vault storage**, et **gère lui-même le transfert** de la data. IA puissante sous-exploitée (~10 % utilisé) : reconnaissance faciale sur les rushs, **bibliothèques de visages**.
- **Coût net** après rationalisation Google (~24 k$/an économisés) : Shade revient à **~12-13 k$** effectifs.
- ✅ **Orientation : basculer sur Shade Enterprise** (paiement annuel). Mohamed relance Shade (offre expirée le 31/03 → repartir sur ce prix). **Validation requise : [[Jordan Leroux]] (finance) + [[Alec Henry]] (validation finale).**
- 🔗 Voir le compte rendu **1:1 Boris × Alec du 20/07** (§ storage) : la veille, la conclusion provisoire était « rester sur Google » faute d'alternative moins chère → l'orientation **Shade** fait évoluer ce point. À trancher ensemble d'ici mercredi.

## 2 — Google Workspace : rationalisation des licences
- Aujourd'hui : **215 licences à 16,80 $** ≈ **3 612 $/mois**.
- Cible : basculer les non-critiques en **Starter (6,80 € / 7,77 $)**, garder ~**10 en Business** (édition, module Vault) → ≈ **1 570-1 670 $/mois**.
- **Économie ≈ 2 000 $/mois (~24 k$/an)**.
- Séquence : analyser les **plus gros drives**, confirmer le transfert des vidéos sur Shade, **puis** demander à Google le passage X licences en Starter / 10 en Business.

## 3 — Riot : contrat signé, accès non livrés
- **Riot** nous a enfin contactés, va envoyer les accès ; **rien payé pour l'instant** → **retarder le paiement au maximum** (« faire comme si on ne savait pas »).
- 🔗 Écho au 1:1 du 20/07 où Boris qualifie Riot de « blague » (2 relances sans nouvelles) → à recadrer/renégocier ou se désengager.

## 4 — Nettoyage des drives (top 3)
- Relances **Grégoire, Charlotte, Samuel** (plus gros volumes). Ça décroît :
  - **Samuel** : 24 756 → **3 015**
  - **Grégoire** : 3 579 → **2 573** (répond peu mais avance)
  - **Charlotte** : 2 225 → **1 686**
- Suivi au fil de l'eau.

## 5 — 2FA / MFA
- **100 % déployé** (« j'ai mis tout le monde »).

## 6 — Passation Thomas Baeumlin (data) ⚠️
- **Thomas** part **début août** ; ses exports HubSpot (depuis février, dernier le 8 juin) **font partie de son job** → RAS côté sécurité.
- Récupérer **tous les accès/outils** : **GitHub, Looker, BigQuery, Stitch** — il détenait **toute la data sensible**.
- Réflexion ouverte : **internaliser** ces postes sensibles (un salarié = plus de levier qu'un freelance qui part du jour au lendemain) → cohérent avec le **recrutement en cours** sur ce poste.
- **Compte archivé, pas de transfert de propriété du drive pour l'instant, pas de remplacement immédiat.** Boris mettra Mohamed « sur le canal comme d'hab ».
- 🔗 [[Ressource - Cartographie Data Thomas Baeumlin 28 mai 2026]] · [[15_Resources/IT-Audit-Mohamed/README|IT-Audit-Mohamed]].

## 7 — Cockpit SaaS (dashboard coûts / accès / utilisateurs)
- V1 en cours : **totalité des licences**, **186 comptes actifs**, **34 licences à examiner** (suspendus/archivés), ~**33 SaaS**, onglet **collaborateurs & accès**, **dépenses** (coût par licence/appli, en dur puis via API), **comptes dormants**, **risque & action** (dont statut **MFA** par utilisateur), **sources de données**.
- Approche : se baser sur les **5 SaaS les plus chers disposant d'une API** (HubSpot, Slack, Airtable…) + **Google Workspace** ; connexion progressive de tout ce qui est connectable.
- Finalité = **cockpit central** : qui a accès à quoi, combien coûte un utilisateur (ex. cumul HubSpot + Aircall + Slack + Microsoft), qui fait/ne fait pas partie d'ENT. Pas d'action directe depuis la plateforme dans un premier temps (trop complexe de répercuter sur Google), mais **à terme** création de comptes Google via le dashboard si un vrai RH arrive.
- **Bouton de refresh** des API (Google Workspace, etc.) ; hébergement sur serveur ; **lien ajouté dans Works**. **V1 ≈ 2 semaines** (5 API + Google), amélioration continue ensuite.
- 🔗 Rapproché de l'idée [[Idée - Pulse - Dashboard de contrôle des automatisations marketing]] et du chantier dashboards/tour de contrôle (cf. 1:1 20/07).

---

## Actions consolidées

| # | Action | Owner | Échéance |
|---|---|---|---|
| 1 | **Relancer Shade** (repartir sur l'offre expirée au 31/03) + cadrer la migration data | **[[Mohamed]]** | Court terme |
| 2 | **Valider Shade Enterprise** côté **finance (Jordan)** + **Alec** | **[[Boris Arduy]]** → [[Jordan Leroux]], [[Alec Henry]] | Avant engagement |
| 3 | Analyser les **plus gros drives** + confirmer transfert vidéos → **demander à Google** le passage Starter / 10 Business | [[Mohamed]] | Après migration Shade |
| 4 | **Temporiser le paiement Riot** + récupérer/valider les accès livrés | Boris + [[Mohamed]] | En attente |
| 5 | Poursuivre le **nettoyage drives** (Grégoire, Charlotte, Samuel) | [[Mohamed]] | Continu |
| 6 | **Récupérer les accès de Thomas** (GitHub, Looker, BigQuery, Stitch) + archiver le compte | Boris + [[Mohamed]] | Avant début août |
| 7 | Trancher l'**internalisation** du poste data sensible (recrutement en cours) | Boris (+ Alec) | À cadrer |
| 8 | Finaliser la **V1 du cockpit SaaS** (5 API + Google) + lien dans Works | **[[Mohamed]]** | ~2 semaines |
| 9 | Message de **validation finance + Alec** puis go NAS | Boris | Dès validation |

## Décisions clés
- **NAS : orientation Shade Enterprise (~33 k$/an brut, ~12-13 k$ net après économies Google)** — sous réserve **finance + Alec**.
- **Google Workspace rationalisé** : Starter pour les non-critiques, ~10 en Business → **~24 k$/an d'économie**.
- **Riot : paiement temporisé** tant que la valeur/les accès ne sont pas au rendez-vous.
- **Thomas : compte archivé, accès récupérés, pas de remplacement immédiat.**
- **Cockpit SaaS V1 sous ~2 semaines** (5 SaaS majeurs via API + Google).

## Points de vigilance
- **Cohérence NAS** : la conclusion du 1:1 Boris × Alec du 20/07 (« rester sur Google, pas de préviz de fichiers ») diffère de l'orientation Shade retenue ici (22/07) → **aligner Alec explicitement** avant tout engagement.
- **Quantifier la data com** (Greg & équipe) avant de dimensionner le stockage actif Shade — « ne pas balancer de la data pour balancer », le stockage coûte cher.
- **Départ Thomas = risque de disparition de valeur** (data sensible) → sécuriser **tous** les accès avant début août ; auditer ce qui a été exporté.
- **Riot** : contrat signé sans livraison → risque de payer dans le vide ; garder l'option désengagement.
- **Cockpit** : pas d'API pour toutes les applis → périmètre V1 volontairement limité aux 5 SaaS majeurs (ne pas survendre la couverture).

## Liens
- [[Boris Arduy]] · [[Mohamed]] · [[Jordan Leroux]] · [[Alec Henry]] · [[Fabrice Jaeger]] · [[Thomas Baeumlin]] · [[Quentin]]
- Réunions liées : [[2026-07-20 - Point hebdo 1-1 (Boris x Alec)]] (storage / Riot / Colbel) · [[2026-06-12 - Mohamed x Boris - Cybersecurite]] · [[Ressource - Replay Mohamed × Boris 29 mai 2026 (weekly cybersec)]] · [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]]
- Ressources : [[Ressource - Cartographie Data Thomas Baeumlin 28 mai 2026]]
- Cadres : [[Cadre - Process IT-SaaS-Cybersec]] · [[Cadre - Inventaire SaaS - Méthode pôles]]
- Projets : [[NAS Dubaï — sortie Google]] · [[Audit SaaS-IT — économies]] · [[Sprint Cybersec & phishing]] · [[Refonte verticale Data-IA-Tech-Ops]] · [[🗼 Tour de contrôle - Projets en cours]]
