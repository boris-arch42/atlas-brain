---
type: call
date: 2026-08-07
source: sembly
participants: ["yohan@betonyou.co", "selim@betonyou.co", "[[Boris Arduy]]"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-08-07
---

# Hubspot - Bet On You

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (07/08/2026 11:00).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 07/08/2026 11:22 — corrige librement hors des marqueurs.

**Résumé** — Call de conseil CRM pour le projet BetoNew/BeExplorer (matching athlètes-entreprises). Boris recommande de démarrer avec Pipedrive plutôt que HubSpot, en capturant d'abord les données dans Excel avant migration, avec deux pipelines distincts (athlètes/entreprises) et automatisation progressive (enregistrement appels, contrats, scoring IA).

**Décisions**
- Recommandation de Pipedrive comme CRM de démarrage plutôt que HubSpot pour sa simplicité
- Deux pipelines CRM séparés : un pour les athlètes, un pour les entreprises
- Stratégie Excel d'abord puis import CRM pour itérer sur le schéma de données
- Enregistrement systématique de tous les appels commerciaux et d'accompagnement
- Automatisation complète du flux contrat (génération, signature, archivage)
- Lead scoring basé sur l'avatar idéal et le timing de reconversion
- Utilisation future d'IA (Claude) pour scorer automatiquement les intentions depuis les enregistrements d'appels
- Plan de réchauffement email démarrant à ~10 emails/jour avec domaine dédié marketing

**Actions**
- [ ] **Équipe BetoNew** : Finaliser le schéma Excel avec champs CRM minimaux pour athlètes et entreprises
- [ ] **Équipe BetoNew** : Décider officiellement de l'adoption de Pipedrive vs autre CRM
- [ ] **Équipe BetoNew** : Définir les champs obligatoires par stade de pipeline pour déclencher les automatisations
- [ ] **Équipe BetoNew** : Concevoir le workflow manuel initial de matching athlètes-entreprises
- [ ] **Équipe BetoNew** : Mettre en place le domaine dédié et le plan de réchauffement email
- [ ] **Équipe BetoNew** : Préparer le message de consentement RGPD pour enregistrement d'appels

**Risques & vigilances**
- Sur-ingénierie initiale : risque de complexifier trop tôt la stack technique avant d'avoir validé le volume
- Coûts croissants des automatisations HubSpot si choix de cet outil sans planification budgétaire
- Adoption CRM limitée si les commerciaux ne sont pas assez formés ou accompagnés (besoin onboarding + process clairs)
- Délivrabilité email compromise si réchauffement insuffisant ou domaine principal utilisé pour marketing
- Conformité RGPD sur enregistrement appels et données sensibles athlètes à sécuriser
- Migration CRM future coûteuse (4-5k€) si schéma de données mal défini au départ

Tags : #crm #pipedrive #hubspot #betonyou #automatisation #lead-scoring #matching
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 07/08/2026 11:00 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a passé en revue le projet BetoNew / BeExplorer et ses besoins opérationnels, avec un consensus clair sur le fait qu’un CRM est nécessaire dès le départ pour structurer les données des athlètes et des entreprises. La discussion a porté sur le choix de l’outil (HubSpot, Pipedrive, ou une solution légère temporaire basée sur Excel/Cloud), sur l’architecture de données à prévoir pour le matching, sur les automatismes à mettre en place (scoring, enregistrement des appels, contrats, suivis), ainsi que sur les besoins d’onboarding et de processus pour les équipes commerciales et opérationnelles. La recommandation dominante a été de commencer simple, avec une structure de données propre et un CRM léger si besoin, puis de migrer vers une solution plus robuste lorsque le volume et la complexité augmenteront.

📋 Outline

1. Présentations et objectif de la réunion • 0:00:23

- Les participants se sont présentés et ont confirmé leurs liens avec Saint-Étienne afin d’installer le contexte et la relation de confiance.
- Boris Arduy a cadré la réunion, expliqué qu’il avait reçu un briefing d’Alec, et indiqué qu’il était prêt à adapter l’échange aux besoins de l’équipe.

2. Vue d’ensemble du projet BetoNew / BeExplorer • 0:03:19

- BetoNew vise à accompagner les athlètes de haut niveau dans leur transition de carrière à travers un écosystème dont l’outil numérique principal est BeExplorer.
- BeExplorer doit collecter des données détaillées sur les athlètes, faire passer des évaluations et fournir des recommandations de trajectoires professionnelles, de formation ou d’entrepreneuriat.
- La plateforme combine des recommandations digitales avec un accompagnement humain assuré par des conseillers, pour orienter les athlètes vers trois voies : emploi, formation ou entrepreneuriat.

3. Modèle de données et sorties attendues de BeExplorer • 0:05:19

- Les athlètes rempliront un profil et un questionnaire de 60 à 100 questions, générant des résultats sur les compétences, les soft skills et une présélection de métiers et de plans d’action.
- Le système doit enregistrer les coordonnées de l’athlète, ses aspirations, ainsi que les résultats du moteur d’adéquation, car ces éléments seront essentiels pour les mises en relation avec les employeurs.
- La plateforme publique / communautaire (Movement) collectera des données plus légères sur les entreprises, les individus et les partenaires, principalement pour l’engagement et les communications.

4. Flux business et segments cibles (B2C et B2B) • 0:08:39

- BeExplorer fonctionnera principalement en B2C pour onboarder les athlètes, tandis que la partie Movement et l’engagement des entreprises relèveront d’une logique B2B, via outreach et campagnes d’e-mailing.
- L’objectif final est de matcher efficacement les athlètes avec les besoins des entreprises afin de réduire le temps et le coût, tout en augmentant la satisfaction des deux côtés.
- Johan a déjà commencé à activer son réseau pour recruter des athlètes et générer une première traction avant le lancement.

5. Nécessité d’un CRM et de la structuration des données dès le premier jour • 0:10:24

- L’équipe a conclu qu’un CRM est indispensable dès le départ pour stocker les contacts, suivre l’engagement et permettre la réactivation future des athlètes et des entreprises.
- Le CRM doit gérer deux flux de données distincts : les profils / évaluations des athlètes et les contacts entreprises / partenaires.
- La solution initiale n’a pas besoin d’être très complexe, mais elle doit capturer les champs essentiels pour permettre le matching et les relances.

6. HubSpot : avantages et limites pour ce projet • 0:11:51

- HubSpot est perçu comme très complet et flexible, avec de nombreuses intégrations et des fonctionnalités avancées adaptées à une montée en charge.
- Sa profondeur peut toutefois compliquer l’usage pour des profils non techniques et exiger une plus forte appétence technique chez les commerciaux ou des rôles de soutien additionnels.
- Les coûts liés à l’automatisation et aux fonctionnalités avancées peuvent rapidement augmenter, d’où la nécessité d’un budget et d’une adoption par paliers.

7. Alternatives et approche de déploiement par étapes • 0:13:05

- Un démarrage léger avec des outils Cloud + Excel (ou Airtable / Sheets) est une option viable à court terme pour capturer les données et tester les flux avant de s’engager sur HubSpot.
- Il est envisageable de prototyper en quelques jours un CRM léger sur mesure afin de valider les champs nécessaires et les processus avant de migrer vers un CRM complet.
- L’équipe devrait aussi évaluer Pipedrive comme alternative plus simple à prendre en main si HubSpot s’avère trop lourd pour les utilisateurs des premiers mois.

8. Rôles de l’équipe, onboarding et besoins de processus • 0:14:37

- Si des commerciaux sont recrutés, il faudra soit des profils avec une sensibilité technique, soit associer les closer à un assistant commercial pour gérer la saisie CRM.
- Des supports d’onboarding simples, comme des Looms enregistrés et des documents de प्रक्रिया structurés, ainsi qu’une formation pratique d’une heure, peuvent fortement améliorer l’adoption par des utilisateurs non techniques.
- L’équipe doit définir des processus de base et les champs CRM obligatoires associés à chaque étape du cycle commercial et relationnel pour assurer une utilisation homogène.

9. Champs de données MVP et stratégie de capture • 0:17:33

- Salim a présenté une liste simplifiée de champs qu’ils souhaitent capturer automatiquement depuis l’onboarding BeExplorer, et a demandé lesquels sont réellement indispensables pour le MVP CRM.
- L’équipe s’est accordée sur la nécessité de définir un ensemble minimal de champs athlètes et entreprises à pousser automatiquement vers le CRM pour le premier matching et les premières relances.
- Le choix de l’outil cible (HubSpot, Pipedrive ou Cloud + Excel) dépendra de la facilité d’automatisation, du coût et du niveau d’adoption utilisateur requis.

10. Choix du CRM : Pipedrive versus HubSpot • 0:18:37

- Boris a estimé que Pipedrive est plus intuitif et probablement suffisant pour les besoins actuels et une phase de croissance significative avant d’atteindre ses limites.
- HubSpot propose des fonctionnalités comparables, mais pourrait être surdimensionné pour les besoins actuels et revenir plus cher en coût par licence.
- Commencer avec Excel, puis migrer plus tard, a été présenté comme une option pertinente pour économiser des coûts de souscription au démarrage.

11. Stratégie de collecte de données : Excel d’abord, import ensuite • 0:19:33

- Centraliser au départ les données dans un Excel structuré permet d’itérer facilement et d’importer ensuite vers Pipedrive ou HubSpot en mappant les champs.
- Un Excel correctement défini facilitera la réimportation, car les CRM savent faire correspondre les colonnes aux champs CRM.
- L’équipe doit itérer sur le schéma Excel pour ajouter ou affiner les champs avant de s’engager sur un CRM, afin de gagner du temps de paramétrage plus tard.

12. Migration CRM et estimation des coûts • 0:21:07

- La migration entre Pipedrive et HubSpot est jugée faisable, et HubSpot propose parfois des outils natifs qui simplifient le transfert.
- Les coûts de migration professionnels en France ont été estimés autour de 4 000 à 5 000 euros, avec des tarifs plus faibles possibles via des équipes offshore.
- Les éditeurs, comme HubSpot, ont intérêt à accompagner les clients quand ils changent d’échelle, y compris via des crédits ou de l’assistance experte.

13. Architecture CRM : pipelines séparés et structure contacts / deals • 0:24:01

- Deux pipelines distincts doivent être mis en place : un pour les athlètes et un pour les entreprises, car leurs étapes, colonnes et cycles de vie sont différents.
- Pour chaque personne ou entité, il faut créer à la fois une fiche contact et une fiche deal ; la fiche deal est l’objet qui progresse dans les étapes du pipeline.
- Les champs du pipeline doivent être organisés par couches : données de contact, champs propres au deal, puis champs obligatoires liés au stade du processus.

14. Logique de matching et lien entre bases de données • 0:26:50

- Le matching repose sur le rapprochement de champs communs, par exemple des champs liés au métier, entre les bases athlètes et entreprises afin de produire des correspondances automatiques lorsque les valeurs coïncident.
- Il faut utiliser une clé cohérente ou une colonne partagée entre les tables pour permettre les jointures et les correspondances automatiques entre les préférences des athlètes et les besoins des entreprises.
- Une troisième base « deals » doit enregistrer les matchs proposés (athlète ↔ entreprise), suivre les démarches de contact et documenter les résultats de placement.

15. Enregistrement des appels et traçabilité • 0:27:39

- Tous les appels commerciaux et d’accompagnement doivent être enregistrés afin de constituer une base de connaissances qui améliorera les scripts et les performances commerciales dans le temps.
- Les enregistrements doivent être reliés aux fiches contact / deal du CRM pour conserver une traçabilité complète des interactions et des décisions.
- Les replays d’appels serviront à la formation, au contrôle qualité et à conserver l’historique contextuel pour les échanges futurs.

16. Automatisation des contrats et champs obligatoires • 0:28:43

- Certains champs liés au contrat doivent être rendus obligatoires avant de faire passer un deal au stade « Engaged », afin de déclencher la génération et l’envoi automatisés du contrat.
- Le flux contrat doit être automatisé de bout en bout : envoi, signature, puis archivage du document signé dans le drive ou le CRM, sans intervention manuelle.
- Les champs contractuels requis pour les athlètes et les entreprises doivent être définis en amont pour permettre le mapping et les workflows documentaires automatisés.

17. Onboarding, paiement, partenaires et planification des rendez-vous • 0:30:12

- L’onboarding des athlètes comprend un parcours en ligne se terminant par un paiement Stripe et un e-mail de confirmation pouvant délivrer automatiquement des documents.
- Les pages d’atterrissage partenaires (entrepreneur.com, OpenClassrooms, partenaire de placement) doivent orienter les utilisateurs vers le système et diriger les dossiers vers les interlocuteurs dédiés.
- Chaque athlète réalise un appel final avec un conseiller entreprise ; cet appel doit capturer la motivation, la trajectoire préférée, le timing de reconversion et les prochaines étapes recommandées.
- Des intégrations de type Calendly, ou équivalent, doivent être utilisées pour planifier les appels et relier les réservations aux enregistrements CRM pour le suivi.
- Le timing de recontact, par exemple dans 3 ou 6 mois, doit être enregistré comme champ CRM afin d’automatiser les futures relances pour les athlètes non prêts immédiatement.

18. Lead scoring et processus de qualification • 0:31:42

- Le lead scoring doit être basé sur les réponses au formulaire et sur un « avatar idéal » afin de prioriser rapidement les leads correspondant au profil cible, pour les athlètes comme pour les entreprises.
- Le scoring doit refléter la maturité et la motivation, par exemple le timing pour démarrer la transition ou le niveau de confiance dans la voie choisie, afin d’orienter l’urgence du suivi.
- Ce système permettra d’identifier les leads à traiter intensivement par la vente et ceux à entretenir ou à recontacter plus tard.

19. Options de matching des athlètes et approche de scoring • 0:38:50

- La plateforme présentera trois issues possibles pour les athlètes : rejoindre une entreprise, devenir entrepreneur avec un accompagnement, ou être mis en relation avec des entreprises partenaires via le matching des compétences.
- Un système de scoring / flagging a été proposé pour classer l’intention des athlètes, par exemple 9/10 pour des profils déjà décidés à entreprendre, 6/10 pour des profils encore indécis.
- Le scoring initial peut être fait manuellement puis automatisé plus tard grâce aux enregistrements d’appels et à des modèles d’IA capables d’extraire l’intention et d’attribuer des scores.
- Le matching devra rapprocher les compétences et trajectoires des athlètes des besoins des employeurs, ces derniers demandant activement à recruter des athlètes.

20. Enregistrements d’appels, automatisation et scoring assisté par IA • 0:40:33

- Boris a recommandé d’enregistrer les appels puis d’utiliser une IA, comme Claude ou un équivalent, pour analyser les enregistrements et attribuer automatiquement des scores d’intention selon des paramètres définis.
- Les enregistrements apportent un contexte riche pour les relances, par exemple en se souvenant des résultats de compétition de l’athlète, et améliorent la personnalisation des échanges ultérieurs.
- Le consentement doit être obtenu au début de l’appel, avec un message introductif indiquant que l’appel est enregistré ; c’est une pratique standard qui réduit le risque juridique.
- L’équipe a souligné le faible taux de refus habituel, tout en rappelant l’importance de la conformité RGPD puisque l’entreprise est basée en France.

21. Gestion des automatisations et offre d’assistance de Boris • 0:41:53

- Selim a demandé qui gérerait les automatisations ; Boris a expliqué qu’il dispose d’une équipe opérations à distance et qu’il possède lui-même les compétences techniques nécessaires.
- Boris a proposé d’aider sur les besoins techniques plus avancés ou sur le déploiement si l’équipe souhaite mobiliser ses ressources OPS.
- L’équipe devra préciser le périmètre si elle veut recourir à ce support.

22. Recommandation CRM et flux d’automatisation clés • 0:44:26

- Boris a recommandé de démarrer avec Pipedrive pour sa simplicité et ses fonctionnalités principales, plutôt qu’avec un système plus lourd comme HubSpot, tout en gardant la possibilité d’une solution sur mesure plus tard.
- Les étapes d’automatisation de base ont été décrites : une réservation via Calendly / iClosed crée un contact dans le CRM ; les réponses au formulaire se mappent sur les champs contact ; le système affecte ensuite le lead au closer qui a réservé le créneau.
- Les automatisations déclenchées doivent inclure l’envoi du contrat ainsi que les workflows post-« deal won », qui lancent la facturation et l’accès aux outils.
- Pipedrive a été mis en avant pour ses statistiques intégrées et ses intégrations natives, réduisant le besoin d’outils d’automatisation externes.

23. Campagnes e-mail, suivi et choix des outils • 0:47:34

- Pipedrive permet d’envoyer des campagnes e-mail et de suivre les ouvertures / clics, ce qui est suffisant pour des volumes modestes en phase initiale ; pour de très gros volumes, des outils spécialisés comme Customer.io ou ActiveCampaign peuvent être envisagés.
- Au démarrage, utiliser les campagnes de Pipedrive est une option raisonnable, et cela permet d’enregistrer l’attribution des campagnes directement sur la fiche contact.
- Lorsqu’un outil externe est utilisé, le CRM doit capturer la campagne à l’origine de la conversion plutôt que chaque événement d’ouverture individuel.
- L’équipe doit mettre en place un réchauffement de la boîte d’envoi et utiliser un domaine dédié pour le marketing afin d’éviter les problèmes de délivrabilité.
- Le plan de réchauffement proposé consiste à commencer avec environ 10 e-mails par jour, puis à augmenter progressivement sur plusieurs jours ou semaines pour éviter que le domaine soit signalé.

24. Volume de données et complexité progressive • 0:50:10

- Boris a insisté sur le fait que les opérations en phase initiale n’ont pas besoin d’une pile technologique très complexe : il faut démarrer léger et ajouter de la complexité au fur et à mesure de la montée en volume.
- L’équipe doit éviter de sur-ingénierier dès le premier jour et n’introduire des suivis avancés ou des modules additionnels que lorsqu’ils sont justifiés par le trafic ou le volume des campagnes.
- Boris a expliqué que sa propre entreprise utilise des pipelines avancés en raison d’un grand nombre de campagnes et de volumes élevés, mais a conseillé à Run d’adopter d’abord une configuration plus simple.

25. Reporting, intégrations et expérience utilisateur • 0:53:13

- Pipedrive propose un module de reporting et de statistiques graphiques plus simple que HubSpot, mais suffisant pour suivre la performance.
- L’équipe doit privilégier les intégrations natives de Pipedrive quand elles existent, afin de réduire la dépendance à Zapier ou Make et de simplifier la maintenance.
- Les commerciaux ont surtout besoin d’un accès direct aux informations de deal, aux numéros de téléphone et au statut de relance ; l’interface doit donc mettre ces éléments en priorité.

26. Prochaines étapes, contacts et soutien • 0:56:02

- Le groupe a convenu de rester en contact et Boris a réitéré sa disponibilité pour aider ; les participants conserveront son numéro pour les questions de suivi.
- Les actions immédiates suggérées sont : décider de l’adoption de Pipedrive, préciser les besoins de synchronisation pour la messagerie privée, concevoir les champs initiaux de scoring et le workflow manuel de matching, et planifier le réchauffement des e-mails.
- L’équipe doit maintenant attribuer les tâches et fixer les délais associés.
%% notes:fin %%
