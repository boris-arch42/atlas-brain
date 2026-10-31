---
type: call
date: 2026-10-30
source: sembly
participants: ["boris@entrepreneurs.com", "julien@aikho.ai", "arnaud@aikho.ai"]
sensitivity: confidential
tags: [call, sembly]
---

# Connection tools Aikho

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (30/10/2026 22:55).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 30/10/2026 22:55 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a passé en revue l’avancement produit et technique, avec un point marquant sur la migration du moteur d’entretien de Gemini V1 vers DeepSync V2, qui permet une forte réduction des coûts et une amélioration de l’efficacité d’évaluation. Les échanges ont ensuite porté sur la stratégie CRM et workflow entre iClose et la plateforme Aïko/ICO : à court terme, iClose doit centraliser les leads et le suivi commercial, tandis qu’un plugin cloud léger doit exposer l’intelligence d’Aïko aux équipes commerciales et automatiser certaines tâches. Par ailleurs, l’équipe a défini une approche opérationnelle progressive pour les leads pré-inscription et le CSM : processus manuel au départ, enregistrement des appels, usage prudent de l’emailing pour préserver la réputation du domaine, puis intégration et automatisation par étapes selon les retours terrain. Les décisions clés incluent la poursuite du déploiement DeepSync et des simulations, l’envoi de synthèses hebdomadaires produit/vente, et la priorisation du plugin cloud ainsi que de l’utilisation d’iClose pour la centralisation des leads à court terme.

📋 Outline

1. Présences et problèmes de connexion • 0:00:10

- Plusieurs participants ont rejoint la réunion depuis leur mobile ou en déplacement, ce qui a entraîné des déconnexions intermittentes pendant l’appel.
- Julien a brièvement quitté la conversation et devait la rejoindre à nouveau.

2. Point développement — migration DeepSync et baisse des coûts • 0:04:38

- Le moteur d’entretien a été migré de Gemini V1 vers DeepSync V2 afin de réduire le coût de traitement par candidat, d’environ 0,85 € à 0,25 €.
- Cette migration a nécessité une recalibration des entretiens et la mise en place d’un système de simulation piloté par Claude pour valider de nombreux indicateurs sur plusieurs personas.
- Des dizaines de milliers de simulations ont été exécutées, et les résultats montrent une meilleure expérience candidat ainsi qu’une efficacité d’évaluation supérieure à la version précédente.
- Le travail de calibration et de validation restant est attendu d’ici le week-end à venir.

3. Évaluation des risques géopolitiques et de conformité liés au choix du modèle • 0:06:44

- La question a été posée de savoir si l’usage de DeepSync/DeepSeek pouvait créer des frictions auprès des investisseurs, notamment américains, ou des contraintes réglementaires.
- Julien a expliqué que les modèles DeepSeek sont des poids open source déployés via des fournisseurs NeoCloud, par exemple CoreWeave, majoritairement basés aux États-Unis, ce qui permet de maîtriser l’hébergement et la conformité.
- L’architecture permet de choisir les fournisseurs et les régions pour respecter le RGPD et les exigences de conformité IA, tout en réduisant le verrouillage fournisseur et les risques de réutilisation des données.

4. Communication hebdomadaire des avancées • 0:09:19

- Julien s’est engagé à envoyer un récapitulatif hebdomadaire de fin de semaine sur l’avancement produit et la feuille de route à court terme, afin de maintenir l’alignement de l’équipe de manière asynchrone.
- Arnaud a proposé de faire la même chose pour les sujets commerciaux et de gouvernance afin de mieux synchroniser le pilotage de l’activité.

5. Définition du périmètre Sales vs CSM et qualification des leads • 0:10:09

- L’équipe a clarifié que l’engagement Sales est déclenché lorsque des limites d’usage sont atteintes, par exemple une fenêtre de 14 jours ou 25 entretiens, et qu’une opportunité d’upsell est suspectée.
- Le périmètre CSM couvre les cas d’activation et de support, notamment lorsqu’un client est bloqué, par exemple en l’absence de description de poste ou de lancement de candidats, et nécessite une aide concrète pour atteindre la première valeur.
- La qualification est continue et peut évoluer du CSM vers les Sales au fur et à mesure que le client se rapproche de l’achat.

