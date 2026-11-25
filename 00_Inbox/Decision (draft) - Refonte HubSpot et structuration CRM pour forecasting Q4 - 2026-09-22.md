---
type: decision
statut: draft
date: 2026-09-22
source: jarvis
call: "[[2026-09-22 - CRO Meeting]]"
tags: [decision, draft]
---

# Refonte HubSpot et structuration CRM pour forecasting Q4

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Le CRM HubSpot est actuellement utilisé comme une simple liste, sans exploitation des fonctionnalités avancées de tracking par étape, de qualification des no-shows/annulations, ni de segmentation fine des leads perdus. Cette sous-utilisation crée :
- Des angles morts importants dans la donnée
- Des prévisions de CA peu fiables (impossibilité de prévoir à 8 jours)
- Une perte de valeur sur les leads historiques non suivis
- Un gaspillage de licence
- Une variabilité importante de la qualité du follow-up selon les commerciaux

Performance actuelle : 850 dossiers signés, 300 encaissés (36%), panier moyen 12 800€, pipeline hot à 49% (baisse vs août).

## Décision

Lancement de deux task forces Q4 pilotées par Boris :

**1. Task Force No-shows/No-calls** (démarrage semaine du 1er octobre)
- Réunions bimensuelles
- Membres : Boris, Alec, Raphaël, Head of Sales, Alex (SDR)
- Objectif : réduire no-shows à ≤25%
- Actions : segmentation granulaire (avant R1 / entre R1-R2), protocole live waiting obligatoire avec sanctions, scripts SDR "sell the call", automatisations rappels 24h et 1 semaine avant RDV, tests A/B séquentiels

**2. Task Force CRM & Forecasting**
- Refonte complète HubSpot avec consultant CRM réactivé
- Remapping processus par étape (N-Gage, R1, R2, R3) avec capture no-shows, annulations, canaux
- KPIs no-shows ajoutés aux dashboards
- Vues CRM dédiées follow-up avec protocoles de réactivation standardisés
- Automatisation réaffectation leads si relances non effectuées sous 72-96h
- Export et segmentation deals perdus 6 mois pour réactivation
- Calcul taux conversion engaged → closed-won et temps moyen par étape pour projections court terme

Ressources : représentants Sales et Ops, utilisateurs accompagnés (ex: Léa), retours terrain collectés (ex: Rachid).

## Conséquences attendues

**Positives :**
- Forecasting fiable à court terme (8 jours) pour pilotage trésorerie
- Réduction des no-shows et récupération de deals perdus = augmentation CA
- Standardisation du follow-up et réduction de la variabilité entre commerciaux
- Exploitation complète de la licence HubSpot
- Données propres pour analyses et optimisations futures
- Templates et playbooks réutilisables par toute l'équipe

**Risques :**
- Charge de travail importante sur Boris et équipes pendant Q4
- Résistance au changement (peur de "casser" HubSpot, contraintes de suivi)
- Nécessite coordination forte entre Sales, Ops, Marketing, Tech
- Délai de mise en place peut retarder bénéfices sur objectifs Q4

**À valider par Boris :**
- Priorisation détaillée des chantiers task force vs autres projets Q4
- Ressources humaines et budget nécessaires (consultant CRM, éventuels recrutements callers)
- Calendrier précis de livraison par workstream
- Métriques de succès et modalités de revue hebdomadaire/bimensuelle
