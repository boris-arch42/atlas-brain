---
type: decision
statut: draft
date: 2026-08-25
source: jarvis
call: "[[2026-08-25 - Raphaël X Boris - Marketing Ops]]"
tags: [decision, draft]
---

# Architecture de tracking granulaire source-to-revenue pour les tunnels marketing

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Le suivi actuel des tunnels marketing présente des lacunes importantes :
- Le tunnel quiz n'a pas d'événement iClosed dédié (contrairement au tunnel book), sous-estimant les appels
- Pas de distinction entre réservations autonomes et réservations par SDR
- Pas d'attribution granulaire au niveau annonce
- Métriques dispersées dans plusieurs outils

## Décision

Mise en place d'une architecture de tracking complète comprenant :
1. **Événements dédiés** : création d'événements iClosed spécifiques par tunnel (quiz final, book final)
2. **Attribution granulaire** : tracking source → medium → campagne → annonce avec métriques de leads, appels et revenu par créatif
3. **Dashboard consolidé** : centralisation des métriques (dépenses pub, pages vues, taux conversion par page, taux présence) avec alertes codées par couleur (vert/orange/rouge) selon objectifs
4. **Séparation des flux** : distinction claire entre réservations autonomes et réservations SDR via bouton unique tracké dans le SDR Hub
5. **Paramètres UTM** : embeds à forte conversion tagués systématiquement en source/medium/campaign
6. **Liaison ventes-paiements** : via ID de deal HubSpot pour relier deals aux données finance

## Conséquences

**Positives :**
- Vision complète et fiable du funnel de la source jusqu'au revenu
- Calcul du ROI par annonce publicitaire
- Détection rapide des anomalies via alertes quotidiennes
- Réduction des erreurs de tracking des SDR
- Décisions data-driven sur les créatifs et tunnels les plus performants

**Négatives :**
- Charge d'implémentation technique importante
- Dépendance à la qualité des données collectées
- Nécessite discipline dans le taggage des campagnes

**À valider :**
- Priorisation des tunnels à instrumenter en premier
- Seuils des alertes vert/orange/rouge par tunnel
- Fréquence de review du dashboard (quotidien/hebdo)
- Ownership long terme de la maintenance du tracking
