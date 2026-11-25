---
type: decision
statut: draft
date: 2026-10-29
source: jarvis
call: "[[2026-10-29 - Rachid & Boris]]"
tags: [decision, draft]
---

# Blocage conditionnel des bookings et assignation obligatoire SDR

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Les données SDR actuelles sont peu fiables : rendez-vous pris sur calendriers personnels non tracés, écarts entre meetings déclarés et revenu réel, attribution erronée via UTM lors d'événements live. Cette situation compromet la prise de décision et nécessite une reconstruction du système de tracking.

## Décision

- **Assignation owner obligatoire** : Le SDR doit s'assigner comme owner du lead avant toute action de booking
- **Génération automatique du lien** : HubSpot/Hotspot calcule et remplit automatiquement le champ "lien de réservation" selon le funnel et l'owner du lead
- **Blocage si non-conforme** : Si le lead owner n'est pas renseigné, le lien ne se génère pas, le booking est bloqué et une alerte est créée
- **Interdiction des liens personnels** : Calendly et autres liens individuels non tracés sont proscrits
- **Chaîne de traçabilité** : booking → deal ID → lead associé → owner SDR (ESR/SDR, pas owner générique)

## Conséquences

- **Positif** : Restauration de la confiance dans les métriques, élimination des trous d'attribution, dashboards fiables, alertes exploitables
- **Effort** : Configuration des règles d'automatisation HubSpot, formation des SDR au nouveau process, coordination avec équipes Boris pour ne pas casser dashboards existants
- **Contrainte** : Process plus strict, nécessite discipline et verrouillage conditionnel de certains champs

## À valider par Boris

- Validation finale de la logique d'assignation owner spécifique par source
- Arbitrage sur les combinaisons de paramètres UTM (liens uniques par funnel vs multiplication)
- Calendrier de déploiement des règles HubSpot et formation équipe
