---
type: decision
statut: draft
date: 2026-08-13
source: jarvis
call: "[[2026-08-13 - CRO Meeting]]"
tags: [decision, draft]
---

# Règle d'attribution unique source initiale vs événement final

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Les closers écrasent actuellement la source initiale (ex: homepage) par l'événement final de conversion (ex: webinaire, 5D) dans HubSpot lors du marquage Won. Cela crée :
- Une impossibilité de séparer performance marketing vs SDR
- Des dashboards de canal inexacts et un ROI marketing non fiable
- Une fuite apparente de 113 appels site → 2 conversions (potentiellement 150k€ manquants)
- Un mélange des données SDR et communication rendant les rapports inutilisables

## Décision à valider

Établir une règle ferme d'attribution à deux niveaux :
1. **Source initiale (first touch)** : conservée et non écrasable, trackant le premier point de contact (homepage, organic, pub, etc.)
2. **Source de conversion (last touch)** : événement final ayant déclenché la vente (5D, Bourbon, webinaire, etc.)
3. Bloquer techniquement la possibilité pour les closers d'écraser la source initiale
4. Former Sales sur la saisie correcte des deux champs dans HubSpot
5. Auditer les 113 appels site pour reconstruire l'attribution correcte

## Conséquences

**Positives :**
- Visibilité claire sur ROI par canal marketing et performance SDR
- Dashboards fiables pour la prise de décision
- Attribution correcte du revenu par source
- Capacité à mesurer l'impact réel du site/organic vs événementiel

**Négatives :**
- Effort one-time d'audit des 113 enregistrements
- Formation nécessaire pour Sales et closers
- Implémentation technique de règles de validation HubSpot

**Responsables :** Boris (technique/CRM), Aziz (Sales), équipe BI

**Timeline :** Règles définies sous 1 semaine, implémentation technique sous 2 semaines, audit des 113 appels parallèle.
