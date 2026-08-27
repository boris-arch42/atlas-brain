---
type: decision
statut: draft
date: 2026-08-27
source: jarvis
call: "[[2026-08-27 - SDR Call - Update]]"
tags: [decision, draft]
---

# Approche data-first pour le dispositif SDR

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

L'équipe SDR manque de données fiables pour optimiser la performance commerciale. Les blocs de données macro existent mais sans profondeur ni corrélations, empêchant les décisions d'optimisation fines. Le système actuel ne permet pas de suivre les métriques clés par canal ni d'identifier les leviers de performance.

## Décision

Prioriser la construction d'un dispositif SDR « data-first » avant le recrutement massif :

1. **Hub SDR central** : plateforme unique agrégeant tous les leads non convertis, remplaçant les feuilles dispersées
2. **Métriques standardisées par canal** : speed-to-lead, appels par lead, taux de décrochage, taux de booking, show-up, closing
3. **Système de priorisation automatique** : coloration des leads selon source et chaleur, routage optimisé
4. **Notifications temps réel** : alertes instantanées pour garantir le speed-to-lead sous 5 minutes
5. **Analyse des top performers** : extraction des meilleures pratiques pour créer des ressources de formation
6. **Scripts adaptés par funnel** : postures différenciées selon quiz/webinaire/VSL/lead magnet

Le recrutement et l'onboarding n'interviendront qu'après la mise en place de ces processus et indicateurs.

## Conséquences

**Positives** :
- Décisions fondées sur des données exploitables plutôt que sur l'intuition
- Allocation optimale des ressources SDR aux funnels les plus performants
- Réduction de la dépendance aux profils exceptionnels grâce aux processus standardisés
- Capacité à générer des améliorations incrémentales de 1-3% sur chaque bloc
- Formation ciblée basée sur les écarts de performance identifiés

**Négatives / Risques** :
- Retard sur le recrutement (2-3 semaines de développement du Hub)
- Dépendance à la qualité d'implémentation technique (APIs, temps réel)
- Complexité accrue du système à maintenir
- Nécessite une discipline rigoureuse de collecte et de revue des données

## À valider par Boris

- Priorisation dev pour les fonctionnalités temps réel du Hub (48-72h annoncées)
- Schéma de données définitif et intégrations API nécessaires
- Allocation ressources tech pour l'implémentation vs autres priorités
- Timeline de déploiement avant reprise du recrutement SDR
