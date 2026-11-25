---
type: decision
statut: draft
date: 2026-09-02
source: jarvis
call: "[[2026-09-02 - Jordan X Boris - Ops Meeting]]"
tags: [decision, draft]
---

# DealUpSpot ID comme identifiant unique du cycle de vie client

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Actuellement, le suivi des transactions de bout en bout (booking → vente → paiement → commission) manque de cohérence entre les systèmes. Les équipes commerciales n'ont pas de visibilité fiable sur leurs commissions et les réconciliations finance sont complexes.

## Décision

Le **DealUpSpot ID** devient l'identifiant persistant de référence pour tout le cycle de vie client, créé dès la réservation d'appel et conservé jusqu'aux paiements. Toute question liée aux commissions ou à la facturation doit systématiquement mentionner cet ID.

L'architecture des dashboards sera construite autour de cet identifiant (et non du contact ID), permettant de relier ventes, CSM et finance dans une source de vérité unique.

## Conséquences

**Positif :**
- Traçabilité complète de chaque deal à travers tous les outils
- Simplification des réconciliations et du calcul des commissions
- Dashboard temps réel pour les ventes basé sur les encaissements réels
- Réduction des frictions et erreurs de paie

**Négatif :**
- Nécessite une discipline stricte de renseignement de l'ID à chaque étape
- Migration progressive des systèmes existants vers ce modèle
- Dépendance technique accrue sur la fiabilité de cet identifiant

## À valider par Boris

- Gouvernance de l'attribution et du cycle de vie du DealUpSpot ID
- Formation des équipes à l'usage systématique de cet identifiant
- Calendrier de migration des dashboards et processus existants
