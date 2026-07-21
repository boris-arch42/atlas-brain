---
type: meeting
date: 2026-07-18
date_call: "18/07/2026 (vendredi) — date confirmée par Boris. Export Sembly « Alkimiy X Boris » sans horodatage ; validée a posteriori."
participants: ["[[Boris Arduy]] — accès outils, centralisation data, rédaction contrat", "[[Théodoric]] — lead closers Alkimiy, demande admin iClosed", "[[Romain (Solveo)]] (Romain Nussmann, fondateur Alkimiy) — détient la data SuperSales, initie le doc de référence, demande un contact GHL", "[[Aziz]] — auteur du doc de passation / due diligence", "Mentionnés : [[Alec Henry]] (intentions/contrat), [[Riyad]] (réunion technique API, avec Théodoric), Julien & Meryem (complétion des sections sensibles), Poisson Fécond (contact GHL/GoHighLevel)"]
contexte: "ENT — Onboarding de l'équipe closing externe Alkimiy sur la campagne Challenge Bourbon en mode white-label (closers Alkimiy aux côtés des commerciaux ENT). Cadrage : formalisation contractuelle du dispositif (Boris ↔ Alec, contrat visé ce week-end), métriques de parité pour comparer les nouvelles équipes à l'équipe actuelle (CA, cash encaissé, CA/appel, présence RDV, remboursement, panier moyen ; base ~6 mois), centralisation des données, correction de l'audience du doc de passation (Aziz), stack iClosed (calendriers/RDV/CRM beta) + SuperSales (enregistrement/analyse appels via Google Meet), besoins API du CRM interne Alkimiy, onboarding closers + accès admin, mise en relation GHL (Poisson Fécond). Coordination via WhatsApp Bourbon."
source: "Export Sembly AI (PDF, archivé via Claude)"
sensitivity: confidential
tags: [meeting, ent, alkimiy, bourbon, white-label, closing-externalise, iclosed, supersales, closers, onboarding, crm, api, parite-performance, passation, due-diligence, ghl, gohighlevel, contrat, q3-2026]
status: inbox
---

# Onboarding Alkimiy — Campagne Bourbon : Stack, Parité & Passation (≈ 18/07/2026)

> [!warning] **Sensibilité.** Évolutions d'effectifs commerciaux non encore annoncées, dispositif partenaire **non contractualisé**, doc de passation à audience restreinte. Cercle direction / pilotage Bourbon uniquement.

> [!note] **Normalisations transcription.** « Alchimie » / « Alchemy » (corps du transcript) = **Alkimiy**, nom canonique du vault (cf. arbitrage prise d'appels Bourbon **CGM vs Alkimiy**, note du 10/07) — agence de closing externe qui sert **plusieurs clients**. · « Super Sales » → **SuperSales** (enregistrement + analyse d'appels). · **iClosed** = calendriers / RDV + **CRM beta** intégré. · **GHL** = GoHighLevel ; « Poisson Fécond » = contact GHL (nom tel que transcrit, probable pseudonyme). · **Bourbon** = campagne Challenge Bourbon / funnel Méthode Bootstrap (cf. Kickoff Mediabuy 10/07). · « L'organisateur » = **Entrepreneurs.com** (client Alkimiy pour Bourbon). · ⚠️ **Romain** = **[[Romain (Solveo)]]** — **Romain Nussmann**, **fondateur d'Alkimiy** (centre d'excellence sales, Casablanca) ; confirmé identique au « Romain (Solveo) » du 04/07 et impliqué côté Tip Talent / lancement Kelly. **Ne pas confondre** avec [[Roman Tebenikhin Bonamy]]. · « Théo » (réunion technique) = **Théodoric** (confirmé). · « rôles commerciaux / AIs » = terme flou du transcript, périmètre non figé.

## TL;DR
Cadrage de l'**intégration de l'équipe closing externe Alkimiy** sur la **campagne Bourbon** en **white-label** (leurs closers travaillent aux côtés des commerciaux ENT). Deux blocs : **(1) commercial/évaluation** — le dispositif n'est **ni contractualisé ni formellement validé** (aucun accord écrit sur les intentions d'Alec), **Boris contacte Alec et vise un contrat ce week-end** ; l'équipe fige un **jeu de métriques de parité** (CA généré, **cash réellement encaissé**, CA/appel, taux de présence RDV, taux de remboursement, panier moyen) pour comparer les nouvelles équipes à **l'équipe actuelle reconstituée sur ~6 mois** (le taux de progression reste **qualitatif, non officiel**) ; **manque de centralisation des données = risque systémique** → **doc unique de référence** (critères + période), **Romain rédige**, **Boris centralise la data**. **(2) technique/onboarding** — stack **iClosed** (calendriers, RDV, **CRM beta** → pas de CRM supplémentaire, vues filtrées) + **SuperSales** (enregistrement via **Google Meet relié à iClosed**, chaque closer connecte son compte Google) ; Alkimiy développe **son propre CRM centralisé** et veut **tirer la data de perf d'iClosed par API** (nouveaux endpoints CRM beta à tester en GET/POST, droits + doc API à vérifier) ; approche **progressive** = onboarder d'abord, réunion technique **Riyad × Théodoric × organisateur** ensuite. **Théodoric** envoie la **liste des closers** (prénom/nom/e-mail) et **demande l'accès admin iClosed** ; licences SuperSales (+ comptes Google temporaires) à provisionner ; **démarrage escalade/config technique visé sous ~11 jours**. Le **doc de passation d'Aziz** (due diligence Alkimiy) a été **diffusé trop largement** → confusion + risque de révéler des évolutions d'effectifs ; on **poursuit mais en corrigeant l'audience**. En bonus : **Romain demande à Boris une mise en relation GHL** (Poisson Fécond) pour un partenariat lié à entrepreneurs.com. Coordination quotidienne via **WhatsApp Bourbon**.

