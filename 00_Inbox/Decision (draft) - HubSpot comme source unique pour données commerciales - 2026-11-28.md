---
type: decision
statut: draft
date: 2026-11-28
source: jarvis
call: "[[2026-11-28 - Mathieu & Boris]]"
tags: [decision, draft]
---

# HubSpot comme source unique pour données commerciales

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

# HubSpot comme source unique pour données commerciales

## Contexte
Intégration entre la plateforme de formation/analyse de Mathieu et les outils internes. HubSpot déclenche plusieurs opérations critiques : envoi contrats, ouverture accès clients, facturation. Risque de perte de données, erreurs de traduction et complexité avec synchronisation bidirectionnelle.

## Décision
HubSpot est défini comme la source de référence pour toutes les données commerciales. Flux unidirectionnel HubSpot → plateforme Mathieu uniquement. Les closers continuent de renseigner les outcomes et informations contrat directement dans HubSpot.

## Conséquences
- Évite les conflits de données et problèmes de traçabilité
- Simplifie l'architecture d'intégration
- Maintient HubSpot comme point central des processus commerciaux
- Nécessite une API pour transmettre les appels gagnés vers plateforme Mathieu
- Transcriptions Ngram transmises séparément pour analyses automatisées

## Statut
À valider par Boris
