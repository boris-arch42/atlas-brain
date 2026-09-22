---
type: call
date: 2026-09-22
source: sembly
participants: ["jordan@entrepreneurs.com", "boris@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Jordan X Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (22/09/2026 16:26).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 22/09/2026 16:26 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

La réunion a couvert trois axes principaux : (1) l’organisation du travail et le contexte opérationnel immédiat, notamment les préférences de bureau/hybride, les déplacements à venir et la disponibilité de chacun ; (2) une revue financière et analytique très orientée réduction de coûts, avec un focus particulier sur le marketing, la rationalisation des outils SaaS, l’amélioration des KPI et la mise en place d’un processus de validation des achats ; (3) plusieurs chantiers techniques et structurels, dont la correction des blocages clients liés à Linpay/Odoo/InPay, la réflexion sur une internalisation de certaines fonctionnalités (LeanPay/Smart Funnel), la gestion des accès et licences HubSpot pour CGM, ainsi que la préparation de la migration d’activité d’Ariès vers Horizon avec une séparation comptable et juridique claire. Les décisions incluent la transmission du détail des dépenses marketing avant lundi, la revue des clients bloqués à débloquer, la mise en place d’un workflow d’approbation SaaS dans Works, et la préparation d’un plan détaillé/Gantt pour la migration Ariès → Horizon.

📋 Outline

1. Préférences de bureau et travail hybride • 0:00:00

- Jordan a expliqué avoir découvert la vue du bureau de Boris et avoir été déçu de perdre cette vue, en soulignant que la proximité dans l’open space permet de capter de l’information informelle.
- Boris a indiqué qu’il prévoit environ 60 % de temps au bureau et 40 % dans l’espace commun pour équilibrer travail concentré et circulation de l’information.
- Le groupe a reconnu que l’open space favorise les échanges spontanés, tout en rappelant que des moments de confidentialité restent nécessaires.

2. Revue financière par unité, avec démarrage par le marketing • 0:01:20

- Boris a proposé une revue financière de chaque business unit, en commençant par le marketing, afin d’auditer les personnes, les outils et les retours réels.
- Il a demandé que les données complètes du marketing soient apportées pour une revue ligne par ligne, y compris les ressources humaines et les outils.
- Jordan a confirmé avoir déjà préparé un audit similaire pour la communication et a annoncé qu’il produirait un état des lieux du marketing avec les rôles et responsabilités de chaque personne.
- L’objectif est double : réduire les coûts et reprendre le contrôle sur certaines activités en les internalisant lorsque cela est possible.

3. Coûts de staffing marketing et d’outillage • 0:02:24

- Jordan a alerté sur la taille importante de l’équipe marketing et sur la réduction prochaine du temps de Cédric, ce qui crée une pression sur la masse salariale et l’organisation.
- Jordan et Boris ont souligné que les outils marketing sont très coûteux et que certains pourraient être supprimés, remplacés ou internalisés.
- Jordan a demandé que les responsabilités de chaque membre du marketing soient documentées afin d’identifier les optimisations possibles.
- Boris a donné l’exemple d’une facture d’outil très élevée, autour de 30K, qui pourrait être remplacée par une solution interne.

4. Mesure de la performance : ROS vs ROAS • 0:03:09

- Jordan a estimé qu’il fallait arrêter de se limiter au ROAS et utiliser un indicateur de type ROS intégrant les dépenses publicitaires, mais aussi les coûts outils et humains sur la période.
- Boris a reconnu que le ROAS actuellement remonté dans les dashboards omet une partie importante des dépenses humaines et d’outillage, ce qui peut donner une vision trompeuse.
- Le besoin d’ajuster les KPI a été validé afin d’évaluer la performance marketing en tenant compte de l’ensemble des coûts pertinents.

5. Conflits de planning liés aux déplacements • 0:04:17

- Jordan a indiqué que son assistante avait réservé des vols compliqués, ce qui le rendra indisponible toute la journée de lundi, et a demandé à Boris de reprogrammer les sujets en conflit.
- Boris a précisé qu’il n’avait pas encore reçu de confirmation de vol pour le premier du mois et qu’il coordonnait son départ depuis Lyon.

6. Intégration Linpay / Odoo et blocages clients incorrects • 0:04:56

- Jordan a confirmé que la plateforme est connectée et que les clients qui doivent être bloqués le sont bien, mais il existe aussi des blocages erronés à corriger.
- L’erreur provenait d’une règle d’intégration Whoop qui bloquait les clients lorsque Whoop indiquait un impayé, même s’ils avaient payé par virement bancaire.
- La règle a été retirée avec l’aide de Quentin, et Jordan a demandé une revue de la liste pour débloquer les clients concernés.
- Jordan a également expliqué que les écritures de facturation Odoo et Pennylane sont dupliquées, et que Linpay traite d’anciens enregistrements Pennylane comme des débits divers, ce qui complique le rapprochement.
- L’opération reste en production sur Linpay, utilisé comme outil principal pendant la phase de nettoyage.

7. Proposition d’internaliser LeanPay • 0:06:21

- Jordan a expliqué que la fonction principale de LeanPay est une classification simple des créances par ancienneté, et qu’un outil interne pourrait reproduire cette logique.
- Une solution interne permettrait de fournir aux équipes de recouvrement des listes priorisées et d’améliorer l’efficacité des relances.
- Jordan a estimé qu’il s’agit d’un projet de moyen terme, à traiter après les priorités liées aux dashboards et aux tâches déjà en cours.
- Il a également souligné le potentiel d’économies récurrentes de plusieurs milliers d’euros par an.

8. Options techniques Odoo et ajustements API / module • 0:07:07

- Boris a suggéré de contacter le correspondant Odoo pour explorer une autre API ou un module personnalisé afin d’obtenir le comportement d’intégration souhaité.
- Jordan a indiqué que le contact Odoo répond mal et pense que le problème se situe surtout entre les connecteurs Linpay et Odoo.
- Jordan a proposé de répliquer LeanPay en interne lorsque l’équipe aura davantage de bande passante.

9. Statut du contrat de Géraud et modalités de paiement • 0:08:45

- Jordan a expliqué que Géraud travaille sur le recouvrement et que le routage actuel des paiements est hebdomadaire, en partie via Upwork.
- Le plan est de le maintenir sur Upwork jusqu’à fin septembre, puis possiblement un mois supplémentaire, avant un recrutement hors Upwork sous contrat direct.
- Boris, Anis et Jordan ont discuté de la consolidation de certains comptes de paiement et ont noté que la méthode de paiement d’Anis est cohérente avec les processus actuels.

10. Option Apple Pay / Stripe sur la plateforme • 0:09:35

- Boris a souhaité réévaluer l’idée d’ajouter Apple Pay sur la plateforme et a demandé si l’implémentation était faisable sans trop de friction.
- Jordan a répondu que les clients peuvent déjà payer via un lien Stripe hébergé par LeanPay/NewPay, et qu’intégrer Apple Pay ferait doublon sauf à supprimer une des voies existantes.
- Le groupe a convenu qu’Apple Pay pourrait être intégré directement sur la plateforme si nécessaire, mais qu’il faut d’abord traiter la duplication des parcours de paiement.

11. Insatisfaction vis-à-vis d’InPay / LeanPay • 0:10:31

- Jordan a exprimé sa frustration vis-à-vis d’InPay, en expliquant que les connecteurs et le support sont faibles et que la reconnexion a été chaotique.
- Boris et Jordan ont convenu qu’il est problématique de payer une somme importante pour un outil qui fonctionne mal.
- Jordan a précisé que Linpay est actuellement en service malgré ses limites, mais que son remplacement ou sa reconstruction reste envisagé à moyen terme.

12. Visibilité des factures clients et liens de paiement • 0:10:31

- Jordan a fait état d’un échange avec Sabrina et Quentin pour afficher les factures dans la plateforme afin que les clients puissent voir leur information de facturation.
- Il a précisé que seules les factures émises à partir d’Odoo seront visibles dans cet environnement.
- Jordan a proposé d’indiquer aux clients que les factures sont disponibles à partir du 1er mai 2026, et que les factures plus anciennes nécessitent un ticket Zendesk.
- Il a suggéré d’ajouter un lien de paiement dans la vue compte client une fois les factures visibles, tout en notant que le lien de paiement est aujourd’hui hébergé par InPay.
- Jordan a demandé à s’éloigner autant que possible de l’hébergement InPay en raison des problèmes d’intégration et de support.

13. Dashboards et avancement du travail de Mohamed • 0:12:02

- Boris a demandé un point d’avancement sur les dashboards en cours de construction par Mohamed.
- Jordan a indiqué qu’il avait peu de bande passante mais qu’il devait voir Mohamed le lendemain pour présenter les maquettes et avancer sur le sujet.
- Boris a proposé d’ajouter le projet Enwork afin de synchroniser le travail et de garder les délais alignés.

14. Collecte des lignes bancaires • 0:12:44

- Jordan a indiqué qu’il commencerait par collecter l’ensemble des lignes bancaires, base de travail nécessaire car les données sont dispersées entre plusieurs sources, y compris des sites fermés et Ibanfer.
- La récupération complète des lignes bancaires a été identifiée comme un sujet technique, long et prioritaire.

15. Priorité stratégique : économies et consolidation des données • 0:12:59

- Boris a indiqué que son focus trimestriel principal est la recherche d’économies et la consolidation des données pour améliorer la clarté opérationnelle.
- Il a insisté sur la nécessité de prioriser les sujets qui génèrent des économies significatives et un meilleur contrôle de la donnée, plutôt que de passer du temps sur des montants marginaux.

16. Analyse de la structure de coûts et des dépenses marketing • 0:13:27

- Jordan a estimé que les coûts globaux de l’entreprise restent cohérents avec la taille actuelle et la marge, mais que le marketing et l’acquisition client sont anormalement élevés.
- Il a ajouté que si le chiffre d’affaires avait atteint le budget prévu, le niveau actuel de dépenses aurait été acceptable.
- Jordan a suggéré qu’un changement de go-to-market ou de head of sales pourrait améliorer nettement la performance et réduire les dépenses inefficaces.

17. Prolifération des outils et exemple Smart Funnel • 0:14:54

- Boris a mis en avant le problème d’un trop grand nombre d’outils payés mais peu utilisés, ce qui crée à la fois un coût et une difficulté de compréhension opérationnelle.
- Il a cité Smart Funnel, coûteux et utilisé pour les relances WhatsApp, comme exemple de fonctionnalité à internaliser pour économiser de l’argent et maîtriser la donnée.
- L’internalisation des outils a été présentée comme un moyen d’améliorer la sécurité, la propriété des données et de supprimer des coûts récurrents par lancement.

18. Demande d’envoi du détail des dépenses marketing avant le board • 0:16:26

- Boris a demandé à Jordan d’envoyer le détail des dépenses marketing avant lundi, ou au plus tard avant le week-end, afin de pouvoir l’analyser.
- Il a précisé qu’il ferait un premier contrôle puis proposerait ce qui peut être automatisé, internalisé ou placé dans un backlog d’optimisation.

19. Processus de validation SaaS dans Works • 0:17:18

- Jordan a décrit des demandes SaaS fréquentes et peu tracées, parfois de l’ordre de 36 € par mois, avec un risque de perte de visibilité dans le temps.
- Il a proposé un workflow de validation dans Works intégrant le nom de l’outil, l’équipe demandeuse, le coût mensuel, l’action envisagée et l’approbation du manager.
- Boris et Anis ont indiqué qu’ils mettront en place ce processus d’approbation afin que tous les achats SaaS soient centralisés, approuvés et historisés.

20. Projet de migration vers la société Horizon • 0:18:40

- Jordan a annoncé la migration planifiée de certaines activités vers une nouvelle société, Horizon, en soulignant qu’il s’agit d’un projet important nécessitant beaucoup de préparation et de tests.
- Il a insisté sur le fait que de nombreux outils et intégrations, notamment HubSpot et Odoo, doivent être prêts pour pouvoir basculer les connecteurs à la date choisie.
- Jordan a préparé un diagramme de Gantt ainsi qu’une liste de tâches qu’il partagera pour une discussion dédiée et un pilotage de projet.

21. Besoin de cadrage du périmètre de transfert entre Ariès et Horizon • 0:20:01

- Boris a demandé un brief clair sur les différences entre Ariès et Horizon, ainsi qu’une liste précise de ce qui sera transféré ou non.
- Il a insisté sur la nécessité d’une liste de décisions documentée pour permettre aux équipes de préparer les systèmes, les contrats et la comptabilité.

22. Justification du périmètre et risque fiscal pour l’isolement des coachs • 0:20:25

- Jordan a expliqué que les avocats avaient conseillé d’isoler les coachs et la facturation managériale dans une entité séparée afin de réduire les risques fiscaux de requalification ou de redressement.
- Le plan consiste à conserver les coachs et la facturation des heads of management chez Ariès, tout en migrant progressivement les autres services opérationnels vers Horizon avec refacturation intragroupe.
- La logique est de protéger les flux de revenus et la valorisation en séparant la facturation du personnel à risque dans une entité distincte.

23. Complexité comptable et opérationnelle de la bascule • 0:22:05

- Jordan a prévenu que la migration générera une charge de travail supplémentaire, notamment avec deux comptabilités et éventuellement deux paies pendant la période de transition.
- Il a néanmoins souligné que repartir sur Horizon apporterait des bénéfices, comme un plan comptable plus propre et un meilleur contrôle des risques historiques.

24. Partage du Gantt et de la vision de transfert • 0:23:13

- Boris a demandé à Jordan de partager le diagramme de Gantt, sa vision et le plan détaillé du transfert Ariès → Horizon pour pouvoir évaluer les impacts de son côté.

25. CGM, prise de leads et accès CRM • 0:23:23

- Jordan a demandé quel serait le plan CRM, puisque CGM commencera à prendre des leads, notamment Evergreen, et a interrogé Boris sur l’accès de CGM à HubSpot.
- Boris a confirmé que les commerciaux CGM auront accès à HubSpot et qu’ils prendront en charge leurs propres licences, ou que leur coût sera déduit de leurs commissions.

26. Gestion des licences HubSpot et réduction des frictions contractuelles • 0:24:20

- L’équipe a convenu de ne pas ajouter de friction inutile via DocuSign ou des contrats supplémentaires, et de s’assurer que toute l’activité commerciale soit bien enregistrée dans HubSpot.
- Boris a réaffirmé que si des licences HubSpot supplémentaires sont nécessaires, CGM ou leurs représentants les paieront, ou que le montant sera traité via des déductions sur commission.

27. Événements à venir et disponibilité • 0:25:28

- Jordan a exprimé son stress mais aussi son enthousiasme concernant les événements à venir, notamment le board, Marrakech et Scaling, et a confirmé sa présence à Marrakech.
- Il a indiqué qu’il pourrait devoir reprogrammer le prochain appel régulier.
- Boris a confirmé une présence limitée : il participera à l’immersion du jour 1 au jour 3, mais ne sera pas présent à l’événement Scaling en raison de priorités opérationnelles.
%% notes:fin %%
