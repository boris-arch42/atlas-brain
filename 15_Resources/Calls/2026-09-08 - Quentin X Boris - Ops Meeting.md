---
type: call
date: 2026-09-08
source: sembly
participants: ["boris@entrepreneurs.com", "42lab@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Quentin X Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (08/09/2026 16:33).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 08/09/2026 16:33 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

La réunion a porté sur l’alignement des priorités entre delivery et marketing, la clarification des canaux de communication et de la visibilité sur la roadmap, ainsi que la définition des besoins, jalons et dépendances pour le nouveau module de statut client « Success Core ». Les échanges ont aussi couvert l’état d’avancement de la release V2, la migration Ngram/CLAP et la réduction des coûts de licences, les sujets de qualité de données qui impactent les dashboards et le leaderboard, le statut du module concierge, ainsi que plusieurs arbitrages de roadmap pour septembre autour de la monétisation, du R&D « moonshot » et des initiatives marketplace/partenariats. Décisions clés : rendre le cookie banner optionnel pour les funnels, poursuivre avec une spécification technique / PRD pour Success Core à partager sur le channel 42labs, finaliser la migration V2 avec les contrôles de sécurité restants, et préparer les coupes de licences CLAP après synchronisation avec Wasim.

📋 Outline

1. Objet de la réunion et approche de coordination • 0:00:01

- L’objectif de la réunion est de centraliser les retours, aligner les attentes entre équipes et lever les ambiguïtés afin que chacun comprenne l’avancement et les responsabilités.
- Boris Arduy se positionne comme conseiller et coordinateur : il distribuera les missions, donnera du feedback lorsque nécessaire et veillera à éviter toute dissonance entre les équipes.
- La session se concentre principalement sur deux thèmes : la delivery (développement) et le marketing.

2. Cookie banner sur les funnels (marketing) • 0:01:56

- L’équipe marketing a observé que la bannière de consentement cookies sur les funnels de prêt peut dégrader les performances ; la bannière doit donc devenir optionnelle plutôt qu’activée par défaut.
- Cette option permettra de réaliser des tests A/B afin de mesurer l’impact de la suppression ou du maintien de la bannière sur la conversion et les autres métriques de performance.
- Léonard est chargé d’implémenter la bannière cookies comme réglage optionnel, puis Boris confirmera la mise en place via le channel 42labs.

3. Module Success Core (questionnaire de statut client) • 0:04:05

- Success Core est un questionnaire client périodique (M0, M3, M6, M9, M12) rempli avec le coach pour évaluer l’évolution du client sur trois piliers : finance, structure et vision ; chaque questionnaire produira un score sur 100.
- Le formulaire doit distinguer les champs obligatoires des champs optionnels et définir des formats de données précis afin de permettre un scoring cohérent et un suivi fiable de l’évolution du client dans le temps.
- Les résultats serviront à prendre des décisions, par exemple ajuster la méthodologie et identifier les meilleurs moments pour demander des témoignages clients, notamment autour de M3 lorsque les progrès sont souvent les plus visibles.
- L’équipe engineering dispose déjà d’un système léger de « nudges » pour M3/M6/M9 ; celui-ci devra être enrichi avec les nouvelles questions et synchronisé avec « my space » côté client.
- Boris publiera une PRD technique retravaillée, orientée sur la consommation technique, sur le channel 42labs afin que l’ingénierie puisse estimer les jalons ; l’équipe souhaite obtenir des jalons de haut niveau et des dates, plutôt qu’un découpage jour par jour.

4. Canaux de communication et workflow (42labs, Slack, Linear) • 0:09:27

- Les équipes préfèrent utiliser le channel 42labs pour la visibilité projet, car il agrège les commits, tickets et mises à jour d’avancement tout en réduisant le bruit des threads privés.
- Il existe actuellement une confusion sur l’orientation des tickets Zendesk et sur la manière dont les tickets support sont remontés ; auparavant, le fait d’envoyer les tickets dans le channel partagé permettait un tri plus rapide et des réponses plus simples à copier-coller.
- Boris demande un niveau de granularité élevé (liens au niveau des tâches, association au projet) afin de suivre l’avancement sans notifications excessives ; il pourra aussi consulter Linear directement pour le statut projet.
- Une piste d’optimisation a été évoquée : séparer éventuellement le channel 42labs en deux flux (tickets vs évolutions produit) si le bruit persiste.

5. Visibilité roadmap, perception des retards et réorganisation de l’équipe • 0:13:12

- Quentin a expliqué que l’ingénierie est dans les temps par rapport à la roadmap publiée pour les travaux de juillet-août, mais que certaines communications internes entre parties prenantes ont créé l’impression de retards.
- Pour réduire le bruit et améliorer le retour terrain, Quentin a réorganisé les responsabilités et ajouté Élodie pour collecter les retours coachs / clients, afin d’éviter de surcharger les parties prenantes de niveau supérieur.
- Boris a insisté sur une collaboration orientée solution : débloquer le travail quel que soit l’endroit du goulot d’étranglement, éviter la recherche de responsables et conserver la dynamique vers les mises en production.

6. Contrôles de sécurité et migration de la plateforme V2 • 0:20:06

- Quatre sujets de sécurité majeurs, déjà soulevés avec Mohamed, doivent être revérifiés pour confirmer leur clôture ; le travail de sécurité a pris du retard car l’équipe s’est concentrée sur la migration V2.
- Quentin indique que la migration V2 est en cours et qu’elle devrait être mise en production en fin de journée ou dans une courte fenêtre, une grande partie du staging et des correctifs étant déjà prête.
- La migration V2 inclut le remplacement de l’implémentation Circle community et doit être suivie immédiatement par la résolution des derniers blocages de sécurité.

7. Statut de la release V2 et périmètre technique • 0:21:08

- Le déploiement V2 est proche de la vérification finale et devrait être poussé peu après l’appel, avec une disponibilité estimée de D2 environ une heure après la réunion.
- V2 a représenté un effort d’ingénierie très important, avec 216 commits et environ 140k lignes de code ajoutées, transformant cette release en un projet majeur plutôt qu’en une simple série de merges légers.
- Les fonctionnalités Ngram / CLAP sont restées bloquées dans le flux de travail V2, car les merger indépendamment risquait d’entraîner des impacts plus larges sur la plateforme.
- La migration V2 inclut un transfert de données de 8 To et impacte les processus de coaching et de plateforme, ce qui a renforcé les besoins de test et de vérification.
- Action : finaliser les vérifications restantes et programmer le push V2 ; responsables : Quentin et les tech leads.

8. Projet Ngram / CLAP : objectif et positionnement • 0:21:38

- Le projet TAI, désormais sur V2, a été repositionné comme un assistant / helper afin d’éviter les inquiétudes des coachs face à une perception de remplacement par une « live AI coaching ».
- Une approche d’intégration via une application Google Meet a été identifiée pour permettre aux coachs d’ouvrir l’assistant en direct pendant les appels.
- Ngram fournit de la transcription en direct et une facturation à l’usage, ce qui le rend plus économique que des licences CLAP facturées par utilisateur.
- Action : finaliser le nommage de l’assistant Ngram et la documentation destinée aux coachs ; responsables : Quentin et produit.

9. Réduction des licences CLAP et transition de facturation • 0:24:52

- Le premier jalon consistait à réduire les coûts CLAP en supprimant immédiatement environ 800 € de licences par mois.
- Une approche par phases a conservé quelques licences actives pour les tests des collaborateurs pendant la beta, avant un cutover complet lié à l’activation de V2.
- Les cycles de facturation CLAP et leur timing ont été discutés : la prochaine date de facture a été évoquée autour de la fin du mois, et les licences retirées restent réassignables au sein du mois déjà payé.
- L’équipe s’attend à ne plus payer CLAP après la période de facturation de septembre, une fois la migration vers Ngram terminée.
- Action : se synchroniser avec Wasim pour réaliser le cutover des licences et confirmer la couverture de la facture finale ; responsables : Quentin et Wasim.

10. Planning de déploiement et segments utilisateurs pour Ngram • 0:26:00

- Le plan de déploiement prévoit les coachs en août puis les ventes et les autres utilisateurs en septembre, et l’équipe estime ce calendrier atteignable.
- Ngram se connectera aux calendriers des collaborateurs entrepreneurs.com afin que les sessions apparaissent automatiquement sur la plateforme.
- L’approche de migration vise une facturation à l’usage, afin que les utilisateurs inactifs ne génèrent pas de coûts.
- Action : confirmer les listes exactes d’utilisateurs et les dates finales de cutover pour les coachs et les équipes sales ; responsables : Quentin, Wasim et product ops.

11. Nuance de facturation à court terme et factures attendues • 0:27:03

- Une confusion initiale existait sur le fait qu’une facture CLAP finale serait ou non payée ; l’équipe a clarifié que, du fait des cycles SaaS, la prochaine facture de renouvellement pourrait encore être émise mais devrait être la dernière.
- Certaines licences ont augmenté sur le compte à cause de nouvelles recrues commerciales et de licences non désactivées ; cela sera rapproché avant le cutover final.
- Action : rapprocher les licences actives et s’assurer que les licences inutilisées sont désactivées avant le dernier cycle de facturation ; responsables : Quentin et finance.

12. Confusion, contournements et travail dupliqué dans les demandes • 0:29:32

- Plusieurs canaux informels de demande (messages privés, contournement de la roadmap) ont créé de la duplication et de l’incertitude, comme l’illustre le projet leaderboard demandé séparément à plusieurs personnes.
- La chaîne de « téléphone arabe » a provoqué un travail parallèle de plusieurs ingénieurs sur les mêmes tâches, réduisant l’efficacité.
- L’équipe a insisté sur la nécessité de faire respecter la roadmap et le processus PRD pour éviter les contournements ad hoc.
- Action : exiger une PRD claire et un canal unique pour les nouvelles demandes et le ticketing ; responsables : Boris (product lead) et Quentin, à faire respecter avec l’équipe.

13. Leaderboard et écarts de données • 0:34:10

- Sabrina a signalé une incohérence : une vue de la plateforme affichait environ 900 sessions tandis qu’une autre en montrait environ 400, ce qui a conduit à demander la remontée du problème via Annie pour investigation.
- Le leaderboard a nécessité de nombreux ajustements de données dispersés pendant le développement, ce qui a créé de la confusion sur les emplacements de source de vérité.
- Les fonctionnalités livrées pour le leaderboard sont bien présentes sur la plateforme et l’équipe estime que l’implémentation correspond au périmètre demandé.
- Action : Boris doit faire en sorte que Sabrina soumette un rapport formel d’issue / chargement de données à Annie, puis l’équipe technique enquêtera et répondra ; responsables : Sabrina -> Annie, investigation par Quentin / tech.

14. Qualité des données, nettoyage et stratégie dashboards • 0:36:53

- La qualité historique des données était faible en début d’année, mais d’importants efforts de nettoyage et d’uniformisation ont été menés depuis janvier.
- Des écarts subsistent, et certaines données perçues comme « mauvaises » relèvent en réalité d’une mauvaise interprétation du timing ou du cycle de vie du dataset, par exemple lorsqu’un client churn entre deux vues.
- Boris prévoit de construire des dashboards qui s’appuient directement sur la plateforme comme source de vérité unique afin d’éviter une dépendance à des vues Looker incohérentes.
- Action : l’équipe technique doit fournir les endpoints de données de la plateforme et le mapping nécessaire pour les dashboards de Boris ; responsables : Quentin (tech) et Boris (dashboards).

15. Protections des données et contrôles admin par conception • 0:38:08

- Certains champs du cycle de vie, comme la date de fin de programme, sont protégés et ne peuvent être modifiés que par des administrateurs ou des rôles autorisés, avec des logs d’audit pour prévenir les modifications non autorisées.
- Cette conception évite les éditions cachées par les sales ou les coachs qui pourraient fausser les métriques de delivery ou de facturation.
- Action : partager la documentation sur les champs protégés et les permissions par rôle avec les opérations et les sales pour garantir une bonne compréhension ; responsable : Quentin.

16. Gestion des downsells, ajustements et recouvrement • 0:39:07

- La plateforme dispose d’un espace admin dédié aux downsells, arrêts de programme, recouvrement et clôture, où les volumes de sessions et les plans peuvent être ajustés.
- Le processus couvre la transformation du produit d’un client vers un nouveau programme (upsell / downsell) et la personnalisation du nombre de sessions lorsque les clients renégocient après un paiement partiel.
- La finance et Sabrina gèrent actuellement ces ajustements sur le plan opérationnel.
- Action : Quentin renverra le TLA / guide concernant le workflow de downsell et de recouvrement à l’équipe.

17. Demande de statut sur le module concierge • 0:41:31

- Boris a demandé un état des lieux du module concierge et de savoir s’il est bloqué ou en progression.
- Les détails de statut n’ont pas été fournis dans l’extrait, et l’équipe a convenu de produire une mise à jour.
- Action : fournir un état synthétique du module concierge, incluant les blocages, les prochaines étapes et les responsables ; responsables : Quentin et product ops.

18. Finalisation du module concierge et passation • 0:41:54

- Le module concierge est techniquement terminé depuis plus d’un mois et prêt à être intégré au déploiement V2 ; Quentin a confirmé que les équipements et les flux sont complets.
- Le module doit être associé à un compte opérateur dédié plutôt qu’à une personne, afin d’éviter des migrations lors des changements de personnel.
- Les admins peuvent répondre au nom du compte concierge pour éviter des problèmes de gestion lorsque l’opérateur individuel change.
- Un court tutoriel Loom ou Tela suffit pour former la personne qui gérera le module au quotidien.

19. Persona et personnalisation à préparer pour le concierge • 0:44:15

- Une persona pour la voix du concierge a été demandée à Sabrina afin d’améliorer l’engagement initial et le taux de réponse des clients.
- Deux comptes de marque ont été créés (conciergerie@entrepreneurs.com et support@) pour distinguer le concierge destiné aux scaling boards du support générique.
- Le système enverra automatiquement le message d’accueil concierge aux nouveaux clients le lendemain matin de l’onboarding, générant les premiers tickets et tâches.

20. Timing de lancement V2 et flux de tickets attendu • 0:47:42

- Le push V2 remettra le staging à zéro puis générera automatiquement des tickets et tâches en conditions réelles à mesure que les clients interagissent.
- Après le lancement, le travail attendu sera principalement composé de corrections, d’ajustements mineurs et de retours terrain, plutôt que de nouvelles fonctionnalités majeures.
- Les premiers tickets issus des workflows concierge et support sont attendus le lendemain matin du push.

21. Checklist sécurité pour V2 • 0:48:39

- La release V2 doit inclure les correctifs de sécurité coordonnés avec Mohamed et être sécurisée pour le lancement en quelques heures.
- L’équipe a validé le comportement optionnel de la bannière cookies / bannière sur le site afin d’assurer la conformité et l’alignement avec les exigences de confidentialité.

22. Confirmation de l’implémentation cookie / bannière • 0:50:34

- L’affichage optionnel de la bannière cookies a été vérifié et validé pour être cohérent avec les pages de fin / marketing.
- Un message de confirmation sera envoyé à Raph afin de finaliser l’implémentation de la page de fin sur entrepreneurs.com.

23. Planification de la roadmap et priorités de septembre • 0:51:04

- Les priorités majeures de septembre sont la stratégie de monétisation / commercialisation, les efforts R&D « moonshot », et l’amélioration de l’adoption produit ainsi que de l’usage de l’intelligence de revenus.
- Un appel dédié à la monétisation doit être programmé pour définir les verticales, les actions et les responsabilités avant la fin septembre.
- La roadmap jusqu’à fin septembre est jugée stable, avec de la place pour une ou deux petites fonctionnalités additionnelles.

24. Gaps de responsabilité sur l’annuaire / marketplace fournisseurs • 0:52:17

- Le projet d’annuaire de prestataires est resté sans propriétaire après le départ d’Aziz et manque aujourd’hui de pilotage actif malgré une demande persistante.
- Les approches passées, notamment le flux marketplace inversé, ont augmenté les demandes entrantes et doivent être réévaluées pour améliorer les conversions et la monétisation.
- Action : la direction produit doit attribuer un responsable au projet.

25. Périmètre et risques du projet Moonshot R&D • 0:55:17

- Le projet Moonshot vise à capturer en profondeur l’activité des clients (applications, suivi du temps, appels) afin de générer des insights exploitables, et nécessitera une R&D substantielle jusqu’au moins janvier.
- Le projet soulève des enjeux de sécurité, de confidentialité et d’adoption qui devront être résolus avant un déploiement large.
- Des décisions sont nécessaires sur le format du produit (appareil, application mobile ou intégrations), le pricing et le recrutement de testeurs bêta internes et clients.

26. Daily Accountability Agents et fonctionnalités communauté • 0:58:40

- La fonctionnalité Daily Accountability Agents progresse et sera intégrée à d’autres travaux d’outillage communautaire menés avec Abdel.
- Un MVP a été préparé pour la phase bêta d’Abdel et devrait être prêt à recevoir les retours utilisateurs d’ici fin septembre.

27. Programmation de l’appel monétisation / roadmap • 1:00:36

- L’équipe a accepté de programmer un appel de 45 minutes, ou 30 minutes si nécessaire, pour se concentrer d’abord sur la monétisation de la plateforme et définir les actions immédiates.
- Les participants principaux proposés sont Boris, Fabrice, Jordan, Alec et Quentin afin de garder une discussion ciblée et actionnable.
- L’appel devrait avoir lieu dans la semaine à venir ou au plus tard début octobre afin de finaliser les livrables de septembre.

28. Présence à l’événement Core Team Building • 1:03:29

- Quentin a confirmé qu’il ne participera pas à l’événement Core Team Building à Marrakech et qu’il en informera Fabrice et Sabrina.
- Boris a confirmé qu’il suit l’organisation de l’événement et supervise la logistique.
%% notes:fin %%
