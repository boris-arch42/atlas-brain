---
type: decision
statut: draft
date: 2026-09-01
source: jarvis
call: "[[2026-09-01 - Raphaël X Boris - Marketing Ops]]"
tags: [decision, draft]
---

# Événement de conversion dédié par funnel

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Les écarts de conversion entre les outils (12 vs 32 vs 39 sur 7 jours) proviennent en partie de la réutilisation de noms d'événements génériques (ex. 'scheduler') qui contaminent les comptes entre différents funnels (BookFunnels, Quiz Funnel, etc.). Les sources de données multiples (produit WOP, intégrations diverses) aggravent la pollution.

## Décision

Créer un événement de conversion unique et dédié pour chaque funnel majeur, à commencer par 'Quiz Final'. Chaque événement sera :
- Nommé de manière distinctive (ex. 'Meeting with an expert' avec emoji)
- Équipé d'un UTM dédié (score-up) réutilisable
- Branché proprement dans iClosed
- Isolé des autres sources de tracking

## Conséquences

**Positif :**
- Attribution propre par funnel et par canal (Meta, Google à venir)
- Fin de la contamination croisée des événements
- Décisions marketing basées sur des données fiables
- Réutilisabilité de l'UTM sur plusieurs funnels avec cohérence

**Négatif :**
- Effort d'implémentation immédiat (création événement + intégration)
- Rupture historique dans les séries de données
- Nécessite discipline pour maintenir la nomenclature

**À valider par Boris :**
- Nomenclature finale des événements et emojis
- Architecture globale d'événements pour tous les funnels
- Process de validation avant création de nouveaux événements
