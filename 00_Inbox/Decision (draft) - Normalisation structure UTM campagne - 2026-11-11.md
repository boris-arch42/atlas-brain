---
type: decision
statut: draft
date: 2026-11-11
source: jarvis
call: "[[2026-11-11 - Sabrina X Boris - Ops Meeting]]"
tags: [decision, draft]
---

# Normalisation structure UTM campagne

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

HubSpot compte 427 valeurs UTM campagne différentes, avec des variantes d'écriture ('quiz funnel' vs 'quiz-funnel') qui empêchent un filtrage fiable. Deux propriétés UTM coexistent (ancienne et nouvelle avec icône flamme), et la multiplicité des funnels/canaux crée de nombreux événements d'acquisition.

## Décision proposée

- Mettre en place une structure à deux niveaux : catégorie principale (liste déroulante) + sous-catégorie (texte libre)
- Publier mensuellement dans Works la liste des UTM à copier-coller pour éviter les variations
- Boris fusionne les données existantes d'ici vendredi 14/11

## Conséquences

**Avantages :**
- Réduction drastique des erreurs de saisie et variantes
- Meilleure traçabilité et reporting fiable des sources d'acquisition
- Repérage facilité des champs vides ou mal renseignés

**Inconvénients :**
- Nécessite mise à jour de la liste à chaque création d'UTM
- Travail initial de fusion/nettoyage des 427 valeurs existantes
- Formation des équipes aux nouvelles conventions

## À valider par Boris

- Structure exacte des catégories principales à définir
- Process de validation avant création de nouvelles UTM
- Responsable de la maintenance de la liste mensuelle
