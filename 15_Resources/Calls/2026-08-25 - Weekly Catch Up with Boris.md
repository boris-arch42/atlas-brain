---
type: call
date: 2026-08-25
source: sembly
participants: ["[[Boris Arduy]]", "aman.verma@entrepreneurs.com", "venugopal.venkatesan@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-08-25
---

# Weekly Catch Up with Boris

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (25/08/2026 11:06).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 25/08/2026 11:11 — corrige librement hors des marqueurs.

**Résumé** — Point hebdomadaire sur le projet Data Dashboard avec définition des 4 priorités clés (création de 15 tables, connexion Adspend, tracking visiteurs, menu utilisateur et UTM). Boris reprend la propriété du projet pour centraliser la coordination inter-équipes compte tenu de la complexité et du nombre de parties prenantes.

**Décisions**
- Boris reprend la propriété du projet Data Dashboard pour centraliser la coordination
- Thomas livrera aujourd'hui le dataset et les documents de structure des 15 tables
- Pas de modification architecture serveur pendant le lancement actif (300k€ dépenses publicitaires)
- Création d'un canal WhatsApp avec Thomas pour synchroniser les questions schéma-table

**Actions**
- [ ] **Thomas** : Créer les documents de données et ressources pour les 15 tables de base de données (échéance 2026-08-25)
- [ ] **Boris** : Créer le canal WhatsApp avec Thomas et y ajouter Aman (échéance 2026-08-26)
- [ ] **Boris** : Faire le suivi avec le marketing pour provisionner les accès Business Manager et comptes publicitaires à Venugopal (échéance 2026-08-27)
- [ ] **Venugopal** : Connecter les données Ads/Adspend au Data Dashboard pour les tunnels Evergreen (Book Funnel, Quiz Funnel, Week of Scale)
- [ ] **Aman** : Vérifier la faisabilité de l'option tracking côté serveur et faire un retour

**Risques & vigilances**
- Bug de tracking entre opt-in et enregistrement nécessitant un délai de 2-2,5 secondes
- Accès Meta limité pour Venugopal empêchant la visibilité complète des comptes publicitaires
- Risque de surcharge avec 30-40 projets simultanés nécessitant des recrutements
- Dépendance forte sur la livraison de Thomas pour débloquer le travail des agents

Tags : #data-dashboard #agents-livraison #tracking #ops-cockpit #ads-spend
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 25/08/2026 11:06 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a examiné le document d’exigences, clarifié les responsabilités et les priorités immédiates pour le projet Data Dashboard, notamment la création de 15 tables de données et les tâches d’intégration associées. Les décisions clés incluent la prise de lead du projet par Boris, la livraison par Thomas du dataset et des documents attendus aujourd’hui, ainsi que le suivi par Aman et Venugopal des agents de livraison et des accès publicitaires. L’équipe a également aligné les canaux de communication, les besoins d’accès, les enjeux de tracking, et les prochaines étapes autour de l’Ops cockpit et des automatismes.

📋 Outline

1. Document d’exigences et livrable de Thomas • 0:01:52

- Le document reçu est un document formel d’exigences de Wasim que Thomas devra expliquer et convertir en données / ressources nécessaires au projet ; responsables : Thomas et Boris.
- Thomas créera aujourd’hui les documents de données et de ressources requis afin que le travail sur les 15 tables de base de données puisse démarrer d’ici la fin de journée ou demain matin ; responsable : Thomas.
- Boris a demandé si Thomas souhaitait prioriser la création d’une première table afin de permettre aux agents d’avancer plus tôt, plutôt que d’attendre la totalité des 15 ; responsable : Boris, avec confirmation à obtenir auprès de Thomas.

2. Canaux de communication et synchronisation • 0:03:47

- Boris a proposé de créer un canal WhatsApp avec Thomas pour synchroniser les questions de schéma vers table et accélérer les échanges ; responsable : Boris, qui doit créer le canal et y ajouter Aman.
- Aman a demandé à être ajouté au canal WhatsApp afin de pouvoir demander quel schéma correspond à quelle table pour le travail des agents ; responsable : Boris doit ajouter Aman.

3. Propriété du projet et rôles • 0:05:36

- Boris a repris la propriété du projet à son nom afin de centraliser la coordination et les interactions inter-équipes compte tenu de la complexité du projet et du nombre de parties prenantes ; responsable : Boris.
- Aman et Gopal restent responsables des agents de livraison (implémentation et exécution des agents), tandis que Boris pilote la coordination transverse ; responsables : Aman, Gopal et Boris.

4. Utilisation de l’Ops cockpit et localisation en anglais • 0:08:36

- Boris a montré l’Ops cockpit et a activé le mode anglais pour aider les personnes ne parlant pas français à consulter la timeline, les tâches, les ressources et les détails du projet ; responsable : Boris, avec usage par les membres du projet.
- L’Ops cockpit servira de référence pour les tâches et les ressources du projet, puis sera migré plus tard vers la plateforme interne entrepreneurs.works ; responsable : Boris.

5. Priorités hebdomadaires du Data Dashboard et quatre tâches clés • 0:09:25

- La priorité absolue de la semaine est la création des 15 modèles / tables de données nécessaires aux agents de livraison et au Data Dashboard ; responsables : Thomas pour la donnée, Aman pour les agents, une fois disponibles.
- Tâche 1 : connecter les données Ads / Adspend au Data Dashboard pour les tunnels Evergreen (Book Funnel, Quiz Funnel et Week of Scale) ; responsables : Venugopal et l’équipe marketing, avec Boris pour la coordination des accès.
- Tâche 2 : ajouter le nombre de visiteurs par fenêtre / page de livre au dashboard afin de permettre le calcul des taux de conversion ; responsables : équipe data et analytics marketing.
- Tâche 3 : mettre en place un menu utilisateur et une capacité d’invitation afin que les accès administrateur soient provisionnés sans partager d’identifiants personnels ; responsables : Boris et l’équipe plateforme / admin.
- Tâche 4 : implémenter le suivi UTM sur chaque tunnel / fenêtre, sur le modèle de Week of Scale, afin d’assurer la précision de l’attribution ; responsables : marketing et analytics.

6. Problèmes de tracking et option côté serveur • 0:12:01

- L’équipe marketing a observé un bug de tracking lié au délai entre l’opt-in et l’enregistrement ; les premiers tests montrent qu’un délai de redirection de 2 à 2,5 secondes résout le problème observé pendant la nuit ; responsables : marketing et analytics.
- Venugopal a proposé une capture côté serveur des données de formulaire comme alternative pour améliorer la fiabilité et l’exhaustivité des données ; responsable : Venugopal pour évaluer la faisabilité.
- Boris ne souhaite pas modifier l’architecture serveur pendant le lancement actif, compte tenu du niveau élevé de dépenses publicitaires (environ 300 000 € sur Meta et Google), mais reste ouvert à tester des solutions côté serveur après le lancement ; décision : Boris.

7. Exigences d’accès au compte publicitaire • 0:16:44

- Venugopal dispose d’un accès Meta limité qui l’empêche de voir l’ensemble des détails du compte publicitaire et demande un accès élargi au Business Manager et aux comptes publicitaires ; responsable : Venugopal pour préciser les besoins et Boris pour relayer auprès du marketing.
- Boris fera le suivi avec l’équipe marketing pour provisionner les bons accès, y compris la vérification des étapes 2FA / sécurité dans le cadre normal du processus d’onboarding des comptes publicitaires ; responsable : Boris.

8. Tunnels d’acquisition et vue d’ensemble du scale • 0:18:53

- L’entreprise exploite plusieurs systèmes d’acquisition, notamment des webinaires ponctuels (par exemple l’événement live Week of Scale) et des tunnels Evergreen (VSL, Book Funnel, Quiz Funnel) avec des flux d’opt-in et de nurturing différents ; responsables : Boris pour l’explication et les équipes marketing.
- Les grands événements live comme Week of Scale visent 30 000 à 40 000 visites de page et utilisent YouTube pour passer à l’échelle plutôt que WebinarJam en raison des limites de participants ; responsable : équipe événements / marketing.
- Les leads sont nourris via des séquences e-mail et de la segmentation afin de les convertir en appels puis en ventes ; responsables : marketing et sales.

9. Échelle de l’entreprise, besoin de structuration et ressources • 0:22:06

- Le principal défi de l’entreprise est la structuration interne et la conception des processus / systèmes, et non l’acquisition ou la vente ; responsable : Boris.
- Boris prévoit de recruter de nouveaux membres d’équipe et d’ajouter potentiellement Pearly et Barat à certains projets afin de gérer la charge de travail sur environ 30 à 40 projets simultanés ; responsable : Boris pour le recrutement.
- Aman et l’équipe cœur sont volontairement concentrés sur un nombre limité de projets au départ afin d’éviter la surcharge et de permettre un onboarding efficace ; responsables : Boris pour l’affectation et Aman pour l’exécution.

10. Agents d’automatisation et intégration à l’Ops • 0:27:14

- Venugopal a proposé de construire une pile d’automatisation composée d’agents pour des rôles tels que le marketing digital, le design front-end et les tâches backend, avec des extensions Chrome pour permettre aux agents d’opérer de manière autonome ; responsable : Venugopal pour la conception.
- Boris dispose déjà d’un système de type Jarvis qui analyse les enregistrements et les tâches de l’équipe puis les injecte dans l’Ops cockpit, et il maintient une base de connaissances Obsidian avec les données de l’entreprise pour alimenter les agents ; responsable : Boris pour le système existant et l’équipe pour l’intégration.
- L’équipe a convenu de planifier des appels OB de suivi, centrés sur l’amélioration des agents et des projets annexes si nécessaire ; responsable : Boris pour organiser ces appels.

11. Clôture de la réunion et prochaines étapes • 0:30:04

- Boris fera le suivi avec le marketing pour obtenir les accès requis aux comptes publicitaires et confirmer la livraison par Thomas du dataset / document attendu aujourd’hui ; responsable : Boris.
- Aman enverra un message à Boris en cas de problème, vérifiera la faisabilité de l’option de secours côté serveur pour le tracking, puis fera un retour ; responsable : Aman.
%% notes:fin %%
