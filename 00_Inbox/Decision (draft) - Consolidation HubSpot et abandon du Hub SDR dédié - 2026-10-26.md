---
type: decision
statut: draft
date: 2026-10-26
source: jarvis
call: "[[2026-10-26 - 🧠 Core Meeting]]"
tags: [decision, draft]
---

# Consolidation HubSpot et abandon du Hub SDR dédié

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

L'équipe utilisait plusieurs systèmes parallèles (Hub SDR dédié, HubSpot, plateforme interne) créant des incohérences de données, des problèmes de réconciliation et une impossibilité de suivre le parcours client de bout en bout.

## Décision

- Abandon complet du Hub dédié SDR
- Consolidation de tous les flux dans HubSpot pour créer un parcours client unique du prospect à la livraison
- Création de 4 pipelines HubSpot distincts :
  1. Pipeline traitement leads SDR
  2. Pipeline transactions commerciales
  3. Pipeline cycle de vie client
  4. Pipeline recouvrements (accessible équipe Jordan en temps réel)

## Conséquences

**Positives :**
- Source de vérité unique pour toutes les équipes
- Visibilité temps réel sur le parcours client complet
- Réduction des erreurs de réconciliation et des doublons
- Meilleure traçabilité des actions et responsabilités
- Dashboards 24/7 accessibles à tous

**Négatives / Risques :**
- Migration technique à orchestrer rapidement (échéance mercredi-jeudi)
- Formation des équipes aux nouveaux pipelines
- Coût des licences HubSpot (en cours de négociation pour réduction)
- Dépendance accrue à un seul outil

**À valider par Boris :**
- Budget final après négociation licences
- Validation de l'architecture des 4 pipelines
- Accès et permissions par équipe
