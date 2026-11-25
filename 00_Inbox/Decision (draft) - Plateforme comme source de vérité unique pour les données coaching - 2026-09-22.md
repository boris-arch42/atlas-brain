---
type: decision
statut: draft
date: 2026-09-22
source: jarvis
call: "[[2026-09-22 - Quentin X Boris - Ops Meeting]]"
tags: [decision, draft]
---

# Plateforme comme source de vérité unique pour les données coaching

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Actuellement, les données de coaching (welcome calls, présence, cohortes, temps de présence) sont dispersées entre plusieurs outils : n8n, tableurs Google, Zoom. Cette fragmentation crée des incohérences, complique les tableaux de bord transverses et empêche une vision unifiée.

## Décision

Toutes les données de coaching principales doivent être centralisées dans la plateforme qui devient la source de vérité unique. Les workflows n8n existants (W1: prospect UpSpot, W2: inscription Zoom, W3: capture présence Zoom) seront reproduits dans la plateforme. Les tableaux de bord et besoins transverses s'alimenteront depuis cette source centrale.

## Conséquences

**Positives :**
- Données propres, cohérentes et fiables pour le pilotage
- Élimination des doubles développements et des désynchronisations
- Statistiques de présence et rattachement utilisateur garantis
- Base solide pour les automatisations futures

**Négatives :**
- Effort de migration et de reproduction des workflows existants
- Dépendance accrue à la disponibilité de la plateforme
- Nécessité de partager des jetons sensibles (Zoom) de façon sécurisée

## Actions

- Quentin reproduit les flows W1, W2, W3 dans la plateforme
- Boris partage les jetons Zoom via OneTimeSecret
- L'équipe se concentrera sur quelques domaines de données par sprint

**À valider par Boris**