6. Stratégie d’intégration entre Aïko/ICO et iClose • 0:12:46

- À court terme, l’équipe a convenu d’importer les leads Entrepreneur existants dans iClose via CSV et de configurer des transferts automatiques depuis les landing pages vers iClose.
- IClose doit centraliser la gestion des leads pour les opérations commerciales, tandis que la plateforme Aïko/ICO doit remonter dans iClose des informations de réservation et d’usage afin d’enrichir le contexte de chaque lead.
- L’équipe a reconnu qu’il n’est pas optimal de conserver deux systèmes déconnectés et qu’il faut soit faire tirer les données par iClose depuis ICO, soit faire pousser les mises à jour de statut par ICO vers iClose.
- Les considérations de coût ont aussi été discutées : utiliser iClose pour toute la vente peut augmenter les abonnements, tandis que développer des fonctions CRM en interne implique des coûts de développement et d’opportunité.

7. Proposition de plugin cloud pour l’intelligence commerciale • 0:16:17

- Julien a proposé de développer un plugin cloud capable de lire de manière sécurisée les données ICO et d’interroger une couche MCP/Claude pour fournir aux commerciaux des recommandations, du contexte et des réponses aux objections.
- Le plugin permettrait aux commerciaux d’opérer directement depuis leur environnement cloud, avec intégrations Gmail et calendrier, tout en automatisant des tâches comme la prise de rendez-vous et l’analyse de leads.
- L’approche par plugin préserve une couche d’intelligence gérée par le produit et réduit la friction pour les commerciaux par rapport au passage entre plusieurs outils.
- Julien estime pouvoir terminer ce travail d’ici le week-end à venir et a indiqué être prêt à le prioriser si l’équipe valide cette orientation.

8. Fonctionnalités CRM jugées prioritaires • 0:21:22

- La fonctionnalité CRM la plus importante identifiée est une vue visuelle du pipeline montrant les étapes de progression des leads et le nombre de leads par étape pour une visibilité rapide.
- La planification de rappels et de relances est jugée essentielle afin que les commerciaux puissent programmer des callbacks pour les prospects qui ne sont pas prêts immédiatement.
- La prise de rendez-vous directement dans les calendriers depuis le CRM est également requise pour l’efficacité opérationnelle, que ce soit via iClose ou via le plugin.

9. Gestion manuelle à court terme des premiers appels • 0:22:59

- Pour les 20 à 30 premiers appels, l’équipe a accepté qu’un processus manuel soit suffisant et puisse être géré sans automatisation lourde.
- L’objectif à long terme reste de disposer d’un outil unique offrant un accès complet à l’intelligence d’Aïko afin de maximiser la valeur et la cohérence.

10. Flux actuel de prise de rendez-vous et limites d’ICO • 0:23:51

- Le flux habituel consiste aujourd’hui à envoyer un lien de réservation à un prospect, mais ce dernier ne peut pas interagir directement avec la vue interne, ce qui oblige à effectuer des relais manuels ensuite.
- ICO considère actuellement un prospect comme un client uniquement après son inscription, ce qui crée un vide avant la souscription qu’il faut traiter séparément.
- L’équipe a identifié le besoin d’une base de données indépendante pour la phase pré-inscription ainsi que d’un processus/cadre de gestion des leads avant leur inscription sur ICO.

11. Rôle d’iClose comme CRM pour les leads pré-inscription • 0:24:28

- IClose peut collecter les leads qui ne s’inscrivent pas sur ICO et servir de CRM pour gérer différents niveaux de maturité des prospects.
- Utiliser iClose en haut de l’entonnoir permet de traiter les leads générés par les landing pages ou les campagnes publicitaires sans surcharger le backend ICO.
- L’équipe a convenu de tester iClose au début du funnel et ICO/Claude à la fin afin d’identifier les intégrations manquantes et les points de blocage au cours des prochaines semaines.

