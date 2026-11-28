---
type: decision
statut: draft
date: 2026-11-28
source: jarvis
call: "[[2026-11-28 - Boris X Mathieu]]"
tags: [decision, draft]
---

# HubSpot comme unique source de vérité pour les données commerciales

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Mathieu dispose d'une plateforme d'analyse commerciale qui nécessite les données de résultats des appels (gagné/perdu). Deux options étaient possibles : faire de sa plateforme la source qui alimente HubSpot, ou l'inverse.

## Décision

HubSpot reste la source de référence (source of truth) pour toutes les données commerciales. Les statuts gagné/perdu seront transmis depuis HubSpot vers la plateforme de Mathieu, et non l'inverse.

## Conséquences

- Les closers continueront à saisir manuellement les résultats dans HubSpot (friction maintenue)
- Évite les risques de décalage et de mauvaise traduction des champs entre systèmes
- Préserve la fiabilité des processus opérationnels déclenchés par HubSpot (création contrats, accès plateforme, facturation)
- Nécessite une intégration technique pour transmettre les données de HubSpot vers la plateforme d'analyse
- La plateforme de Mathieu reste en lecture seule vis-à-vis des données commerciales

## À valider

Boris doit confirmer cette architecture et valider les implications techniques et de sécurité.
