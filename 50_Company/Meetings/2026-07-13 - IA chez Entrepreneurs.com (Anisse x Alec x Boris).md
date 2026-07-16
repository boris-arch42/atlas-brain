---
type: meeting
date: 2026-07-13
date_call: "13/07/2026 (lundi) — export Sembly « Anisse x Alec — IA chez Entrepreneurs.com », sans ID visible ; déclaré « call du jour » par Boris ; cohérent avec le contenu : Agent Joe déployé « mercredi soir » (= 08/07), pentests « jeudi ou vendredi » (= 16–17/07), premiers rapports Michael « dès vendredi » (= 17/07)"
participants: ["[[Anisse Rbibe]]", "[[Alec Henry]]", "[[Boris Arduy]]", "Mentionnés : [[Aziz Sfaihi]], Walid, Julien Bouissonnade, Naïma, [[Jordan Leroux]], [[Abdel El Mahi]], [[Océane De Queiros]], [[Sabrina Dahel]], [[Mohamed]]"]
contexte: "ENT — Revue IA/agents : Agent Joe V1 sans retours métier → règle d'escalade 24–48 h + canaux Slack par app + appels directs dev↔utilisateur ; blocage Aircall (agent Collections) ; coûts/jetons du rétrospectif ; Marcus renommé Michael (reporting hebdo ven 15h, visibilité par rôle) aligné sur la masterclass management (30/07 10h30 à valider) ; OCR ; standardisation des rapports de fin de semaine dans Work ; Smart Funnel communauté ; suivi mensuel conso IA + segmentation clés API ; Wiki Notion unique ; suivi accès/offboarding dans Work ; pentests Mohamed."
source: "Export Sembly AI (PDF, archivé via Claude) — sans ID meeting visible"
sensitivity: confidential
tags: [meeting, ent, ia, agents, agent-joe, michael, reporting, aircall, collections, ocr, work, wiki, conso-ia, api, offboarding, pentest, masterclass, playbook, q3-2026]
status: inbox
---

# IA chez Entrepreneurs.com — Anisse × Alec × Boris (13/07/2026)

> [!warning] **Sensibilité élevée.** Contient des tensions nominatives sur la réactivité de collaborateurs (Aziz, Walid), un renommage d'agent motivé par des « déclencheurs émotionnels », et des sujets sécurité (pentests) non annoncés. Diffusion restreinte.

> [!note] Normalisations transcription : « Works » → **Work** (canonique vault, orthographe à confirmer) · « Julien Bussonade » → **Julien Bouissonnade** (orthographe du CR core team du même jour ; vraisemblablement le même que « Julien, Team Leader Sales » cité en §3 — à confirmer) · « N8N » = retours sur les workflows **n8n**.

## TL;DR
Revue IA à trois : **Agent Joe V1** (déployé mer 08/07 au soir) est **bloqué par l'absence de retours métier** malgré relances (Aziz, Walid) → ✅ **règle d'escalade 24–48 h** (relance à 24 h, call reprogrammé le lendemain si réponse absente/insuffisante), **1 canal Slack par application**, **dev du quotidien = interlocuteur direct des utilisateurs** (appel direct si silence, ex. Naïma), et **Julien Bouissonnade (TL Sales)** enrôlé comme référent feedback. **Agent Collections bloqué par Aircall** (numéros/config admin) → **Boris vérifie config + droits** ; le rétrospectif d'appels sera **contrôlé** (fenêtre 1 mois, max 3 ; coût/jetons estimé avant run ; lot test ; option GPU Maroc à instruire). ✅ **Marcus renommé Michael** : rapports hebdo **obligatoires ven 15h**, visibilité par rôle (managers = leurs équipes seulement), comparaison S-1, **lancement coordonné avec la masterclass management (30/07 10h30 heure FR — à valider par Boris)**, annonce **managers-first** avec premiers rapports **dès ven 17/07**. **Alec exige la standardisation des rapports de fin de semaine dans Work** (Anisse + Boris coordonnent) + **reporting mensuel de la conso IA** (dashboards par app/fournisseur, ligne budgétaire 2027) ; **Boris recommande la segmentation des clés API par projet** ✅. Wiki Notion unique (doc CSM Sabrina intégrée, agent IA de création de pages en test) ; **Boris produit un brief « suivi des accès/offboarding » natif Work**. Fin de réunion : Agent Joe livrable **cette semaine** (Anisse → Julien B. pour tests/optimisation coûts), comms internes dans le fil d'activité Work (Océane × Anisse), **rapprochement bancaire Jordan = chantier immédiat**, **pentests Mohamed** (invitation Anisse ; **Boris cadre le périmètre, planif visée jeu 16 ou ven 17/07**).

