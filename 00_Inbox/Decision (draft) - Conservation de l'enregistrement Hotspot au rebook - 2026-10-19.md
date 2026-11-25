---
type: decision
statut: draft
date: 2026-10-19
source: jarvis
call: "[[2026-10-19 - Léa & Boris]]"
tags: [decision, draft]
---

# Conservation de l'enregistrement Hotspot au rebook

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Actuellement, chaque replanification ou rebook d'un prospect dans iClose génère un nouveau deal dans Hotspot, créant environ 1 doublon pour 1 client sur 5. Cela fragmente le tracking, complique le suivi de l'historique client et impose un nettoyage manuel quotidien.

## Décision

Plutôt que de créer un nouveau deal Hotspot à chaque rebook, le système conservera l'enregistrement existant et mettra à jour ses champs (date, heure, propriétaire si nécessaire). Boris implémentera l'automatisation nécessaire et vérifiera avec Axos la possibilité de privilégier le même closer ou de changer automatiquement le propriétaire sans dupliquer la fiche.

## Conséquences

- **Positif** : Réduction drastique des doublons, préservation de l'historique complet des interactions, moins de nettoyage manuel.
- **Positif** : Meilleure fiabilité du reporting et du suivi client.
- **Risque** : Si l'automatisation échoue ou crée des bugs, retour arrière nécessaire ; Léa remontera les incidents pour ajustement.
- **Transition** : En attendant l'automatisation, Léa continue le nettoyage manuel quotidien.

## À valider par Boris

Faisabilité technique de la mise à jour automatique du propriétaire et confirmation du paramétrage iClose/Hotspot.
