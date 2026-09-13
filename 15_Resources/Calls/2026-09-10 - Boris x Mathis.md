---
type: call
date: 2026-09-10
source: sembly
participants: ["boris@entrepreneurs.com", "mathisfaivre.pro@gmail.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Boris x Mathis

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (10/09/2026 22:08).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 10/09/2026 22:08 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

La réunion a porté sur la réflexion stratégique de l’entreprise autour de son modèle opérationnel, de sa structure de données et de ses outils internes. Les participants ont comparé deux approches d’organisation commerciale et delivery — profils créatifs en première ligne versus chefs de projet en première ligne —, ont identifié les frictions entre sales, PM et créatifs, et ont convenu qu’un meilleur chaînage entre les données projet et le pipeline commercial est nécessaire pour automatiser la relance commerciale et éviter les pertes d’opportunités.

La discussion a aussi beaucoup porté sur les limites de Notion et des SaaS généralistes face aux besoins métiers spécifiques. Boris a défendu l’idée de construire un outil léger, propriétaire et brandé, potentiellement exécuté avec une équipe offshore, afin d’obtenir de meilleures vues, davantage d’automatisation, une meilleure sécurité et une structure de coûts plus saine. En parallèle, l’équipe a abordé la méthode de prototypage, la centralisation de l’historique client, l’automatisation de la détection de signaux commerciaux à partir des appels, ainsi que les règles de gouvernance des processus internes.

Enfin, la réunion a débouché sur plusieurs décisions opérationnelles : travailler sur une structure plus claire du type « companies > prestations > batches », prototyper rapidement un V1 à partir des données existantes, évaluer la construction d’un CRM/commercial intégré ou connecté, et préparer un cadrage fonctionnel complet avant de lancer un développement plus ambitieux. L’équipe a également discuté du recrutement offshore, des précautions de sécurité et des outils d’automatisation du recrutement.

📋 Outline

1. Objet de la réunion et manière d’aborder le sujet • 0:00:00

- L’objectif était de présenter la vision d’ensemble de Mathis et de faire émerger les vrais problèmes opérationnels pour aller chercher leurs causes profondes.
- Les échanges devaient s’appuyer sur les mots de Mathis et sur des exemples opérationnels réels, plutôt que sur des résumés externes ou une reformulation trop générique.

2. Structure Notion actuelle et limites opérationnelles • 0:04:25

- L’architecture actuelle dans Notion repose sur des bases de données pour les companies, contacts, opportunités, prestations et batches.
- L’objectif est de représenter correctement les multiples services simultanés d’un même client.
- Les prestations peuvent combiner plusieurs lignes de service : vidéos courtes, créas statiques, montage, etc.
- Le concept de batch sert à suivre les packs récurrents dans le temps.
- Notion reste utile pour les portails clients et son usage est connu de tous, mais il limite les vues personnalisables et les workflows opérationnels nécessaires à une automatisation fluide et à de vraies vues sales.
- Nathan a la responsabilité de retravailler le schéma de base de données afin de clarifier les handoffs, les briefs et les tâches par rôle à chaque étape.

3. Segmentation client et implications sur le pricing • 0:05:12

- Certains clients — notamment des e-commerçants à fort budget et des infopreneurs — exigent un volume créatif élevé et préfèrent parler directement aux créateurs.
- Cette réalité a influencé le basculement vers des profils créatifs plus en frontal.
- Les clients à plus faible budget nécessitent moins d’attention commerciale et de gestion de projet ; leur relance doit donc être davantage automatisée et proportionnée à leur valeur.
- Il faut mettre en place un scoring client pour répartir plus efficacement l’effort sales/PM.
- Pour les modèles qui nécessitent à la fois un créatif et un PM en frontal, un ajustement du prix ou de la durée d’engagement doit être envisagé.

4. Friction opérationnelle entre sales, PM et créatifs • 0:06:05

- Les transferts entre sales et PM sont irréguliers et s’appuient souvent sur des canaux informels comme WhatsApp, ce qui provoque des retards et des opportunités manquées.
- Les relances commerciales étaient auparavant gérées par les PM, mais cela s’est révélé moins efficace car leur rôle est perçu comme moins orienté vente que celui d’un commercial dédié.
- Le levier identifié consiste à automatiser les tâches de réengagement dans le pipeline commercial, afin que les bons déclencheurs créent automatiquement des tâches pour les sales, indépendamment du fait qu’un créatif ou un PM soit en frontal.
- Le CRM doit être fortement lié au board de gestion de projet pour que les tâches basculent automatiquement dans les bons pipelines commerciaux.

5. Proposition de plateforme custom plutôt que dépendance continue à Notion • 0:09:36

- Boris a proposé de ne pas lutter contre les limites de Notion et de développer à la place une application légère, brandée, avec des vues dédiées, des dashboards et des API adaptées aux besoins opérationnels.
- Les avantages attendus sont un contrôle total des vues, du branding et des portails clients, des coûts de licences plus faibles et une automatisation plus simple via webhooks et APIs.
- Le développement et la maintenance peuvent rester raisonnables via des services cloud et une petite équipe dev/ops.
- Une approche par étapes a été évoquée : commencer par un MVP qui reproduit les workflows Notion, exécuté par un assistant virtuel ou un prestataire offshore pour valider les flux avant de construire une vraie application.

6. Recours à des équipes offshore pour l’exécution et la maintenance • 0:11:30

- Boris a recommandé de s’appuyer sur des spécialistes offshore à temps plein, notamment en Inde ou au Pakistan, pour exécuter et faire évoluer la plateforme à un coût bien plus bas qu’un recrutement local.
- Ces profils offshore peuvent assurer une couverture quasi continue et réagir rapidement aux correctifs et itérations.
- Le modèle envisagé consiste à fournir une spécification ou une revue Loom, puis à laisser l’équipe offshore implémenter les dashboards, automatisations ou ajustements UI.
- Cette approche réduit les coûts SaaS récurrents par utilisateur et centralise la propriété technique tout en gardant le contrôle sur le branding et l’expérience client.

7. Licences, sécurité et bénéfices des portails clients • 0:12:58

- Une plateforme custom réduit le coût des licences multiples et améliore la sécurité en donnant accès à des portails privés via des identifiants email plutôt que des liens Notion publics.
- Les emails d’onboarding brandés et les portails privés renforcent la perception de professionnalisme et simplifient l’accès des clients à leurs données projet.
- Un environnement consolidé permet aussi une automatisation plus robuste, puisque tous les événements et toutes les données peuvent être reliés aux systèmes sales et opérationnels via webhooks et APIs.

8. Question de stratégie CRM : outil externe ou CRM intégré • 0:15:36

- L’équipe s’est interrogée sur le fait de conserver un CRM du marché comme Pipedrive ou HubSpot, ou de construire le CRM commercial directement dans la plateforme custom.
- L’évaluation doit prendre en compte la complexité d’intégration, les besoins de reporting, les coûts de licence et le niveau de liaison nécessaire entre sales et données projet pour générer automatiquement les tâches.
- Prochaine étape recommandée : cartographier les vues sales et les automatisations nécessaires, puis piloter la connexion d’un CRM au nouveau schéma projet ou au MVP pour valider la faisabilité.

9. Coût et limites des grands SaaS généralistes • 0:15:44

- HubSpot et les SaaS équivalents sont jugés très chers et trop riches en fonctionnalités, dont une grande partie n’est jamais utilisée.
- Ce type d’outil crée de l’inefficacité budgétaire et du bruit opérationnel.
- L’usage de SaaS généralistes peut obliger l’équipe à adapter son processus à l’outil plutôt que l’inverse.

10. Bascule vers des outils internes codés sur mesure • 0:16:28

- L’orientation privilégiée est de développer en interne des outils code-based adaptés aux besoins concrets de l’entreprise.
- La baisse des barrières d’entrée pour lancer des produits SaaS rend cette stratégie plus réaliste et potentiellement différenciante.

11. Limites de Notion pour des opérations flexibles • 0:16:47

- Notion est jugé adapté aux organisations très structurées, mais limitant pour les structures qui ont besoin de flexibilité et de changements rapides de schéma.
- Les tables synchronisées peuvent provoquer des effets en cascade lorsqu’on ajoute de nouveaux champs, ce qui complique l’introduction de données spécifiques à certains projets.
- Posséder son application et ses données évite les points de défaillance uniques et donne un contrôle complet sur les clients et les déploiements de fonctionnalités.

12. Méthode pour découvrir les besoins et prototyper les fonctionnalités • 0:19:34

- L’idée est d’enregistrer les appels clients et internes, d’en extraire les problèmes et objections, puis d’utiliser ces éléments pour construire des prompts destinés à une IA comme Claude afin de générer des propositions d’écrans.
- Les retours des parties prenantes doivent ensuite être recueillis de manière asynchrone pour affiner l’UX/UI avant un lancement plus large d’un prototype.
- Des instances Cloud Code peuvent être utilisées pour héberger ou traiter les prototypes et les intégrations en continu.

13. Automatisation de la détection des signaux commerciaux dans les appels • 0:22:00

- Il est jugé utile d’analyser la transcription de chaque appel client pour détecter automatiquement les intentions d’upsell ou de cross-sell et remonter des alertes aux sales.
- Le système doit agréger l’historique des appels et fournir au commercial un script ou des points de discours pré-rédigés lorsqu’un signal est détecté.
- La même logique peut servir à identifier automatiquement les clients satisfaits afin de déclencher des demandes d’avis, de témoignages ou des workflows NPS.
- Les intégrations peuvent s’appuyer sur Fatome, des webhooks et des APIs pour pousser appels et transcriptions dans la plateforme.

14. Centralisation de l’historique client et rendu interrogeable • 0:23:43

- Chaque interaction liée à un client — coaching, appels CSM, appels commerciaux, devis signés ou refusés — doit être stockée sur sa fiche comme un historique complet.
- L’intégration d’un chat IA dans la plateforme permettrait aux équipes de demander l’historique complet d’un client ou une sélection des éléments pertinents pendant un appel.
- Une fiche client unique, recherchable, améliore le contexte de réponse et facilite les décisions entre sales, delivery et support.

15. Équilibre entre culture d’équipe et automatisation pour la capture des données • 0:26:27

- La centralisation des données demande à la fois des habitudes culturelles — les équipes doivent contribuer — et de l’automatisation pour réduire la dépendance humaine.
- L’enregistrement automatique des appels et la conservation des transcriptions doivent devenir la norme pour éviter de dépendre de la prise de notes manuelle.
- Lorsqu’un client demande à être rappelé, des alertes et tâches calendrier doivent être créées automatiquement pour réduire le risque d’oubli.

16. Méthodes techniques pour capter les communications de manière fiable • 0:27:31

- Les appels entrants et sortants doivent passer par les numéros Aircall de l’entreprise afin que toutes les conversations soient enregistrées et rattachées à l’historique client.
- Quand WhatsApp est utilisé, l’API WhatsApp Business doit permettre de conserver l’historique des messages et de l’enregistrer sur la fiche client.
- L’objectif est de réduire au maximum les lieux où les humains doivent penser à journaliser les interactions.

17. Stratégie de transition depuis les outils existants vers la nouvelle plateforme • 0:29:03

- Le plan consiste à déployer rapidement une V1, collecter les retours, puis ouvrir progressivement le nouvel outil à un sous-ensemble d’utilisateurs pour itérer.
- Après plusieurs itérations et une stabilité confirmée, les données doivent être migrées et l’ancien outil doit être complètement coupé pour éviter les régressions.
- Une baisse temporaire de productivité est attendue pendant la migration, mais elle doit être compensée par les gains long terme d’un système mieux adapté.

18. Exemple de résultat avec un outil de gestion de leads • 0:31:45

- La construction d’une V1 centralisée pour la gestion des leads a pris environ une semaine d’itérations et a significativement augmenté la capacité des SDR une fois adoptée.
- Le passage de V1 à V2 a pris environ un mois, puis les itérations suivantes ont été plus rapides.
- Le système actuel traite entre 1 000 et 3 000 leads par jour et permet aux SDR de se concentrer sur une seule tâche, avec des gains de productivité mesurables.

19. UX de la plateforme SDR et intégrations • 0:33:45

- L’interface SDR interne intègre Aircall et enregistre les appels sans que les SDR aient à changer d’outil, ce qui réduit la friction technique.
- Les intégrations incluent iClosed pour la prise de rendez-vous et des UTMs par SDR pour suivre la source des leads et la performance.
- Le fait d’avoir une interface unique et simple réduit fortement la friction d’onboarding et améliore l’adoption.

20. Règle opérationnelle : communication écrite concise • 0:34:06

- Il a été recommandé d’imposer des demandes courtes, presque de type tweet, en interne afin d’éliminer les formulations superflues et d’accélérer la prise de décision.
- La réduction des formules longues, salutations et phrases de remplissage fait gagner du temps de lecture et améliore la clarté opérationnelle.

21. Des formulations courtes améliorent l’alignement des équipes • 0:34:44

- Boris a expliqué que des descriptions très courtes du problème et du résultat attendu améliorent fortement la clarté et l’exécution.
- Il a recommandé de limiter les blocs narratifs longs pour que le besoin principal reste immédiatement visible pour les opérateurs.

22. Principe de processus ouverts avec un propriétaire humain unique • 0:35:49

- La bibliothèque de processus doit rester ouverte et accessible à tous, plutôt que verrouillée par équipe ou par rôle.
- Chaque processus doit avoir un propriétaire humain nommé, responsable du résultat, et non une équipe abstraite.

23. Catégorisation des processus et périmètre pratique • 0:36:30

- Seuls les grands blocs opérationnels — par exemple les lancements marketing ou les événements physiques — doivent être formalisés en processus pour éviter l’encombrement.
- Les tâches mineures, comme la création d’un compte Google, ne doivent pas faire l’objet d’un processus complet pour éviter une bureaucratie inutile.

24. Processus stockés dans une base searchable avec dates de revue • 0:37:21

- Boris a décrit un outil interne fonctionnant comme une base de données où les processus sont recherchables par titre, propriétaire, utilisateur et filtres.
- Chaque processus doit inclure une première date de revue, idéalement à 30 jours, puis une revue périodique, idéalement à 90 jours, pour valider et faire évoluer le processus.

25. Droit de créer des processus et modèle de support • 0:38:26

- Tout le monde dans l’entreprise peut proposer et créer des processus, à condition que les contributions soient globales et non enfermées dans des cas personnels.
- Les propriétaires peuvent être aidés par leur manager ou par l’OPS, mais l’OPS ne créera pas les processus à leur place, sauf pour les grands processus macro.

26. Limites de Notion et besoin d’une UX / plateforme dédiée • 0:39:49

- Notion est jugé suffisant comme base de données, mais il atteint vite ses limites UX pour des besoins avancés comme des portails clients combinés ou des vues de delivery complexes.
- Dans un contexte d’agence où il faut gérer à la fois des parties prenantes internes et externes, un portail ou une plateforme dédiée devient nécessaire.

27. Exemples de fonctionnalités d’un dashboard projet dédié • 0:41:41

- Boris a montré un tableau de bord projet affichant les projets par stade, les missions actives, le nombre de tâches, la progression moyenne, les tâches en retard, les blocages ouverts, les prochaines étapes et la charge par utilisateur.
- Le dashboard propose plusieurs vues — planning, charge, Kanban, liste — et enregistre l’activité par utilisateur pour renforcer la visibilité opérationnelle.

28. La complexité client impose une conception guidée par les user stories • 0:42:38

- Mathis a décrit la complexité client : multi-batches, timing de livraison, production et canaux payants, ainsi que des clients multi-services nécessitant des flux systématisés.
- Boris a conseillé de segmenter les clients en archétypes de user stories — acheteurs ponctuels, acheteurs fréquents, clients multi-agences — pour couvrir tous les besoins par profil.

29. Approche de prototypage recommandée avant un build complet • 0:44:07

- La première étape doit être un document de spécification propre, consolidant les besoins de chaque fonction pour définir la plateforme cible.
- Avant de coder, il faut donner les données Notion existantes à un service de prototype Cloud / IA, puis demander un artefact montrant une UX organisée pour la delivery, les sales et le portail client afin de valider la vision.

30. Conduite du changement et stratégie d’adoption • 0:46:22

- Le succès d’un nouveau processus nécessite un accompagnement terrain, une répétition des bénéfices et une approche politique / humaine pour obtenir l’adhésion.
- La plateforme doit rester ouverte aux retours, avec une boucle de priorisation des demandes de changement pour éviter les outils figés.

31. Décision de construire maintenant et risques de retard • 0:48:30

- Boris a recommandé de construire l’outil dédié immédiatement, car attendre risque d’augmenter les pertes de revenus, les frictions opérationnelles et l’insatisfaction client à mesure que l’entreprise grandit.
- Reporter le chantier exposerait aussi à des coûts de correction plus élevés plus tard, lorsque le volume et la complexité seront plus importants.

32. Externalisation du développement en Inde et précautions de recrutement • 0:49:14

- Boris a suggéré de sourcer des développeurs en Inde avec des filtres clairs : localisation obligatoire, portfolio de dashboards pertinents et test pratique avec délai de livraison.
- Il a mis en garde contre les risques courants de delivery, notamment la connexion et les délais, et a insisté pour que les comptes critiques — GitHub, Vercel, Supabase — restent propriété de l’entreprise.
- Il a également recommandé de privilégier des candidats ayant une expérience dans les filiales high-tech de grandes entreprises américaines comme Amazon ou Uber.

33. Outil d’automatisation du recrutement pour le screening initial • 0:51:30

- Boris a présenté ICO, un outil partenaire connecté à LinkedIn, capable de scorer automatiquement les CV et de mener des premiers entretiens par IA.
- L’outil effectue des entretiens initiaux d’environ 40 à 45 minutes et aide à filtrer les candidats avant les entretiens humains pour gagner du temps et standardiser la sélection.

34. Prochaines étapes et éventuelle participation à un événement d’immersion • 0:53:35

- Mathis doit suivre la recommandation de Boris et prototyper via Cloud / Claude, puis préparer un document de besoins consolidant les attentes de chaque pôle.
- Les participants ont convenu de coordonner leur participation à un événement d’immersion à des dates évoquées pour septembre / octobre ou janvier / février.
- Ils ont également convenu de garder une communication ouverte pour les questions et le support supplémentaires.

35. Dilemme du modèle de staffing : créatifs en première ligne ou chefs de projet en première ligne • 0:59:00

- Deux modèles ont été testés : un modèle où les chefs de projet sont l’interlocuteur client principal, et un autre où des profils créatifs sont en frontal client.
- Le modèle orienté créatif améliore la satisfaction client, car le client échange directement avec la personne qui produit le résultat.
- En revanche, les profils créatifs gèrent plus difficilement la coordination de comptes multi-services et ont moins de capacité d’orchestration que des chefs de projet.
- Le modèle orienté chef de projet fonctionne mieux à l’échelle pour la coordination, les délais et le suivi, mais peut créer de la friction pour les clients qui veulent un accès direct aux créatifs.
- L’équipe doit déterminer quel modèle hybride ou scalé adopter selon les types de comptes et la stratégie tarifaire.
%% notes:fin %%