---

## 1 — Agent Joe V1 : déployé, mais sans retours métier 🔴
- **V1 déployée mercredi soir (08/07)** ; depuis, **quasi aucun retour substantiel côté sales** → améliorations et itérations bloquées.
- Relances multiples Slack + WhatsApp auprès d'**[[Aziz Sfaihi]]** et **Walid** : une confirmation minimale (retours n8n), puis plus rien.
- Côté dev : tests, corrections de bugs et améliorations avancent, mais **inintégrables sans feedback utilisateur rapide et exploitable**.

## 2 — Règle d'escalade des retours : 24–48 h ✅
- **Tout retour sans réponse à 24 h → suivi ; réponse absente/insuffisante → call reprogrammé le lendemain** pour obtenir une réponse claire.
- Objectif : plus jamais 2 jours sans feedback ; boucles **responsables et traçables** ; cadre de réactivité **commun produit ↔ équipes terrain**.
- 🔗 Décalque exact du **SLA interne 24 h** acté en gouvernance le 10/07 ([[2026-07-10 - Gouvernance Ops, Conformité & Support Client (Alec x Boris x Sabrina)]] §14).

## 3 — Julien Bouissonnade = référent feedback sales
- Identifié comme **particulièrement réactif et motivé** → à solliciter davantage sur Agent Joe et les déploiements similaires.
- **Team Leader Sales (pas SDR)** : à ajouter aux canaux Slack concernés + demandes de feedback → validations plus rapides quand les utilisateurs habituels ne répondent pas.

## 4 — Organisation : canal Slack par app + appels directs dev↔utilisateur ✅
- **Un canal Slack par application** ; le **développeur du quotidien devient l'interlocuteur principal** des utilisateurs finaux, sous supervision managériale.
- Si silence ou réponse insuffisante : **le dev appelle directement** (ex. **Naïma**) pour clarifier le besoin — réduire la distance développement ↔ usage, éviter les allers-retours dispersés.

## 5 — Culture : respect du travail des développeurs ⚠️
- Frustration exprimée : des devs (y compris en contexte personnel difficile) **ne reçoivent pas de retours dans des délais raisonnables** → risque moral/engagement sur les échéances futures.
- Le manque de priorisation de certains utilisateurs — qui savent répondre vite ailleurs, même en vacances — est perçu comme un possible **manque de bonne volonté**, pas un simple désordre.
- **La direction doit clarifier les attentes, recadrer, et rappeler la valeur du travail technique.**

## 6 — Agent Collections : blocage Aircall 🔴
- L'agent d'**analyse des appels Collections** est bloqué par l'**intégration Aircall** : numéros de téléphone manquants et/ou mauvaise configuration d'administration.
- **[[Jordan Leroux]] et ses équipes attendent le déblocage**, puis seront **owners des retours fonctionnels**.
- **Boris a déjà fourni certaines lignes** ; il **vérifie le reste de la config Aircall + les droits d'administration** pour lever le blocage.

## 7 — Rétrospectif d'appels : périmètre contrôlé & coûts jetons
- Plan : **annoncer l'outil, définir des attentes de reporting claires, puis activer sur un périmètre contrôlé** — pas de rattachement indiscriminé de tout l'historique.
- **Fenêtre minimale ~1 mois, jusqu'à 3 mois max** pour des rapports réellement utiles ; **coût + conso jetons estimés et validés avant toute exécution à grande échelle** ; **petit lot test** pour démontrer la valeur avant élargissement.
- Option évoquée : **exécution locale GPU / datacenter au Maroc** (coût + confidentialité) — contraintes matérielles et opérationnelles à instruire.

## 8 — Marcus → Michael : reporting hebdomadaire ✅
- L'agent **Marcus a été désactivé puis renommé Michael** (éviter des déclencheurs émotionnels + corriger des bugs).
- **Rapports hebdomadaires obligatoires, envoyés chaque vendredi 15h aux administrateurs**, avec **visibilité restreinte par rôle** : les managers de pôle ne voient que leurs propres collaborateurs.
- Les rapports incluent une **comparaison avec la semaine précédente** (continuité, tendances).

## 9 — OCR + standardisation des rapports de fin de semaine dans Work ✅
- **OCR à intégrer** aux fonctionnalités d'agent et de reporting (enrichir la captation de données).
- **Alec demande la standardisation des retours de fin de semaine directement dans Work** : traçabilité des demandes, visibilité sur ce qui a réellement été corrigé d'une semaine à l'autre — fin des fils Slack dispersés.
- **Anisse + Boris coordonnent l'intégration** ; le rapport standardisé inclut une **vue managériale** + des **consignes précises d'amélioration** par collaborateur.

