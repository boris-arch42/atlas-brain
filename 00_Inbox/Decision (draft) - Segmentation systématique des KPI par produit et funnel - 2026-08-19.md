---
type: decision
statut: draft
date: 2026-08-19
source: jarvis
call: "[[2026-08-19 - CRO Meeting]]"
tags: [decision, draft]
---

# Segmentation systématique des KPI par produit et funnel

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Les métriques agrégées (taux closing global 34%, délai closing moyen 11j, panier moyen 12k€) masquent des écarts majeurs entre produits (Bourbon vs Atelier vs Scaling) et funnels (Evergreen vs Challenge vs workshops). Cette agrégation empêche d'allouer correctement les commerciaux, d'évaluer le ROI publicitaire réel et de piloter la performance. Bourbon représente 86% du CA août, mais les autres produits (YouTube, workshops) n'apparaissent pas dans les dashboards actuels.

## Décision

- **Segmentation obligatoire** de tous les KPI commerciaux, marketing et finance par produit (Bourbon / Atelier / Scaling / autres) et par funnel (Evergreen / Challenge / workshops / organique)
- **Tagging systématique** des leads avec source (Evergreen/Atelier/Bourbon) pour traçabilité complète publicité → lead froid → client converti
- **Dashboards distincts** par produit dans Looker une fois mapping corrigé
- **Attribution UTM** restaurée dans HubSpot avec filtres et tutoriel pour commerciaux (action Boris)

## Conséquences

- Visibilité réelle sur performance par produit et canal, permettant optimisation allocation budget publicitaire et affectation closer
- Identification précise des causes d'échec et de la qualité lead selon funnel
- Capacité à comparer performance Evergreen (leads froids) vs Challenge (leads chauds) de manière factuelle
- Complexité accrue des reportings et nécessité de nettoyer données historiques pour rétro-compatibilité
- Dépendance à la correction préalable du mapping Make/Hotspot/Looker (deadline Boris vendredi 22/08)

## À valider par Boris

- Faisabilité technique de segmentation dans Looker une fois mapping corrigé
- Capacité à rétablir tags Bourbon et autres produits manquants dans historique
- Confirmation que tutoriel UTM et filtres HubSpot seront opérationnels d'ici fin août pour usage commercial
