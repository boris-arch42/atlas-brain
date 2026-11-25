---
type: decision
statut: draft
date: 2026-11-03
source: jarvis
call: "[[2026-11-03 - ⚔️ Squad SDR - Finaliser la machine de guerre]]"
tags: [decision, draft]
---

# Architecture de tracking double niveau : contact initial + lead par funnel

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

L'équipe SDR doit tracer à la fois l'origine initiale du contact (première interaction) et l'origine de chaque lead/réservation générée ultérieurement. Un contact peut provenir d'Instagram puis réserver via un webinar des mois plus tard.

## Décision

- **Contact** : tracking initial du contact figé à la création, jamais écrasé (source d'acquisition première)
- **Lead** : tracking spécifique par funnel (opt-in + réservation), avec deux jeux distincts d'UTM (source opt-in / source booking)
- **Deal** : hérite du tracking du lead associé
- Tous les champs de tracking convertis en listes déroulantes verrouillées pour éviter saisies libres
- Propriété calculée pour générer liens iClose dynamiques par funnel + owner

## Conséquences

**Avantages :**
- Attribution multi-touch fiable sur cycles longs
- Dashboards cohérents par canal et par funnel
- Réduction drastique des erreurs de saisie
- Automatisation des liens iClose réduit la maintenance

**Inconvénients :**
- Complexité accrue pour les utilisateurs (deux niveaux de tracking)
- Risque de doublons si workflow de fusion non configuré
- Formation obligatoire pour toute l'équipe marketing et SDR

**Actions de suivi :**
- Documenter l'architecture dans un schéma visuel
- Former équipes marketing, SDR et ops sur la gouvernance des listes déroulantes
- Mettre en place workflow de déduplication automatique

## Statut

À valider par Boris
