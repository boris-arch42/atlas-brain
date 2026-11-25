---
type: decision
statut: draft
date: 2026-11-04
source: jarvis
call: "[[2026-11-04 - Sprint 75 jours - Fabrice x Boris x Anisse x Alec - Point sur les chiffres et pr]]"
tags: [decision, draft]
---

# Centralisation des processus de fidélisation dans HubSpot

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Les processus de retention et d'upsell sont actuellement éclatés sur 5 plateformes (Hotspot, Google Sheet, Works, Common Center, Cloud/artifacts), générant des pertes de données importantes, une friction opérationnelle majeure et empêchant l'automatisation des workflows de relance client.

Alexandre travaille principalement dans Google Sheets sans pousser vers des optimisations système. L'audit des logs d'usage BI doit vérifier l'utilisation réelle des outils construits.

## Décision

**Centraliser l'ensemble des processus et du reporting de fidélisation/upsell dans Hotspot (HubSpot)** afin de :
- Automatiser les workflows de relance clients en fin de programme
- Éliminer les artefacts manuels Google Sheet/Cloud
- Rendre le tunnel de fidélisation actionnable via triggers, scoring et gamification

**Actions immédiates** :
1. Quentin audite les logs d'usage BI retention (deadline : 8 nov)
2. Atelier 2-3h avec Caro, Alex et équipe retention pour inventorier capacités Works/Hotspot, définir specs manquantes et préparer intégration (deadline : 11 nov)
3. Production specs Hotspot (triggers, workflows, reporting) par Alec et Quentin
4. Accompagnement d'Alexandre pour déplacer processus manuels vers Hotspot et développer posture proactive d'optimisation

## Conséquences

**Positives** :
- Réduction drastique de la friction opérationnelle
- Visibilité temps réel sur pipeline retention
- Automatisation relances = augmentation conversion upsell
- Meilleure scalabilité équipe retention

**Négatives / Risques** :
- Charge migration technique court terme sur Quentin et équipe produit
- Courbe d'apprentissage pour Alexandre et équipe
- Risque de rupture temporaire si migration mal exécutée

**À valider par Boris** : Arbitrage priorisation produit/tech pour specs Hotspot vs autres chantiers, timeline réaliste migration, budget éventuel support externe HubSpot.
