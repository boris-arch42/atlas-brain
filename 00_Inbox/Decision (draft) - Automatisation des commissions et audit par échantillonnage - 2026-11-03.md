---
type: decision
statut: draft
date: 2026-11-03
source: jarvis
call: "[[2026-11-03 - Jordan X Boris - Ops Meeting]]"
tags: [decision, draft]
---

# Automatisation des commissions et audit par échantillonnage

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Le système de commission actuel génère des erreurs de rapprochement entre paiements et deals, notamment pour les deals historiques pré-avril. Les factures coach deliveries (200-220k€/mois, ~40 factures) sont contrôlées manuellement par Claire sans centralisation dans la plateforme.

## Décision

1. **Commission** : Maintenir le dashboard automatisé qui relie paiements→deals→closers→SDR. Corriger le matching IA qui utilise d'anciens identifiants. Documenter exceptions historiques.

2. **Factures deliveries** : Centraliser toutes les données de facturation dans la plateforme. Mettre en place un audit par échantillonnage (20% des factures/mois en rotation) plutôt qu'un contrôle exhaustif. Crash test prévu pour valider la méthode de rapprochement sessions enregistrées vs facturées.

## Conséquences

- Réduction des erreurs de commission et des frictions internes
- Maintien d'un contrôle acceptable (échantillonnage) tout en automatisant
- Nécessite implication Mohamed (IA matching), Claire (process actuel), Quentin/Léonard (automatisation)
- Libère du temps ops pour tâches à plus forte valeur

## À valider

- Résultats du crash test 03/11 20h30
- Faisabilité technique de l'automatisation par Quentin/Léonard
- Niveau de risque acceptable pour l'échantillonnage