## 10 — Communauté gratuite : Smart Funnel & IA
- Boris présente l'extension d'un système type **Smart Funnel à la communauté gratuite** : automatiser les réponses aux messages, réduire progressivement les interventions humaines, répliquer des logiques evergreen.
- **[[Abdel El Mahi]] devait vraisemblablement présenter le sujet en détail** ; une indisponibilité explique peut-être que tout le monde n'ait pas été bouclé → boucle à refermer.
- 🔗 [[Communauté gratuite ENT — lead magnet & réactivation base]] · [[2026-07-09 - Communauté gratuite - Cadrage & MVP (Alec x Boris x Abdel x équipe)]]

## 11 — Lancement Michael ⇄ masterclass management
- **Lancement de Michael coordonné avec la masterclass management** pour structurer les rapports de fin de semaine et accélérer l'adoption.
- **Date pressentie : 30/07, 10h30 heure française — à valider par Boris.**
- **Annonce managers-first** : retours contrôlés + identification des bugs avant déploiement large ; puis déploiement selon **liste fournie par les managers à la date de la masterclass**.
- **Coachs : pas de Michael par défaut** (sauf rapports réguliers requis) ; les sales ont déjà des reportings fin de journée/semaine → centralisables dans Slack.
- ⚠️ **Boris : équilibre feedback vs productivité** — ne pas générer une inflation de slides/rapports.
- 🔗 [[Manager Playbook — Core V1 & certification]] · [[2026-07-09 - Manager Playbook - Cadrage V1-V2 (Alec x Boris)]]

## 12 — Conso IA : suivi mensuel & segmentation des clés API ✅
- **Alec demande un reporting mensuel** (au minimum 1re + dernière réunion du mois) : **coûts d'exécution IA, conso jetons, volume de données** — ligne budgétaire importante **d'ici 2027** ; visibilité actuelle insuffisante, plusieurs équipes consomment sans suivi centralisé.
- **Anisse propose des dashboards quotidien/hebdo/mensuel par application**, ventilés par fournisseur (ChatGPT, cloud, DeepSeek/OpenRouter), + contournements de réduction de coûts.
- **Boris : clés API segmentées par projet/client** → attribution propre de la conso, rayon d'impact réduit en cas d'incident, audit et responsabilisation facilités. ✅ Recommandation retenue.

## 13 — Wiki, processus & documentation IA
- ✅ **Consolidation de Notion dans un Wiki unique**, gestion des dossiers + accès affinés (documents ↔ départements ↔ utilisateurs).
- **Doc CSM de [[Sabrina Dahel]] transmise et déjà intégrée** au Wiki.
- **Agent IA en test** : création automatique de pages Wiki/processus à partir de prompts conversationnels — améliorations en cours avant déploiement complet.
- **Boris demande une stratégie claire de stockage/récupération pour la documentation *système*** (distincte de la doc *processus*) — meilleur emplacement encore incertain.

## 14 — Accès, offboarding & intégration Work
- Préoccupation cybersécurité/offboarding (Boris) : **mécanisme de suivi des demandes d'accès et de leur statut, basé sur Work** → audits et sorties de collaborateurs gérables.
- **Boris produit un brief** décrivant fonctionnalités attendues + exigences du projet.
- ✅ Principe : **intégration native dans Work** plutôt que plateformes doublons.
- 🔗 Recoupe la règle d'offboarding du [[Sprint Cybersec & phishing]].

## 15 — Actions de clôture (Agent Joe, Jordan, sécurité)
- **Anisse livre une version déployable d'Agent Joe dans la semaine** + transmet les tâches à **Julien Bouissonnade** pour démarrer **tests + optimisation des coûts**.
- **Annonce Michael envoyée d'abord aux managers uniquement** → premiers rapports de fin de semaine **dès vendredi 17/07**.
- **[[Océane De Queiros]] × Anisse** : intégration des communications internes dans le **fil d'activité Work** (visibilité).
- **Besoin immédiat de Jordan : automatisation du rapprochement bancaire + identification des factures** → chantier à démarrer au plus vite.
- **Pentests : Anisse a invité [[Mohamed]]** (tests de pénétration + sécurité des données) ; **Boris coordonne le périmètre avec son responsable sécurité — planification visée jeudi 16 ou vendredi 17/07**.

---

## Actions consolidées

