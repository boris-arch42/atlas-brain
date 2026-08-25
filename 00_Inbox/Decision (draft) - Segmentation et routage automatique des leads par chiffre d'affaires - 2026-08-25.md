---
type: decision
statut: draft
date: 2026-08-25
source: jarvis
call: "[[2026-08-25 - Alexandre X Boris - SDR Ops]]"
tags: [decision, draft]
---

# Segmentation et routage automatique des leads par chiffre d'affaires

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Alexandre souhaite éviter de « gaspiller » les leads d'élite (entreprises >500K€ CA) en les réservant à des profils SDR plus seniors. Proposition initiale : lien/événement dédié et petite équipe privilégiée.

## Décision

Mise en place dans iClosed d'une **segmentation automatique par paliers de CA** :
- >500K€
- >1M€
- >3M€
- >10M€

Allocation automatique vers pool SDR général pour les leads ne correspondant pas aux paliers.

Pas de création de nouveau lien dédié.

## Conséquences

- Meilleur ciblage des leads à forte valeur
- Routage automatisé et scalable
- Nécessite configuration technique dans iClosed + capture origine lead (challenge, SDR, VIP) dans DataOps
- Nécessite formation SDR seniors sur approche différenciée leads VIP

## Statut

À valider par Boris
