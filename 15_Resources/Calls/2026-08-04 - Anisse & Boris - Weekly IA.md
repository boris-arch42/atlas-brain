---
type: call
date: 2026-08-04
source: sembly
participants: ["[[Boris Arduy]]", "[[Anisse Rbibe]]"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-08-05
---

# Anisse & Boris - Weekly IA

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (04/08/2026 15:37).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 05/08/2026 15:50 — corrige librement hors des marqueurs.

**Résumé** — Revue hebdomadaire IA couvrant les priorités de développement (max 3 projets par dev), la qualité du feedback des stakeholders, et un problème critique sur la fiabilité des analyses SuperSales détecté lors de l'audit Alchemy. Validation d'un programme de coaching opérationnel de 2 mois ciblant 15-20 exécutants et d'une décentralisation de la propriété via mini-projets.

**Décisions**
- Limiter chaque développeur à maximum 3 projets en parallèle pour préserver la concentration
- Fournir à Alchemy un accès contrôlé en lecture seule à Clap pour l'audit commercial
- Créer un template standardisé de brief projet avec prompt Claude pour réduire l'ambiguïté des demandes
- Produire systématiquement une vidéo Loom de présentation après chaque livraison
- Programme de coaching opérationnel de 2 mois (août-septembre) ciblant 15-20 exécutants
- Piloter la décentralisation de propriété via attribution de mini-projets à des non-heads
- Créer un agent Slack pour managers afin de collecter les demandes de développement

**Actions**
- [ ] **Boris** : Configurer un rôle d'accès limité dans Clap pour Alchemy (audit commercial)
- [ ] **Anisse** : Préparer la liste des dossiers Clap pertinents pour l'audit Alchemy
- [ ] **Anisse** : Créer une démo Loom de Super Joe pour améliorer l'adoption par les équipes
- [ ] **Boris** : Ajouter Alec à la liste de diffusion pour tester les messages de fin de semaine
- [ ] **Naïma** : Implémenter le template de brief projet dans l'outil de roadmap
- [ ] **Anisse** : Identifier 15-20 personnes pour le programme de coaching et planifier 3 sessions par personne sur 2 mois (échéance 2026-10-04)
- [ ] **Mohamed** : Prendre ownership de deux mini-projets correspondant à ses compétences
- [ ] **Wassim** : Continuer le développement de SDR AI
- [ ] **Naïma** : Travailler sur Webby Pilot (outil de gestion de projet)
- [ ] **Myriam** : Traiter les tâches en attente de feedback Raphaël et les demandes Céline/Océane

**Risques & vigilances**
- Les analyses de SuperSales semblent corrompues ou inexactes, compromettant la fiabilité des analytics commerciales
- Feedback tardif ou superficiel de certains stakeholders (notamment Cédric) bloque les développeurs pendant plusieurs jours
- Faible adoption de Super Joe : aucun membre ne consulte régulièrement les dashboards ou rapports hebdomadaires
- Risque de doublons et licences gaspillées avec plusieurs outils payants utilisés de façon incohérente (Ager vs SuperSales)
- Absence de boucle de feedback vers Sofian depuis qu'il n'est plus impliqué activement sur SuperSales
- Qualité très variable des briefs selon les profils, créant une qualité inégale des demandes

**Projets liés** : [[Pôle Tech & Ops interne — structuration]]

Tags : #ia #développement #coaching #feedback #audit-commercial #super-sales #standardisation
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 04/08/2026 15:37 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a revu les priorités de développement, les lancements V1, les boucles de feedback et plusieurs sujets d’outillage/ops. Un point critique a été soulevé sur la qualité des analyses de SuperSales dans le cadre de l’audit commercial d’Alchemy, avec demande d’accès aux enregistrements Clap afin de vérifier les appels. L’équipe a également discuté de Super Joe, de la qualité des briefs de projet, de la mise en place d’un agent Slack et d’un template standardisé pour les demandes, puis a validé une orientation de coaching plus opérationnelle, ciblée sur les exécutants, ainsi qu’un transfert progressif de propriété sur des mini-projets. Décisions clés : limiter les développeurs à trois projets parallèles maximum, fournir à Alchemy un accès contrôlé aux enregistrements d’appels pour l’audit, et standardiser les briefs projets pour réduire l’ambiguïté des demandes.

📋 Outline

1. Retour de l’équipe, focus et priorités de développement • 0:00:19

- L’équipe est revenue de déplacement et se recentre sur le travail cette semaine ; les membres de retour sont attendus très concentrés. (Responsables : Boris / Anisse).
- Chaque développeur devra travailler sur un maximum de trois projets en parallèle afin de préserver la concentration. (Responsables : Anisse / leads dev).
- Les développeurs doivent consacrer environ 15 à 20 % de leur temps aux corrections de bugs et aux petites améliorations sur d’autres applications. (Responsables : Anisse / devs).
- Priorités de la semaine : Wassim sur SDR AI, Naïma sur Webby Pilot (outil de gestion de projet pour Webby), Myriam sur les tâches en attente du feedback de Raphaël et sur les demandes de Céline / Océane. (Responsables : Wassim, Naïma, Myriam).

2. Processus de feedback et problèmes de réactivité des parties prenantes • 0:01:52

- Le feedback tardif ou trop superficiel de certaines parties prenantes, notamment Cédric, bloque les développeurs qui attendent parfois plusieurs jours des clarifications. (Risque : ralentissement des livraisons ; responsable : Cédric doit améliorer sa réactivité).
- Exemple : le V1 marketing de Launchpad était terminé en juin, mais un feedback vraiment utile n’est arrivé que la semaine dernière, et il montrait surtout une mauvaise utilisation du produit plutôt qu’un défaut produit. (Impact : temps perdu ; responsable : Naïma pour le suivi).
- Raphaël est cité comme exemple positif : son feedback est rapide et utile ; son fonctionnement, notamment avec des enregistrements Loom, doit servir de modèle. (Responsables : Raphaël / Anisse pour diffuser les bonnes pratiques).
- Consigne équipe : une fois un travail terminé, produire systématiquement une vidéo Loom de présentation pour accélérer la compréhension et le retour des parties prenantes. (Responsables : tous les développeurs).

3. Statut des projets : Market Pilot, Webiboard et recouvrement • 0:04:37

- Market Pilot V1 a été lancé la semaine dernière et une démonstration Loom a été partagée aux parties prenantes. (Statut : lancé ; responsables : Raphaël / Myriam).
- Les tâches liées à Webiboard / à l’outil de gestion de projet pour Webby restent prioritaires pour Naïma, y compris les sujets liés à l’IA. (Statut : en cours ; responsable : Naïma).
- Sur le recouvrement, Jordan a fourni un retour très détaillé et de grande qualité, de type masterclass, sur les types d’appels et la manière de les évaluer, ce qui aide à mieux déployer les améliorations du process. (Impact : clarification des cas d’usage ; responsables : Jordan / équipe recouvrement).
- Océane et Céline ont demandé de nouvelles intégrations et ont fourni des spécifications claires, ce qui permet de démarrer le développement. (Responsables : Céline, Océane, Myriam).

4. Sources des enregistrements d’appels et inquiétudes sur la précision de SuperSales • 0:07:18

- L’audit Alchemy de la fonction commerciale a mis en évidence un problème majeur : les analyses de SuperSales semblent corrompues ou inexactes, ce qui nuit à la fiabilité des insights. (Risque : analytics commerciales non fiables ; responsables : auditeurs Alchemy).
- Tous les enregistrements bruts des appels existent sur Clap, qui contient 100 % des appels ; il n’y a donc pas de perte totale de données, mais il peut y avoir eu une mauvaise exploitation ou catégorisation. (Clarification : pas de perte de données ; responsables : Anisse / Boris pour vérification des logs).
- SuperSales est une couche d’analyse au-dessus de Clap ; les inexactitudes pourraient venir d’un manque de boucle de feedback vers Sofian, l’expert externe dev/ML, depuis qu’il n’est plus impliqué activement. (Cause probable : absence de boucle de retour ; responsables : les owners produit doivent collecter et remonter les problèmes de précision).
- Il existe aussi un risque de doublons et d’inefficacité avec plusieurs outils payants et utilisés de façon incohérente, par exemple Ager vs SuperSales. (Risque coût : licences gaspillées ; responsables : ops / direction commerciale pour consolidation).

5. Accès d’Alchemy aux enregistrements pour l’audit • 0:14:35

- Alchemy a demandé un accès aux enregistrements d’appels Clap afin de finaliser l’audit commercial et d’examiner l’historique des appels ainsi que les enregistrements. (Demande : accès en lecture seule préféré ; responsable : Alchemy / Boris pour l’octroi).
- Boris évaluera et créera un rôle d’accès approprié (owner/admin/member) pour permettre à Alchemy de consulter les données sans exposer des permissions inutiles. (Action : configurer un compte à accès limité ; responsable : Boris).
- L’organisation Clap actuelle stocke les enregistrements par utilisateur et les classe mal, ce qui rend le tri chronophage ; une meilleure catégorisation ou des partages de dossiers ciblés seront nécessaires pour l’audit. (Action : préparer des dossiers ciblés ou des exports filtrés ; responsables : Anisse / Boris / admin Clap).
- Décision suivante : donner à Alchemy un accès de consultation à Clap avec choix prudent du rôle et partager des indications sur les dossiers / étiquettes à inspecter. (Responsable : Boris pour l’implémentation ; Anisse pour préparer la liste des dossiers pertinents).

6. Super Joe : usage actuel, fonctionnalités et besoin de démonstration • 0:15:35

- Les logs de Super Joe montrent que les appels sont « analysés » puis qu’un texte de coaching est généré dans la minute qui suit, ce qui explique le workflow automatisé actuel. (Anisse).
- Le coaching produit est aujourd’hui un feedback textuel envoyé à l’utilisateur ayant passé l’appel ; l’usage observé ne va pas au-delà de cette génération. (Anisse).
- Aucun membre de l’équipe ne se connecte régulièrement à Super Joe pour consulter ses rapports hebdomadaires ou ses dashboards, ce qui indique une faible adoption. (Anisse).
- Super Joe propose un tableau de bord avec scores d’équipe, recommandations hebdomadaires, liste d’appels recherchable et une section ressources pour les supports commerciaux comme les listes d’objections. (Anisse).
- Super Joe s’intègre aussi à Slack pour envoyer des messages de fin d’appel, quotidiens ou hebdomadaires ; cette semaine, les messages de fin de journée seront modifiés pour provenir de Super Joe et non du canal global Aziz. (Anisse).
- Wassim a principalement construit les fonctionnalités Super Joe, et Anisse créera une démonstration Loom pour expliquer le fonctionnement aux équipes Alchemy afin d’améliorer l’adoption. (Anisse / Wassim).

7. Comptes utilisateurs, invitations en attente et suivi des accès • 0:18:59

- Le registre actuel indique 72 utilisateurs actifs et deux invitations en attente pour les closers Shamsdeen et Nawal. (Anisse).
- Un compte a été désactivé, celui de Clémentine Baptiste, ce qui explique l’écart observé précédemment dans les comptes. (Anisse).
- Boris surveillera l’évolution du nombre d’utilisateurs actifs après les changements de canaux et de contrôles d’accès. (Boris).

8. Notifications de fin de semaine et préoccupations sur l’accès • 0:21:11

- Certains utilisateurs, par exemple Alec, ont indiqué ne pas recevoir les messages de fin de semaine car ils n’étaient pas sur la liste de diffusion ; il faut donc vérifier et mettre à jour les destinataires. (Anisse).
- Boris ajoutera Alec pour tester le flux de fin de semaine et confirmer la bonne distribution. (Boris).
- Une prudence particulière est exprimée avant de donner l’accès à certains utilisateurs ayant déjà mal utilisé ou dénigré des outils ; l’accès pourra être accordé par étapes. (Anisse).

9. Retour sur l’outil OKR, expérience avec Michael et approche d’onboarding • 0:22:03

- Boris a eu une courte session productive avec Michael, durant laquelle des OKR pertinents et des KRs clairs ont été définis rapidement, avec seulement quelques clarifications mineures nécessaires. (Boris).
- L’ancien système Marcus imposait des OKR/KR très spécifiques et poussait vers des résultats mesurables et propres à l’équipe, ce qui a influencé la préparation initiale des objectifs. (Anisse).
- L’équipe convient d’adopter au départ une approche d’onboarding plus souple pour les OKR, afin de ne pas submerger les utilisateurs, puis de renforcer progressivement la rigueur de l’outil selon l’usage. (Boris / Anisse).
- Michael prend en charge les prompts saisis au clavier et les commandes vocales, ce qui réduit la barrière à l’entrée pour les utilisateurs qui préfèrent parler plutôt que taper. (Boris).

10. Intégration IA personnelle de Boris (« Jarvis ») • 0:25:37

- Boris teste un assistant personnel contrôlé à la voix (« Jarvis BIS ») relié à son second cerveau, à son système de gestion de projet, à ses e-mails, à Slack et bientôt à WhatsApp, pour centraliser et faire ressortir les actions du matin. (Boris).
- Le système synchronise Speakment à 07h15 chaque matin afin de rafraîchir le second cerveau avec les tâches, blocages et alertes d’éléments en retard. (Boris).
- Boris affine un flux permettant de filtrer automatiquement quelles données d’appels issues d’Assembly doivent être stockées dans le second cerveau, afin d’éviter les éléments temporaires ou non pertinents. (Boris).

11. Template standardisé de brief projet pour les demandes de développement • 0:29:33

- Boris propose un template unique de brief projet que les responsables rempliront pour tout nouveau projet, en précisant les objectifs, les fonctionnalités requises en V1, les fonctionnalités optionnelles V2/V3 et les résultats mesurables, afin de réduire l’ambiguïté des demandes. (Boris).
- Un document standard ainsi qu’un prompt recommandé pour Claude (ou un autre outil IA) devraient être fournis afin que les demandeurs puissent soumettre une description orale ou écrite, puis recevoir un template complété à transmettre à l’équipe dev. (Boris).
- Anisse a commencé à créer la tâche pour construire ce template et a suggéré de l’assigner à Naïma pour l’implémentation dans l’outil de roadmap / gestion. (Anisse / Naïma).
- Quentin note que les roadmaps mono-plateforme et les propositions mensuelles de fonctionnalités sont en cours, et que des briefs plus clairs aideront à aligner la roadmap avec la capacité de développement. (Quentin).

12. Agent Slack et workflow documentaire pour les demandes managers • 0:33:00

- L’équipe va créer un agent Slack accessible uniquement aux managers pour collecter les demandes liées aux fixtures, fonctionnalités, usages et user stories avant de générer un résumé pour l’équipe produit ; responsables : produit / engineering et managers.
- Les managers continueront à tenir et faire évoluer un Google Doc central pour les demandes et les pièces jointes, comme de petites images, que le flux via agent Slack ne gère pas forcément ; responsables : managers (propriétaires du document).
- Cette approche est un prototype visant à conserver une architecture cohérente et à évaluer si elle réduit l’ambiguïté des retours et le nombre d’itérations ; responsables : Boris et les leads produit.

13. Variabilité de la qualité des briefs et causes observées • 0:34:03

- La qualité des briefs et des retours dépend fortement du rôle, de la personnalité et des habitudes de chacun, ce qui crée une qualité inégale des demandes dans l’équipe ; responsables : tous les managers et heads doivent surveiller ce point.
- Certains membres, par exemple Jordan, produisent des briefs très détaillés grâce à leur rigueur et à un mélange d’habitudes administratives et design ; responsable : Jordan comme exemple.
- D’autres profils, par exemple Aziz et Cédric, ont tendance à travailler plus de manière pratique et à réutiliser des supports existants plutôt qu’à produire des documents denses et très précis ; responsables : Aziz et Cédric comme exemples de profils.

14. Améliorations opérationnelles d’Anisse et tests d’applications • 0:35:34

- Anisse intégrera des tests pratiques et la remise en question des applications pendant et après le développement afin d’améliorer la qualité produit avant les mises en production ; responsable : Anisse.
- Ces tests seront formalisés dans le processus pour que les applications reçoivent un retour utilisateur concret avant les déploiements ; responsables : propriétaire du process produit et Anisse.
- Anisse indique avoir davantage de bande passante et d’énergie grâce à la réduction du nombre de réunions, ce qui lui permet de prendre ces responsabilités supplémentaires. (Responsable : Anisse).

15. Programme de coaching : cible et justification • 0:36:56

- Anisse prévoit un programme de coaching continu de deux mois, en août-septembre, afin de maximiser l’impact sur les priorités en cours ; responsable : Anisse.
- Le coaching ciblera les employés au niveau de l’exécution qui réalisent directement les tâches (par exemple Wassim, Naima, Adil, Mohamed), car améliorer leur performance apporte un meilleur retour opérationnel que de se concentrer uniquement sur les heads ; responsables : Anisse avec l’aval de Boris.
- Le coaching est présenté comme une démarche de conseil orientée résolution de problèmes plutôt qu’un travail uniquement sur le mindset, afin de produire des améliorations concrètes dans l’exécution quotidienne ; responsable : Anisse.

16. Décentralisation de la propriété et approche pilote • 0:39:35

- L’objectif de leadership est de décentraliser la propriété des projets en confiant de petits projets concrets à des non-heads disposant des compétences pour exécuter, afin de réduire la charge mentale des heads ; responsable : Boris pour la stratégie, avec Anisse pour l’exécution.
- Exemple : Mohamed recevra la responsabilité de deux projets correspondant à ses compétences, même s’il n’a pas encore été owner auparavant ; responsable : Mohamed, sous supervision de Boris et Anisse.
- L’entreprise pilotera la prise de propriété sur des mini-projets, et non sur de grands programmes multi-personnes, pour évaluer la manière dont les individus gèrent la responsabilité et la livraison ; responsables : les heads pour identifier les mini-projets adaptés et Anisse pour coacher les participants.

17. Communication directe avec les exécutants et reconnaissance des livraisons • 0:42:39

- Le processus permettra d’interagir directement entre décideurs et exécutants, par exemple pour contacter directement la personne en charge d’un sujet Zendesk, plutôt que de passer par plusieurs niveaux de heads ; responsables : décideurs et exécutants.
- Les livraisons réussies de projets portés par une seule personne seront reconnues publiquement en réunion d’équipe afin de mettre en valeur la contribution à l’exécution ; responsables : Boris et les animateurs de réunion.
- Le sujet Trustpilot a été évoqué comme exemple où la propriété pourrait être confiée à une personne de niveau CSM plutôt qu’à un head, afin de mieux exploiter la proximité avec les clients au quotidien ; propriétaire proposé : un CSM (pas Sabrina), avec supervision possible de Sabrina si nécessaire.

18. Déploiement du coaching et périmètre opérationnel • 0:48:01

- Anisse identifiera de manière proactive 15 à 20 personnes dans les différentes équipes pour le coaching et organisera trois sessions par personne sur deux mois ; responsable : Anisse pour la planification et l’animation.
- Chaque parcours de coaching commencera par une session diagnostique afin de définir un objectif précis et d’identifier les écarts de mindset, de compétences ou de stratégie à traiter ; responsables : Anisse et la personne coachée.
- Les premiers exemples informels de coaching avec Adil, Raphaël et Océane ont validé l’approche et serviront à structurer le programme ; responsables : Anisse pour la synthèse des apprentissages et le reporting à Boris.
%% notes:fin %%
