---
type: decision
statut: draft
date: 2026-08-07
source: jarvis
call: "[[2026-08-07 - Hubspot - Bet On You]]"
tags: [decision, draft]
---

# Architecture CRM double pipeline + scoring IA pour BetoNew

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

BetoNew/BeExplorer accompagne les athlètes de haut niveau en reconversion via un matching avec des entreprises. Le projet nécessite de gérer deux flux distincts (athlètes B2C / entreprises B2B) avec des données d'évaluation complexes (60-100 questions, soft skills, trajectoires) et un moteur de matching.

## Décision

- **CRM recommandé** : Pipedrive plutôt que HubSpot en phase initiale (simplicité, coût, adoption)
- **Architecture** : 2 pipelines séparés (athlètes / entreprises) + base deals pour tracer les matchs
- **Stratégie de lancement** : Excel structuré → import CRM pour valider schéma avant automatisation
- **Automatisations clés** :
  - Enregistrement systématique appels + analyse IA (Claude) pour scoring intention
  - Génération/signature/archivage contrats automatisés sur champs obligatoires
  - Lead scoring basé avatar idéal + timing reconversion
  - Workflows email avec réchauffement progressif (10 emails/j départ)
- **Matching** : clés communes entre bases athlètes/entreprises (métiers, compétences) pour rapprochement automatique

## Conséquences

**Positives** :
- Démarrage rapide sans sur-ingénierie ni coûts lourds
- Traçabilité complète des interactions et amélioration continue via enregistrements
- Scalabilité : migration vers HubSpot ou custom possible plus tard (4-5k€)
- Base de connaissance constituée pour formation commerciale

**Négatives / Vigilance** :
- Nécessite discipline sur définition schéma Excel et champs CRM MVP
- Onboarding commercial obligatoire (Loom + doc + 1h pratique) pour adoption
- Conformité RGPD critique (consentement enregistrement, sécurité données athlètes)
- Migration future à budgéter si croissance forte

**À valider par Boris** :
- Périmètre exact du support équipe OPS Entrepreneurs pour déploiement automatisations
- Choix final Pipedrive vs solution custom légère si besoins très spécifiques matching
- Budget et timeline migration CRM si scaling rapide prévu < 12 mois
