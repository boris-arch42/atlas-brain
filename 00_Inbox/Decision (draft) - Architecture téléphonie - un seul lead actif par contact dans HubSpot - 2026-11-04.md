---
type: decision
statut: draft
date: 2026-11-04
source: jarvis
call: "[[2026-11-04 - Entrepreneurs.com KO]]"
tags: [decision, draft]
---

# Architecture téléphonie : un seul lead actif par contact dans HubSpot

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Un contact HubSpot peut avoir plusieurs leads issus de différentes campagnes marketing, chacun avec le même numéro de téléphone. CloudTalk risque d'appeler plusieurs fois le même numéro ou de créer de la confusion dans l'attribution.

## Décision

Mise en place d'un workflow HubSpot automatique qui :
- Ferme automatiquement les anciens leads lorsqu'un nouveau lead est créé pour le même contact
- Ne conserve qu'un seul lead actif par contact, le plus récent
- Met à jour le contact avec la source du lead le plus récent
- Permet ainsi au composeur parallèle CloudTalk de ne voir qu'un seul lead actif à appeler

## Conséquences

**Positives :**
- Évite les doublons d'appels sur le même numéro
- Simplifie la vue commerciale (un seul lead actif visible)
- Facilite l'intégration CloudTalk ↔ HubSpot
- Préserve l'historique des leads fermés pour analytics

**Négatives :**
- Perte potentielle de visibilité multi-campagne en temps réel
- Nécessite un workflow HubSpot robuste et testé
- Dépendance à l'automation HubSpot pour la cohérence des données

## À valider par Boris

- Cette logique est-elle compatible avec le modèle de qualification et d'attribution existant ?
- Faut-il prévoir des exceptions (certains leads ne se ferment jamais automatiquement) ?
- Quel impact sur les reportings multi-sources et l'attribution marketing ?