| # | Action | Owner | Échéance |
|---|---|---|---|
| 1 | Vérifier **config Aircall + droits admin** (agent Collections) | **[[Boris Arduy]]** | Immédiat |
| 2 | Retours fonctionnels agent Collections (post-déblocage) | [[Jordan Leroux]] + équipes | Après déblocage |
| 3 | **Estimer coût/jetons du rétrospectif** + lancer un lot test | [[Anisse Rbibe]] (+ Boris) | Avant tout run large |
| 4 | Instruire l'option **GPU/datacenter Maroc** | Anisse + Boris | Court terme |
| 5 | **Valider date/heure masterclass (30/07 10h30)** | **Boris** | Cette semaine |
| 6 | **Annonce Michael aux managers** → premiers rapports | Anisse (+ Alec) | **Ven 17/07** |
| 7 | Standardiser les **rapports de fin de semaine dans Work** (vue managériale + consignes) | Anisse + **Boris** | Court terme |
| 8 | Livrer **Agent Joe déployable** + transmettre tâches à Julien B. (tests, coûts) | Anisse | Cette semaine |
| 9 | Ajouter **Julien B. aux canaux Slack** + boucles feedback | Anisse | Immédiat |
| 10 | **Reporting mensuel conso IA** + dashboards par app/fournisseur | Anisse | 1re réunion d'août |
| 11 | **Segmenter les clés API** par projet/client | Anisse + **Boris** | Court terme |
| 12 | **Brief suivi des accès/offboarding** (natif Work) | **Boris** | Court terme |
| 13 | Comms internes → **fil d'activité Work** | [[Océane De Queiros]] × Anisse | Court terme |
| 14 | Démarrer le **rapprochement bancaire + identification factures** | Anisse + Jordan | ASAP |
| 15 | **Cadrer le périmètre pentests** avec Mohamed + planifier | **Boris** + [[Mohamed]] | **Jeu 16 – ven 17/07** |
| 16 | Stratégie **stockage/récupération doc système** (vs process) | Anisse (+ Boris) | Court terme |

## Décisions clés
- **Escalade feedback 24–48 h** : relance à 24 h, call reprogrammé le lendemain si réponse absente/insuffisante.
- **1 canal Slack par application** + dev du quotidien = interlocuteur direct (appel si silence).
- **Marcus renommé Michael** ; **rapports hebdo obligatoires ven 15h**, visibilité par rôle, comparaison S-1.
- **Lancement Michael aligné masterclass (30/07 10h30, à valider Boris)** ; annonce **managers-first**, coachs pas par défaut.
- **Standardisation des rapports de fin de semaine dans Work** (Anisse + Boris).
- **Reporting mensuel conso IA** (coûts, jetons, data) + dashboards par app/fournisseur.
- **Clés API segmentées par projet/client.**
- **Wiki Notion unique** ; **suivi des accès intégré nativement à Work** (pas de plateforme doublon).

## Points de vigilance
- ⏰ **Semaine dense** : validation masterclass (Boris), Agent Joe livrable, annonce Michael, pentests jeu/ven — tout atterrit avant le 17/07.
- **Le renommage Marcus → Michael** évoque des « déclencheurs émotionnels » : garder la raison exacte hors des comms larges.
- **Risque d'inflation de reporting** (slides, rapports) explicitement flaggé par Boris — à surveiller dès les premiers rapports du 17/07.
- **Coût du rétrospectif d'appels** : ne rien lancer à l'échelle sans estimation validée ; l'option Maroc est séduisante (coût/confidentialité) mais opérationnellement lourde.
- **Boucle Abdel/communauté incomplète** — à refermer avant que le Smart Funnel communauté n'avance en silo.
- **Tension culturelle dev ↔ métier** : le recadrage direction demandé (§5) doit précéder la règle d'escalade, sinon elle sera vécue comme punitive.

## Liens
- [[Anisse Rbibe]] · [[Alec Henry]] · [[Boris Arduy]] · [[Aziz Sfaihi]] · [[Jordan Leroux]] · [[Abdel El Mahi]] · [[Océane De Queiros]] · [[Sabrina Dahel]] · [[Mohamed]]
- Projets : [[Manager Playbook — Core V1 & certification]] · [[Communauté gratuite ENT — lead magnet & réactivation base]] · [[Sprint Cybersec & phishing]] · [[Refonte verticale Data-IA-Tech-Ops]] · [[Audit SaaS-IT — économies]]
- Réunion sœur du jour : [[2026-07-13 - Réunion Hebdo Core Team (Core Team)]]
- Contexte (bloc 09-10/07) : [[2026-07-09 - Manager Playbook - Cadrage V1-V2 (Alec x Boris)]] · [[2026-07-10 - Gouvernance Ops, Conformité & Support Client (Alec x Boris x Sabrina)]] · [[2026-07-09 - Communauté gratuite - Cadrage & MVP (Alec x Boris x Abdel x équipe)]] · [[2026-07-10 - Point hebdo 1-1 (Boris x Alec)]]
