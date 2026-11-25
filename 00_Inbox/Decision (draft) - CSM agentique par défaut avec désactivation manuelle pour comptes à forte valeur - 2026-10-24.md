---
type: decision
statut: draft
date: 2026-10-24
source: jarvis
call: "[[2026-10-24 - Update Aikho]]"
tags: [decision, draft]
---

# CSM agentique par défaut avec désactivation manuelle pour comptes à forte valeur

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Pour passer à l'échelle sur l'onboarding et le suivi client, l'équipe doit choisir entre un CSM manuel sur tous les comptes (non scalable) et un CSM agentique automatisé. Les 75 premiers comptes pilotes nécessitent davantage de feedback qualitatif, tandis que les comptes enterprise à forte valeur attendent un service personnalisé.

## Décision

Un CSM agentique sera activé par défaut pour tous les nouveaux inscrits. Il détecte automatiquement les blocages (ex: aucune activité depuis 7 jours, absence de premier entretien complété) et envoie des emails adaptés pour guider l'utilisateur. Il apprendra également à répondre aux emails entrants et à escalader vers humain si pertinent.

Pour les comptes enterprise à très forte valeur, le CSM agentique sera désactivé manuellement et ces comptes recevront un onboarding et des check-ins humains, avec tableau de bord affichant signaux d'escalade.

Pour les 75 comptes pilotes initiaux, l'équipe mènera davantage d'appels manuels et de collecte de feedback avant de basculer vers l'automatisation complète.

## Conséquences

- Scalabilité de l'onboarding et du suivi pour croissance rapide
- Économie de temps humain sur comptes standards, concentration sur comptes à forte valeur
- Risque de sur-automatisation si CSM agentique ne détecte pas correctement les signaux ou envoie messages inadaptés
- Besoin de scripts standardisés et branche conditionnelle robuste pour le CSM agentique
- Nécessité de définir critères clairs de désactivation (seuil valeur compte, volume recrutements, etc.)
- Pipeline de feedback automatisé (entretiens conversationnels 10min via ICO AI) complète le dispositif pour collecter retours structurés

## À valider par Boris

- Confirmer seuils de valeur pour désactivation CSM agentique (ex: deals >X k€, >Y postes/an)
- Valider allocation ressources humaines sur les 75 pilotes vs automatisation
- Arbitrer priorité développement pipeline feedback automatisé vs autres fonctionnalités