---

## 1 — Effectifs commerciaux & contractualisation des rôles · 0:00:00
- **Nombre exact de rôles commerciaux / « AIs » flou**, évoqué de manière incohérente selon les échanges → **ambiguïté sur le périmètre réel**.
- **Aucun contrat officiel ni accord formel** sur les intentions d'Alec ou sur l'organisation commerciale : l'arrangement **n'est ni juridiquement ni opérationnellement confirmé**.
- **Boris contacte Alec immédiatement** et **vise la rédaction d'un contrat durant le week-end** pour formaliser responsabilités et conditions.
- **Règle d'alignement** : si un lead interne (ex. **Romain**) n'a pas l'info, elle est **non validée** → **confirmation croisée** nécessaire entre les leads pour aligner **Alec, Boris et Romain**.

## 2 — Métriques de parité & base de référence · 0:02:10
- Décision : figer un **ensemble fixe de métriques de parité** pour comparer les **nouvelles équipes / équipes en transition** à **l'équipe actuelle** (référence de performance).
- Métriques retenues : **CA généré · cash réellement encaissé · CA par appel · taux de présence aux RDV · taux de remboursement · panier moyen**.
- Objectif : **reconstituer la performance historique** de l'équipe actuelle (ex. **6 derniers mois**) pour disposer d'une base de comparaison robuste.
- **Taux de progression** = important mais **indicateur qualitatif et non officiel** (trop difficile à mesurer de façon fiable pour devenir une métrique de parité stricte).

## 3 — Disponibilité & extraction des données · 0:04:02
- **Romain** dispose d'un **détail sur ~3 mois issu de SuperSales** + un **export Excel** ; il faut des **données historiques plus complètes** pour une base solide.
- L'**extraction des métriques par appel** devrait être **relativement simple** depuis les systèmes existants → **figer les indicateurs** une fois extraits et vérifiés.
- **Manque de données centralisées et partagées de façon cohérente = problème systémique** et risque pour la qualité de l'évaluation.
- Proposition : **un document unique** rassemblant critères de parité + période de référence, pour un **cadre d'analyse partagé**. **Boris coordonne la centralisation/mise à dispo des données** ; **Romain initie la rédaction** du document et y intègre la structure de référence.

## 4 — Doc de passation / due diligence & communication · 0:06:41
- **Aziz** a produit un **doc de passation / due diligence** destiné à être **complété par des contacts internes précis** (**Julien, Meryem**) pour transférer la connaissance opérationnelle liée à Alkimiy.
- Le doc a été **diffusé à un groupe plus large que prévu** → confusion, impression de mauvaise communication ops, **risque de révéler prématurément des évolutions d'effectifs**.
- **Théodoric** précise que l'intention était d'assurer une **visibilité au groupe** tout en réservant la **complétion à certaines personnes** ; exécution maladroite mais **approche jugée utile**.
- Décision : **poursuivre la passation** en **corrigeant l'audience** et en veillant à ce que **seules les bonnes personnes complètent les sections sensibles**. **Aziz** mieux contrôler la diffusion ; **Boris + Théodoric** coordonnent audience et next steps.

