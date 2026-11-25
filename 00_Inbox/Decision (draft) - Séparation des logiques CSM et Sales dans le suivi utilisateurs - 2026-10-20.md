---
type: decision
statut: draft
date: 2026-10-20
source: jarvis
call: "[[2026-10-20 - Julien & Boris]]"
tags: [decision, draft]
---

# Séparation des logiques CSM et Sales dans le suivi utilisateurs

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Le produit SaaS de recrutement nécessite un suivi différencié des utilisateurs selon leur stade d'activation et leurs besoins. Confusion potentielle entre aide technique et pression commerciale.

## Décision

Deux typologies d'appels distinctes :
- **Appels CSM** : non-commerciaux, déclenchés sur inactivité ou écart aux jalons d'onboarding. Objectif = déblocage, feedback, aide. Arnaud en charge avec dashboard des inactifs J+3.
- **Appels Sales** : déclenchés à 14 jours d'essai ou 25 candidats atteints. Objectif = upgrade, discussion offre supérieure, feedback produit.

Un dashboard CSM montrera les trois typologies d'utilisateurs et leurs écarts (création compte, publication job, réception candidats) avec jalons attendus (24-48h pour config, 2-3 jours pour premiers candidats).

## Conséquences

**Positif** : Meilleure expérience utilisateur, feedback plus authentique, clarté pour Farno et l'équipe.

**Négatif** : Complexité opérationnelle accrue, nécessite dashboard et process clairs.

**À valider par Boris** : Scripts/prompts pour chaque type d'appel, seuils exacts des jalons, règles d'escalade.
