---
type: project-hub
status: active
phase: cadrage-technique
owner: "[[Boris Arduy]]"
created: 2026-05-07
deadline: 2026-05-12
tags: [lancement, kelly, sales, closers-externes, funnel, hubspot, zoho, automation, project]
sensitivity: internal
---

# Lancement Kelly — Project Hub

> Hub d'accueil du projet. Point d'entrée unique pour la navigation, le statut et les actions en cours.

## Statut au 7 mai 2026

**Phase actuelle** : cadrage technique
**Prochaine milestone** : go-live funnel parallèle closers externes
**Deadline cible** : J+5 (~12 mai 2026)

## Contexte

Le lancement Kelly est un événement type webinar / 5-day challenge où le volume de leads attendu impose la mise en place d'un funnel parallèle dédié aux closers externes. La structure :

- **Funnel interne (existant)** : Tally → Calendly → HubSpot → Claap → OneFlow — pour les leads qualifiés (CA ≥ 50K€ + activité)
- **Funnel externe (à construire)** : Tally → iCloseit → Zoho → Supersales → DocuSign → push HubSpot — pour les leads sub-50K€ ou sans activité

Volume cible côté externe : **3 sales teams partenaires, ~30 closers, 3 managers**. HubSpot reste la source de vérité business — Zoho est un CRM opérationnel temporaire.

## Documents du projet

- [[Architecture - Funnel parallèle closers externes]] — architecture technique complète + plan de déploiement 5 jours
- (à venir) Brief closers externes
- (à venir) Charte de saisie Zoho
- (à venir) Scénarios Make détaillés
- (à venir) DPA modèle pour les sales teams partenaires
- (à venir) Mapping de champs HubSpot ↔ Zoho détaillé (avec les ops)

## Décisions actées

- HubSpot reste source de vérité, push automatisé Zoho → HubSpot après deal gagné
- Sheet Google de tracking pour validation par assistante
- Plans payants iCloseit / Zoho / Supersales (pas de cap volume)

## Points à trancher cette semaine

- Make ou Zapier ? (recommandation : Make)
- Qui code les automations (interne / freelance / partenaire ?)
- Identifier l'assistante owner du Sheet de validation HubSpot
- Date exacte de go-live alignée avec marketing
- Format brief closers externes : visio unique ou par team ?
- Communication interne : qui dans l'équipe doit être au courant ?

## Risques principaux

- **Comportement des 30 closers externes** (saisie incomplète, oubli de passer le deal en gagné) → mitigations dans automations A6/A7 du doc d'architecture
- **RGPD / DPA** à signer avec chaque sales team avant ouverture des accès Zoho
- **Délai 5 jours tendu** sans intégrateur Make dédié 2-3 jours pleins
- **Assistante validation** = goulot opérationnel critique si non identifiée à J+4

## Stakeholders

| Rôle | Personne | Statut |
|---|---|---|
| Driver opérationnel | [[Boris Arduy]] | — |
| Validation business | [[Alec Henry]] | À informer |
| Lien marketing (challenge / VSL) | À identifier | — |
| 3 managers teams externes | À identifier | Recrutement lancé |
| Assistante validation HubSpot | À identifier | Critique J+4 |
| Intégrateur Make | À identifier | Critique J+2 |

## Prochaines actions clés

### Aujourd'hui — demain

- [ ] Confirmer qui code les automations Make
- [ ] Identifier l'assistante owner du Sheet
- [ ] Valider la date de go-live avec marketing
- [ ] Récupérer accès iCloseit / Zoho / Supersales / DocuSign

### J+1 (mercredi 8 mai)

- [ ] Setup HubSpot : custom properties + stage "External Won — À valider"
- [ ] Cadrage avec les 3 managers teams externes
- [ ] Création du Google Sheet de tracking
- [ ] Vérifier les comptes / licences

### J+2 à J+5

Voir le plan de déploiement détaillé dans [[Architecture - Funnel parallèle closers externes]] section 8.

## Liens connexes

- [[People-RH - Process recrutement Aikho v1]] — note : les closers externes ne passent **pas** par ce process, ils sont recrutés via leurs sales teams partenaires
- [[Alec Henry - Garant de la vision]] — le pilier 2 (prédictibilité revenue par triptyque + récurrence) est directement servi par ce projet

## Historique

- 2026-05-07 — Création du hub projet, livraison de l'architecture v1
