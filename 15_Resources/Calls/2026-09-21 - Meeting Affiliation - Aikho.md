---
type: call
date: 2026-09-21
source: sembly
participants: ["boris@entrepreneurs.com", "alec.henry@entrepreneurs.com", "julien@aikho.ai", "arnaud@aikho.ai"]
sensitivity: confidential
tags: [call, sembly]
---

# Meeting Affiliation - Aikho

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (22/09/2026 07:38).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 22/09/2026 07:38 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a d’abord examiné le modèle de classification à faible latence JEV de Typesafe AI, capable de faire du sourcing quasi temps réel et de la validation sémantique en ligne, puis a concentré la discussion sur la conception d’un programme d’affiliation / tracking pour IKO/Nova : faisabilité technique, logique d’attribution, tarification, commissions, et modalités de mise en œuvre. En parallèle, la réunion a détaillé l’économie du sourcing, les coûts unitaires, les hypothèses de pricing, la structure des offres et le plan de validation produit/commerciale. Décisions et points à trancher : calendrier d’implémentation, niveaux de prix, règles de commission, limites des offres, mode initial manuel ou automatisé, et structure de test rapide avec quelques clients/pilotes avant l’intégration PSP complète.

📋 Outline

1. Introduction au modèle JEV (Typesafe AI) • 0:00:04

- Le modèle JEV est un classifieur universel encodeur-décodeur entraîné par apprentissage par renforcement, qui renvoie des probabilités structurées au lieu de générer du texte ; il est développé par Typesafe AI et a été présenté par Julien Recan.
- Le modèle a été entraîné sur des trillions de tokens et peut accepter de très grandes entrées structurées, avec une prise en charge allant jusqu’à 64k tokens par requête.
- Le prix annoncé est d’environ 42 $ par milliard de tokens d’entrée, avec une latence d’inférence d’environ 200 millisecondes, ce qui le rend rentable pour la classification et l’orientation structurées.

2. Cas d’usage : sourcing et profiling en temps réel • 0:02:01

- Julien intègre JEV dans le pipeline de sourcing pour générer des questions à partir d’un brief de poste et scorer des profils LinkedIn sur 23 questions générées dynamiquement, avec des métriques agrégées telles que « bon pour le poste » et « susceptible de le vouloir ».
- Le prototype a montré un flux de sourcing en streaming et la capacité de passer à des centaines, voire des milliers de profils par minute grâce au multithreading, la contrainte principale restant les limites des API d’enrichissement.
- Sur un poste de Deputy Head of Legal, les premiers résultats ont montré des scores de type 58 % d’adéquation et 67 % d’intention, avec un potentiel de réduction importante du temps de sourcing et du coût par profil.

3. Améliorations produit rendues possibles par le modèle à faible latence • 0:08:01

- Le temps de réponse de 200 ms permet une validation sémantique en ligne, par exemple la validation de formulaires et le contrôle de contenu, au lieu de règles codées en dur, ce qui améliore l’expérience utilisateur et l’ergonomie pour les développeurs.
- Le modèle peut alimenter de nouvelles expériences produit : routage, systèmes de décision, recommandations de prochaine action, tout en réduisant les coûts et en améliorant la précision sur plusieurs cas d’usage.

4. Objet de l’appel : feuille de route affiliation / tracking • 0:09:03

- L’objectif de la réunion est de définir comment suivre et rémunérer le business amené à IKO via des affiliés, et de s’accorder sur une feuille de route pour implémenter le tracking, les commissions et l’activation avec les partenaires.
- L’équipe veut évaluer ce qui existe déjà techniquement et ce qui doit être développé pour faire fonctionner un programme d’affiliation sur les événements, réseaux et partenaires.

5. Ce qu’il faut tracker et priorité d’attribution • 0:10:25

- Le signal d’attribution prioritaire est la personne ou le partenaire qui a recommandé le client, pas nécessairement le canal marketing exact utilisé.
- Le tracking par canal (Instagram, site web, etc.) reste utile pour mesurer l’efficacité du funnel et la performance des campagnes, mais il est distinct de l’attribution d’affiliation.

6. Approche d’implémentation : token à l’inscription et impacts tarifaires • 0:12:38