12. Workflow opérationnel pour le CSM outbound : appels, calendrier et statut • 0:27:56

- Les CSM se concentreront sur les prospects au statut « qualifié », c’est-à-dire disposant d’un numéro de téléphone et pouvant ou non déjà avoir un rendez-vous réservé.
- Si un rendez-vous existe, le CSM appelle le prospect à l’heure prévue ; sinon, il prend l’initiative d’un appel en fonction du statut du prospect et de son jugement métier.
- Le premier contact doit privilégier le téléphone et WhatsApp via un numéro français pour instaurer une crédibilité locale, plutôt que l’email.

13. Enregistrement des appels et capture des notes via Google Meet / Gemini / Whisper • 0:30:32

- L’équipe enregistrera les appels et utilisera les outils disponibles, comme Whisper ou Google Meet avec prise de notes Gemini, pour générer des résumés et des transcriptions.
- Google Meet avec Gemini a été recommandé car il peut produire automatiquement des notes et des synthèses qui peuvent ensuite être copiées dans l’enregistrement CSM/ICO.
- Le plan consiste à coller ces notes dans ICO afin que toute interaction ultérieure dispose du contexte et que le CSM voie les conversations précédentes.

14. Commencer manuellement puis automatiser après validation du modèle • 0:31:11

- L’équipe a accepté de lancer le processus manuellement au départ afin de recueillir des retours qualitatifs avant de construire des automatisations et intégrations.
- Ces tests manuels permettront d’identifier les automatisations et les intégrations réellement nécessaires, ainsi que les fonctionnalités qui seraient prématurées.

15. Intégration site web / landing page pour la génération de leads et la réservation • 0:36:13

- Un bouton simple du type « Réserver votre démo » ou une popup sur la page d’accueil Aïko/landing page peut afficher directement les créneaux disponibles du calendrier et transmettre les réservations au calendrier du CSM.
- L’approche popup permet de capter rapidement les visiteurs à forte intention et peut être déployée via un petit extrait HTML, ce qui facilite sa mise en production sur la landing page.
- Si le trafic du site est suffisant, cette intégration générera des appels entrants et des réservations alimentant le calendrier d’Arnaud.

16. Gestion de plusieurs membres d’équipe et calendriers partagés dans iClose • 0:39:55

- Pour permettre à plusieurs hunters ou CSM de prendre des appels, iClose nécessite plusieurs abonnements ainsi qu’une configuration de partage et d’assignation des calendriers.
- Le système peut répartir les rendez-vous réservés entre plusieurs membres de l’équipe, mais les détails de configuration seront expliqués et mis en place au moment de la montée en charge.

17. Gestion des cinq premiers prospects de Marrakech et timing de relance • 0:41:36

- Les cinq prospects de Marrakech se sont tous inscrits sur ICO et sont considérés comme des leads activés qui ont déjà été recontactés par des coachs.
- L’équipe a convenu d’attendre quelques jours, sans relance pendant le week-end, puis de les recontacter en début de semaine prochaine s’ils n’ont pas ouvert de poste sur la plateforme.
- Si les prospects n’ont pas ouvert de poste en début de semaine, Arnaud les appellera en premier pour prendre la température et recueillir leurs retours.

18. Prudence sur l’emailing et la réputation du domaine • 0:42:54

- Le groupe a convenu de rester prudent sur les volumes d’email sortants afin d’éviter les plaintes pour spam et de protéger la réputation du domaine d’envoi pour les futurs besoins de campagnes plus larges.
- Pour le petit échantillon initial, les appels manuels sont préférés à l’emailing massif afin d’éviter tout risque de mise sur liste noire du domaine.
- L’équipe limitera ou désactivera les déclencheurs d’emails automatisés pour les petits groupes pilotes afin de préserver la délivrabilité des prochaines campagnes à plus grande échelle.
%% notes:fin %%
