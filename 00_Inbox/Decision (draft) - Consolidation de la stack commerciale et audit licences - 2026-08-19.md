---
type: decision
statut: draft
date: 2026-08-19
source: jarvis
call: "[[2026-08-19 - CRO Meeting]]"
tags: [decision, draft]
---

# Consolidation de la stack commerciale et audit licences

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Le pôle commercial utilise trop d'outils superposés (HubSpot, Hotspot, OneFlow, Clap, Eager, Supercell, Superjoe, plateforme SDR interne) créant confusion, coûts récurrents inutiles et faible exploitation de la donnée. Les commerciaux remontent un manque de visibilité sur les métriques et des process non standardisés. Plusieurs licences actives sont potentiellement redondantes.

## Décision

- **Résiliation immédiate** : Eager (action Aziz)
- **HubSpot confirmé** comme CRM de référence unique pour sales
- **Audit complet** des licences (Supercell, Superjoe, Zoho, HubSpot, OneFlow, Clap) pour arbitrer conservation/arrêt/remplacement
- **Processus** : cahier des charges co-construit avec Boris, Aziz, Fabrice et team leads sélectionnés (Martin, Walid, Julien), suivi d'une réunion de décision Boris/Aziz pour arbitrage final coût/bénéfice
- **SuperJoe** : évaluation approfondie (comparaison avec Super Sales, documentation scoring leads/coaching par Anis) avant décision

## Conséquences

- Réduction attendue des coûts récurrents évitables (ex: Eager, possiblement Supercell 1000$/mois, Calendly 720$)
- Simplification de la stack avec risque transitoire de perte de capacité si arrêt trop rapide
- Nécessité de documenter besoins réels avant suppression pour éviter régression fonctionnelle
- Contrainte licence HubSpot (capacité max, engagement 24 mois pour ajout sièges) à intégrer dans arbitrage
- Zoho maintenu transitoirement pour septembre et onboarding pendant nettoyage

## À valider par Boris

- Faisabilité technique et planning de migration/remplacement pour chaque outil candidat à l'arrêt
- Capacité Ops à absorber corrections mapping et implémentation filtres UTM en parallèle de l'audit licences
- Confirmation que SuperJoe peut ou non remplacer d'autres outils selon retours team leads