- Une implémentation réaliste consiste à émettre un token d’affiliation personnel que le filleul saisit à l’inscription, ce qui déclenche des récompenses à la fois pour le parrain et pour le nouvel utilisateur.
- Les récompenses pour les filleuls seront probablement exprimées en avantage tarifaire (réduction ou essai prolongé) sur le plan choisi ; les parrains peuvent recevoir soit une réduction (s’ils sont déjà clients), soit une commission cash (s’ils ne sont pas clients).
- Le système d’affiliation dépend de la définition préalable des offres d’abonnement et des paliers de prix avant d’automatiser complètement le dispositif.

7. Modèles de commission, cadence de paiement et gestion du risque • 0:16:28

- Les commissions sont généralement payées sur le revenu effectivement encaissé, ce qui réduit le risque par rapport à des avances versées à l’avance.
- Dans le B2B, les commissions d’affiliation sont souvent exprimées en pourcentage du revenu du plan (par exemple 25 à 40 %) ou via des incitations alternatives comme des essais prolongés ; les apporteurs à fort volume préfèrent souvent du cash.
- La cadence de paiement est en général agrégée (mensuelle ou trimestrielle) via un dashboard d’affiliation plutôt qu’un virement à chaque vente, et les conditions contractuelles doivent définir les règles de reporting et de paiement.

8. Contraintes, conditions et contrôles anti-fraude / qualité • 0:16:47

- L’équipe doit définir des conditions d’éligibilité aux commissions, par exemple un seuil minimal de rétention ou une durée minimale, afin d’éviter de rémunérer des inscriptions de faible qualité ou très éphémères.
- Une modélisation financière est nécessaire pour s’assurer que les niveaux de commission choisis ne créent pas de tension de trésorerie, surtout selon que la facturation soit mensuelle ou annuelle.

9. Décisions à court terme et prochaines étapes • 0:20:01

- Le groupe doit trancher la faisabilité, le périmètre technique et le calendrier d’implémentation du système d’affiliation / tracking.
- L’équipe doit finaliser les paliers tarifaires et les dimensions qui définissent les packages avant d’automatiser les récompenses d’affiliation.
- Le choix opérationnel immédiat est de savoir si le tracking des recommandations doit être géré manuellement au début, ou si l’on doit prioriser la construction d’une infrastructure d’affiliation automatisée une fois le pricing et la facturation stabilisés.

10. Privilégier un tracking de paiement lié à l’affilié plutôt que des appels manuels • 0:21:30

- La meilleure approche pour l’attribution d’affiliation est un paiement effectué côté front-end, enregistré et relié à la ligne de recommandation, afin que les referrals soient traçables.
- L’équipe a discuté de l’utilisation de n’importe quel PSP (Stripe, Wop, etc.) tant que les paiements sont connectés à la plateforme pour permettre l’attribution.

11. Validation produit avec un petit groupe de testeurs avant de finaliser le pricing • 0:21:50

- La prochaine étape immédiate consiste à valider rapidement le produit auprès d’un petit nombre de testeurs gratuits afin d’identifier les plus gros problèmes plutôt que de viser une finition exhaustive.
- Les retours des premiers testeurs peuvent influencer de manière significative l’usage du LLM, donc les coûts d’exploitation, ce qui impactera le modèle de tarification.
- Le pricing devra préciser ce qu’est un « plan » : limites sur les mandats, les candidats, l’usage de sourcing, les invitations, etc., et cette structure déterminera l’implémentation dans le PSP.

12. Démarrer avec des plans fixes simples, puis ajouter des plans variables • 0:24:03

- Boris recommande de lancer d’abord avec 2 à 3 plans fixes et de repousser les plans variables plus complexes à plus tard.
- L’objectif des premiers plans est de permettre aux gens de payer et de tester le volume, plutôt que de construire un pricing sophistiqué dès le départ.

13. Déploiement immédiat de tests internes et crash-test du système • 0:24:55

- L’équipe a décidé de lancer des tests internes immédiatement, avec Julien et Boris utilisant au moins cinq jobs sur la version V2 actuelle pour observer le comportement du système en charge.
- Les tests seront menés en mode « test-and-learn » ; l’équipe s’attend à des bugs et utilisera les boutons de support / signalement pour remonter les problèmes.
- Les tests internes permettront de déterminer la maturité pour des clients externes et de révéler les écueils de montée en charge.

14. Routage du trafic depuis les séminaires et suivi séminaires-vers-inscription • 0:27:02

- Si Alec fait la promotion du produit dans des séminaires, l’équipe doit décider s’il faut envoyer les participants directement vers le site web ou vers une landing page traquée.
- L’équipe doit pouvoir tracer les conversions issues de ces promotions via des QR codes, codes promo ou paramètres UTM pour connaître la source.

