---
type: decision
statut: draft
date: 2026-08-05
source: jarvis
call: "[[2026-08-05 - Sabrina X Boris - Ops Meeting]]"
tags: [decision, draft]
---

# Intégration données tracking dans la plateforme

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

# Données et tableaux de bord doivent être intégrés dans la plateforme

## Contexte
Sabrina consacre 2h/semaine à consolider manuellement des sources disparates. Données de coût coach incorrectes (tarifs génériques vs tarifs réels variant de 70€ à 160€). Pas de tracking présence onboarding, pas de métriques opérationnelles clés. Solution temporaire HTML externe non soutenable.

## Décision
Tous les besoins de tracking, tableaux de bord et données opérationnelles doivent être résolus dans la plateforme elle-même, pas via outils ad hoc. Process en 3 étapes :
1. Boris consolide liste exacte des points de données à capturer par étape (présence discovery call, inscription onboarding, présence onboarding, complétion, etc.)
2. Sabrina fournit exemples et contournements actuels
3. Quentin/engineering estiment et implémentent dans la roadmap produit

Objectif : passer d'un volume d'entrées à une logique de conversion par "portes" avec taux mesurables (ex: présence onboarding 70% → 75% → 85%).

## Conséquences
- Élimination du travail manuel de consolidation
- Coûts de livraison réels fiables (impact P&L)
- Métriques de churn et conversion exploitables
- Nécessite priorisation roadmap produit et capacité dev Quentin
- Permet amélioration itérative mesurable du customer journey

## Statut
À valider par Boris
