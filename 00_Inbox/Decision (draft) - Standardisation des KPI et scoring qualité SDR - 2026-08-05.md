---
type: decision
statut: draft
date: 2026-08-05
source: jarvis
call: "[[2026-08-05 - Vision SDR]]"
tags: [decision, draft]
---

# Standardisation des KPI et scoring qualité SDR

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Absence de KPI clairement définis et suivis de manière homogène pour le pôle SDR. Confusion terminologique ("calls" = tentatives vs conversations décrochées). Performance hétérogène : moyenne historique de 6 R1/jour/SDR au T2 tombée à 3,4 R1/jour mois récent, avec seulement 17 signatures pour 391 opportunités perdues.

## Décision

Définition d'un set standardisé de **4 KPI quantitatifs** + **1 KPI qualitatif** :

**Quantitatifs :**
1. **Appels tentés** : objectif 80-120 par SDR/jour (Aziz préfère 120)
2. **Conversations décrochées** : objectif ~15-20 par jour
3. **Durée moyenne d'appel** : à benchmarker et suivre
4. **R1 bookés** : objectif ~5 par SDR/jour

**Qualitatif :**
5. **Score de conformité au script** : analyse transcriptions vs script attendu, seuil ≥8,7/10, avec pénalités/remédiations si non-atteint

Le questionnaire cloud 4 piliers créé par Alex servira de base pour le scoring qualité.

Automatisation de la collecte via le SDR Hub une fois intégration Aircall finalisée.

## Conséquences

**Positives :**
- Pilotage objectif de la performance SDR avec métriques claires et mesurables
- Séparation nette entre volume d'activité (tentatives) et efficacité (conversations, R1)
- Introduction d'un critère qualité évite la dérive vers volume sans résultats
- Base commune pour coaching, incentives et recrutement
- Automatisation EOD réduit charge manuelle et améliore fiabilité données

**Négatives / À anticiper :**
- Nécessite intégration Aircall prioritaire (actuellement manquante)
- Questionnaire qualité à calibrer et maintenir à jour avec évolution scripts
- Risque de gaming des métriques si incentives mal alignés
- Charge de suivi qualité (écoute appels) à budgéter dans temps management

**Actions de suivi :**
- Finaliser intégration Aircall pour collecte automatique métriques
- Calibrer seuils et objectifs avec historique performance réelle
- Former managers à l'utilisation du questionnaire scoring qualité
- Définir processus de remédiation si score <8,7/10
- Aligner système d'incentives sur ces KPI

**Statut** : À valider par Boris
