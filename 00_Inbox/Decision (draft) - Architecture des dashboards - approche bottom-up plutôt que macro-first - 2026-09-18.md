---
type: decision
statut: draft
date: 2026-09-18
source: jarvis
call: "[[2026-09-18 - Review le programme core team building]]"
tags: [decision, draft]
---

# Architecture des dashboards : approche bottom-up plutôt que macro-first

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Lors de la construction du système de dashboards transverses (marketing, sales, product, finance), deux approches étaient possibles :
- Top-down : construire d'abord un command center macro puis cascader vers les équipes
- Bottom-up : partir des besoins micro de chaque fonction puis agréger vers un tableau de bord consolidé

## Décision

L'équipe a décidé de privilégier une approche **bottom-up** : construire les dashboards à partir des besoins opérationnels spécifiques de chaque responsable de fonction (marketing, sales, product, finance) puis les faire converger vers un command center macro.

Le dashboard événementiel présenté illustre cette approche avec 5 onglets spécialisés (résumé, marketing, sales, product, finance) permettant une granularité fine avant agrégation.

## Conséquences

**Positives :**
- Favorise l'adoption par les équipes qui voient directement la valeur dans leurs métriques quotidiennes
- Les responsables de fonction s'approprient leurs données et participent activement aux revues data
- Construction progressive et itérative alignée sur les besoins réels

**Négatives :**
- Risque de silos de données si l'intégration transverse n'est pas maintenue
- Nécessite des revues de données fréquentes entre départements pour assurer la cohérence
- Le command center macro arrive plus tard dans le processus

**Mitigations :**
- Boris organise des calls data réguliers (le mardi) pour aligner marketing, sales, product et finance
- Objectif d'intégration avec SuperDuo et SuperDuo SDR pour assurer la cohérence des outils
- Dashboard événementiel sert de modèle d'intégration transverse

## Statut

⚠️ **À valider par Boris** — décision en cours d'exécution, premiers résultats visibles au 1er octobre 2026.
