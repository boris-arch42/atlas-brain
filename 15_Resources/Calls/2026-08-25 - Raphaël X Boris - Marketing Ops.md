---
type: call
date: 2026-08-25
source: sembly
participants: ["[[Boris Arduy]]", "raphael.dalleau@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-08-25
---

# Raphaël X Boris - Marketing Ops

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (25/08/2026 11:06).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 25/08/2026 11:11 — corrige librement hors des marqueurs.

**Résumé** — Audit approfondi du tracking et de l'analytique des tunnels marketing (book et quiz), révélant des lacunes importantes dans le suivi des événements, les emails de pré-appel et l'attribution par source. Mise en place d'un dashboard consolidé pour centraliser les métriques de performance de bout en bout.

**Décisions**
- Création d'un événement iClosed dédié 'quiz final' pour atteindre la parité avec le tunnel book
- Ajout d'un bouton unique tracké dans le SDR Hub pour éviter les erreurs de liens
- Intégration des dépenses publicitaires et pages vues au dashboard avec alertes codées par couleur
- Attribution granulaire du revenu au niveau source/medium/campagne/annonce pour chaque tunnel

**Actions**
- [ ] **Raphael** : Lister tous les champs de données et objectifs nécessaires pour chaque funnel (book final, quiz final, troisième funnel) (échéance 2026-08-25)
- [ ] **Boris** : Implémenter l'événement iClosed dédié 'quiz final'
- [ ] **Boris** : Ajouter les dépenses publicitaires et pages vues au dashboard avec taux de conversion par page
- [ ] **Boris** : Configurer l'attribution granulaire par source/medium/campagne/annonce avec métriques de revenu
- [ ] **Boris** : Corriger les emails de pré-appel manquants pour les réservations du quiz final (priorité haute)
- [ ] **Boris** : Ajouter un bouton unique tracké dans le SDR Hub pour éviter les erreurs manuelles
- [ ] **Boris** : Configurer les paramètres UTM (source/medium/campaign) pour les embeds à forte conversion
- [ ] **Boris** : Fournir un lien tracké pour les campagnes Meta et YouTube du nouveau funnel (échéance 2026-08-25)
- [ ] **Boris** : Renforcer la configuration Looker Studio pour remonter davantage d'événements
- [ ] **Raphael** : Publier le nouveau formulaire et lancer le funnel avec petit budget test (échéance 2026-08-25)

**Risques & vigilances**
- Le suivi des SDR reste fragile car l'envoi de plusieurs liens trackés est source d'erreurs importantes
- De nombreux événements ne sont toujours pas suivis, ce qui bloque l'exhaustivité de l'analytique et fausse les métriques de conversion
- Les emails de pré-appel manquants pour le quiz final impactent négativement les taux de présence aux appels
- Le tunnel quiz sous-estime probablement les appels réels (183 vs attendu beaucoup plus) à cause du tracking incomplet
- Le VSL événementiel manque de description d'événement et de questions, ce qui peut nuire aux conversions

Tags : #marketing-ops #tracking #analytique #dashboard #tunnels-conversion
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 25/08/2026 11:06 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

La réunion a porté sur les lacunes de suivi et d’analytique des tunnels « book » et « quiz ». L’équipe a convenu de mettre en place des événements dédiés, le suivi des pages vues, des embeds hautement convertis tagués en UTM, ainsi que des vues de tableau de bord pour centraliser les performances et les métriques de source vers revenu. Les actions principales sont les suivantes : Raphael doit lister les données nécessaires par tunnel, Boris doit implémenter les événements, les paramètres UTM et les intégrations au dashboard, et l’équipe doit corriger les emails de pré-appel manquants ainsi que les flux de suivi des SDR.

📋 Outline

1. Écart de suivi entre le tunnel book et le tunnel quiz • 0:00:29

- Boris a constaté que le tunnel book dispose d’un événement iClosed dédié, alors que le tunnel quiz n’en a pas, ce qui entraîne probablement une sous-estimation des appels issus du quiz. (Responsable : Boris).
- Raphael a confirmé que les données du tunnel book sont fiables, mais que le tunnel quiz ne montre que 183 appels enregistrés, signe d’événements suivis manquants. (Responsable : Raphael).
- Boris a demandé la création d’un événement iClosed dédié « quiz final » afin d’atteindre la parité avec le tunnel book et d’améliorer la précision du suivi. (Responsable : Boris / Ingénierie).

2. Emplacement des embeds iClosed et déclenchement du suivi • 0:01:36

- Boris a demandé où sont placés les embeds iClosed et a appris qu’ils ne sont intégrés que sur la page finale de ScoreApp, et non dans les emails. (Responsable : Raphael).
- Raphael a confirmé qu’il n’existe pas d’embeds iClosed dans les emails, ce qui simplifie le périmètre du suivi. (Responsable : Raphael).

3. Suivi des réservations effectuées par les SDR versus réservations autonomes • 0:02:56

- Boris souhaite une visibilité complète du funnel en distinguant les appels réservés directement par les utilisateurs de ceux réservés par les SDR afin de mesurer la performance des sources. (Responsable : Boris).
- Le suivi actuel des SDR est fragile, car l’envoi de plusieurs liens suivis aux SDR est source d’erreurs. (Responsable : Boris / Responsable SDR).
- Boris a proposé d’ajouter un bouton unique suivi dans le SDR Hub, qui redirigerait automatiquement les SDR vers le bon lien tracké pour éviter une sélection manuelle. (Responsable : Boris).

4. Ajout des dépenses publicitaires, des pages vues et des métriques de conversion par page au tableau de bord • 0:05:15

- Boris ajoutera les dépenses publicitaires et les pages vues au dashboard afin de pouvoir consulter les taux de conversion par page sans quitter le tableau de bord. (Responsable : Boris / Analytique).
- L’équipe veut centraliser des métriques comme le taux de conversion des pages et le taux de présence pour faciliter des contrôles quotidiens de la santé de chaque tunnel. (Responsable : Boris / Raphael).
- Boris prévoit d’implémenter des alertes quotidiennes codées par couleur (vert/orange/rouge) selon les objectifs de chaque tunnel afin de faire ressortir les anomalies. (Responsable : Boris / Analytique).

5. Attribution granulaire du revenu et des conversions au niveau source / annonce • 0:07:50

- Raphael a demandé des ventilations d’origine par source, medium, campagne et annonce afin que la contribution de chaque annonce en leads, appels et revenus soit visible. (Responsable : Raphael).
- Boris a accepté d’ajouter des métriques par annonce montrant le nombre d’appels et le revenu généré par chaque créatif, afin de permettre un calcul du ROI par annonce. (Responsable : Boris / Analytique).
- La vue souhaitée doit afficher la part d’opt-in, le nombre d’appels générés et le revenu par annonce pour les principaux tunnels evergreen. (Responsable : Raphael pour préciser les objectifs ; Boris pour implémenter).

6. Concept d’un agent IA pour analyser les données du funnel • 0:08:59

- Boris a proposé un agent IA capable d’analyser le contexte complet des données collectées, d’identifier les métriques sous-performantes et de suggérer des remédiations. (Responsable : Boris / Produit).
- Raphael a exprimé des doutes sur l’efficacité d’un agent IA pour cette tâche, mais a convenu qu’il s’agit d’un projet séparé à traiter plus tard, une fois la qualité des données améliorée. (Responsable : Raphael).

7. Prochaines étapes pour l’inventaire des données requises du funnel • 0:10:03

- Boris a demandé à Raphael de fournir un document listant tous les champs de données et les objectifs nécessaires pour chaque funnel (book final, quiz final et le troisième funnel à venir). (Responsable : Raphael).
- Raphael a accepté d’envoyer cette liste plus tard dans la journée afin que Boris puisse configurer le suivi et le dashboard. (Responsable : Raphael puis Boris).

8. Utilité du dashboard et besoins de suivi quotidien • 0:10:37

- Raphael a confirmé que le dashboard consolidé sera très utile et remplacera la consultation de plusieurs outils pour contrôler quotidiennement la santé des tunnels. (Responsable : Raphael).
- Boris a indiqué que le lien entre ventes et paiements passera par l’ID de deal HubSpot afin de relier ensuite les deals aux données finance. (Responsable : Boris / Ops).

9. Emails de pré-appel manquants et urgence sur l’automatisation • 0:14:00

- Raphael a découvert qu’aucun email de pré-appel n’est envoyé pour les réservations du quiz final et que les emails de pré-appel manquent aussi pour certains flux d’appel. (Responsable : Raphael).
- Boris a reconnu le caractère urgent du problème et a précisé que les emails du tunnel book ont été corrigés, mais que ceux du quiz final doivent encore l’être. (Responsable : Boris / Propriétaire de l’automatisation email).
- L’équipe a classé la remise en place des emails de pré-appel pour les réservations du quiz final comme une priorité élevée. (Responsable : Boris / Automatisation).

10. Suivi des embeds à forte conversion et paramétrage UTM • 0:16:50

- Boris a demandé que les embeds à forte conversion soient suivis et incluent des paramètres UTM source / medium / campaign pour l’attribution. (Responsable : Boris / Ingénierie).
- Raphael publiera un nouveau formulaire et souhaite que le VSL événementiel soit revu, car il manque actuellement de description d’événement et de questions. (Responsable : Raphael ; revue : Boris).

11. Calendrier de lancement, canaux et liens trackés pour le nouveau funnel • 0:18:52

- Raphael prévoit de lancer aujourd’hui le nouveau funnel / landing page et de commencer avec un faible budget pendant que les données se stabilisent. (Responsable : Raphael).
- Raphael diffusera du trafic payant sur Meta et YouTube et a demandé à Boris un lien tracké à ajouter aux créatifs publicitaires. (Responsable : Raphael pour les campagnes ; Boris pour fournir le lien tracké).

12. Événements non suivis restants et données Looker Studio • 0:20:31

- Raphael a indiqué que de nombreux événements ne sont toujours pas suivis, ce qui bloque l’exhaustivité de l’analytique. (Responsable : Raphael / Ingénierie).
- Boris a confirmé qu’il surveille Looker Studio et qu’il va renforcer la configuration afin que davantage de données y remontent. (Responsable : Boris).
- Raphael a signalé que certaines données apparaissent déjà dans Looker Studio, mais que tous les événements n’y figurent pas encore. (Responsable : Raphael).
%% notes:fin %%