15. URL de signup / démo rapide disponible et contraintes sur les comptes démo • 0:28:14

- Julien a montré un flux existant de landing / démo rapide (getnova.aiko.ai ou nova.aiko.ai/line-up/hiring) qui crée un compte démo limité par défaut à un poste et 25 candidats.
- Le mécanisme de compte démo est volontairement restreint pour capturer les usages et éviter une consommation gratuite incontrôlée.

16. Création manuelle de tenants via un backdoor admin pour l’onboarding direct • 0:31:32

- Le panneau d’administration (admin.nova.ico.ai) permet au personnel de créer rapidement des tenants et de provisionner manuellement des comptes démo ou complets pour des utilisateurs spécifiques.
- Le flux manuel de création de tenant est prévu pour les cas où un humain aide à l’onboarding ou pour des clients particuliers avant l’automatisation complète des paiements.

17. Les comptes démo sont nécessaires pour capturer l’usage et limiter la consommation gratuite • 0:33:17

- Les comptes démo sont indispensables car des comptes gratuits non contrôlés pourraient être largement adoptés et générer des coûts élevés en LLM et en sourcing.
- Après utilisation de la démo, les utilisateurs seront incités à passer à une offre payante, et ce chemin d’upgrade doit exister avant même l’intégration automatique du PSP.

18. Processus d’upgrade transitoire avant les paiements automatisés • 0:36:15

- Tant que l’intégration de paiement n’est pas automatisée, l’équipe convertira les utilisateurs de démo via un processus manuel de type Compact ICO : la vente / l’opérations envoie un lien de paiement et vérifie le paiement avant de convertir l’utilisateur en tenant standard.
- Ce flux manuel n’est pas censé passer à l’échelle, mais il est acceptable pour les clients early-stage et les tests contrôlés.

19. Complexité du paramétrage Stripe / PSP et nécessité de définir le pricing d’abord • 0:38:30

- Julien a souligné que configurer les produits, plans, options additionnelles et la facturation dans Stripe (ou tout autre PSP) n’est pas trivial et exige que le modèle de tarification soit défini en amont.
- Le choix du PSP (Stripe, Wop, autres) doit tenir compte du coût, de la complexité et de la disponibilité de l’équipe ; Joe a déjà réalisé des travaux Stripe par le passé.

20. Structure tarifaire de départ proposée et limites associées • 0:39:44

- Un modèle proposé consiste à reproduire V1 avec deux plans fixes, par exemple 200 € et 500 € par mois, qui plafonnent le nombre de postes ouverts simultanément et les volumes de candidats.
- Les plafonds des plans doivent être liés aux métriques d’usage qui génèrent les coûts (volume de candidats, entretiens, activité de sourcing) afin de préserver les marges.

21. Le sourcing et les crédits pay-as-you-go doivent être définis • 0:41:20

- Le sourcing a historiquement été en bêta et souvent vendu sous forme de crédits pay-as-you-go (talent points) qui se déduisent à chaque action de sourcing.
- L’équipe doit concevoir la monétisation et le pricing du sourcing, car ses coûts auront un impact matériel sur l’économie unitaire globale et sur la définition produit dans le PSP.

22. Définir « candidat » vs « entretien » et mesurer le funnel • 0:42:07

- L’équipe a convenu de mesurer le nombre de candidats (définis comme les utilisateurs qui atteignent l’URL et se connectent) plutôt que le nombre d’entretiens, car « entretien » est mal défini.
- Plusieurs mécanismes de baisse de conversion existent : abandon utilisateur, problèmes techniques, refus de continuer et élimination lors du screening CV.
- La métrique principale à suivre est le taux d’abandon entre la connexion et l’entretien terminé, car c’est elle qui pilote le coût par entretien réussi.

23. Taux de drop-off observés selon le canal d’acquisition • 0:43:03

- Les candidats sourcés via email direct montrent environ 10 % de drop-off entre la connexion et l’entretien.
- Les candidats issus de prospection LinkedIn à froid montrent un drop-off beaucoup plus élevé, autour de 50 à 60 %.
- Responsabilité : le produit / l’analytics doit segmenter le drop-off par canal d’acquisition et remonter les différences chaque semaine.

24. Hypothèses de coût de production par candidat et cible • 0:43:34

