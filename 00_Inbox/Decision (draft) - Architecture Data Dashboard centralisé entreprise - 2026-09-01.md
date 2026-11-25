---
type: decision
statut: draft
date: 2026-09-01
source: jarvis
call: "[[2026-09-01 - Weekly Catch Up with Boris]]"
tags: [decision, draft]
---

# Architecture Data Dashboard centralisé entreprise

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

L'entreprise manque de visibilité centralisée sur les données de funnels, événements marketing et opérations. Les données sont fragmentées entre différents outils (HubSpot, calendriers, pages funnel) sans process documenté d'ingestion.

## Décision

Mise en place d'un Data Dashboard centralisé avec :
- Process documenté d'ingestion des données de Thomas vers BigQuery/Looker Studio
- Architecture en couches (storage, queries, staging)
- ID de deal HubSpot comme clé de référence pour relier visiteurs, leads, appels et ventes
- Filtres calendaires précis et pop-ups de détails sur chaque deal
- Template validé sur book/quiz funnel puis dupliqué sur autres funnels
- Organisation cloud dédiée si nécessaire (séparée de l'équipe IA)

## Conséquences

**Positives :**
- Vision unifiée des performances sur tous les funnels
- Réconciliation fiable entre événements calendrier et ventes HubSpot
- Scalabilité par duplication de templates
- Autonomie de l'équipe data via process documenté

**Négatives :**
- Deadline serrée fin septembre nécessite focus total équipe
- Complexité de coordination avec Thomas et équipe IA
- Risque de dérive de périmètre si tous funnels à couvrir

## À valider par Boris
- Périmètre exact des funnels prioritaires vs secondaires
- Budget et setup organisation cloud
- Niveau de détail des pop-ups et métriques dashboard
