---
type: decision
statut: draft
date: 2026-08-24
source: jarvis
call: "[[2026-08-24 - Adil & Boris]]"
tags: [decision, draft]
---

# Synchronisation complète Tally → Customer.io via propriétés personnalisées

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Actuellement, les réponses aux formulaires Tally (CA, ARR, secteur, etc.) ne remontent pas automatiquement dans Customer.io comme propriétés. L'équipe doit exporter/importer manuellement les données pour segmenter (ex: envoyer un email uniquement aux leads 1M€ ARR). Ce processus manuel empêche la réactivité et la granularité des campagnes.

## Décision

Les champs Tally seront poussés automatiquement vers Customer.io sous forme de propriétés personnalisées. Adil fournira un brief précis (noms de champs, valeurs attendues) ; Boris implémentera les champs et mettra à jour l'automatisation existante (flux 'Mario' Tally → système) pour activer la synchronisation.

## Conséquences

**Positif :**
- Segmentation et ciblage en temps réel sans export manuel
- Campagnes plus fines (par tranche de CA, secteur, etc.)
- Gain de temps opérationnel pour Adil et l'équipe growth

**À surveiller :**
- Cohérence du nommage des champs entre Tally, HubSpot et Customer.io
- Performance de l'automatisation Mario sous charge accrue
- Qualité des données (valeurs manquantes, formats incohérents)

**Timeline :** Brief Adil d'ici 25/08 matin, implémentation Boris 26-28/08.

## Validation Boris

- [ ] À valider
