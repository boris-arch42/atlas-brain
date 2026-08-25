---
type: decision
statut: draft
date: 2026-08-24
source: jarvis
call: "[[2026-08-24 - Adil & Boris]]"
tags: [decision, draft]
---

# Architecture d'attribution multi-niveaux (UTM + liens courts parent/enfant)

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

L'équipe lance une semaine de scaling avec acquisition payante et souhaite mesurer le ROI jusqu'au niveau publicité → vente. Actuellement, l'attribution est incomplète (pas d'UTM sur les liens calendrier, incohérence des liens iClosed) et les dashboards Looker montrent ~2% de leads à source non définie, mais la granularité reste insuffisante pour des A/B tests précis.

## Décision

Mise en place d'une architecture d'attribution à deux niveaux :

1. **Niveau tunnel/funnel :** liens iClosed avec UTM (source, medium, campaign) alignés sur la nomenclature iClosed, codés par couleur dans les dashboards (rouge challenge/webinar, vert evergreen, jaune organique, bleu calendrier).
2. **Niveau canal/diffusion :** liens courts enfants (par canal : WhatsApp, newsletter, etc.) redirigent vers des liens parents, permettant de changer globalement la destination tout en conservant l'attribution canal.

Les SDR recevront deux liens calendrier par funnel (standard + UTM), les dashboards Data Studio d'Adil fourniront l'attribution granulaire ad→sale.

## Conséquences

**Positif :**
- Attribution complète publicité → présence live → RDV → vente
- Possibilité d'A/B tests au niveau créa publicitaire
- Flexibilité : modifier la destination globale sans recréer les liens diffusés
- Dashboard unifié pour les décisions d'acquisition

**À surveiller :**
- Complexité de gestion pour les SDR (plusieurs liens calendrier)
- Maintenance du mapping parent/enfant dans la feuille de calcul
- Risque d'erreur humaine (utilisation du mauvais lien)
- Nécessité de formation/briefing pour Alex et l'équipe SDR

**Responsabilités :**
- Boris : création liens iClosed + UTM, mapping funnels/embed, documentation templates
- Adil : gestion tableau liens courts, convention UTM, coordination SDR

## Validation Boris

- [ ] À valider
