---
type: decision
statut: draft
date: 2026-08-25
source: jarvis
call: "[[2026-08-25 - Cédric & Boris]]"
tags: [decision, draft]
---

# Remplacement de Looker par dashboard interne granulaire

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte
Looker offre une visibilité limitée et peu de flexibilité. L'équipe veut une vue de bout en bout du tunnel (ads → leads → réservations → closes → appels → revenus) avec granularité UTM et segmentation (nouveaux vs récurrents, VIP, média/campagne).

## Décision
- **Remplacement** : construire un dashboard interne 2.0 (main-to-scale) qui remplace Looker d'ici **30 septembre 2026**.
- **Périmètre** : tunnel complet, métriques de qualité lead (opt-ins / questionnaires complétés / réservations), attribution revenue par campagne/création, intégration iClosed.
- **Responsabilités** : Boris pilote l'implémentation avec Raph/devs ; Cédric fournit le cahier des besoins data détaillé.
- **Itération** : revues hebdomadaires du dashboard, ajout de métriques supplémentaires entre les lancements si nécessaire.

## Conséquences
- **Gains** : meilleure attribution ads → revenus, reproduction des campagnes gagnantes, optimisation au-delà du CPL.
- **Risques** : délai serré (5 semaines), dépendance aux intégrations (iClosed, HubSpot, Customer.io), courbe d'apprentissage équipe sur le nouvel outil.
- **Pré-requis** : schéma UTM standard, identifiant réservation HubSpot, conventions de nommage appliquées par toutes les équipes.

## À valider par Boris
- [ ] Priorisation des métriques (MVP vs nice-to-have) pour tenir le 30 septembre ?
- [ ] Qui forme les équipes sales/marketing à l'utilisation du nouveau dashboard ?
- [ ] Plan de rollback si Looker doit rester actif en parallèle ?
