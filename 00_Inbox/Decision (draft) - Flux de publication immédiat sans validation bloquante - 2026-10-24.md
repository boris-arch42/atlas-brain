---
type: decision
statut: draft
date: 2026-10-24
source: jarvis
call: "[[2026-10-24 - Update Aikho]]"
tags: [decision, draft]
---

# Flux de publication immédiat sans validation bloquante

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Le terme « publish » dans Aikho doit déclencher la génération de tous les artefacts RH (scorecard, description de poste, plan d'entretien, image) et lancer la diffusion multi-canaux (LinkedIn, Google Jobs, ATS, outreach agentique). L'équipe a débattu d'ajouter une étape de validation manuelle pour permettre aux RH de revoir les artefacts avant diffusion externe.

## Décision

Le bouton « publish » génère immédiatement tous les artefacts et déclenche la diffusion sans validation bloquante par défaut. Les RH auront une visibilité en lecture seule sur scorecard et plan d'entretien, avec option self-test optionnelle pour passer l'entretien eux-mêmes. Pas d'étape de pause ou de confirmation supplémentaire dans le flux standard.

Pour les grands comptes enterprise demandant plus de contrôle, des configurations spéciales ou étapes de validation seront étudiées au cas par cas, sans modifier le flux par défaut.

## Conséquences

- UX fluide et sans friction pour le parcours standard brief → publish → diffusion
- Réduction du risque de perte d'utilisateurs par ajout de validations intermédiaires
- Les artefacts (scorecard, plan d'entretien) sont fortement couplés ; les modifier après génération casse la cohérence
- Positionnement produit sur la confiance dans l'intelligence IA plutôt que micro-revue manuelle
- Besoin d'améliorer agents et drivers configurables si clients demandent artefacts différents
- Test A/B possible mais nécessite support de deux versions produit (effort engineering significatif)

## À valider par Boris

- Confirmer que le flux par défaut reste sans validation bloquante
- Arbitrer seuil de déclenchement pour configurations spéciales grands comptes
- Décider si un test A/B validation pré-publication doit être priorisé court terme
