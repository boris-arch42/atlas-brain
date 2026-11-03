---
type: call
date: 2026-11-03
source: sembly
participants: ["boris@entrepreneurs.com", "rachid.oubih@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# ⚔️ Squad SDR - Finaliser la machine de guerre

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (03/11/2026 11:49).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 03/11/2026 11:49 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

La réunion a couvert la normalisation du tracking des leads et des transactions dans HubSpot, la gestion des doublons, la standardisation des phases et statuts, ainsi que l’automatisation des liens de réservation iClose. L’équipe a également abordé le nettoyage massif des propriétés/segments, la consolidation des licences téléphonie, les besoins de reporting pour les SDR, et les sujets de recrutement/ATS. Les décisions clés incluent : création de leads sans propriétaire pour chaque nouvelle réservation, verrouillage des champs de tracking via des listes déroulantes, fusion progressive des anciennes données dans le nouveau système, ajout d’une phase transactionnelle « signed », automatisation du passage en closed-won au paiement, et clarification des responsabilités entre Boris, Rachid, l’équipe Inde, le marketing et les opérations.

📋 Outline

1. Création automatique des leads et règles de propriété par défaut • 0:00:00

- Chaque nouvelle réservation de call crée désormais automatiquement un lead, même si l’utilisateur réserve seul, et ce lead est initialement créé sans propriétaire.
- Les leads nouvellement créés sont placés automatiquement dans la colonne « call booked ».
- L’équipe SDR devra repérer les leads sans propriétaire puis les assigner au bon interlocuteur.
- Responsable technique : Boris.

2. Choix du système de tracking : ancien vs nouveau • 0:01:32

- Un nouveau système de tracking est en cours de remplissage et pourrait devenir la référence pour les nouveaux leads.
- Boris propose de conserver l’ancien système pour les leads historiques et d’utiliser le nouveau pour les nouveaux arrivants dans un premier temps.
- Rachid recommande de fusionner les données historiques UTM/leads dans le nouveau tracking afin de disposer de dashboards cohérents et d’une analyse de tendance fiable.
- Action attendue : l’équipe Inde importera les données historiques dans le nouveau tracking à la demande de Boris et Rachid.

3. Déduplication des leads et traitement des doublons • 0:02:28

- Des doublons peuvent apparaître lorsqu’un prospect s’inscrit deux fois ; le système les signale et les opérateurs doivent les marquer ou les supprimer pendant le traitement.
- Conserver temporairement les doublons permet d’analyser des problèmes de parcours, par exemple des doubles soumissions générées par un double clic.
- À terme, un workflow pourrait fusionner ou supprimer automatiquement les doublons une fois les règles définies.
- Action : Boris et Rachid doivent définir le futur workflow de déduplication.

4. Tracking séparé pour l’opt-in du lead et la réservation d’appel • 0:04:06

- Deux jeux distincts de tracking UTM sont nécessaires : un pour la source d’opt-in du lead, un autre pour la source de réservation d’appel.
- Un lead peut provenir d’un endroit et réserver son call via un autre canal ; il faut donc conserver les deux attributions.
- Exemple donné : opt-in depuis Instagram avec une campagne publicitaire, puis réservation depuis un webinar avec une campagne différente.
- Rachid reconnaît que cette logique peut créer des doublons, mais estime que les deux informations sont indispensables pour l’attribution et les dashboards.

5. Verrouillage des champs de tracking et listes déroulantes • 0:06:29

- Tous les champs liés au tracking doivent être convertis en listes déroulantes pour éviter les saisies libres et les valeurs incohérentes.
- Les champs concernés incluent notamment Funnel Marketing, UTM Source, UTM Medium et Campaign.
- Seuls quelques super-admins pourront ajouter de nouvelles options ; les utilisateurs classiques ne pourront pas modifier ces listes.
- Les champs générés automatiquement par le tracking devront être en lecture seule pour éviter les modifications accidentelles.
- Des options historiques ou nouvelles pourront être injectées en masse via import Excel.

6. Gouvernance des données et blocage des modifications manuelles • 0:09:58

- Rachid a insisté sur le blocage des modifications manuelles, car les fautes de frappe créent de nouvelles valeurs et cassent les dashboards.
- Lorsqu’une nouvelle campagne ou un nouveau funnel est lancé, l’ajout de l’option correspondante dans la liste déroulante doit faire partie du processus.
- Cette gouvernance oblige les équipes à signaler les valeurs manquantes au lieu de les inventer à la volée.
- Responsabilités : Rachid définit la politique, Boris l’implémente, et les équipes marketing doivent suivre le processus.

7. État actuel du tracking sur contacts, leads et deals • 0:11:50

- Boris a confirmé que, sur des contacts échantillons, la source d’opt-in et le tracking de réservation sont correctement enregistrés à la fois sur les leads et sur les deals.
- Les deals et les leads affichent actuellement correctement les champs de tracking.
- Boris prévoit d’ajouter des emojis visuels sur les deals pour faciliter l’identification rapide.
- La logique de double tracking permet de couvrir différents scénarios, du booking direct aux cycles multi-touch sur plusieurs mois.

8. Nettoyage et standardisation des phases et statuts de leads • 0:12:37

- Le champ « type of lead » contient de nombreuses valeurs héritées (new company, upsell, qualification, etc.) et doit être simplifié ou supprimé.
- Rachid fournira une liste définitive de phases/statuts alignée sur CloudTalk.
- Les statuts cibles incluent notamment : new attempt, connected, attempt in progress, meeting book, qualified, disqualified et NRP.
- Le statut « meeting book » sera conservé car il est utile pour le filtrage ; les autres statuts hérités devront être retirés pour éviter la confusion.
- Boris et Rachid aligneront ces statuts avec les besoins de reporting et de workflow.

9. Impact des changements sur le champ de step lead • 0:18:13

- Le champ « lead step » est utilisé dans 58 emplacements : workflows, vues, rapports et segments.
- Tout changement devra être évalué avec prudence pour éviter de casser les automatisations existantes.
- Une revue des dépendances est nécessaire avant suppression ou renommage de champs.
- Boris doit produire la liste des dépendances, puis les workflows et rapports devront être mis à jour.

10. Visibilité du champ natif dans le pipeline et limites techniques • 0:18:58

- Un champ natif « type » sur l’objet lead apparaît dans la vue pipeline et ne peut pas être archivé, ce qui encombre l’interface.
- Une tentative de masquer conditionnellement le champ a caché des étapes entières au lieu de masquer uniquement la propriété.
- La limitation technique empêche de masquer un seul champ sans impacter l’ensemble de la vue pipeline.
- Un contournement technique devra être trouvé plus tard.

11. Doublons de leads créés par le quiz funnel • 0:21:45

- Le contact Céline Arambour affiche deux leads distincts au statut « meeting booked » à 08:45 et 09:49, alors qu’un seul deal existe.
- Le premier lead provient probablement d’un quiz partiellement complété, qui a créé un lead avec des données d’opt-in incomplètes.
- Le second lead a été créé lorsque l’utilisatrice a terminé le quiz et réservé un appel.
- L’équipe doit vérifier si un workflow existant fusionne ou déduplique automatiquement les leads créés à quelques minutes d’intervalle.

12. Distinction entre tracking niveau contact et tracking niveau lead • 0:26:12

- Le contact doit conserver de manière permanente sa source d’acquisition initiale, appelée « tracking initial du contact », sans être écrasée par les sources ultérieures.
- Chaque lead créé pour ce contact doit conserver ses propres propriétés de tracking au niveau lead, afin de garder l’origine par funnel.
- Rachid a demandé que le tracking du lead soit très visible dans la vue lead pour identifier immédiatement l’origine.
- Boris renommerait le champ contact en « tracking initial du contact » et séparerait clairement les libellés de tracking du lead.

13. Règles de propriété entre contacts, leads et closers • 0:31:26

- L’équipe doit définir si les owners closers/Gadoff doivent prendre en charge le contact ou seulement les leads individuels lorsqu’il existe plusieurs leads pour un même contact.
- S’il existe plusieurs leads liés à un contact, il faut une personne unique responsable afin d’éviter les doublons de traitement.
- Rachid a insisté sur la nécessité d’un process simple, documenté et accompagné de formation.
- Le risque principal est une prospection parallèle sur le même prospect et une confusion dans le suivi.

14. Tests publicitaires et préparation des dashboards • 0:35:41

- Des tests publicitaires ont été lancés la veille au soir et des dashboards doivent être préparés dans la journée pour analyser les résultats.
- Les dashboards permettront de comprendre quels canaux génèrent des contacts et si les flux produisent des doublons ou des enregistrements partiels.
- Boris est chargé de produire les dashboards avec l’aide de l’analytics.
- Objectif : rendre visibles rapidement les effets des nouveaux tests marketing.

15. Création automatique de contacts par CloudTalk et pollution du CRM • 0:35:49

- Les appels entrants depuis CloudTalk créent automatiquement des contacts dans HubSpot lorsque l’appelant n’existe pas déjà.
- Cela génère souvent des contacts place-holders avec uniquement un numéro de téléphone, ce qui pollue la base.
- Un workflow existait pour archiver ou fusionner ces contacts, mais l’équipe doit décider s’il faut désactiver la création automatique.
- Le compromis à évaluer est le suivant : éviter la pollution CRM, sans perdre les données d’appel.

16. Comportement du VSL, réservation et tracking lead/deal • 0:37:33

- Le trafic VSL mène généralement les utilisateurs à réserver directement via iClose plutôt qu’à passer par une opt-in préalable.
- IClose capture le nom, l’email et met le tracking sur le deal, mais les réservations incomplètes peuvent créer des leads plutôt que des deals.
- L’équipe a discuté de l’ajout d’un formulaire obligatoire ou d’une capture UTM sur la réservation VSL.
- Objectif : permettre le retargeting et la réactivation des personnes ayant commencé sans terminer la réservation.

17. Évaluation d’une solution type Opspot pour limiter les multi-saisies • 0:40:16

- Rachid a proposé d’évaluer une solution de type Opspot permettant au prospect de saisir ses coordonnées une seule fois.
- Ce fonctionnement réduirait les leads en double liés à la répétition des formulaires.
- Un flux unifié améliorerait aussi la conversion VSL et faciliterait le retargeting des personnes qui n’ont pas finalisé.
- Boris et l’ingénierie doivent évaluer l’adaptation des liens iClose ou HubSpot pour conserver les UTM et le tracking.

18. Objectif de centralisation de toutes les sources dans HubSpot • 0:42:01

- L’objectif est d’acheminer toutes les sources — site web, événements, YouTube, publicités, CloudTalk, etc. — vers HubSpot.
- Les données doivent être taguées clairement pour que les dashboards reposent sur un seul jeu de données cohérent.
- Rachid a demandé que les dashboards affichent « avec owner » et « sans owner » pour suivre la couverture et l’assignation.
- Boris doit cartographier toutes les sources et confirmer quelles intégrations envoient aujourd’hui les données vers iClose ou HubSpot.

19. Création d’un fichier partagé pour le suivi des nouveaux éléments • 0:43:16

- Un fichier partagé doit être créé pour centraliser tous les nouveaux éléments : funnels, pages et mises à jour.
- Ce fichier servira à vérifier que les tâches requises ont bien été réalisées, notamment les limites, les liens corrects entre systèmes et les automatisations.
- Les trois sources de trafic de Raphaël ont été confirmées : book funnel, quiz funnel et VSL.
- À ce stade, seul le VSL est disponible et nécessite un suivi complémentaire.

20. Revue des vues HubSpot contact, lead et transaction • 0:45:06

- La carte contact/lead doit afficher les informations de transaction associées, notamment le nom de la personne et les paramètres UTM source, medium et campaign.
- Rachid n’avait pas la même vue de prévisualisation de transaction que Boris ; l’écart vient du layout interne et des paramètres de preview.
- Boris alignera les vues pour que les affichages soient cohérents.
- Boris supprimera aussi les propriétés de lead inutilisées ou en doublon afin de simplifier l’interface.

21. Ajout de la phase transactionnelle « signed » et automatisation du closed-won • 0:47:28

- Une nouvelle phase de transaction « signed » sera ajoutée avant « closed-won » afin de distinguer les contrats envoyés, signés et les paiements reçus.
- Le passage en closed-won sera automatisé lorsqu’un paiement est détecté dans Udoo.
- Cela évitera à Léa de faire des vérifications manuelles.
- Le but est de clarifier les statuts qui mélangent actuellement « engaged » et « signed ».

22. Nettoyage et archivage massif des propriétés, segments, dossiers et automatisations • 0:49:16

- Des milliers de propriétés, segments et dossiers dupliqués ou hérités d’anciens utilisateurs doivent être revus, puis supprimés ou archivés.
- Une sauvegarde/export complet doit être réalisé avant toute suppression en masse.
- Les anciens leads, y compris ceux de l’année précédente, doivent être exportés et conservés s’ils présentent encore de la valeur.
- La suppression de segments ne supprimera pas les leads, mais retirera leur catégorisation existante.
- Environ 98 automatisations dépendent actuellement des segments et devront être auditées.

23. Évaluation de Sales Workspace et des licences SDR • 0:51:10

- La fonctionnalité enterprise « Sales workspace » pourrait centraliser les workflows des SDR et des vendeurs.
- Rachid doit la tester ; Boris l’implémentera si elle est validée.
- Si l’outil n’est pas satisfaisant, le plan est de revenir à deux licences standard et de gérer les SDR via listes et pipelines segmentés.
- De nombreuses segmentations et listes de test inutilisées encombrent aujourd’hui l’espace de travail.

24. Liens iClose par funnel, stratégie UTM et Funnel ID • 0:57:00

- L’équipe veut créer des liens iClose standardisés par type de funnel récurrent, par exemple challenge ou webinar.
- Les SDR et les clients utilisant ces liens rempliront les champs iClose, y compris le revenu/CA, afin de router les leads vers le bon pipeline ou la bonne offre.
- Boris propose un champ Funnel ID pour identifier et router les leads automatiquement.
- Il souhaite aussi créer une propriété calculée qui agrège les UTM source dans une seule propriété source.

25. Engagement du prestataire CGM, livrables et responsabilités • 1:01:33

- CGM a proposé de fournir un process de recrutement et d’onboarding SDR, un script d’installation, les spécifications d’outillage, la connexion du hub SDR, des pipelines de reporting et une formation pour Alexandre.
- L’objectif annoncé est d’atteindre 8 à 10 SDR opérationnels.
- Les SDR seraient rémunérés directement par l’entreprise à hauteur de 1 200 € fixes plus commission ; CGM ne gère pas la paie.
- Rachid n’a pas encore reçu de confirmation claire ni de profils, et doit vérifier si CGM a été payé et quels profils ont été réellement fournis.
- Des contributions précédentes de CGM incluent la structure initiale du hub SDR et des données, ainsi que des vidéos d’onboarding réalisées par Alexandre.

26. Paiement du prestataire et perception de la valeur • 1:03:46

- Le prestataire sera payé car il a déjà effectué du travail pour l’équipe.
- Rachid estime que certaines tâches CRM proposées sont redondantes puisque l’équipe migre vers HubSpot.
- Il a aussi remis en question le prix annoncé pour des profils marocains, jugé trop élevé par rapport au marché local.
- Boris et Rachid doivent cadrer le périmètre pour ne garder que les tâches à valeur ajoutée.

27. Cadrage des tâches d’onboarding et de formation pour la ressource externe • 1:03:56

- Rachid est ouvert à ce que le prestataire travaille sur des supports d’onboarding et de formation pour renforcer les compétences de l’équipe.
- L’idée est de limiter le périmètre à des livrables utiles, plutôt que de refaire des montages CRM déjà couverts.
- Boris et Rachid doivent clarifier ce que la ressource doit réellement produire.
- L’objectif est d’obtenir une valeur concrète et mesurable.

28. Besoin de liens iClose automatisés par événement • 1:05:07

- L’équipe souhaite créer un lien iClose de réservation par événement plutôt qu’un lien par SDR.
- Le suivi SDR permettra d’identifier quel SDR a envoyé le rendez-vous.
- Boris a confirmé que les liens existent déjà mais doivent être générés de manière technique avec les bons paramètres UTM via HubSpot.
- Le besoin est d’automatiser la génération pour éviter la multiplication manuelle des liens.

29. Construction d’une propriété calculée pour les liens dynamiques • 1:07:49

- Boris a travaillé sur une propriété calculée qui concatène les paramètres UTM source, medium et campaign avec les propriétés de lead et les champs owner.
- Il a dû ajuster le type de propriété pour produire une chaîne de caractères utilisable comme URL.
- La solution permet de générer un lien dynamique correct sans créer une grande quantité de liens manuels.
- Boris considère qu’une seule formule bien construite peut suffire.

30. Alternative par workflows et complexité de maintenance • 1:10:11

- Rachid a proposé une alternative avec des branches de workflow pour remplir l’URL finale selon les combinaisons possibles.
- Boris a jugé cette option trop lourde à maintenir en raison du nombre élevé de branches.
- Le risque principal est de devoir mettre à jour manuellement les liens à chaque nouveau funnel.
- L’équipe reste favorable à l’approche par formule unique pour limiter la maintenance.

31. Les champs owner retournent un ID et non un nom lisible • 1:18:01

- Boris a constaté que les champs owner HubSpot renvoient un ID interne et non un prénom/nom lisible.
- Cela empêche d’utiliser directement le nom du propriétaire dans l’URL générée.
- La solution prévue consiste à faire un mapping des IDs vers des noms lisibles via une logique IF.
- Cette approche est nécessaire car HubSpot utilise des IDs pour éviter les ambiguïtés entre utilisateurs portant le même nom.

32. Sélecteur déroulant pour limiter les erreurs utilisateur • 1:19:37

- Boris a proposé d’ajouter une liste déroulante des owners au-dessus du champ de lien de réservation afin que l’utilisateur choisisse explicitement le propriétaire avant génération.
- Rachid a averti que cela peut introduire des erreurs humaines si l’utilisateur sélectionne le mauvais owner ou conserve une ancienne valeur.
- L’équipe considère que le dropdown réduit la complexité pour l’utilisateur final, mais nécessite des garde-fous et une validation claire.
- Le principe général retenu est de simplifier l’usage sans dégrader la qualité des données.

33. Maintenance continue et protocole d’onboarding des nouveaux SDR • 1:20:05

- Boris a rappelé que la solution par formule doit réduire au maximum la maintenance future par rapport à des liens manuels par funnel.
- Rachid a insisté sur la robustesse du process et sur la nécessité de concevoir le système comme si les utilisateurs étaient débutants.
- L’équipe a convenu que tout nouvel SDR ajouté devra être signalé à Boris pour mise à jour de la formule, du mapping et des propriétés HubSpot.
- Objectif : éviter les erreurs répétées lorsque l’équipe grandit.

34. Liste des SDR et collecte des IDs HubSpot • 1:22:56

- Rachid a confirmé qu’il y a actuellement cinq SDR dans l’équipe.
- Il s’est engagé à fournir la liste complète des noms de SDR pour le mapping.
- Il a également partagé dans le chat les prénoms et noms complets à utiliser pour la formule.
- Boris a demandé les IDs HubSpot de chaque SDR pour finaliser le mapping IF.

35. Tests UTM et validation des liens de tracking • 1:31:35

- Une série complète de tests UTM a été exécutée pour plusieurs membres de l’équipe afin de valider le taggage source/medium/campaign sur les funnels.
- Les cas testés incluaient notamment des sources SDR, quizdiagnosticentrepreneurs.com et l’attribution par owner.
- La plupart des liens test produisent bien le lien Eclose attendu avec les paramètres UTM visibles en haut du tunnel.

36. Noms de leads dupliqués ou incohérents dans les rapports iClose • 1:32:33

- L’extraction iClose a montré que certains contacts, comme Lisa ou Achille, apparaissent sous plusieurs variantes de nom.
- Parfois, une même personne est enregistrée jusqu’à quatre fois sous des formats différents.
- Les dashboards comptent actuellement toutes les variantes, ce qui gonfle artificiellement les volumes.
- Une normalisation des noms est nécessaire, ainsi qu’une vérification de la déduplication dans les dashboards.

37. Liens cliquables cassés à cause d’un séparateur manquant • 1:33:37

- Un problème a été identifié sur les liens complets d’ID lead : l’absence de tiret ou de séparateur entre le prénom et le nom casse le lien.
- La logique de construction du lien doit être corrigée pour insérer les bons séparateurs ou encoder l’URL.
- Un contournement temporaire a été appliqué pendant la réunion pour valider le flux.
- Un correctif permanent doit être réalisé par le développement.

38. Verrouillage des champs de tracking et renommage des libellés ambigus • 1:35:06

- Il a été convenu de verrouiller ou de convertir en listes déroulantes tous les champs liés aux sources, afin d’éviter les valeurs mal formées.
- Le libellé « client illimité » a été jugé ambigu et devra être renommé en identifiant de boucle/funnel plus explicite.
- Les champs de tracking internes sensibles seront masqués dans l’interface pour ne pas exposer de valeurs techniques sans intérêt aux SDR.
- Les informations de date, d’heure et de fuseau horaire resteront visibles pour l’exploitation.

39. Accès des SDR au CA et aux données issues du quiz • 1:38:12

- Le quiz funnel est actuellement la seule source qui capture le revenu déclaré, les objectifs et le score du quiz.
- Les formulaires de réservation de vente contiennent bien un champ revenu obligatoire, mais les SDR n’y ont pas toujours accès avant l’appel.
- L’équipe doit revoir le process avec Raphaël afin de fournir aux SDR une vue synthétique avant appel, incluant réponses au quiz et revenu.
- Il faut également définir où le CA doit être collecté pour les autres funnels.

40. Documenter l’architecture et produire un schéma global • 1:39:47

- Boris a indiqué vouloir créer un schéma complet de l’architecture de tracking et des funnels mis en place.
- Ce document servira de référence visuelle pour l’équipe et permettra d’identifier les derniers cas limites.
- Il aidera aussi à guider le nettoyage final des champs, listes déroulantes et conventions de nommage.
- L’objectif est d’avoir une vue consolidée et facile à partager.

41. Outils IA, crédits et usage pour le nettoyage de données • 1:41:31

- Rachid a épuisé ses crédits ChatGPT en nettoyant des bases SDR et prévoit d’utiliser Claude pour les tâches de base de données et de texte.
- Boris a proposé un accès à une formule payante et d’ajouter Rachid à l’équipe Claude.
- L’équipe a convenu d’utiliser les outils selon le type de tâche : ChatGPT pour le technique, Claude pour le traitement de données et les résumés.
- Rachid doit également demander un résumé historique des données fournies afin d’améliorer l’automatisation et le recrutement.

42. Consolidation des licences de téléphonie et optimisation des coûts • 1:43:45

- L’examen a mis en évidence de nombreuses licences Aircall inutilisées.
- La consolidation vers CloudTalk et des licences admin mutualisées pourrait réduire les coûts mensuels d’environ 1 500 €.
- La décision est de réattribuer et mutualiser les licences admin plutôt que d’acheter des licences simultanées inutiles.
- Une comparaison coût/fonctionnalité entre CloudTalk et l’offre actuelle doit être finalisée avant engagement.

43. Workflow de recrutement, ATS et définition des rôles • 1:45:35

- Les rôles dans l’ATS ont été clarifiés : le sourcer trouve les profils, le reviewer les qualifie et les note, et l’interviewer mène les entretiens.
- Les reviewers rejettent actuellement automatiquement les profils sans expérience SDR, ce qui bloque potentiellement de bons candidats.
- Le fonctionnement de publication pour la Libye et le Liban a été clarifié : les candidatures passent par les liens Aéco, pas par LinkedIn.
- Rachid a envoyé manuellement des liens personnalisés aux candidats.
- Action : ajuster les filtres ATS pour éviter les rejets excessifs et confirmer quels canaux doivent aller automatiquement en phase d’entretien.
%% notes:fin %%
