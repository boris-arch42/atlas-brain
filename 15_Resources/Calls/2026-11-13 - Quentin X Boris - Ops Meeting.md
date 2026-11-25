---
type: call
date: 2026-11-13
source: sembly
participants: ["[[Boris Arduy]]", "[[Quentin]]"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-11-20
---

# Quentin X Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (13/11/2026 10:44).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 20/11/2026 10:48 — corrige librement hors des marqueurs.

**Résumé** — Point opérationnel sur l'onboarding payant, la gestion des chambres immersion et le suivi HubSpot. Quentin alerte sur les graves problèmes d'exécution du pôle fidélisation malgré la satisfaction client, et recommande une due diligence technique indépendante avant tout investissement dans Aïko.

**Décisions**
- Privilégier une stratégie de mise à jour légère du code pour éviter 300k lignes de conflits
- Lancer l'onboarding payant en début de semaine après tests finaux
- Créer un canal privé pour les alertes de suivi des ventes
- Alexandre Gauthier doit retravailler son document de fidélisation après analyse insuffisante de la plateforme

**Actions**
- [ ] **Quentin** : Vérifier que le produit onboarding payant existe dans HubSpot et que l'automatisation fonctionne (échéance 2026-11-15)
- [ ] **Quentin** : Tester le parcours complet onboarding payant avec le compte test (échéance 2026-12-05)
- [ ] **Jordan** : Préparer les contrats pour les ventes par téléphone de l'onboarding payant
- [ ] **Boris** : Transmettre les paramètres pour la gestion des chambres (dates limites, nombre max)
- [ ] **Quentin** : Vérifier que les achats d'immersion remontent correctement dans HubSpot
- [ ] **Boris** : Examiner avec les équipes le rapport des automatisations Make qui écrasent des données HubSpot
- [ ] **Boris** : Créer le canal privé pour les alertes de suivi des ventes et y ajouter Quentin (échéance 2026-11-14)
- [ ] **Quentin** : Intégrer le bot plateforme au canal privé une fois créé pour publier les infos ventes (échéance 2026-11-15)
- [ ] **Quentin** : Envoyer à Boris le document d'Alexandre Gauthier sur la fidélisation (échéance 2026-11-13)

**Risques & vigilances**
- Écrasement de données contacts dans HubSpot par des automatisations Make non maîtrisées
- Pôle fidélisation : taux d'upsell historiquement très faible malgré la satisfaction client
- Alexandre Gauthier : manque de rigueur dans l'étude préalable (quelques connexions seulement entre fin septembre et 23 octobre) et absence de réponse depuis mercredi
- Projet fidélisation : aucun projet créé dans Worx malgré la demande de Boris
- Validation Caroline attendue depuis plusieurs semaines sur automatisation HubSpot clients sortants
- Aïko : collaboration difficile (retards clés API, tensions initiales, accusation de copie produit)
- Aïko : différenciation technique jugée faible face à la concurrence, nécessité d'une due diligence indépendante avant investissement si l'argument principal est technologique

**Projets liés** : [[Immersion]] · [[Cadence transverse & top 10 process]]

Tags : #ops #onboarding-payant #hubspot #fidelisation #aiko-due-diligence
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 13/11/2026 10:44 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a fait le point sur l’onboarding payant, la gestion et le suivi des chambres pour les immersions, ainsi que sur les risques d’écrasement de données dans HubSpot. Aura a été livré avec de bons retours préliminaires, et le suivi des ventes doit être lancé après la création d’un canal privé dédié. Quentin a signalé de graves problèmes de suivi et d’exécution sur le pôle fidélisation, malgré une forte satisfaction des clients accompagnés jusqu’au bout. Il a également partagé un retour prudent sur Aïko : l’intégration fonctionne, mais tout investissement fondé principalement sur la technologie devrait être précédé d’une due diligence technique indépendante.

📋 Outline

1. Stratégie de gestion des conflits de code • 0:00:00

- Une mise à jour importante présentait environ 300 000 différences de code et aurait entraîné des conflits majeurs.
- L’équipe a privilégié une stratégie de mise à jour plus légère.

2. Finalisation de l’onboarding payant • 0:00:14

- Quentin finalise l’onboarding payant et prévoit encore quelques ajustements avant un lancement en début de semaine.
- Le produit semble déjà créé dans HubSpot, mais Quentin doit le vérifier et confirmer que l’automatisation fonctionne correctement.
- Un compte de test est disponible et le parcours doit être testé avant le 5 décembre.
- Les contrats destinés aux ventes par téléphone doivent être préparés par Jordan ; le parcours ne repose pas sur un lien de paiement en libre-service.

3. Gestion des chambres pour les immersions • 0:01:46

- La plateforme permet déjà de gérer les places d’immersion, mais pas encore clairement l’achat de chambres supplémentaires.
- Pour l’organisation, il faut distinguer les clients dont la chambre est incluse au contrat et ceux qui achètent une chambre supplémentaire que l’équipe doit réserver.
- Les participants qui réservent eux-mêmes leur chambre n’ont pas besoin d’être inclus dans les réservations gérées par l’équipe.
- Quentin indique que la rooming list existe déjà sur la plateforme et peut être améliorée pour afficher les chambres incluses ou achetées en supplément.
- Les données peuvent aussi être exportées en CSV ; l’interface doit être simplifiée et un paiement avec une date limite pourra être ajouté.
- Boris doit transmettre les paramètres nécessaires, notamment les dates limites et le nombre maximal de chambres disponibles.

4. Remontée des achats d’immersion dans HubSpot • 0:05:43

- Boris souhaite que les achats de places d’immersion soient enregistrés dans HubSpot afin de disposer d’un historique complet des transactions et d’analyser la valeur vie client.
- Quentin pense que le suivi est déjà configuré, mais doit le vérifier et confirmer le fonctionnement de bout en bout après un nouvel achat.

5. Prévention des écrasements de données entre systèmes • 0:07:45

- Un rapport recense des automatisations Make susceptibles de modifier ou d’écraser des champs de contacts, avec les identifiants des automatisations concernées.
- La revue de HubSpot vise à conserver un contact unique par personne, avec plusieurs leads et deals associés selon les inscriptions et rendez-vous.
- Des exemples de données incorrectement remplacées, notamment des prénoms, ont été signalés.
- Boris va examiner le rapport avec ses équipes pour identifier l’origine du problème, y compris les échanges de données potentiels entre HubSpot et Odoo.
- Quentin précise que la plateforme autorise certaines mises à jour, mais que des contrôles empêchent notamment les commerciaux de modifier certaines dates contractuelles après la clôture d’un deal.

6. Livraison et adoption d’Aura • 0:11:46

- Aura, le nom définitif du produit de coaching en direct assisté par IA, a été livré.
- Le produit analyse les séances et suit les éléments abordés afin d’améliorer les trames de coaching et de faire remonter des notes dans Superbob.
- Le déploiement a été progressif auprès de coachs testeurs ; les retours sont bons et plusieurs améliorations ont déjà été apportées.
- L’équipe continue de suivre l’adoption, car le volume de retours reste encore limité.

7. Mise en place des alertes de suivi des ventes • 0:12:43

- Quentin dispose des journaux et des données historiques issues de Google Workspace et Ngram, notamment les dates d’arrivée, la présence et la durée de participation.
- La mise en place des alertes dépend encore de la création d’un canal privé et de l’ajout de Quentin à ce canal.
- Boris va créer le canal privé et y ajouter Quentin ; Quentin y intégrera le bot de la plateforme pour publier les informations.
- Quentin indique que les données et les préparatifs sont prêts, et qu’il pourra lancer le dispositif une fois le canal disponible.

8. Suivi du pôle fidélisation et qualité du travail d’Alexandre Gauthier • 0:15:30

- Quentin rapporte que Claire confirme que les clients qui vont au terme de l’accompagnement et ne sont pas en impayé reçoivent une réelle valeur et sont très satisfaits.
- Selon Quentin, le taux historique d’upsell et de fidélisation est très faible malgré les initiatives successives.
- Quentin estime qu’Alexandre Gauthier n’a pas suffisamment étudié la plateforme pour produire son document de fidélisation et indique que ses journaux de connexion montrent seulement quelques accès entre fin septembre et le 23 octobre, avec une dernière ouverture le 23 octobre.
- Quentin a demandé à Alexandre de retravailler son document et de respecter le temps de l’équipe, mais indique ne pas avoir reçu de réponse depuis mercredi matin.
- Boris indique qu’il n’a pas reçu le document et qu’aucun projet de fidélisation n’a été créé dans Worx, malgré sa demande.
- Quentin précise que trois tâches existent et qu’il a signalé les problèmes, tagué Alexandre et passé les tâches en statut bloqué faute de retour.
- Quentin explique que les échanges avec les clients sortants pourraient porter sur leur avancement sans coach, puis proposer une reprise de l’accompagnement si les progrès sont insuffisants.
- Quentin rappelle qu’une automatisation HubSpot a été réalisée sur un compte test et documentée plusieurs semaines auparavant, mais qu’une validation attendue de Caroline n’a pas été remontée.
- Quentin suggère qu’en période de recherche de trésorerie, l’équipe pourrait contacter directement les clients sortants, même sans s’appuyer sur la plateforme.
- Boris demande à Quentin de lui envoyer le document d’Alexandre.

9. Retour sur Aïko et précautions avant un éventuel investissement • 0:22:55

- Quentin décrit des difficultés de collaboration avec Aïko, notamment des retards dans la transmission des clés nécessaires aux tests et dans les étapes de mise en production.
- Quentin rapporte que le premier échange a été tendu et qu’Aïko aurait accusé l’équipe d’avoir copié son produit, alors que leur module RH avait été développé auparavant.
- L’intégration d’Aïko sur la plateforme fonctionne et Quentin considère que le travail d’intégration est terminé, tout en estimant que certains aspects de l’expérience produit pourraient être améliorés.
- Quentin estime que le produit présente une forte concurrence et que certains éléments techniques, notamment la génération et la prospection de contacts, ne semblent pas constituer une différenciation technique majeure.
- Quentin recommande la prudence si l’investissement envisagé repose principalement sur la technologie et suggère une due diligence menée par une société d’audit technique.
- Quentin distingue cette réserve d’un investissement orienté vers le potentiel commercial, qu’il dit ne pas être en mesure d’évaluer.
- Quentin propose de détailler le fonctionnement technique ou de réaliser une preuve de concept rapide pour éclairer l’évaluation.
%% notes:fin %%
