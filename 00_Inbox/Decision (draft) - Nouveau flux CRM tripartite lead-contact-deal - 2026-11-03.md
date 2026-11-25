---
type: decision
statut: draft
date: 2026-11-03
source: jarvis
call: "[[2026-11-03 - Sabrina X Boris - Ops Meeting]]"
tags: [decision, draft]
---

# Nouveau flux CRM tripartite lead/contact/deal

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

L'ancien flux CRM générait des frictions dans le tracking des opt-ins, la traçabilité des interactions multiples et la propreté des données SDA pour les SDR. Les funnels Evergreen et de lancement nécessitaient une meilleure séparation entre la capture initiale et les opportunités commerciales.

## Décision

Implémentation d'un objet intermédiaire « lead » entre contact et deal :
- **Contact** : unique par personne (consolidation)
- **Lead** : une carte par interaction avec un funnel (opt-ins, réponses quiz)
- **Deal** : une transaction par appel réservé
- Génération automatique des liens iClosed trackés (source, support, UTM) au moment de l'attribution du lead par le SDR
- Tous les funnels Evergreen et de lancement branchés ; site web en cours de finalisation

## Conséquences

**Positives :**
- Meilleure traçabilité des parcours multi-touch
- Données SDA propres pour les SDR
- Suppression du tagging manuel
- Tracking précis si propriété correctement définie

**Négatives / À suivre :**
- Nécessite discipline des SDR sur l'attribution de propriété
- Formation requise sur le nouveau flux
- Migration/nettoyage des données historiques à clarifier

## Statut
✅ Déployé sur Evergreen et lancements | 🚧 Site web à finaliser

**À valider par Boris** : plan de formation équipe et migration données historiques