## 5 — Périmètre, finalité & temporalité du handover · 0:12:34 → 0:13:41
- Les infos partagées servent à **préparer la passation** et à **clarifier la collaboration des prochains mois** — **pas** à figer un processus final.
- Livrable attendu = **décrire comment les équipes échangent/communiquent jusqu'en septembre**, en acceptant que les process **évolueront ensuite**. C'est un **support de travail de transition**, pas la définition de l'organisation cible.
- **Phase d'audit en cours** : le **modèle opérationnel final à M3/M6 n'est pas encore connu**. Les procédures du **1er août ≠ celles du 30 septembre** → faciliter la collaboration et l'ajustement progressif plutôt que **verrouiller des workflows définitifs trop tôt**.

## 6 — Stack technique campagne Bourbon (white-label) · 0:15:15
- Campagne en **white-label** : les **closers Alkimiy travaillent aux côtés des commerciaux de l'organisateur** (ENT).
- Deux outils principaux : **iClosed** (calendriers, RDV, **nouveau CRM beta**) et **SuperSales** (enregistrement + analyse des appels).
- Le **CRM beta d'iClosed** apporte des fonctionnalités CRM intégrées → **évite d'ajouter un CRM supplémentaire** ; des **vues filtrées** n'afficheront que les commerciaux et RDV pertinents.

## 7 — SuperSales, enregistrement & intégrations · 0:16:58
- **SuperSales confirmé** pour l'enregistrement des réunions, **intégré via Google Meet relié à iClosed**.
- **Chaque closer connecte son compte Google à iClosed** (partage des dispos + lien avec les réunions).
- **Licences SuperSales** — et potentiellement des **comptes Google temporaires** — à fournir à l'équipe commerciale.

## 8 — Accès données CRM & besoins API (CRM interne Alkimiy) · 0:20:32
- Alkimiy développe **son propre CRM centralisé** et veut **récupérer les données de perf depuis iClosed** pour **éviter de maintenir un CRM distinct par client**.
- Les nouvelles fonctionnalités CRM d'iClosed impliquent de **nouveaux endpoints API** à **tester** (extraction **GET / POST**) → **droits d'accès + documentation API à vérifier**.
- Approche **progressive** retenue : **d'abord onboarder les commerciaux** sur les outils, **puis réunion technique** entre **Riyad, Théodoric et l'organisateur** pour détailler les besoins et tester la connexion API.

## 9 — Onboarding, accès admin & calendrier · 0:22:14
- **Théodoric** envoie la **liste des closers** (prénom, nom, e-mail) pour **création des comptes iClosed**.
- **Théodoric demande à être admin** sur le compte iClosed pour **superviser/dépanner** sans tout remonter à Boris.
- Cible : **démarrage des sujets d'escalade + config technique sous ~11 jours**, avec une **avancée rapide** dès la transmission des accès.

## 10 — Partenariat potentiel & contact GHL · 0:25:52
- **Romain** demande à Boris une **mise en relation avec un contact GHL** (**Poisson Fécond**) pour explorer une **opportunité de partenariat stratégique** liée à entrepreneurs.com et Alkimiy.
- **Boris accepte** de prendre contact et de **faire un retour à Romain**.

## 11 — Prochaines étapes & canal de communication · 0:26:55
- **Semaine suivante** : lister les comptes commerciaux, **provisionner les licences**, accorder les **accès admin**, **finaliser la config technique** et **synchroniser les outils**.
- **Coordination quotidienne** + questions via le **groupe WhatsApp Bourbon** (mises à jour rapides).
- Convergence sur une **exécution progressive**, avec un **besoin fort de clarification documentaire et de centralisation**.

---

## Actions consolidées

