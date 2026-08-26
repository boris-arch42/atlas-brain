---
type: decision
statut: draft
date: 2026-08-26
source: jarvis
call: "[[2026-08-26 - CRO Meeting]]"
tags: [decision, draft]
---

# Automatisation CRM des cycles de réactivation leads avec seuils et alertes

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

La réactivation des leads repose actuellement sur des actions humaines individuelles, ce qui n'est ni fiable ni scalable. Des volumes importants de contrats engagés (296k€ depuis juillet, 1,2M€ YTD) et de leads inactifs ne sont pas systématiquement relancés.

## Décision

Formaliser les rappels et suivis via des règles CRM automatiques :
- **Alerte après 15 jours d'inactivité** : lead « en attente », réactivation via invitation atelier
- **Après 1 à 1,5 mois** : lead considéré « mort » sauf raison bloquante claire (ex. financement), dépriorisation
- **Filtre à deux niveaux** : commercial d'origine puis team leader avant orientation atelier
- **Scoring** pour orienter leads vers invitation atelier ou intervention team leader

Boris et le CRM manager sont propriétaires techniques, Léa exécute/brief après 2 mois.

## Conséquences

- **Scalabilité** : processus fiable indépendant de la discipline individuelle
- **Revenu additionnel** : meilleure capture des 250-300k€ dans le funnel engagé
- **Expérience client** : distinction entre relance à valeur (atelier) et relance commerciale forte
- **Charge** : automatisation réduit la charge commerciale manuelle, libère du temps pour R2/R3

## À valider par Boris

- Validation des seuils (15j / 1-1,5 mois) et règles de scoring
- Attribution finale des responsabilités CRM manager / Léa
- Calendrier d'implémentation et métriques de suivi
