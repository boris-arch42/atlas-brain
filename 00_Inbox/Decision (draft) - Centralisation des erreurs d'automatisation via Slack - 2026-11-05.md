---
type: decision
statut: draft
date: 2026-11-05
source: jarvis
call: "[[2026-11-05 - Weekly catchup with Boris]]"
tags: [decision, draft]
---

# Centralisation des erreurs d'automatisation via Slack

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Plus de 100 automatisations obsolètes continuent de s'exécuter suite à des changements de processus ou départs de collaborateurs, générant des notifications d'erreur. Les connexions entre outils désactivés (Monday.com, Airtable) créent des erreurs récurrentes difficiles à tracer.

## Décision

Création d'un canal Slack dédié recevant toutes les notifications d'erreur d'automatisation, incluant le nom/lien de l'automatisation concernée. Boris arbitrera pour chaque erreur signalée : suppression, correction ou archivage de l'automatisation.

## Conséquences

- Visibilité centralisée des automatisations défaillantes
- Processus de décision clair pour nettoyer l'environnement technique
- Réduction progressive du bruit et des faux positifs
- Nécessite discipline de suivi et arbitrage régulier de Boris

## Statut

**À valider par Boris** — implémentation par Aman.
