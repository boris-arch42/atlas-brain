---
type: strategic-input
date-received: 2026-06-03
author: "Fabrice Jaeger"
source: "Capture d'écran « Projets équipe — Juin 2026 » partagée par Fabrice suite à l'échange du lundi 1er juin"
context: "Déclinaison opérationnelle « juin » de la [[Roadmap stratégique 6 mois (Fabrice) - juin-déc 2026]]"
status: reçu
sensitivity: confidential
tags: [fabrice, roadmap, juin-2026, projets, support-infra, dataops, saas, cybersec, recrutement, pilotage, entrepreneurs-com]
---

# Tableau projets juin (Fabrice) — 9 projets, owner Boris

> **Ce que c'est.** Capture d'un board « Projets équipe — Juin 2026 » (l'en-tête affiche « Juin 2025 », **coquille** probable) partagé par **Fabrice** après l'échange du lundi 1er juin. **9 projets, tous avec Boris en owner.** C'est la traduction « actions de juin » de sa [[Roadmap stratégique 6 mois (Fabrice) - juin-déc 2026|roadmap 6 mois]] (chantiers A→K), recentrée sur mon périmètre Support Infra.
>
> Compteur affiché : 9 total · 1 en cours · 0 bloqué · 0 terminé.

## Les 9 projets (fidèle à la source)

| # | Projet | Description | Échéance | Prio | Statut | Commentaire |
|---|---|---|---|---|---|---|
| 1 | **Coupure Notion** | Couper Notion à 80 % minimum. Valider avec les heads (Océane, Sabrina, Aziz, Anisse, Cédric, Fabrice). | 15 juin | Haute | À démarrer | Kick-off à planifier avec les heads |
| 2 | **Coupure Monday** | Sauvegarder tous les projets & datas. Migrer les process vers Slack. Prévenir Finance, Sabrina, Océane. | 30 juin | Haute | À démarrer | Call migration Slack à planifier |
| 3 | **Migration process → Entrepreneurs.work** | Transférer tous les process existants (finance, comms, marketing, sales, Yuccan) depuis Notion/wikis. | Fin juin | Moyenne | À démarrer | À définir avec Anisse |
| 4 | **Infrastructure Laravel — DataOps** | Reprendre la roadmap Yoann/Cédric. Déployer Laravel pour le 3D Challenge. **Couper Make** et automations coûteuses. | 3D Challenge juin | Haute | À démarrer | Urgent — avant le 3D Challenge |
| 5 | **Twilio — anti-fraude** | Vérifier que le programme anti-fraude est activé. Suivre le remboursement des SMS frauduleux. | Fin juin / mi-juillet | Moyenne | À démarrer | Vérification immédiate |
| 6 | **Aircall — reprise des licences** | Reprendre les licences, redéployer aux sales, attribuer à Angèle. Tableau quotidien : calls, conversations, notes. | Fin juin | Haute | À démarrer | À planifier avec Jordan |
| 7 | **NAS — sauvegarde vidéos** | Sauvegarder vidéos sur disques durs externes à Dubaï. Vider Google Workspace pour renégocier les licences. | Juin | Moyenne | À démarrer | À planifier dès début juin |
| 8 | **Recrutement Revenue Ops** | Recruter remplaçant Nicolas. Décider pour Yoann. Boris présente le déploiement data Thomas Baeumlin + ROI. | Décision juin | Haute | À démarrer | Présentation ROI data à fixer |
| 9 | **Cybersécurité** | Avancement avec Mohamed. Audit des licences « gruyères » (Aircall, Notion, Monday…). | Juin (continu) | Moyenne | **En cours** | Déjà en cours |

## Correspondance avec le vault (rien de net-neuf à 90 %)

| Projet board | Carte / source existante |
|---|---|
| 1-2-3 Coupures Notion/Monday + migration | [[Audit SaaS-IT — économies]] (licences « gruyères ») + chantier plateforme interne |
| 4 Laravel/DataOps (couper Make) | [[Refonte verticale Data-IA-Tech-Ops]] · roadmap Fabrice **I4/G7** · recoupe directement le [[2026-06-03 - Post-mortem technique Kelly (Nicolas - Ops tech)|post-mortem Kelly]] (Archi 2.0, idempotence) |
| 5 Twilio anti-fraude | [[2026-06-03 - Post-mortem technique Kelly (Nicolas - Ops tech)]] §1.a/1.b (ticket Fraud Reimbursement 27177400) |
| 6 Aircall | reprise licences (roadmap, co-owner Jordan) |
| 7 NAS Dubaï | [[NAS Dubaï — sortie Google]] (call prévu 13 juin) |
| 8 Recrutement Revenue Ops | [[Nicolas Farolfi]] (remplaçant via Aikho) · roadmap **D3** · décision Yoann ([[Ressource - Trame call Yohan 28 mai 2026]]) · ROI Thomas **G10/I10** ([[Thomas Baeumlin]]) |
| 9 Cybersécurité | [[Sprint Cybersec & phishing]] · [[Ressource - Replay Mohamed × Boris 29 mai 2026 (weekly cybersec)]] · roadmap **H1/H6** |

## Lecture Boris

- **9/9 owner = moi.** Cohérent avec le triptyque (tout ça est Support Infra : SaaS, DataOps, sécu, recrutement Ops). Mais c'est un mois très chargé, déadlines tassées sur juin, majorité « Haute / À démarrer ». À transformer en cartes projet avec `prochaine` + `echeance` dans la [[🗼 Tour de contrôle - Projets en cours|Tour de contrôle]], sinon ingérable.
- **Lecture politique.** À recouper avec le plan privé d'Alec (call 30/5) : Fabrice est en **retrait progressif**, ses sujets sont « rapatriés vers d'autres personnes » — et j'en suis un destinataire. Ce board, sous l'étiquette « Projets équipe », **matérialise ce transfert sur moi**. Renforce l'argument de **revalorisation** (Alec a explicitement dit vouloir corriger l'asymétrie de rému) : la charge documente la valeur. Ne pas endosser pour autant la centralité de Fabrice — ces projets se pitchent en propre.
- **🔴 Risque de séquencement majeur — projet 4 (Laravel avant le 3D Challenge).** Le post-mortem Kelly que je viens d'archiver montre que la stack Make est fragile **mais fonctionnelle**. Couper Make et faire du **3D Challenge (23-25 juin) le premier passage en prod d'une infra Laravel neuve** = le pire timing possible. Recommandation à porter : faire tourner Laravel **en shadow/parallèle**, garder Make comme chemin de prod pour le lancement de juin, basculer **après**. On ne branche pas une infra v1 sur un lancement à 40k leads.
- **Projet 8 — deux décisions distinctes à ne pas fusionner.** (a) Remplacement Nicolas (offshore Maroc via Aikho) et (b) décision Yoann (garder/structurer le CTO de l'autre structure d'Alec) sont deux sujets différents ; les traiter séparément. La présentation ROI data Thomas est un livrable à fixer (lié à G10/I10, sensible).
- **Dépendance Nicolas.** Le projet 5 (Twilio) et la coupure Make (projet 4) reposent sur de la connaissance Nicolas. Ne pas couper ses accès avant cartographie/ré-ownership des scénarios orphelins (cf. post-mortem + fiche Nicolas).
- **Coupures Notion/Monday.** Vraie perte de données potentielle (projet 2 = « sauvegarder tous les projets & datas »). Le kick-off heads (projet 1, 15 juin) est coordination-lourde : aligner les heads avant de couper, pas l'inverse.

## Liens
- Parent : [[Roadmap stratégique 6 mois (Fabrice) - juin-déc 2026]]
- Supervision : [[🗼 Tour de contrôle - Projets en cours]] · [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]]
- Infra/Make : [[2026-06-03 - Post-mortem technique Kelly (Nicolas - Ops tech)]] · [[Refonte verticale Data-IA-Tech-Ops]]
- People : [[Fabrice Jaeger]] · [[Nicolas Farolfi]] · [[Thomas Baeumlin]] · [[Jordan Leroux]]
- Org : [[2026-05-30 - Post-mortem Kelly & Aikho (call Alec)]] · [[Diag - Nouvel Organigramme & Cordon Sanitaire 2026-05-27]]