- Le coût initial de matching CV de bas niveau est d’environ 0,01 $ par candidat.
- Le coût moyen en phase d’entretien a été débattu ; l’équipe propose d’utiliser 0,5 $ par candidat comme estimation prudente pour la modélisation actuelle.
- Le produit devrait viser une réduction progressive du coût moyen d’entretien vers 0,3 $ ou 0,2 $ grâce à des améliorations opérationnelles.
- Responsabilité : Finance / Produit doivent maintenir un modèle de coûts vivant et mettre à jour les écarts entre réel et cible.

25. Importance de la vélocité et arbitrages client • 0:44:02

- La vélocité des candidats, c’est-à-dire la rapidité avec laquelle les postes sont pourvus, influence la satisfaction client mais peut être gérée via le niveau d’abonnement ; recruter plus vite peut nécessiter des offres plus haut de gamme.
- L’équipe a reconnu un arbitrage : les clients peuvent prioriser la vitesse en montant en gamme, et Nova peut contrôler les limites de capacité pour imposer des niveaux de service.
- Responsabilité : Sales / Product doivent mapper les niveaux d’abonnement aux promesses attendues en matière de vélocité.

26. Architecture de pricing et remises d’échelle • 0:46:42

- La proposition est de commencer avec des prix de packages fixes simples (exemples évoqués : 200 $ et 500 $) et d’introduire de petites remises d’échelle, autour de 20 % d’économie entre 200 et 500.
- Des exemples de prix unitaires par candidat ont été suggérés : 1,20 $ au palier 200 $ et 1,00 $ au palier 500 $, avec éventuellement une remise pour engagement annuel (par exemple 10 %).
- Dans les négociations enterprise, la tarification variable par candidat dans Stripe a déjà existé, mais l’équipe préfère des paliers fixes pour éviter la complexité.
- Responsabilité : Sales et Finance doivent finaliser les prix concrets et les règles de remise pour le lancement.

27. Suivi du coût par tenant et politique de buffer • 0:50:17

- L’équipe suivra le coût moyen par candidat et par tenant et appliquera un buffer, suggéré à 20 %, pour garantir les marges et la sécurité de capacité.
- Les tenants peuvent avoir des coûts différents selon les canaux de sourcing et les types de jobs, d’où la nécessité d’un suivi au niveau tenant.
- Responsabilité : Engineering / Product doivent mettre en place le suivi de coût par tenant et des alertes automatisées lorsque les coûts dépassent les seuils.

28. Coûts opérationnels additionnels (tokens de simulation, connexion inbox) • 0:52:11

- Il existe des coûts supplémentaires au-delà de la production candidat / entretien, notamment les tokens pour les simulations et le traitement du brief vers publication, relativement faibles par job mais non nuls.
- La connexion de la boîte mail d’un client à Nova entraîne un coût estimé à 5 $ par mois et par adresse email connectée, coût à intégrer dans l’économie unitaire.
- Responsabilité : Finance doit inclure ces coûts marginaux dans le modèle de coût par client et dans les décisions de packaging.

29. Nouveau modèle de sourcing (Jev) et son économie • 0:55:49

- Un nouveau modèle (« Jev ») permet d’identifier rapidement environ 300 à 500 profils de type LinkedIn pertinents par poste en 1 à 2 minutes, pour un coût faible de quelques dollars.
- Le coût additionnel majeur consiste à trouver les emails de contact pour ces profils ; la recherche d’email coûte environ 0,20 $ par succès, avec un taux de succès d’environ 20 % en découverte d’email.
- L’équipe doit décider s’il faut plafonner le sourcing à coût fixe (exemples de caps : 2 à 5 $) et comment packager le sourcing séparément, car tous les clients n’en auront pas l’usage ni l’envie de payer.
- Responsabilité : Product doit prototyper l’offre avec des paliers de sourcing à prix fixe et documenter les coûts variables attendus ainsi que le taux d’adoption.

30. Coûts variables du sourcing et mécanismes de facturation • 0:58:46

- Les actions de relance / outreach (inviter beaucoup de candidats ou envoyer des emails personnalisés) augmentent fortement les coûts par rapport à la simple identification.
- Pour les clients qui utilisent seulement l’évaluation Nova mais s’appuient sur leur propre base LinkedIn ou CV, le sourcing doit être optionnel ou limité dans les offres les moins chères.
- Packaging suggéré : inclure un minimum de sourcing (par exemple 15 à 20 invitations) dans le package à 200 $ et proposer des tiers « sourcing plus » en option.
- Responsabilité : Sales et Product doivent définir le nombre d’invitations incluses par offre et un prix visible pour les add-ons de sourcing.

