---
type: call
date: 2026-09-23
source: sembly
participants: ["boris@entrepreneurs.com", "raphael.dalleau@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Raphaël X Boris - Marketing Ops

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (23/09/2026 14:40).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 23/09/2026 14:40 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

Boris et l’équipe ont passé en revue la version mise à jour du dashboard ainsi que plusieurs problèmes de qualité de données. Ils se sont accordés sur des améliorations du classement des publicités, des correctifs de tracking, et une granularité plus fine des métriques de funnel afin de permettre des décisions fiables. Les actions prioritaires incluent la finalisation d’une maquette visuelle, la définition d’un algorithme de scoring des annonces, la correction des écarts de tracking, ainsi que l’ajout de formations pour les SDR/closers et de responsables par point de blocage du funnel. Ils ont également relevé des problèmes de calcul du ROAS et des incohérences sur la métrique de no-show, à résoudre avant de déployer des systèmes de décision automatisés.

📋 Outline

1. Mise à jour du dashboard et structure visuelle • 0:00:25

- Boris a produit une nouvelle version du dashboard, en cours de mise à jour pour afficher le book funnel avec des découpages plus visuels des appels, présences, annulations et revenus ; responsable : Boris.
- Le dashboard affichera le revenu par statut d’appel (réservé, non annulé, réellement effectué) et comparera les paiements upfront du book avec les revenus générés après-coup ; responsable : Boris.
- Le dashboard inclura le suivi commercial par closer ainsi qu’un rythme quotidien du revenu pour l’activité book et call ; responsable : Boris.
- Boris demande à Alec une maquette simple montrant la structure de la page et les publicités classées, afin que l’interface finale corresponde aux besoins utilisateurs et améliore l’usage au quotidien ; responsables : Alec et Boris.

2. Classement des publicités et algorithme de scoring • 0:03:24

- L’équipe a discuté l’ajout d’une vue plein écran dédiée au classement des publicités, avec des métriques par annonce incluant transcripts, créatifs, hooks, CTR et performance, ainsi que la possibilité d’inspecter chaque ad en détail ; responsables : Boris et Alec.
- Ils ont proposé un score de ranking flexible, combinant différentes métriques (par exemple, appels bookés × CPA pour le funnel book), avec la possibilité pour les utilisateurs de choisir les pondérations ; responsable : Boris pour rédiger la formule, Alec pour la revoir.
- Boris a suggéré un scoring par tranches de métriques (par exemple, buckets de CTR ou de CPA) afin que les annonces gagnent des points selon des paliers de performance, avec des seuils supérieurs pouvant déclencher des coupes ; responsable : Boris pour définir le barème et les plages.
- L’équipe a convenu d’identifier les annonces qui génèrent déjà des ventes mais ne sont pas encore considérées comme ‘winning’, afin de les mettre en avant comme opportunités à potentiel ; responsables : Boris et l’équipe Ads.

3. Écarts de données, problèmes de tracking et bugs • 0:06:52

- Boris a identifié un bug où une clôture de Walid Melal apparaît dans la vue 30 jours mais pas dans la vue all-time ; il va approfondir l’investigation ; responsable : Boris.
- Plusieurs leads et ventes n’ont pas été trackés car les SDR utilisaient des liens sans paramètres de tracking, et Boris ajoutera les ventes manquantes du funnel book dès réception des bonnes informations ; responsables : Alex (SDR) pour fournir les détails de tracking, Boris pour mettre à jour le dashboard.
- De nombreux leads non tracés suggèrent des lacunes dans l’attribution UTM et d’origine, qu’il faut corriger pour améliorer le reporting des sources ; responsables : Boris et l’équipe Marketing/Ads.
- L’équipe ajoutera une page dédiée aux ads et envisagera de dupliquer certaines vues afin de faire ressortir les annonces à potentiel, même si elles ne sont pas encore parmi les meilleures performances ; responsables : Boris et l’équipe Ads.

4. Totaux de ventes et problèmes de calcul du ROAS • 0:09:14

- Boris a indiqué que l’ajout des ventes manquantes ferait passer le revenu total du book d’environ 67 k à environ 100–120 k, ce qui élargit aussi les estimations de rentabilité ; responsable : Boris.
- Le ROAS affiché actuellement (3,46) est trompeur, car l’allocation de la dépense marketing est masquée par l’absorption des ventes book dans les comptes ; responsables : Boris et Finance/Analytics.
- L’équipe a reconnu la difficulté de trouver une formule de ROAS mathématiquement cohérente pour des flux de revenus mixtes / instantanés, et a convenu de ne pas trop s’appuyer sur le ROAS pour les décisions opérationnelles ; responsables : Boris et l’équipe Data.
- Boris a proposé de suivre des objectifs comme le revenu par appel et les pourcentages d’upsell plutôt que le ROAS seul, afin de mieux refléter la croissance evergreen et la rentabilité ; responsables : Boris et Alec.

5. Définition du no-show et préoccupations sur la conversion du funnel • 0:13:19

- La métrique de no-show provient actuellement des closers qui marquent les leads comme ‘closed lost’ et ‘no-show’, ce qui crée des incohérences entre les funnels ; responsables : équipe Closers et Boris pour standardiser.
- Le book funnel montre environ 65,8 % de présence (34,2 % de no-show), tandis que le quiz funnel est à environ 70 % de présence (30 % de no-show), ce qui met en évidence des variations selon les funnels ; responsable : Boris.
- Des incohérences dans le reporting des closers et dans les données source font varier les taux de no-show déclarés par rapport à d’autres calculs d’équipe (Thomas Boblin voit environ 48 % dans Looker) ; responsables : Thomas Boblin et Boris pour réconcilier les méthodes.
- Si le volume de trafic warm est plus faible que supposé, le taux de conversion après présence pourrait être mauvais, ce qui déplacerait l’identification du problème plus en amont dans le funnel et nécessiterait des corrections ciblées upstream ; responsables : Boris et Marketing.

6. Fiabilité des données, vue macro et systèmes de décision • 0:17:16

- Boris a insisté sur la nécessité d’une vue macro fiable pour permettre la mise en place de règles de décision et d’alertes en temps réel, au lieu d’opérer sur des micro-vues incohérentes ; responsables : Boris et l’équipe Data.
- Le groupe a discuté d’une future intégration avec des modèles d’IA orientés décision (sorties basées sur des probabilités) afin d’automatiser des recommandations actionnables une fois la granularité et la fiabilité des données résolues ; responsables : Boris et l’équipe Data/ML.
- Les données actuelles n’atteignent pas encore le niveau souhaité par Boris pour une prise de décision automatisée, et il a demandé une visibilité plus granulaire du funnel ainsi que des métriques standardisées avant de déployer des systèmes pilotés par l’IA ; responsables : Boris et Alec.

7. Mises à jour SDR, ajout de closers et formation • 0:19:40

- Boris a limité le calendrier Evergreen à trois closers actuels dans le dashboard et a noté que Walid et Martin devront être ajoutés plus tard, après formation ; responsables : Boris et Julien pour coordonner les ajouts.
- L’équipe a convenu d’exiger que Walid et Martin regardent le replay de la formation récente de Lucas avant d’être ajoutés aux calendriers de production, afin d’assurer une application cohérente du process ; responsables : Lucas pour fournir le replay, Boris/Julien pour faire respecter la règle.
- Boris ajoutera les deux nouveaux closers à la liste des agents après qu’ils auront complété les étapes de formation requises ; responsable : Boris.
- Raphael et Alex ont soulevé des préoccupations d’alignement culturel et d’équipe concernant l’ajout de membres sans concertation, et l’équipe a décidé que le monitoring révélera rapidement d’éventuels problèmes ; responsables : Boris et la direction.

8. Visualisation du funnel, analyse des goulots d’étranglement et ownership • 0:22:01

- Boris a demandé un graphique de funnel élargi, de type Lucidchart, montrant chaque étape, les pourcentages de drop-off et les données par segment afin d’identifier précisément les goulots d’étranglement ; responsable : Alec pour concevoir la visualisation étendue.
- La visualisation doit relier chaque goulot d’étranglement à un owner nommé (par exemple Alex pour les problèmes SDR, Raphael pour le marketing), afin que la remédiation soit claire et imputable ; responsable : Alec pour intégrer la cartographie des owners, Boris pour valider.
- L’objectif est de permettre un triage rapide depuis le dashboard macro vers des micro-vues ciblées pour les actions correctives et l’attribution des corrections ; responsables : Boris et l’équipe Data.
%% notes:fin %%
