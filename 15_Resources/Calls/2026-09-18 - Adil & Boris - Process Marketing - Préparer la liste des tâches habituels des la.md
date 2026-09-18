---
type: call
date: 2026-09-18
source: sembly
participants: ["adil.ziane@entrepreneurs.com", "boris@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Adil & Boris - Process Marketing - Préparer la liste des tâches habituels des lancements Adil

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (18/09/2026 14:24).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 18/09/2026 14:24 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a convenu de standardiser des checklists réutilisables et un tableau de bord unique faisant foi pour les événements récurrents et les lancements marketing, afin de clarifier les responsabilités et d’améliorer la fiabilité des données. Boris doit livrer des dashboards centralisés et gérer les imports du SDR Hub, tandis qu’Adil fournira les Google Sheets et confirmera les mappings de champs.

La réunion a également couvert l’import de listes, la création et le suivi d’événements, la synchronisation des leads et des bookings, ainsi que les risques d’intégration liés à Customer.io, iClosed, Twilio et à la migration des landing pages en interne. L’équipe a insisté sur la nécessité d’un mode de fonctionnement centralisé pour les SDR, d’une nomenclature UTM cohérente, d’un traitement robuste des désinscriptions / STOP RGPD, et de tests de charge avant les lancements d’octobre / novembre.

📋 Outline

1. Objectif de créer des checklists répétables et une responsabilité claire pour les événements et les lancements • 0:01:18

- L’objectif principal est de construire des checklists pour les tâches récurrentes (recrutement, événements physiques, webinars, ateliers du mardi) afin que les équipes puissent réutiliser les processus et capitaliser sur le travail déjà effectué ; responsabilité : Boris pour définir la structure de la checklist.
- Les checklists doivent préciser qui fait quoi et à quel moment par rapport aux dates limites finales, afin de lever toute ambiguïté ; responsabilité : Boris et les propriétaires de projets.
- L’état cible est une checklist J-30 qui puisse être ouverte et exécutée de bout en bout pour n’importe quel événement ; responsabilité : Boris pour l’implémenter et partager des modèles.

2. Problème actuel avec plusieurs sources de données et besoin d’une source de vérité unique • 0:04:21

- Plusieurs systèmes (SDR Hub, iClose, HubSpot, Customer.io, Meta Pixel) remontent aujourd’hui des métriques incohérentes, par exemple sur les calls bookés, ce qui crée de la confusion ; responsabilité : Adil et Boris pour réconcilier les sources.
- L’équipe doit décider quel système est la source de référence pour chaque métrique afin d’éviter les chiffres contradictoires ; responsabilité : Boris pour proposer, Adil pour valider.
- Le risque immédiat est de prendre des décisions opérationnelles faussées à cause d’écarts de chiffres pendant les lancements et les challenges ; responsabilité : toutes les parties prenantes pour adopter la source de vérité convenue.

3. Dashboards centralisés comme source de vérité retenue • 0:05:55

- Boris construit des dashboards qui recroiseront et normaliseront les données de toutes les plateformes, avec une mise à disposition estimée à environ dix jours ; responsabilité : Boris et son équipe analytics.
- Le dashboard inclura une synthèse au niveau événement (leads, spend, calls bookés, commerciaux assignés, revenu) ainsi qu’une vue performance par publicité (opt-ins, calls générés, revenu par annonce) pour permettre des analyses détaillées ; responsabilité : Boris pour configurer les drill-downs.
- Les dashboards afficheront les états du funnel d’appels (volume, tentatives de contact, stades de reprogrammation R1–R3, engagés), en reflétant le pipeline des closers ; la précision dépendra de la bonne mise à jour du pipeline par les humains ; responsabilité : SDR et closers pour maintenir les pipelines à jour.
- Les métriques de performance SDR devront être affinées, car les chiffres actuels ne sont pas totalement exacts ; responsabilité : Boris pour améliorer les métriques, managers SDR pour assurer la qualité des données.

4. Nécessité d’un workflow SDR Hub consolidé et d’une utilisation imposée • 0:11:42

- Les SDR doivent désormais utiliser exclusivement le SDR Hub afin de maintenir la précision du tracking et d’éviter la fragmentation ; responsabilité : les team leads SDR pour faire respecter cette règle.
- Le SDR Hub détecte automatiquement le contexte du lead et redirige “Book a call” vers le bon lien tracké (Evergreen, événements live, funnels), ce qui évite aux SDR de gérer manuellement plusieurs liens ; responsabilité : Boris / engineering pour maintenir le système, SDR pour l’adopter.
- Si les SDR continuent à utiliser des systèmes externes, le tracking se cassera et des données seront perdues ; responsabilité : managers SDR pour communiquer et contrôler la conformité.

5. Processus d’import des Google Sheets dans le SDR Hub • 0:12:50

- Le workflow attendu consiste à partir d’une structure de Google Sheet de base et à créer un nouvel onglet pour chaque import, plutôt que de créer de nouveaux formats de fichiers ; responsabilité : Adil pour respecter la structure, Boris pour importer.
- Boris fera le mapping des colonnes lors de l’import et peut créer de nouveaux mappings / champs si des données supplémentaires sont fournies ; responsabilité : Boris pour effectuer le mapping et documenter les correspondances.
- Adil peut ajouter des colonnes supplémentaires qui ne seront pas importées ; Boris décidera quelles colonnes importer en fonction des champs du SDR Hub ; responsabilité : Boris pour filtrer et mapper, Adil pour confirmer les champs nécessaires.
- Pour les listes urgentes déjà appelées par les SDR, l’équipe doit vérifier si la feuille a bien été importée afin d’éviter les doublons de relance ; responsabilité : Alex / ops SDR pour confirmer le statut d’import.

6. Test immédiat d’import de données et boucle de feedback • 0:14:23

- Adil a envoyé une Google Sheet via Slack pour que Boris l’importe et la valide, et a demandé un retour afin de savoir si l’import est correct et prêt pour les SDR qui ont déjà commencé à appeler ; responsabilité : Adil pour envoyer le fichier, Boris pour importer et faire un retour.
- La feuille d’exemple contenait le prénom, l’email et deux champs téléphone, et Boris a confirmé qu’il pouvait mapper et réduire aux champs nécessaires ; responsabilité : Boris pour mapper le champ téléphone et normaliser les noms.
- Boris ajoutera des notes dans les mappings pour expliquer des champs comme “revenue band” et “maturity level” afin que les imports futurs soient cohérents ; responsabilité : Boris pour documenter les mappings.

7. Doublons de leads et mapping des champs profil / maturité • 0:17:25

- L’import a montré que la plupart des enregistrements étaient déjà connus du système et que seulement 14 étaient nouveaux, ce qui explique les écarts apparents dans les volumes de leads ; responsabilité : Boris pour identifier les doublons et reporter le caractère unique.
- Les champs fréquents à mapper incluent la situation professionnelle, la tranche de revenus, le niveau de maturité, les objectifs, les défis, le coaching déjà réalisé et les angles de call suggérés aux SDR ; responsabilité : Boris pour mapper les champs et l’équipe SDR pour utiliser les angles d’appel.
- Les valeurs de tranche de revenus doivent suivre les buckets établis dans le SDR Hub (par ex. 10 000–50 000) plutôt que des nombres en texte libre, afin de rester analysables ; responsabilité : Adil pour formater les valeurs en conséquence et Boris pour faire respecter les conventions.
- Le “niveau de maturité” provenait historiquement d’exports CTO et doit être standardisé dans les mappings pour être utilisé de manière cohérente ; responsabilité : Boris pour standardiser et documenter.

8. Import de listes et création d’événements • 0:22:08

- De nouvelles listes peuvent être importées dans le système pour ajouter des leads à un événement ou une campagne spécifique, et les événements sont créés depuis l’interface événement en saisissant le nom de l’événement, le type (webinar ou challenge), la date de début et la campagne UTM ; responsabilité : Boris pour guider la mise en place, Adil pour créer l’événement.
- Le lien iClosed associé à la campagne doit être fourni et recevra les paramètres UTM (source, medium, campaign) pour le tracking ; responsabilité : Adil pour fournir le lien iClosed, Boris pour aligner la structure UTM.
- Les événements sont marqués actifs ou fermés selon le nombre de leads traités ; responsabilité : le propriétaire de l’événement (Adil) pour mettre à jour le statut.

9. Timing d’import des leads et options d’automatisation • 0:23:04

- La préférence est d’importer les leads automatiquement lorsqu’une personne s’inscrit, ou au minimum chaque nuit une fois le premier live lancé, afin que les SDR aient les listes dès le lendemain matin ; responsabilité : Cedric / Quentin pour confirmer l’automatisation, Boris pour coordonner.
- Les bookings live doivent être détectés automatiquement et retirés de la liste SDR afin d’éviter les relances en double ; responsabilité : l’équipe technique (Quentin) pour implémenter la synchronisation.

10. Gestion des leads VIP / 500K et priorisation • 0:24:29

- Les leads VIP ou 500K doivent être signalés et placés en tête des files SDR avec des alertes prioritaires et un statut de lead-show maximal, en raison de leur valeur plus élevée ; responsabilité : Boris pour assurer le tracking et la configuration des alertes.
- Le funnel et la segmentation des événements doivent permettre de distinguer les leads 500K d’un événement à l’autre pour une attribution précise ; responsabilité : Boris et data engineering (Quentin) pour implémenter la segmentation.

11. Synchronisation Customer.io, iClosed et segment des calls bookés • 0:25:49

- Adil ne dispose pas d’un segment fiable dans Customer.io pour les personnes ayant déjà booké un call, ce qui provoque l’envoi inutile d’emails de rappel ; responsabilité : Adil pour définir le segment nécessaire, Boris / Quentin pour implémenter la synchro avec iClosed.
- Il faut vérifier si Customer.io est bien connecté à iClosed et qu’un segment “call booked” est disponible pour exclure ces contacts des envois de campagne ; responsabilité : Boris pour revérifier les intégrations existantes et les reconnecter si elles sont en pause.

12. Désinscription, RGPD et gestion du STOP multi-canal • 0:28:14

- Il existe des risques de délivrabilité et de conformité, car les désinscriptions retirent actuellement les contacts d’une seule liste seulement, ce qui a déjà entraîné des avis Trustpilot négatifs et des problèmes de compte ; responsabilité : Adil et Boris pour traiter le sujet avec le légal / la tech.
- Les SMS et autres canaux (Twilio, WhatsApp) doivent gérer correctement les mots-clés STOP sur tous les points de contact, car des tests manuels ont montré que des contacts recevaient de nombreux messages sans opt-out efficace ; responsabilité : Boris pour revoir les webhooks et la configuration Twilio, Adil pour fournir des exemples.
- Une automatisation robuste de désinscription avec filtres doit être mise en place pour garantir un vrai opt-out global et protéger la réputation ; responsabilité : Boris et engineering (Quentin) pour créer l’automatisation.

13. Prospection SDR pour ateliers vs webinars et suivi des commissions • 0:32:53

- Les SDR appellent aujourd’hui à la fois pour faire venir des personnes aux ateliers du mardi et pour convertir des participants qui n’ont pas booké de call, et le tracking doit différer car les conversions ne sont pas les mêmes (présence vs call booké) ; responsabilité : Adil pour continuer à utiliser Google Sheets pour les invitations aux ateliers, Boris pour conseiller sur le tracking à long terme.
- Il n’existe pas aujourd’hui d’attribution ni de commission pour les SDR qui amènent simplement des participants aux événements, et un modèle d’incitation ou un mécanisme de suivi pourrait être envisagé pour des raisons d’équité ; responsabilité : sales ops et la direction pour définir la politique, Boris pour proposer des options techniques.

14. Migration des landing pages en interne, APIs et risques de load testing • 0:35:13

- Cédric souhaite migrer de Framer vers des outils internes, et le nouveau système peut centraliser les données mais nécessite du travail API et des paramètres que Quentin doit configurer ; responsabilité : Quentin pour les API / connecteurs, Boris pour préciser les besoins en données.
- Le risque majeur est la capacité / charge de la nouvelle infrastructure de landing, car certains événements peuvent générer des milliers d’opt-ins simultanés et doivent être validés par des tests de stress avant les lancements d’octobre / novembre ; responsabilité : engineering (Quentin) pour exécuter les tests de charge et fournir des estimations de capacité, Boris pour plaider en faveur d’un déploiement progressif.
- L’approche recommandée est un test par étapes sur des événements plus petits (par ex. le webinar du mardi) afin de valider les opt-ins, le tracking et les cas limites avant un lancement à grande échelle ; responsabilité : Adil pour planifier les tests et Boris / Quentin pour soutenir.

15. Alertes en temps réel, notifications SDR et tests de lancement • 0:39:02

- Les leads à forte valeur (500K) déclenchent des alertes sonores et apparaissent dans une file très visible pour être traités rapidement dans une fenêtre de cinq minutes ; responsabilité : l’équipe SDR pour répondre, Boris pour vérifier le comportement des alertes.
- Avant le lancement d’octobre, il faut réaliser des tests de démarrage de 15 minutes avec Alex et Boris pour confirmer le flux d’opt-in, la nomenclature du funnel et le bon affichage des alertes avec les bons noms de funnel ; responsabilité : Adil pour planifier la session de test, Boris et Alex pour participer.
- Il faut s’assurer que l’automatisation du canal (par ex. canal 651) et les listes de tâches dans Work sont activées et assignées, afin que les tâches de lancement et les deadlines soient visibles par toutes les parties prenantes ; responsabilité : Adil pour taguer les personnes dans Work, Boris pour suivre ses tâches assignées.

16. Convention de nommage UTM et alignement entre les outils • 0:42:20

- Le nommage UTM principal doit venir d’Adil (naming des événements Customer.io) et être utilisé à l’identique dans le tracking iClosed, les bookings SDR, les calls live et les calls CTO afin d’assurer une attribution cohérente ; responsabilité : Adil pour définir le nom canonique, Boris pour faire respecter la cohérence du tracking.
- Il faut utiliser une nomenclature claire et logique (par ex. nom-date), suffisamment complète sans être excessivement longue, pour éviter la confusion dans les futures campagnes ; responsabilité : Adil pour proposer le format de nommage, Boris pour le valider.

17. Accès, prochaines étapes et suivis • 0:43:48

- Boris a déjà donné accès aux dashboards présentés et reverra les webhooks ainsi que la gestion des désinscriptions pour faire un retour la semaine suivante ; responsabilité : Boris pour le suivi.
- Adil continuera à utiliser Google Sheets pour les ateliers du mardi pour le moment et relancera Boris la semaine suivante si besoin pour l’unsubscribe / RGPD et la gestion STOP Twilio ; responsabilité : Adil pour le suivi et la coordination des tests avec Boris.
%% notes:fin %%