31. Positionnement de la valeur vs LinkedIn / chasseurs de têtes • 1:02:52

- L’équipe positionnera la valeur de Nova non seulement sur la recherche de candidats, mais aussi sur la réduction drastique des coûts par rapport aux chasseurs de têtes et au sourcing manuel sur LinkedIn.
- L’automatisation de Nova et la pré-analyse de l’adéquation des candidats réduisent le temps des recruteurs et constituent donc un message commercial clair d’économie de coûts.
- Responsabilité : Marketing / Sales doivent préparer des matrices et des supports chiffrant les gains par rapport aux processus chasseurs de têtes et LinkedIn.

32. Trois piliers du produit Nova • 1:04:48

- Le produit est structuré autour de trois piliers : évaluation en entretien, sourcing (identification + outreach) et fonctionnalités de valeur ajoutée post-évaluation.
- Ces piliers guideront le packaging, le message commercial et la priorisation de la roadmap.
- Responsabilité : Product doit maintenir cette structure de piliers dans la roadmap et s’assurer que chaque pilier dispose de KPI mesurables.

33. Comparaison des coûts de sourcing et valeur économique • 1:05:13

- Julien a expliqué que le coût pour la team d’envoyer un candidat évalué est d’environ 0,20 $ par candidat, ce qui sert d’unité de base pour calculer l’économie du sourcing.
- Il a comparé cela à l’acquisition via LinkedIn, où chaque clic coûte aux employeurs 2 à 3 $, rendant l’acquisition de candidats via LinkedIn nettement plus chère.
- Il a précisé que la tarification du marché appliquée aux candidats ou employeurs dans les flux issus de LinkedIn se situe souvent entre 2 et 3 $ par candidat, contre 20 à 25 cents pour l’équipe.
- Il a ajouté qu’appliquer une marge, par exemple x5, sur le coût de 0,20 $ reste extrêmement compétitif pour les clients.

34. Ratios de conversion, drop-off et volume nécessaire pour obtenir des recrutements • 1:06:43

- Julien a recommandé de présenter le coût du sourcing en fonction du coût total nécessaire pour obtenir une forte probabilité d’avoir, parmi les candidats actifs, 2 à 4 bons matchs.
- Il a estimé que pour trouver 3 à 4 bons candidats via des candidatures LinkedIn génériques, il faut souvent environ 200 candidats, qui, après drop-off, donnent ces 3 à 4 recrutements.
- Il a donné des exemples montrant que l’entretien de 200 candidats via des flux pilotés par LinkedIn peut coûter plusieurs centaines à plus d’un millier de dollars en tenant compte du coût des clics et du temps d’entretien manuel.
- Arno a confirmé l’interprétation selon laquelle les coûts LinkedIn (2 à 3 $ par clic) se traduisent par environ 600 $ et plus pour obtenir un volume suffisant de candidats de qualité.

35. Avantage du sourcing ciblé et économie unitaire • 1:10:27

- Julien a soutenu que des invitations ciblées vers 200 profils évalués et pertinents produisent un taux de réussite bien supérieur à 200 candidats aléatoires, car les invitations sont adaptées au rôle (par exemple des serveurs plutôt que des secrétaires).
- Il a calculé que l’invitation de 200 candidats ciblés à 0,20 $ chacun coûte environ 40 $, contre 600 $ pour un sourcing large via LinkedIn, ce qui représente un avantage de coût supérieur à 15 fois.
- Il a expliqué que traiter un candidat invité coûte à peu près autant que l’inviter, ce qui double effectivement le coût unitaire une fois qu’il entre dans les workflows d’évaluation.

36. Plans tarifaires, options d’abonnement et positionnement • 1:12:32

- Arno a proposé une matrice de niveaux d’abonnement basée sur l’inclusion du sourcing : sans sourcing, avec sourcing partiel et avec sourcing complet, plutôt qu’un simple abonnement de base complété par des crédits.
- Julien a recommandé d’offrir des add-ons de sourcing optionnels où un package mensuel pourrait inclure le droit d’inviter / interviewer jusqu’à N candidats (par exemple 200), et d’indiquer que l’inclusion du sourcing doublerait à peu près le prix de l’abonnement.
- Ils ont convenu que packager le sourcing en option, par exemple en doublant le prix du package, n’est pertinent que si le sourcing délivre de manière fiable la qualité de candidats promise.

