---
type: call
date: 2026-08-24
source: sembly
participants: ["[[Alec Henry]]", "[[Boris Arduy]]", "[[Jordan Leroux]]"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-08-24
---

# Review budget Tools / SAAS (12 derniers mois et projections)

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (24/08/2026 14:16).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 24/08/2026 14:19 — corrige librement hors des marqueurs.

**Résumé** — Revue ligne par ligne du budget SaaS et outils sur 12 mois pour identifier les économies immédiates (Zoom, Slack, Google Workspace, SuperSales) et les migrations à planifier. Attribution des responsabilités par propriétaire et mise en place d'une gouvernance budgétaire trimestrielle.

**Décisions**
- Annuler Zoom d'ici novembre et migrer vers Google Meet
- Réduire fortement les licences Slack (20-40 personnes cœur) et migrer vers Works + WhatsApp
- Finaliser la réduction des licences Google Workspace vers le plan à 4$ d'ici fin août
- Remplacer SuperSales par la solution interne Gladia développée par Quentin
- Annuler la licence Apollo Pro facturée pour un ancien collaborateur
- Mettre en place un screening trimestriel des dépenses SaaS piloté par Jordan
- Donner à Mohamed un accès owner/admin sur tous les outils conservés pour la cybersécurité

**Actions**
- [ ] **Boris** : Examiner les lignes marquées 'à investiguer' et proposer suppressions ou remplacements
- [ ] **Mohamed** : Piloter l'exécution de la réduction des licences Google Workspace (échéance 2026-08-31)
- [ ] **Boris** : Vérifier avec Anis l'effort de développement et le calendrier pour migration Slack, produire un plan de migration phasé
- [ ] **Jordan** : Planifier un deep dive sur Zendesk dans 2 à 3 mois (échéance 2026-11-30)
- [ ] **Finance** : Investiguer la ligne Aeroalex/Rwalex et confirmer sa légitimité
- [ ] **Finance** : Produire un extrait de toutes les lignes de facturation actives pour réconciliation
- [ ] **Boris** : Consolider les besoins CRM pour décider du renouvellement HubSpot vs iClose vs solution interne (échéance 2026-09-30)
- [ ] **Alec** : Suivre les dates de renouvellement et de résiliation des contrats
- [ ] **Fabrice** : Poursuivre ou clôturer l'opportunité de partenariat Aircall et confirmer l'usage réel des licences
- [ ] **Boris** : Mener l'audit SuperSales cette semaine pour supprimer utilisateurs fantômes (échéance 2026-08-29)
- [ ] **Océane** : Retirer les utilisateurs fantômes de SuperSales (échéance 2026-08-29)
- [ ] **Jordan** : Identifier la carte associée à Apollo et procéder à l'annulation
- [ ] **Alec** : Récupérer l'accès au compte Apollo de l'ancien collaborateur
- [ ] **Jordan** : Vérifier l'usage et l'accès de Payfunnel
- [ ] **Alec** : Vérifier OneFlow et iClose
- [ ] **Boris** : Réévaluer le plan de stockage Backblaze/Shade et fournir une projection de coût actualisée
- [ ] **Océane** : Confirmer les besoins Luma et Emirates Graphics et annuler si redondants
- [ ] **Océane** : Vérifier si Riverside reste nécessaire pour podcast/vidéos
- [ ] **Jordan** : Pousser le marketing à mieux exploiter les outils et traiter la dette Twilio estimée à 20k$
- [ ] **Jordan** : Mettre en place le screening trimestriel des dépenses SaaS (échéance 2026-11-30)
- [ ] **Alec** : Définir les règles de responsabilité budgétaire avec les responsables marketing
- [ ] **Boris** : Finaliser l'état des licences Notion et confirmer qu'aucune réduction supplémentaire n'est nécessaire
- [ ] **Alec** : Redocumenter la colonne des actions et envoyer un message aux personnes concernées pour confirmer leurs responsabilités

**Risques & vigilances**
- Retards déjà accumulés sur la réduction des licences Google avec surcoûts récurrents non imputés
- Migration Slack non triviale nécessitant déploiement par étapes et vérifications techniques développement
- Absence de synchronisation Zendesk avec plateforme de données/CRM et paramétrage insuffisant de l'automatisation
- Risque de sécurité si Keeper est coupé sans solution de remplacement pour le partage de mots de passe
- Risque de casser les processus de revenu lors de la suppression d'outils transactionnels (Payfunnel, OneFlow, iClose)
- Dépenses à forte consommation (Twilio 37k€/an, Shade 30k$/an) nécessitant optimisation des flux
- Manque de cartographie complète des accès pour plusieurs outils et absence de propriétaires identifiés
- Migration de School (LMS) vers Works nécessitant inventaire des clients et contenus avant suppression

**Projets liés** : [[Audit SaaS-IT — économies]] · [[Pôle Tech & Ops interne — structuration]]

Tags : #budget-saas #optimisation-couts #gouvernance-budgetaire #audit-outils #migration-tech
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 24/08/2026 14:16 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a passé en revue, ligne par ligne, les dépenses SaaS, outils et charges récurrentes afin d’identifier rapidement les abonnements à couper, à migrer ou à investiguer, dans le but d’améliorer la marge. Les discussions ont porté sur les économies immédiates possibles (Zoom, certains accès Google, Slack, Zendesk, Keeper, etc.), sur les migrations à planifier (Works, OneFlow/iClose, outils internes), ainsi que sur les postes à forte consommation à optimiser (Twilio, stockage vidéo, WebinarJam). Des propriétaires ont été attribués pour les investigations et l’exécution : Boris pour les deep dives et la coordination, Mohamed pour l’exécution des migrations/licences, Jordan pour les audits et le suivi périodique, Alec pour la consolidation des responsabilités et la gouvernance budgétaire, et Finance/Fabrice pour les charges bancaires ou les anomalies de facturation. Le groupe a aussi insisté sur la nécessité d’un suivi formalisé des échéances contractuelles, des accès admin/owner pour Mohamed sur tous les outils conservés, et d’un plan d’action priorisé avec calendrier lors du prochain point.

📋 Outline

1. Ouverture et objectif de la réunion • 0:00:01

- La réunion a débuté par quelques remarques de contexte sur la disponibilité des participants et le timing.
- L’objectif explicite était de revoir l’inventaire des outils et les prévisions, ligne par ligne, afin de décider quoi couper, quoi réduire et quoi investiguer.
- L’enjeu était d’identifier rapidement les lignes réductibles pour optimiser les marges.

2. Remplacement de Zoom par Google Meet et économies immédiates • 0:01:25

- L’équipe a convenu que Zoom pouvait être annulé au profit de Google Meet, déjà couvert par les licences Google existantes.
- Zoom a été considéré comme une dépense superflue et une cible évidente de réduction.
- Action retenue : prévoir la suppression de Zoom d’ici novembre et vérifier avant la coupure que tous les besoins restants sont bien couverts.

3. Méthode de revue ligne par ligne et répartition des responsabilités • 0:02:29

- Un tableau de suivi contient les abonnements actuels et les prévisions, et sert de base de travail pour les décisions.
- Chaque ligne doit être classée en trois catégories : couper, garder mais optimiser, ou investiguer.
- Action : Boris est chargé d’examiner les lignes marquées « à investiguer » et de proposer des suppressions ou remplacements concrets.

4. Réduction des licences Google Workspace et exécution des migrations • 0:02:29

- L’équipe veut finaliser la migration des outils vidéo et réduire les licences Google Workspace vers le plan à 4 $ dès que possible.
- Boris a proposé une finalisation d’ici la fin du mois, tandis qu’Alec a souligné les retards déjà accumulés et la question de l’imputation des surcoûts.
- Action : Mohamed pilote l’exécution de la réduction des licences, et Boris confirme le calendrier avec lui.

5. Responsabilité budgétaire et surcoûts internes • 0:03:30

- Alec a exprimé sa frustration face aux retards de plusieurs mois et a interrogé la prise en charge des écarts de coût récurrents.
- Des exemples de surcoûts ont été cités, notamment un écart de 1 800 $ et un coût Calendly de 700 $.
- L’équipe a discuté de l’idée d’imputer les dépassements aux budgets individuels, sans pour autant recourir à des paiements ad hoc personnels.
- Action : clarifier qui est responsable financièrement des coupes retardées et renforcer la responsabilisation des dirigeants sur le contrôle des coûts.

6. Réduction de Slack et migration vers Works • 0:05:36

- La proposition consiste à réduire fortement les licences Slack à un noyau dur d’environ 20 à 40 personnes.
- Les communications générales et annonces opérationnelles devraient migrer vers Works, le wiki interne, et WhatsApp pour les équipes opérationnelles.
- Slack resterait temporairement pour l’équipe cœur afin d’assurer la continuité jusqu’en décembre/janvier.
- Le changement est jugé non trivial : il nécessite un déploiement par étapes, l’identification des 20 % d’utilisateurs à conserver, des vérifications techniques côté développement et une cible de mise en œuvre plus large autour d’octobre.
- Action : Boris doit vérifier avec Anis l’effort de développement et le calendrier, puis produire un plan de migration phasé.

7. Problèmes opérationnels et de données sur Zendesk • 0:10:56

- Deux problèmes principaux ont été identifiés sur Zendesk : l’absence de synchronisation avec la plateforme de données/CRM et un paramétrage insuffisant de l’automatisation par les utilisateurs.
- Le coût par licence étant élevé, chaque nouvel utilisateur augmente sensiblement la dépense récurrente.
- Jordan a proposé de réaliser un approfondissement sur Zendesk dans 2 à 3 mois et d’en prendre éventuellement la responsabilité sur les optimisations.
- Alec a également proposé de monter en compétence pour aider, mais pas immédiatement.
- Action : déterminer un responsable pour l’audit immédiat des utilisateurs actifs et du nombre de licences, puis planifier le deep dive de Jordan dans les 2 à 3 mois.

8. Autres lignes SaaS à couper, valider ou investiguer • 0:13:46

- Keeper, le gestionnaire de mots de passe, devrait être coupé sauf si une solution de remplacement est retenue ; le risque évoqué est un partage de mots de passe potentiellement non sécurisé.
- La question de Minari reste ouverte : l’équipe hésite entre gadget temporaire et besoin réel jusqu’à maturité des systèmes SDR.
- Stitch Data est considéré comme justifié pour l’ingestion des dépenses publicitaires et les tableaux de bord utilisés par les media buyers ; il est donc plutôt recommandé de le conserver.
- ScoreUp, le tunnel de quiz, est actif et fonctionne à un niveau supérieur en raison du volume de réponses ; son coût doit être vérifié.
- Plusieurs petits outils ou charges peu identifiées (Synetic, DNH, CKO, Rwalex, Fillout, etc.) doivent être rattachés à des propriétaires et vérifiés par Finance, car certains peuvent être obsolètes ou mal imputés.

9. Contrats, outils de signature électronique et impacts CRM • 0:18:56

- DocuSign a été évoqué avec une volonté de le couper là où il n’est pas nécessaire, tout en garantissant l’accès aux contrats via le CRM si l’abonnement est supprimé.
- Pour les processus commerciaux (Evergreen, OneFlow), les responsables sales et les closer doivent conserver l’accès à l’outil de signature choisi.
- Action : vérifier quels lancements et quelles équipes dépendent de DocuSign et préparer, si besoin, une transition vers OneFlow ou un équivalent.

10. Audit Finance des charges bancaires et charges inattendues • 0:20:46

- Une ligne intitulée Rwalex semble correspondre à des frais bancaires annuels ou à une charge mal attribuée et doit être immédiatement vérifiée par Finance.
- Action : Finance et Fabrice doivent investiguer la ligne Aeroalex/Rwalex afin de confirmer sa légitimité et empêcher tout prélèvement automatique non désiré.
- Action complémentaire : produire un extrait de toutes les lignes de facturation actives afin d’identifier les outils non utilisés et de réconcilier prévisions et charges réelles.

11. Charges inconnues, Buffer et cartographie des accès • 0:21:32

- L’équipe a relevé une ancienne charge bancaire non identifiée, possiblement liée à un compte déjà fermé, qui nécessite une vérification de l’historique du compte.
- Buffer, l’outil de planification sociale, apparaît dans les exports et semble probablement déjà coupé, mais son statut d’accès doit être confirmé.
- Il manque une cartographie complète des accès pour plusieurs outils figurant dans les exports bancaires ; il faut donc associer un propriétaire à chaque service.

12. Choix CRM, renouvellement HubSpot et échéances contractuelles • 0:22:28

- Le coût annuel de HubSpot est d’environ 40 000 € et l’équipe doit décider d’ici septembre s’il faut le renouveler, passer à iClose ou construire une solution interne.
- Boris doit consolider les besoins pour nourrir cette décision.
- Les fenêtres de résiliation contractuelle impliquent qu’un traitement formel doit être engagé maintenant, avec une vigilance particulière sur les échéances de novembre/janvier selon les clauses.
- Alec doit suivre les dates de renouvellement et de résiliation des contrats.

13. Aircall : partenariat et suite à donner • 0:23:38

- La dépense Aircall a augmenté et l’intention initiale était d’obtenir un partenariat afin de bénéficier de licences gratuites pour les événements et Scale, mais la négociation n’a pas abouti.
- Boris doit réévaluer le potentiel du partenariat.
- Action : Fabrice doit être mandaté pour poursuivre ou clôturer cette opportunité et confirmer l’usage réel des licences Aircall.

14. Outils d’analyse d’appels, suppressions et plan de remplacement • 0:24:55

- SuperSales coûte environ 5 500 € par mois et apparaît redondant avec le travail interne de Quentin et Anis ; il doit être remplacé ou retiré rapidement pour stopper la surconsommation.
- Gladia, développé par Quentin, devrait remplacer Clap et/ou SuperSales si la solution est validée et correctement déployée.
- Un audit immédiat est requis pour supprimer les utilisateurs fantômes et corriger les attributions de propriétaires afin de ne plus payer pour des licences inutilisées.
- Action : Boris mène l’audit cette semaine, tandis qu’Océane et Lucas retirent les utilisateurs fantômes.

15. Apollo : licence mal utilisée et résiliation nécessaire • 0:27:02

- Une licence Apollo « Pro » d’environ 140 € par mois a été facturée pendant sept mois au nom d’un ancien collaborateur et n’a jamais été résiliée.
- L’équipe doit retrouver l’ancien compte Google utilisé pour Apollo, retirer l’ancien utilisateur et annuler ou réattribuer la licence pour stopper les charges récurrentes.
- Action : Jordan et Alec doivent identifier la carte associée et procéder à l’annulation ; Alec tentera également de récupérer l’accès.

16. Nettoyage des paiements divers et vérification des flux transactionnels • 0:30:02

- Plusieurs petits SaaS, comme Payfunnel, OneFlow et iClose, nécessitent une vérification des accès et soit une justification de maintien, soit une suppression.
- IClose bénéficie actuellement d’un accord token/deal générant environ 10 000 $ d’économie par an, et il faut préserver cet avantage s’il est valide.
- L’équipe doit inventorier tous les tunnels et flux de paiement liés aux outils transactionnels afin d’éviter de casser les processus de revenu lors des suppressions.
- Action : Jordan vérifie l’usage et l’accès de Payfunnel ; Alec vérifie OneFlow et iClose ; marketing doit auditer les tunnels.

17. Coûts de stockage et vidéo : Backblaze et Shade • 0:32:08

- Les coûts de Backblaze et de Shade sont élevés à cause des besoins de stockage vidéo, avec Shade projeté autour de 30 000 $ par an.
- Backblaze devrait évoluer après les migrations en cours.
- Boris doit réévaluer le plan de stockage et fournir une projection de coût actualisée.
- L’équipe souhaite également produire une cartographie claire de l’usage du stockage par rapport au coût, afin de comprendre l’impact des réductions de licences Google.

18. Dépenses événementielles et services récurrents à supprimer • 0:33:23

- Luma, lié à la location de studio, et Emirates Graphics sont considérés comme des dépenses de service à supprimer une fois le nouvel espace de bureau opérationnel.
- Océane doit confirmer les besoins à venir et annuler les abonnements devenus redondants.
- Riverside semble avoir un usage incohérent et pourrait déjà être coupé ; Océane doit vérifier s’il reste nécessaire pour la publication de podcasts ou de vidéos.

19. Twilio et autres outils à forte consommation • 0:34:20

- La dépense Twilio est d’environ 37 000 € par an et relève d’un modèle à la consommation ; l’équipe doit optimiser les flux marketing/communication pour réduire les coûts variables.
- Il existe aussi une dette historique et des dépenses non exploitées, estimées à environ 20 000 $, qui doivent être suivies auprès des fournisseurs et des responsables internes.
- Jordan doit pousser le marketing à mieux exploiter les outils et à traiter cette dette ; Alec interviendra si nécessaire sur les aspects juridiques ou de recouvrement.

20. WebinarJam et discipline budgétaire sur les outils marketing • 0:35:13

- WebinarJam coûte environ 1 500 $ par mois et n’a pas été utilisé récemment ; il doit donc être remis en question et potentiellement annulé.
- L’équipe marketing dispose de plusieurs outils payants sous-utilisés, comme Vidalytics ou ARIA, et Clickfunnels a déjà été coupé.
- Il faut mettre en place une gouvernance budgétaire stricte et une revue trimestrielle des dépenses pour éviter les gaspillages récurrents.
- Action : Jordan met en place le screening trimestriel et Alec définit les règles de responsabilité budgétaire avec les responsables marketing.

21. Plateforme School, Notion et migration des données • 0:39:00

- Le LMS School héberge des communautés clients et des cours payants ; il ne peut donc pas être supprimé immédiatement.
- Avant toute migration vers Works ou une autre plateforme, l’équipe doit inventorier les clients et les contenus concernés.
- Les licences Notion ont déjà été minimisées et resteront à ce niveau réduit pendant la phase de transition.
- Action : Boris finalise l’état des licences Notion et confirme qu’aucune réduction supplémentaire n’est nécessaire.

22. Plan d’action global, cadence de suivi et accès cybersécurité • 0:40:10

- L’équipe a retenu trois grands volets : suivi asynchrone pour confirmer les coupes, screening trimestriel par Jordan pour détecter les nouvelles charges ou charges oubliées, et mise en place de budgets/propriétaires pour les dépenses outils.
- Tous les outils conservés doivent donner à Mohamed, responsable cybersécurité, un accès owner/admin ou une licence dédiée de monitoring afin de pouvoir configurer tableaux de bord et alertes de sécurité.
- Alec va redocumenter la colonne des actions et envoyer immédiatement un message aux personnes concernées pour confirmer leurs responsabilités et les prochaines étapes.
%% notes:fin %%
