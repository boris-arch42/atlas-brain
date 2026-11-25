---
type: decision
statut: draft
date: 2026-11-10
source: jarvis
call: "[[2026-11-10 - Kick off Mediabuy - Webi Anisse]]"
tags: [decision, draft]
---

# Séparation pixel evergreen vs événement et événement dédié par campagne

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Lors du lancement de campagnes mediabuy pour des événements spécifiques (Webby, challenges), l'attribution des leads devient ambiguë lorsque plusieurs événements se déroulent simultanément. Le pixel evergreen peut contaminer les données événement et inversement, rendant difficile l'analyse des performances par source.

## Décision

- **Séparer physiquement le pixel evergreen et le pixel événement** : utiliser un sous-domaine dédié (ex: anisse.entrepreneurs.com) ou ajouter l'URL du projet aux exceptions evergreen pour empêcher le chargement croisé des pixels.
- **Créer un événement dédié par campagne** plutôt que de s'appuyer sur des événements génériques.
- **Utiliser des UTM uniques et un tag d'événement dédié** pour chaque campagne afin de garantir une attribution claire dans le CRM.

## Conséquences

**Positif :**
- Attribution claire des leads par source dans le CRM pour l'équipe commerciale
- Stabilisation des performances des pixels sans contamination croisée
- Dashboard WebGalix avec données fiables par période/événement
- Capacité à comparer les performances entre différents Webby

**Négatif :**
- Complexité technique accrue : gestion de plusieurs pixels et sous-domaines
- Nécessite une coordination étroite entre Cédric (landing/DNS) et Boris (tracking/dashboards)
- Risque d'erreur de configuration si les exceptions ou sous-domaines ne sont pas correctement paramétrés

## À valider par Boris

- Architecture DNS définitive (sous-domaine dédié vs exceptions evergreen)
- Workflow de création d'événement dédié : qui le crée, quand, nomenclature standardisée
- Responsabilités dans la maintenance des pixels et mapping d'attribution