37. Présentation, documentation interne et livrables immédiats • 1:14:45

- Arno a demandé le lien et a demandé à Julien de produire un slide deck formel expliquant la valeur, l’économie unitaire, le détail du pricing et l’impact client afin d’aligner l’équipe et les investisseurs.
- Julien s’est engagé à produire une présentation de haute qualité visualisant l’économie, par exemple le coût par 1 000 entretiens, et la logique de tarification.
- Arno prendra ensuite cette présentation pour finaliser les slides à distribuer aux parties prenantes (Alec, Boris, autres) et pour soutenir les échanges de fundraising.
- Ils ont convenu que la réunion HLD du 8 octobre est un jalon important pour disposer de cette documentation et de cette présentation.

38. Calendrier de levée de fonds et plan de validation • 1:16:08

- Arno a indiqué viser une levée de fonds avant Noël et a insisté sur le fait qu’une boucle de feedback de six semaines avec des métriques mesurables renforcera le dossier de financement.
- Cette boucle de six semaines doit inclure des tests internes, des tests de cross-sell auprès des clients existants et un essai de marketing direct response pour collecter des métriques de performance.
- La demande de financement sera présentée comme servant à affiner davantage le produit, l’intégrer plus profondément dans la chaîne de valeur, étendre les verticales, accroître le marketing et couvrir les coûts d’onboarding si la mise à l’échelle n’est pas totalement automatisée.

39. Clients pilotes et essais • 1:16:32

- Julien a confirmé disposer de contacts dans des entreprises mentionnées comme Yen White et Accenture, prêts à essayer le produit dès qu’une version testable sera disponible.
- Ils ont convenu de lancer des pilotes pour générer des métriques précoces et valider le produit avant la levée de fonds.
- Les pilotes alimenteront la boucle de feedback sur six semaines et fourniront des preuves concrètes d’ARR / MRR pour les supports investisseurs.

40. Intégration LLM / classifieur et avantage technologique • 1:17:29

- Julien a décrit l’intégration d’un modèle classifieur rapide (« Gem ») qui ne nécessite pas d’entraînement supplémentaire et répond en 2 à 400 millisecondes pour scorer l’adéquation des candidats en temps réel.
- Il a expliqué une approche à deux niveaux : utiliser un grand LLM pour transformer les briefs et rédiger les prompts d’évaluation, puis exécuter le classifieur rapide pour scorer et calculer les probabilités d’adéquation.
- Julien a soutenu que la validation sémantique en temps réel de réponses en texte libre constitue une avancée majeure, permettant des évaluations automatisées bien plus précises que les filtres traditionnels basés sur des formulaires.
- Il a proposé d’imiter la pensée humaine « rapide » (intuition immédiate) et « lente » (analytique) en combinant des classifieurs rapides avec des LLM plus profonds pour améliorer la qualité des entretiens / évaluations.

41. Implications marché et positionnement stratégique (banques, cabinets de conseil) • 1:22:16

- Julien et Arno ont discuté du fait que les grandes entreprises historiques (banques, grands cabinets) adoptent lentement les workflows LLM à cause des contraintes de conformité et de gouvernance, ce qui ouvre une fenêtre d’opportunité pour des acteurs plus agiles.
- Ils ont noté que les rôles de conseil et de consulting boutique sont perturbés par la baisse du coût de l’expertise induite par les modèles génératifs, et que les entreprises qui investissent dans une connaissance métier « agentisée » peuvent capter de la nouvelle valeur.
- Le groupe a conclu qu’il existe un potentiel de revenus significatif à aider les banques et institutions similaires à transformer des fonctions spécifiques (conformité, modélisation, etc.), mais que cela exige une spécialisation et une exécution focalisée.

42. Focalisation stratégique et arbitrages de ressources • 1:27:40

- Julien a recommandé de se concentrer d’abord sur le produit actuel (Echo / ICO) et de capter l’opportunité recrutement / sourcing avant de disperser l’effort sur plusieurs grandes initiatives.
- Arno a accepté que l’objectif immédiat est de monétiser Echo rapidement avec un nombre limité de clients payants, puis d’étendre ensuite.
- Ils ont admis que le succès à court terme (12 à 18 mois) pourrait ouvrir la voie à une valorisation beaucoup plus importante si l’adéquation produit-marché et les métriques de scale sont démontrées.
%% notes:fin %%
