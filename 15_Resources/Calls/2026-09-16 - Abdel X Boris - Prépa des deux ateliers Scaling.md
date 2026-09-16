---
type: call
date: 2026-09-16
source: sembly
participants: ["abderrahim@entrepreneurs.com", "boris@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Abdel X Boris - Prépa des deux ateliers Scaling 

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (16/09/2026 11:27).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 16/09/2026 11:27 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

La réunion a porté sur la préparation des supports d’atelier pour Alec et sur la formalisation, à destination de clients, de deux axes complémentaires : d’une part la structuration opérationnelle et data mise en place chez entrepreneurs.com par Boris, et d’autre part la présentation d’un process de recrutement automatisé avec ICO/Aïko. Les échanges ont couvert les coûts évités grâce à la consolidation des outils et à l’amélioration des intégrations, la refonte de l’architecture dashboards/data, la logique de mesure des KPI et de pilotage temps réel, ainsi que la décomposition du workflow de recrutement (sourcing, tri CV, entretiens IA, scoring, gestion des candidats). Les décisions clés incluent la production d’un fil conducteur, de captures d’écran anonymisées de dashboards et d’écrans clés, d’un prompt réutilisable pour créer un cockpit KPI, et de templates de scorecard/process de recrutement à transmettre à ICO. Les responsabilités ont été réparties entre Boris, Abderrahim, et les parties prenantes concernées pour finaliser les supports et validations.

📋 Outline

1. Accueil, objectif de la réunion et cadrage du workshop • 0:00:02

- Abderrahim a ouvert la réunion, a pris des nouvelles des participants et a rappelé la nécessité d’être efficaces sur cette session de 47 minutes.
- L’objectif annoncé était de préparer les ressources nécessaires pour l’atelier d’Alec sur le scaling / l’immersion, avec l’appui indispensable de Boris pour documenter la réalité opérationnelle.

2. Dépendances du workshop et livrables attendus • 0:00:53

- Abderrahim a expliqué qu’il devait produire des supports pour Alec, faute de temps de ce dernier, et que ces contenus dépendaient directement de la connaissance opérationnelle de Boris.
- Il a demandé un fil conducteur détaillé ainsi que deux processus à intégrer dans les matériaux de l’atelier.
- Il a également demandé des captures d’écran anonymisées d’outils et de tableaux de bord pour illustrer des problèmes réels, les corrections apportées et la logique de pilotage.

3. Disponibilité pour l’immersion et organisation de la présence • 0:01:45

- Boris a précisé qu’il n’était pas certain d’assister à toute l’immersion ; à ce stade, il était surtout prévu sur la réunion du noyau dur et pouvait ajuster son déplacement si nécessaire.
- Abderrahim a indiqué que d’autres membres de l’équipe, notamment Raph et Cédric, couvriraient les activités du jour 2, ce qui réduisait la nécessité d’une présence physique de Boris sur cette journée.

4. Introduction du workshop : coût de l’absence de mesure • 0:02:18

- Abderrahim a proposé que l’introduction de l’atelier mette en avant le coût financier et opérationnel du fait de ne pas mesurer la donnée ni auditer régulièrement les dépenses.
- Il a demandé à Boris de fournir des exemples concrets, par exemple l’alerte Slack sur les licences inutilisées, ainsi que d’autres preuves issues d’entrepreneurs.com illustrant les conséquences d’un mauvais suivi.

5. Diagnostic opérationnel initial et complexité des outils • 0:03:53

- Boris a décrit un système initial trop complexe, avec trop d’outils, trop d’étapes et trop de friction, ce qui entraînait des pertes d’information et des dépenses inutiles.
- Il a cité plusieurs cas de doublons ou d’outils superflus : paiement de Calendly alors que d’autres licences gratuites existaient, usage simultané de Cal.com et iClosed, ou encore recours à Tally lorsque cela ajoutait de la friction.
- Il a insisté sur le fait que la friction dans le tunnel réduisait la conversion et augmentait les coûts d’automatisation.

6. Économies réalisées grâce à la consolidation des outils • 0:06:08

- Boris a indiqué que l’usage de Make (Integromat) était passé d’environ 2 millions de tokens par mois, soit environ 1 800 dollars, à un plan à 300 dollars.
- Il a estimé cette évolution à environ 1 500 dollars d’économie mensuelle, soit près de 18 000 dollars par an.
- Il a expliqué qu’en remplaçant certaines automatisations tierces par des intégrations natives, l’équipe avait supprimé de nombreux intermédiaires et réduit les coûts récurrents d’intégration.

7. Optimisation RH et stratégie de recrutement • 0:08:20

- Boris a expliqué avoir fortement réduit les coûts humains en s’appuyant sur des équipes internationales moins coûteuses et en optimisant les rôles, avec selon lui une réduction d’environ huit fois des coûts opérationnels liés aux personnes.
- Il a reconnu l’existence de coûts initiaux et d’erreurs de configuration antérieures, notamment sur le développement de dashboards et sur certaines décisions prises sans données fiables.
- Abderrahim a demandé des précisions sur la méthode de recrutement — recherche LinkedIn, critères de sélection et déroulé du process — pour l’intégrer dans la seconde partie de l’atelier dédiée au recrutement assisté par IA.

8. Stratégie dashboards et migration de plateforme • 0:10:37

- Boris a décrit une migration de Looker vers une stack plus flexible, avec notamment Vercel comme exemple, afin de permettre des visuels plus riches et l’intégration d’agents IA dans les tableaux de bord.
- Il a précisé que le coût de développement des dashboards était auparavant d’environ 60 000 euros par an pour une ressource dédiée, contre environ 12 000 euros par an dans la configuration actuelle.
- Il a souligné la mutualisation des appels et le choix d’un outil adapté aux compétences de l’équipe, plutôt que de supposer qu’une architecture de data engineering haut de gamme était nécessaire.

9. Amélioration des sources de données et des fréquences de rafraîchissement • 0:12:27

- Boris a expliqué que la connexion directe aux API sources, par exemple Meta Ads et les jetons Google, avait fait passer les rafraîchissements d’environ 24 heures à environ 1 heure.
- Il a précisé que ce changement avait réduit la latence de décision d’un facteur 24 et supprimé des couches intermédiaires comme Stitch, qui provoquaient des pertes ou des retards de données.
- Il a insisté sur le fait que des données fiables nécessitent une connexion à la source d’origine où la métrique est créée, notamment pour la publicité, les ventes et la finance.

10. Approche data centrée sur les funnels plutôt qu’une logique macro d’abord • 0:14:18

- Boris a opposé l’ancienne approche Looker, partant du macro vers le micro, à sa stratégie bottom-up qui démarre par les besoins de chaque équipe en matière de funnel, puis construit le dashboard entreprise à partir de ces vues locales.
- Il a soutenu que cette approche augmente l’adoption des dashboards par les équipes, car chaque tableau est conçu selon leurs usages et reste plus compréhensible.
- Il a conclu qu’un dashboard central de direction n’est fiable que si les dashboards de niveau funnel sont eux-mêmes exacts et utilisables par chaque équipe.

11. Exercice workbook / cockpit KPI pour la prise de décision • 0:15:39

- L’équipe a convenu que les clients rempliront manuellement un workbook avec les métriques immédiatement disponibles afin d’ancrer la prise de décision pendant la session.
- Les KPI critiques proposés pour l’exercice incluent les coûts humains, les coûts outils, le spend publicitaire total, les coûts des équipes internes et un tableau de situation in/out de l’entreprise.
- Le résultat attendu du workbook est de faire apparaître les marges opérationnelles et de prioriser les données à centraliser dans un futur outil.
- Abderrahim et Jordan sont associés à la définition du résultat final du workbook.

12. Métrique centrale : productivité du système et théorie des contraintes • 0:16:50

- Boris a présenté une métrique centrale, décrite comme le flux ou le output restant après annulations, inversions et livraison, plus pertinente selon lui que le revenu brut.
- L’équipe a reconnu que la recherche d’optimisations locales — par exemple pousser chaque rôle à 100 % de capacité — crée des goulots d’étranglement et des stocks cachés, ce qui réduit la productivité globale du système.
- Les participants ont retenu l’idée d’appliquer les principes de la théorie des contraintes pour éviter la constitution de stock, notamment de leads surbookés, et optimiser le flux de bout en bout.
- Le livre The Goal a été recommandé comme ressource de référence sur les contraintes et l’optimisation système.

13. Approche de conception du dashboard et prompts d’artifact • 0:21:26

- Boris a recommandé de commencer par la création d’un artefact visuel : définir les métriques, la logique de funnel et le style de visualisation avant l’implémentation technique.
- L’équipe a prévu de fournir un prompt réutilisable permettant aux clients de générer un premier artefact et de le transmettre ensuite à leurs développeurs ou de le construire eux-mêmes.
- Les livrables envisagés comprennent deux ou trois captures d’écran d’un dashboard anonymisé ainsi qu’un modèle de prompt permettant de reproduire l’artefact.

14. Alertes temps réel et suivi marketing au niveau des ads • 0:23:34

- La fonctionnalité de niveau supérieur discutée concerne des alertes automatisées signalant les écarts de KPI, par exemple un taux de closing sous l’objectif, avec renvoi direct vers la zone du dashboard à analyser.
- L’objectif est d’atteindre des cycles de décision quasi temps réel, en réduisant le délai entre la donnée et l’action de plusieurs jours à quelques minutes.
- Le dashboard peut également exposer la performance au niveau des publicités via API, notamment Meta, en suivant les opt-ins, les calls bookés et les ventes par ad afin de mesurer précisément le ROI des canaux.

15. Principal poste de coûts évitable : les dépenses humaines et les choix de recrutement • 0:26:36

- Boris a souligné que les mauvaises décisions d’embauche, en particulier le fait de surpayer des talents tech locaux alors que des profils distants sont disponibles, constituent une source majeure de dépenses inutiles.
- Il a recommandé d’élargir l’horizon de recrutement, tout en exigeant un niveau d’anglais de base, pour réduire les coûts et améliorer l’adéquation sur les rôles techniques.

16. Processus de recrutement, templates IA et transmission à ICO • 0:27:06

- L’équipe a prévu de présenter un process de recrutement durant un atelier en s’appuyant sur la plateforme Aiko/ICO et sur un assistant IA pour rédiger les premières définitions de poste.
- Boris peut partager un modèle PDF et un prompt qui génèrent un brief de poste, une scorecard, les objectifs, le niveau de séniorité, les responsabilités, les critères de performance, la stratégie d’évaluation et des exemples de référence.
- Le document initial généré par l’IA servira de base à un mandat formel à remettre à ICO pour la recherche de candidats et l’ensemble du workflow de recrutement.

17. Fiches de poste générées par IA et normalisation des intitulés • 0:30:50

- Boris a expliqué que les intitulés de poste peuvent être générés et standardisés, avec des exemples comme Integrator Market, Integrator Sales ou Integrator Hotspot.
- Il a indiqué qu’une fois le document de poste généré, celui-ci peut être intégré au système afin d’indiquer à l’IA de “faire le job” en fonction des compétences définies.
- Il a donné l’exemple d’un Customer Success Manager dont le brief peut remplir automatiquement les champs du rôle via l’IA.

18. Rémunération, cadrage du rôle et pré-paramétrage des personas IA • 0:31:28

- Le brief doit inclure la rémunération, la charge de travail (temps plein / temps partiel), la date de démarrage cible, l’objectif, le niveau de séniorité, le poste, les responsabilités, les KPI, l’équipe et la stratégie afin de pré-cadrer l’IA.
- Ce pré-cadrage permet à ICO d’exposer quatre “personnalités” IA capables de gérer les différents volets du recrutement.

19. Les quatre agents IA et leurs fonctions • 0:31:28

- Le système expose quatre agents : le sourcer, qui récupère des profils similaires dans les bases ICO ; le reviewer, qui réalise le tri initial des CV ; l’interviewer, qui conduit les entretiens IA ; et le candidate manager, qui gère les communications et relances.
- Boris a précisé que le sourcer est moins utile dans leur niche spécifique, car la base ICO contient peu de profils réellement comparables.

20. Dépôt de CV et flux de tri par le reviewer • 0:32:32

- Les candidats déposent leur CV via le lien de candidature ICO/Aïko ; l’agent reviewer effectue un premier tri pour envoyer les profils soit vers l’entretien, soit vers un message de refus automatique.
- Les messages de refus sont automatisés et incluent des raisons ; les candidats retenus avancent vers l’étape d’évaluation / entretien.

21. Entretiens IA, scoring et enregistrements audio • 0:33:28

- Les candidats interviewés reçoivent un statut évalué avec un score fondé sur le CV, l’adéquation à l’entreprise et la performance pendant l’entretien IA.
- Les entretiens sont enregistrés en audio בלבד, avec par exemple un entretien de 51 minutes que l’on peut réécouter pour revue.

22. Compétences, niveau de langue et détection de fraude • 0:34:31

- Le système extrait et affiche les compétences candidates, par exemple Zendesk ou DataDriven, afin de les comparer aux exigences du poste.
- L’analyse linguistique affiche les niveaux de maîtrise, par exemple C1 en français et B2 en anglais, utile pour les rôles bilingues.
- Des mécanismes de détection de fraude signalent une éventuelle assistance par IA, des réponses scénarisées ou des anomalies de plusieurs interlocuteurs pendant l’entretien.

23. Lien de candidature et langues prises en charge • 0:35:35

- Lors de la création d’une offre sur ICO, la plateforme génère un lien de candidature à diffuser, par exemple sur LinkedIn.
- ICO prend actuellement en charge plusieurs langues, au moins cinq, et le lien peut spécifier la langue attendue chez les candidats.

24. Tarification et périmètre de délégation • 0:36:09

- Boris a estimé le coût du plan autour de 200 dollars pour accéder aux fonctionnalités discutées, en précisant que le prix exact restait à confirmer.
- La plateforme peut effectuer une préqualification très poussée, ne laissant qu’environ 5 % des profils pour les entretiens humains ; la décision finale de recrutement reste humaine.

25. Abandon en cours de processus et notes de feedback • 0:37:24

- Abderrahim a observé un taux d’abandon après le clic d’accès lorsque les candidats découvrent les étapes de qualification, ce qui constitue une donnée mesurable.
- Boris a estimé que cet abandon est souhaitable, car il élimine les candidats qui ne sont pas prêts à s’engager dans un processus piloté par IA.
- Les notes de feedback candidats remontées sur les entretiens sont élevées, par exemple 4 à 5 sur 5, et les communications automatisées sont historisées.

26. Types de contrats : salaire, freelance et contraintes régionales • 0:39:06

- L’approche est mixte : certains rôles sont salariés, de plus en plus pour les placements à Dubaï, tandis que d’autres restent en freelance / contrat selon les besoins de l’activité.
- Boris a expliqué qu’amener des contractors à Dubaï augmenterait fortement les coûts et n’est souvent pas faisable pour ses équipes.

27. Bénéfices de temps, de coût et de précision pour le recrutement • 0:40:27

- Boris a insisté sur le gain de temps majeur, car les équipes de recrutement n’ont plus à conduire un grand nombre d’entretiens initiaux et se concentrent sur les meilleurs candidats.
- L’outil réduit les coûts par rapport à des entretiens entièrement humains et améliore la précision grâce à une expertise de recrutement apportée par l’IA.
- Le système réduit le risque de mauvais recrutements grâce à une meilleure préqualification et à une meilleure évaluation, sans pour autant garantir à 100 % le succès du recrutement.

28. Détails des agents de la plateforme et rôle du candidate manager • 0:42:53

- Boris a rappelé les quatre sous-agents : sourcer, reviewer, interviewer et candidate manager, chacun intervenant sur une étape spécifique du pipeline.
- Le candidate manager gère les communications automatisées avec les candidats : invitations à entretien, notifications de refus et e-mails de statut.

29. Erreurs d’IA et cas limites observés • 0:43:35

- Boris a indiqué que les erreurs d’évaluation IA restent rares mais se sont déjà produites une ou deux fois avec des candidats qui interagissaient mal avec l’IA.
- Lors des écarts constatés, l’équipe a vérifié et a souvent conclu que le problème venait d’un manque d’adéquation du candidat avec la tech ou avec la culture d’entreprise plutôt que d’une défaillance de la plateforme.

30. Questions sur la stack technologique • 0:44:28

- Abderrahim a demandé si ICO/Aïko s’appuie sur OpenAI, Anthropic ou un modèle interne.
- Boris n’a pas confirmé et a suggéré qu’il pouvait s’agir d’un modèle propriétaire ; un suivi reste nécessaire sur ce point.

31. Livrables finaux, captures d’écran et prochaines validations • 0:45:59

- Abderrahim a demandé des captures d’écran des étapes clés d’onboarding et d’enregistrement, ainsi qu’une vue cockpit/dashboard avec des chiffres modifiés pour l’intégrer dans les slides.
- Boris a accepté de produire quatre captures des étapes les plus importantes et de partager les fichiers via Drive dès qu’ils seront prêts.
- Abderrahim doit ensuite relancer Alex, Anis et les autres parties prenantes pour collecter les éléments manquants et obtenir les validations nécessaires.
- Les deux parties ont convenu de rester alignées avec les contributions d’Anis afin d’éviter toute représentation inexacte de ses idées.
%% notes:fin %%
