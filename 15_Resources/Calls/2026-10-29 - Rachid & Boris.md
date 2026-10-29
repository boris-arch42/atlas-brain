---
type: call
date: 2026-10-29
source: sembly
participants: ["boris@entrepreneurs.com", "rachid.oubih@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Rachid & Boris

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (29/10/2026 15:33).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 29/10/2026 15:33 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a convenu que les données SDR sont actuellement peu fiables et qu’il faut standardiser les liens de prise de rendez-vous, l’assignation obligatoire des leads et les automatisations HubSpot/Hotspot afin de tracer correctement toute l’activité SDR et les bookings pour les dashboards. Les discussions ont aussi porté sur le nettoyage du CRM, la déduplication, le modèle contact/lead/deal, l’intégration des sources marketing et des événements, ainsi que sur l’utilisation d’un sandbox/tenant dupliqué pour sécuriser les changements. Des actions ont été réparties entre Rachid, Boris, Wassim, Sabrina et Fabrice.

📋 Outline

1. Objet de la réunion et aide immédiate • 0:00:00

- Boris a ouvert la réunion en proposant son aide et en demandant à Rachid ce qu’il devait préparer pour la prochaine réunion de revue.
- Rachid a demandé quels éléments préparer précisément pour l’appel de revue revenu / SDR.

2. Problèmes de qualité des données SDR • 0:00:20

- Rachid a remonté plusieurs problèmes d’intégrité de données, notamment des rendez-vous enregistrés sur des calendriers individuels (Raphaël) sans traçabilité dans le système.
- Il a signalé des écarts entre le nombre de réunions déclarées et le revenu réel, ainsi qu’un grand nombre de meetings de faible qualité ou mal alignés avec la cible.
- Rachid a aussi indiqué que certains rendez-vous créés automatiquement par des prospects pendant des événements live étaient attribués à tort aux SDR via les UTM, ce qui faussait les métriques.

3. Impact sur la confiance et besoin de reconstruire le tracking • 0:02:47

- Boris a confirmé que des données SDR peu fiables compromettent la prise de décision et qu’il faut reconstruire le système de tracking pour restaurer la confiance.
- Rachid a insisté sur le fait qu’il fournira des chiffres vérifiés et recoupés, et qu’il refuse de présenter des données artificiellement positives.

4. Structure de la réunion de revue et responsabilité • 0:03:27

- Boris a expliqué que Fabrice animera la réunion de revue en tant que Revenue Lead et présentera les slides revenu ainsi que les KPI ; les données SDR viendront en complément de sa présentation.
- Il a été convenu que Rachid préparera des métriques SDR vérifiées afin d’apporter davantage de clarté à la revue.

5. Plan de consolidation : Hotspot, OpsPod, OneFlow • 0:04:43

- Rachid a proposé de consolider toutes les données SDR dans des dashboards Hotspot et d’automatiser les flux contractuels pour remplacer OneFlow, afin de centraliser le tracking.
- Il a précisé avoir laissé Wassim travailler avec le contact OpsSpot/OpSpot pour automatiser une partie du processus et accélérer le remplacement d’OneFlow.

6. Fonctionnement actuel de iClose pour la prise de rendez-vous et le tracking • 0:05:37

- Boris a décrit la configuration SDR Hub : les SDR utilisaient un lien calendrier commun et le tracking reposait sur des UTM capturant le nom du SDR, le média et la campagne au moment de la réservation.
- Il a expliqué que iClose conserve des données partielles de réservation (prénom, nom, email/téléphone) même si le prospect ne termine pas le parcours de booking, ce qui permet de créer des traces de pré-qualification.

7. Distinction des opportunités qualifiées dans le pipeline • 0:06:38

- L’équipe a convenu que les « qualified potentials » capturés par iClose sont les éléments réellement utiles pour le reporting SDR et le suivi commercial.

8. Proposition d’automatisation des liens et des champs par funnel / SDR / source • 0:07:45

- Rachid a proposé soit de générer un lien de booking unique par SDR et par source, soit d’automatiser le choix dans HubSpot afin de fournir automatiquement le bon lien tracé sans sélection manuelle.
- Boris a indiqué que la complexité existe, mais que des règles HubSpot et des automatisations de champs peuvent remplir automatiquement le bon lien et les paramètres UTM.
- Cette approche réduirait les erreurs manuelles et transformerait l’absence de lien en alerte exploitable.

9. Incident Calendly et nécessité de bloquer les bookings non tracés • 0:08:49

- Rachid a rappelé un incident où Lisa avait utilisé le lien Calendly personnel de Raphaël, créant des rendez-vous non tracés et sans enregistrement transactionnel.
- L’équipe a convenu qu’il faut empêcher les réservations en dehors des liens contrôlés afin d’éviter les rendez-vous introuvables et les trous d’attribution.

10. Règles d’automatisation HubSpot/Hotspot et ownership obligatoire du lead • 0:10:39

- Boris et Rachid ont discuté de règles de calcul dans HubSpot/Hotspot qui auto-rempliraient le champ du lien de réservation lorsque le owner du lead et le funnel sont renseignés.
- Le processus exige un respect strict : le SDR doit s’assigner comme owner du lead avant que le système n’active le lien de booking.
- Si le lead owner n’est pas renseigné, le lien de réservation ne se remplira pas et le booking sera bloqué, avec une alerte générée.

11. Croissance du nombre de SDR et des liens par funnel • 0:11:10

- Rachid a reconnu que la montée en charge des SDR et des sources augmente le nombre de combinaisons de paramètres, mais a précisé que les liens sont définis par funnel et que les paramètres varient, ce qui limite la multiplication des URLs.
- Boris a expliqué qu’un lien unique par funnel peut être utilisé avec des paramètres additionnels (UTM) plutôt que de créer une URL de base différente pour chaque combinaison SDR-source.

12. Décisions finales sur le blocage et les dashboards • 0:11:41

- Le groupe a décidé de bloquer l’action « booked » tant que le SDR n’a pas qualifié le lead et n’est pas correctement positionné comme owner, afin de garantir l’intégrité des données.
- Les dashboards seront alimentés par les données OpsPod/Hotspot une fois les automatisations en place, pour assurer un reporting fiable.
- Rachid fournira des chiffres vérifiés sur les appels et les bookings pour la réunion de revue, et Boris examinera les détails d’implémentation des dashboards.

13. Chaîne de mapping booking -> deal -> lead -> owner SDR • 0:12:30

- Le système doit suivre une réservation jusqu’à son deal ID, puis jusqu’au lead associé, et enfin récupérer l’owner du lead (le SDR).
- L’owner à récupérer est l’owner ESR/SDR, et non une étiquette owner générique.
- Boris discutera de la logique d’assignation avec ses équipes afin de ne pas casser les dashboards existants et d’implémenter des liens d’owner spécifiques par source.

14. Suivi des sources et intégration marketing • 0:13:46

- Chaque nouvelle source (site web, événements, etc.) doit remplir correctement le champ source afin que les leads soient attribués avec précision.
- Le marketing doit connecter ses outils d’événements directement au CRM plutôt que d’envoyer des exports Excel, afin d’éviter le nettoyage manuel.
- Les nouveaux outils doivent pousser automatiquement les inscriptions dans le CRM pour créer les leads et les deals en temps réel.

15. Segmentation et workflow de traitement des appels SDR • 0:14:07

- Les SDR utiliseront CloudTalk pour créer des segments selon différents états de leads, par exemple des leads à rappeler en masse ou des leads chauds assignés selon le principe du premier arrivé, premier servi.
- Les segments seront créés et clôturés par campagne, par exemple un segment « 5D » de septembre, pour garder une opération propre.

16. Stratégie sandbox / tenant dupliqué pour sécuriser les changements • 0:14:56

- Un sandbox ou un tenant dupliqué doit être utilisé pour tester les changements sur Opspot sans impacter les données de production ni l’architecture front-end.
- Une réunion sera planifiée avec Sabrina et Fabrice pour décider quelles données conserver ou supprimer avant toute migration ou modification de l’environnement.

17. Nettoyage des données CRM et problème de doublons • 0:16:10

- Le CRM contient de nombreux champs dupliqués et un excès de propriétés, ce qui crée de la confusion et de la pollution de données.
- Il existe des dizaines de milliers d’anciens leads, environ 80 000 de l’année précédente, qui doivent être clôturés, convertis ou archivés afin de ne pas polluer la base active.
- Boris a commencé le nettoyage en utilisant des indicateurs visuels (alertes par emoji) pour marquer les enregistrements problématiques, et il poursuivra progressivement.

18. Modèle contact / lead / deal et traçabilité historique • 0:18:45

- Le modèle validé est le suivant : un enregistrement contact par personne, un lead créé à chaque inscription du contact, et un deal (transaction) créé lorsqu’un booking a lieu.
- S’assurer que chaque contact possède toujours des lead records lors de ses interactions préservera l’historique pour les audits et la logique de nurturing.
- Le marketing doit être impliqué dans le projet pour garantir que le nouvel outil conserve un tracking cohérent entre inscriptions et événements live.

19. Données de présence aux événements live et charge d’automatisation • 0:20:16

- La capture en temps réel des métriques de présence (présence, durée) pour des milliers d’inscrits à des événements consommera beaucoup de ressources d’automatisation.
- Il est techniquement possible de mettre à jour les leads chaque nuit avec les données de présence, mais l’équipe doit concevoir une approche économe en ressources pour limiter les coûts d’automatisation.
- Un dédoublonnage et un filtrage préalables sont nécessaires, car les listes incluent des clients actuels, des comptes en retard de paiement et d’autres données bruitées nécessitant des traitements différents.

20. Verrouillage des champs, suivi UTM et règles d’assignation des rendez-vous • 0:24:22

- Le champ source et le tracking UTM doivent être implémentés et imposés pour garantir une attribution fiable des sources.
- Certains champs, par exemple l’assignation SDR, devraient être verrouillés conditionnellement jusqu’à ce que les critères requis soient remplis, comme l’affectation d’un SDR.
- Boris a demandé une courte vidéo Loom ou une explication du point précis où les champs sont définis, afin que ses équipes puissent suivre le bon processus lors de l’implémentation des champs verrouillés ou conditionnels.
%% notes:fin %%
