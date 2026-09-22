---
type: call
date: 2026-09-22
source: sembly
participants: ["boris@entrepreneurs.com", "42lab@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Quentin X Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (22/09/2026 15:56).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 22/09/2026 15:56 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

La réunion a couvert le suivi des correctifs de sécurité, l’avancement de l’intégration Clap et des fonctionnalités d’administration associées, la gestion des avis Trustpilot, le déploiement de l’application et de la communauté gratuite, l’avancement de la facturation, ainsi que la centralisation des données de présence des welcome calls via Zoom et n8n. Elle a également aligné l’équipe sur plusieurs workflows n8n à mettre en place (prospect via UpSpot, inscription Zoom en un clic, capture de présence Zoom), sur les règles d’accès et de partage sécurisé des jetons/identifiants, sur le périmètre produit entre application mobile et plateforme, et sur plusieurs pistes d’automatisation et d’IA. Décisions clés : poursuivre le déploiement bêta de Clap, livrer automatiquement le bonus Trustpilot après 48 h si la vérification échoue, et fournir un jeton Zoom afin que l’équipe puisse reproduire les flows n8n existants dans la plateforme.

📋 Outline

1. Suivi du correctif de sécurité • 0:00:16

- Le correctif de sécurité prévu pour vendredi semblait avoir été appliqué, mais Quentin doit vérifier et confirmer que toutes les corrections sont bien en place.
- Les corrections concernent des vulnérabilités signalées par Mohamed ; une nouvelle réanalyse pourra être nécessaire dans les semaines à venir si des problèmes persistent.

2. Développement de l’intégration Clap et bêta • 0:01:06

- Quentin a finalisé une partie importante du développement de synchronisation avec Clap et a reproduit les fonctionnalités clés de l’intégration HubSpot utilisées par Clap.
- Deux utilisateurs commerciaux servent actuellement de bêta-testeurs : l’un depuis vendredi, l’autre depuis ce matin.
- Quentin a corrigé de nombreuses erreurs, prévoit d’ajouter trois correctifs supplémentaires d’ici demain et coordonne les profils ainsi que l’onboarding avec Léa.
- Si tous les tests sont au vert, l’équipe activera l’accès pour tous les utilisateurs en une seule fois.

3. Interface d’administration et gestion des coachs pour la déduplication • 0:02:31

- Une interface d’administration a été ajoutée pour automatiser la déduplication entre l’école Clap et la plateforme, afin d’éviter les doubles intégrations pour les coachs.
- Cette interface d’administration prévoit un mécanisme de repli permettant à Clap de prendre temporairement le relais si Ngram rencontre des bugs, afin d’assurer la continuité pour les coachs.
- Une page plateforme expliquant le fonctionnement de Ngram et indiquant où rejoindre les réunions a été construite, afin d’éviter aux coachs et aux utilisateurs de devoir changer d’outil externe.

4. Déploiement du score de module et du premier measure client • 0:04:40

- Le score de module a été déployé et configuré pour éviter tout déclenchement erroné sur les anciennes cohortes et garantir des fenêtres de déclenchement correctes.
- Aucun bug majeur n’a été signalé et l’environnement de préproduction correspondait au comportement attendu pour les envois basés sur les mois.
- 69 clients ont terminé leur premier measure à ce stade ; certains utilisateurs ont volontairement ignoré les pop-ups, conformément au comportement prévu.

5. Vérification des avis Trustpilot et livraison du bonus • 0:06:05

- Les bots qui tentent de vérifier les avis sont bloqués par les mécanismes anti-bot de Trustpilot ; le système utilise donc plusieurs fournisseurs et techniques pour retrouver les URL des avis.
- Si la vérification ne peut pas être finalisée sous 48 heures, le bonus est livré automatiquement et la page de coaching est mise à jour pour refléter la ressource livrée.
- Le statut actuel indique environ huit entrées Trustpilot, incluant des tests internes, avec plusieurs avis en attente de vérification et au moins un validé par un bot.

6. Facturation et discussion Apple Pay / InPay • 0:07:51

- Quentin et Jordan n’ont pas encore échangé sur l’intégration Apple Pay.
- Une discussion distincte a avancé sur la mise à disposition des factures clients dans la plateforme via le nouvel InPay et la récupération rétroactive depuis l’ancien système PennyLine.
- Boris gérera manuellement les ajustements de licences afin d’éviter une facturation indésirable le 25 et surveillera les messages de prévention.

7. Mise à jour de l’application et intégration de la communauté gratuite • 0:08:40

- L’application a été mise à jour ce matin pour supporter une expérience unifiée, permettant de basculer vers la communauté gratuite depuis la plateforme sans nécessiter de redéploiement App Store pour les changements ultérieurs.
- Les règles d’accès empêchent les utilisateurs de la communauté qui ne sont pas clients de la plateforme de se connecter ; les clients de la plateforme verront un onboarding invisible lors de leur connexion à la communauté.
- Le build Android est prêt, en attente de la vérification du domaine et de l’envoi ; la validation Google est attendue plus rapidement que celle d’Apple.

8. Centralisation de la présence aux welcome calls via Zoom et n8n • 0:11:28

- Boris dispose déjà d’un tableur et de flows n8n qui capturent les inscriptions aux welcome calls, la présence, la cohorte et le temps de présence, et souhaite centraliser ces données dans la plateforme.
- L’approche la plus simple consiste pour Boris à ajouter l’équipe à son instance n8n et à fournir un jeton Zoom afin que les développeurs puissent reproduire les flows dans la plateforme.
- Quentin va reproduire la logique existante dans la plateforme pour éviter les doubles développements et garantir des statistiques cohérentes ainsi qu’un rattachement fiable des utilisateurs.

9. Workflows n8n pour capter les leads, les inscriptions Zoom et la présence • 0:13:39

- Trois workflows nécessaires ont été identifiés et nommés W1, W2 et W3 pour une implémentation dans n8n.
- W1 correspond au flux UpSpot « closed and won » qui ajoute les nouveaux clients comme clients.
- W2 est le flux d’inscription Zoom en un clic, qui préremplit le nom et l’email depuis le lien mail et ajoute l’utilisateur à la prochaine cohorte avec une page de remerciement Zoom.
- W3 capture la présence Zoom à la fin de la cohorte et mesure la durée pendant laquelle les participants sont restés.
- Quentin a confirmé avoir accès au projet Delivery contenant W1 à W3 dans n8n et vérifiera directement les workflows.

10. Accès et partage sécurisé des identifiants et jetons • 0:14:20

- Quentin avait besoin d’accéder aux workflows n8n et Boris a accordé l’accès au projet Delivery afin que Quentin puisse inspecter W1 à W3.
- Les jetons et identifiants sensibles ne sont pas visibles directement dans n8n et doivent donc être partagés de façon sécurisée.
- Boris stocke les identifiants dans Dashlane et partagera les jetons nécessaires une fois que Quentin les aura listés.
- Quentin préfère recevoir les identifiants via OneTimeSecret afin de garantir un partage éphémère et sécurisé.
- Action : Quentin liste les jetons nécessaires et Boris les partage via OneTimeSecret ou via une autre méthode sécurisée convenue.

11. Périmètre produit : application iOS unique versus consolidation dans la plateforme • 0:18:55

- Le client demande actuellement uniquement une application mobile, mais l’équipe avait précédemment décidé de livrer une application iOS unique tout en gardant community.entrepreneurs.com et plateforme.entrepreneurs.com comme propriétés web séparées.
- Certains interlocuteurs proposent de tout consolider dans la plateforme principale, mais l’équipe estime qu’héberger entièrement les fonctionnalités orientées client dans la plateforme n’est pas sûr et crée de la friction pour les utilisateurs.
- L’équipe va retravailler et représenter les propositions, puis décider d’ici lundi de la meilleure approche de mise en œuvre, tout en évitant une consolidation risquée.

12. Initiatives IA et autres projets produit • 0:21:25

- Les progrès sont positifs sur le projet Live AI Assistant et l’équipe réfléchit à des cas d’usage pour Moonshot.
- Un nouveau modèle, nommé « Jev », est apparu et pourrait offrir des capacités de décision rapides et peu coûteuses, avec des cas d’usage inspirants pour la plateforme et Moonshot.
- L’équipe doit éviter les projets « shiny object » et privilégier les fonctionnalités IA qui créent une valeur mesurable pour les coachs, les clients et les flux de travail internes.

13. Automatisation des processus coachs et stratégie d’adoption • 0:22:27

- L’équipe a constaté que de nombreux coachs utilisent des processus archaïques et répétitifs qui peuvent être automatisés pour gagner du temps et réduire la friction.
- Un exemple concret consiste à automatiser le flux standard de bienvenue / email lorsqu’un coach reçoit un nouveau client, ce qui peut faire gagner environ dix minutes par onboarding.
- Le nom du concept Assistant Coaching a été adouci afin d’être plus acceptable pour les coachs et d’éviter les craintes de remplacement.
- La communication avec les coachs s’est améliorée grâce à des échanges directs avec Élodie et Léonard, renforçant la confiance et la volonté d’adopter les workflows automatisés.
- L’équipe priorisera les automatisations qui concernent un grand nombre de coachs plutôt que de petits gains ponctuels.

14. Centralisation des données et plateforme comme source de vérité • 0:27:18

- Boris a insisté sur le fait que toutes les données de coaching principales doivent provenir de la plateforme afin de garantir des jeux de données propres et cohérents pour les tableaux de bord et les besoins transverses.
- La plateforme doit rester l’outil central de l’unité coaching, et les tableaux de bord dérivés devront être alimentés à partir de cette source selon les besoins.
- L’équipe se concentrera sélectivement sur quelques domaines de données par sprint et pourra consacrer un effort concentré à certaines améliorations de données pendant un à trois mois selon les priorités.

15. Estimation de la durée du welcome call pour le pilotage de projet • 0:29:32

- Boris a demandé une estimation du temps requis pour le flux de welcome call afin de l’ajouter au suivi de projet et d’éviter des relances quotidiennes.
- Quentin a accepté de fournir cette estimation de durée et d’ajouter la tâche au système de gestion du travail une fois celle-ci définie.
%% notes:fin %%
