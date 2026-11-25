---
type: decision
statut: draft
date: 2026-09-16
source: jarvis
call: "[[2026-09-16 - Abdel X Boris - Prépa des deux ateliers Scaling]]"
tags: [decision, draft]
---

# Migration dashboards et approche bottom-up data

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Ancienne architecture Looker coûtait ~60k€/an (ressource dédiée), rafraîchissement données 24h, approche macro-first peu adoptée par les équipes. Stack complexe avec Stitch provoquant pertes et retards.

## Décision

- Migration vers stack flexible (ex: Vercel) permettant visuels riches et agents IA
- Connexion directe aux API sources (Meta Ads, Google) pour rafraîchissement ~1h (vs 24h)
- Approche bottom-up : construire dashboards à partir des besoins funnel de chaque équipe, puis agréger au niveau direction
- Coût réduit à ~12k€/an

## Conséquences

- Latence de décision réduite d'un facteur 24
- Meilleure adoption par les équipes (dashboards alignés sur leurs usages)
- Économies ~48k€/an sur développement dashboards
- Alertes temps réel possibles avec renvoi vers zones spécifiques du dashboard
- Suivi performance au niveau des ads individuelles via API

## Validation

À valider par Boris pour intégration atelier Scaling.