| # | Action | Owner | Échéance |
|---|---|---|---|
| 1 | **Contacter Alec** + **rédiger le contrat** (responsabilités & conditions du dispositif) | **[[Boris Arduy]]** → [[Alec Henry]] | **Ce week-end (19-20/07)** |
| 2 | **Confirmation croisée** Alec ↔ Boris ↔ Romain sur l'organisation commerciale (info non partagée = non validée) | **[[Boris Arduy]]** | Immédiat |
| 3 | **Coordonner la centralisation** & la mise à disposition des données de perf | **[[Boris Arduy]]** | Court terme |
| 4 | **Rédiger le doc unique de référence** (métriques de parité + période retenue) | **[[Romain (Solveo)]]** | Court terme |
| 5 | **Reconstituer la perf historique** de l'équipe actuelle (~6 mois) sur les métriques de parité | Romain (data SuperSales) + Boris (centralisation) | Court terme |
| 6 | **Mieux contrôler la diffusion** du doc de passation (audience restreinte) | **[[Aziz]]** | Immédiat |
| 7 | **Coordonner l'audience & les next steps** de la passation ; réserver les sections sensibles aux bonnes personnes (Julien, Meryem) | [[Aziz]] + [[Théodoric]] + [[Boris Arduy]] | Court terme |
| 8 | **Envoyer la liste des closers** (prénom, nom, e-mail) pour création des comptes iClosed | **[[Théodoric]]** | Immédiat |
| 9 | **Ajouter Théodoric en admin iClosed** (supervision/dépannage) | [[Boris Arduy]] | Court terme |
| 10 | **Connecter le compte Google à iClosed** (dispos + lien réunions Meet) | Chaque closer Alkimiy | À l'onboarding |
| 11 | **Provisionner les licences SuperSales** (+ comptes Google temporaires éventuels) | [[Boris Arduy]] / ENT | À l'onboarding |
| 12 | **Vérifier droits d'accès + doc API iClosed** (nouveaux endpoints CRM beta) | [[Théodoric]] / [[Riyad]] (+ Boris) | Avant test API |
| 13 | **Réunion technique** (besoins API + test connexion GET/POST) — *après* l'onboarding | [[Riyad]] × [[Théodoric]] × organisateur | Après onboarding |
| 14 | **Contacter Poisson Fécond (GHL)** + retour à Romain | **[[Boris Arduy]]** | Court terme |
| 15 | **Lister comptes, licences, accès admin, config technique, sync outils** | Équipe | Semaine suivante |

## Décisions clés
- **Jeu de métriques de parité figé** : CA généré, **cash réellement encaissé**, CA/appel, taux de présence RDV, taux de remboursement, panier moyen. **Taux de progression = qualitatif/non officiel**.
- **Base de référence = perf historique de l'équipe actuelle reconstituée sur ~6 mois**.
- **Un doc unique de référence** (critères + période) : **Romain rédige**, **Boris centralise la data**.
- **Poursuivre la passation** en **corrigeant l'audience** (sections sensibles réservées).
- **Campagne en white-label** : closers Alkimiy + commerciaux ENT.
- **Stack = iClosed (calendriers/RDV + CRM beta) + SuperSales (enregistrement/analyse)** ; **pas de CRM supplémentaire** (CRM beta suffit) ; **vues filtrées**.
- **SuperSales via Google Meet relié à iClosed** ; **chaque closer connecte son compte Google**.
- **Alkimiy récupère la data iClosed par API** (CRM centralisé, éviter un CRM par client) ; **approche progressive** onboarding → technique.
- **Démarrage escalade/config technique sous ~11 jours**.

## Points de vigilance
- **Dispositif non contractualisé** : aucun accord écrit sur les intentions d'Alec → **formaliser d'urgence** (contrat visé ce week-end) avant de scaler les engagements.
- **Périmètre effectifs / rôles flou** + **infos contradictoires** → risque d'ambiguïté ; toute info non confirmée par les leads = **non validée**.
- **Absence de centralisation fiable des données = risque systémique** pour la qualité de l'évaluation de parité → le doc de référence + la centralisation doivent précéder toute décision d'éval.
- **Doc de passation sur-diffusé** → risque de **révéler prématurément des évolutions d'effectifs** ; verrouiller l'audience.
- **API iClosed CRM beta** : **nouveaux endpoints non testés** (GET/POST), **droits + documentation à vérifier** avant de brancher le CRM Alkimiy.
- **Phase d'audit** : modèle opérationnel final **M3/M6 inconnu**, procédures **01/08 ≠ 30/09** → ne pas verrouiller de workflows définitifs trop tôt.
- 🔗 Le dispositif prolonge l'**arbitrage prise d'appels Bourbon CGM ([[Lucas (CGM)]]) vs Alkimiy** (cf. 10/07) : caler le dimensionnement sur les **volumes réels du funnel Méthode Bootstrap**.

## Liens
- [[Boris Arduy]] · [[Alec Henry]] · [[Aziz]] · [[Théodoric]] · [[Romain (Solveo)]] · [[Riyad]]
- Réunions sœurs / contexte Bourbon : [[2026-07-10 - Kickoff Mediabuy Méthode Bootstrap - Challenge Bourbon (Adil x Hubert x Cédric x Boris)]] · [[2026-07-10 - Point hebdo 1-1 (Boris x Alec)]] (arbitrage prise d'appels Bourbon CGM/Alkimiy) · [[2026-06-30 - Aziz - Fin de collaboration & transition pôle Sales]]
- Projets liés : [[🗼 Tour de contrôle - Projets en cours]]
- ⏳ Carte projet à créer : **Alkimiy — dispositif de closing externalisé (campagne Bourbon)**


---
