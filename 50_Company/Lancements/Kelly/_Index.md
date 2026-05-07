---
type: project-hub
status: active
phase: cadrage-technique-et-partenariats
owner: "[[Boris Arduy]]"
created: 2026-05-07
deadline-go-live: 2026-05-17
event-dates: "17 mai - fin mai (5 jours d'event + queue R2/R3)"
tags: [lancement, kelly, sales, closers-externes, funnel, hubspot, zoho, automation, project]
sensitivity: confidential
---

# Lancement Kelly — Project Hub

> Hub d'accueil du projet. Point d'entrée unique pour la navigation, le statut et les actions en cours.

## Statut au 7 mai 2026

**Phase actuelle** : cadrage technique + partenariats sales
**Prochaine milestone** : coaching commun 3 agences (week-end 10-11 mai)
**Go-live event** : 17 mai 2026 (Marrakech)

## Contexte business

Le Lancement Kelly est un événement type challenge avec un volume d'inscrits exceptionnel : **50 000 à 60 000 inscrits** projetés (vs 20 000 sur les lancements habituels), grâce à un CPL exceptionnellement bas (~5€ vs 17€ habituels — certaines campagnes à 12 centimes).

Conséquence : les leads sont d'une **typologie différente** (B2C orienté business, sub-50K€, sans activité ou en lancement) que l'équipe sales interne ne traite pas habituellement (équipe interne sur cycle B2B / R1-to-close avec posture business coach).

Décision business : **externaliser le traitement de ces ~20 000 prospects** vers 3 sales teams partenaires, avec une offre dédiée à 5 700€ (cible 5K-7K, 6 mois).

## Architecture du dispositif

- **Funnel interne (existant)** : Tally → Calendly → HubSpot → Claap → OneFlow — pour les leads qualifiés (CA ≥ 50K€ + activité)
- **Funnel externe (à construire)** : Tally → iCloseit → Zoho → Supersales → DocuSign → push HubSpot — pour les leads sub-50K€ ou sans activité, traités par les 3 agences partenaires
- **HubSpot reste source de vérité business** — Zoho est CRM opérationnel temporaire pour les sales externes uniquement

## Volume cible

- **2500-2800 calls** sur l'avatar externe
- Réparti à **800-1000 calls par agence**
- Sur la durée du challenge (5 jours d'event intenses + queue R2/R3)

## Documents du projet

### Cadrage technique
- [[Architecture - Funnel parallèle closers externes]] — architecture technique complète + plan de déploiement

### Partenariats
- [[Partenaires - Vue d'ensemble 3 agences]] — vue agrégée des 3 sales teams
- [[Partenaires - Tip Talent (Romain Nussmann)]] — fiche partenaire #1 (✅ confirmé)
- (à créer) Fiche Agence Lucas
- (à créer) Fiche Axel Greiber

### Sources
- [[2026-05-07 - Call Alec Aziz Romain Nussmann (Tip Talent)]] — transcript intégral du call de cadrage Tip Talent

### À produire
- Brief closers externes (support écrit + structure visio coaching)
- Charte de saisie Zoho
- Kit branding Entrepreneurs.com pour les 3 agences (témoignages, contexte Kelly)
- One-pager process (qui fait quoi à quel moment)
- Cahier des charges Make pour intégrateur
- DPA modèle pour les 3 sales teams

## Décisions actées

- **Aikho/process recrutement** ne s'applique **pas** aux sales externes (recrutés via leurs sales teams partenaires, pas via Entrepreneurs.com)
- **HubSpot source de vérité** + push automatisé Zoho → HubSpot après deal gagné + DocuSign signé
- **Sheet Google de tracking** pour validation par assistante
- **Plans payants** iCloseit / Zoho / Supersales (pas de cap volume)
- **Commission 10%** sur l'offre Kelly pour les 3 agences (vs 7,5% standard sur gros tickets)
- **Boris = pont opérationnel et tech** entre Aziz/Cédric et les 3 agences (mandat explicite Alec)
- **Contrat de partenariat rédigé côté Entrepreneurs.com** (vs habituellement côté agences)
- **Coaching commun** ce week-end aux 3 agences (à confirmer Lucas et Axel)
- **Tip Talent : GO confirmé** (10 sales possibles 12, capacité ~1500 calls/mois théoriques)

## Points à trancher cette semaine

- Make ou Zapier ? (recommandation : Make)
- Qui code les automations (interne / freelance / partenaire ?)
- Identifier l'assistante owner du Sheet de validation HubSpot
- Date exacte de go-live alignée avec marketing (17 mai event, mais setup tech à activer avant)
- Format coaching : mélangé 3 agences vs individuel (dépend OK Lucas + Axel)
- Communication interne : qui dans l'équipe Entrepreneurs.com doit savoir qu'il y a un funnel parallèle ?
- Politique moyens de paiement à aligner avec Tip Talent (tension Romain ↔ Aziz à arbitrer)

## Risques principaux

- **Comportement des sales externes** (saisie incomplète, oubli de passer le deal en gagné) → mitigations dans automations A6/A7 du doc d'architecture
- **RGPD / DPA** à signer avec chaque sales team avant ouverture des accès Zoho
- **Délai 10 jours tendu** sans intégrateur Make dédié 2-3 jours pleins
- **Assistante validation** = goulot opérationnel critique si non identifiée à J+4
- **Image Kelly** : c'est sa première fois, elle sera très vigilante sur la qualité des sales (point Alec). Validation finale photos + replays sales avant l'event.
- **Disparité qualité entre les 3 agences** (cf. fiche vue d'ensemble)

## Stakeholders

| Rôle | Personne | Statut |
|---|---|---|
| CEO / sponsor | [[Alec Henry]] | ✅ Engagé, intervention possible coaching 13/14 mai |
| Head of Sales | [[Aziz Sfaihi]] | ✅ Owner business du dispositif partenaires |
| CMO | [[Cédric De Saint Jean]] | Lien marketing (challenge, VSL, Kelly) |
| Driver opérationnel et tech | [[Boris Arduy]] | ✅ Mandaté par Alec |
| Tip Talent — fondateur | Romain Nussmann | ✅ Confirmé, à Bangkok |
| Tip Talent — opérationnel | Julien (CRO) | ✅ Interlocuteur réel sur le quotidien |
| Agence Lucas | Lucas (+ Kevin) | 🟡 À confirmer cette semaine |
| Axel Greiber | Axel Greiber | 🟡 À confirmer cette semaine |
| Marketing Kelly | Anne (en lien avec VSL recrutement) | À confirmer comme contact |
| Intégrateur Make | À identifier | 🔴 Critique J+2 |
| Assistante validation HubSpot | À identifier | 🔴 Critique J+4 |

## Prochaines actions clés

### Aujourd'hui — demain (7-8 mai)

- [ ] Aziz envoie l'offre Kelly finalisée aux partenaires (deadline 8 mai)
- [ ] Aziz cale un call avec Lucas pour confirmer participation
- [ ] Aziz cale un call avec Axel pour confirmer participation
- [ ] Romain crée le groupe WhatsApp Tip Talent (Romain + Julien + Aziz + Boris)
- [ ] Boris confirme qui code les automations Make
- [ ] Boris identifie l'assistante owner du Sheet
- [ ] Aziz envoie kit ressources (témoignages, contexte Kelly)

### J+1 (jeudi 8 mai)

- [ ] Setup HubSpot : custom properties + stage "External Won — À valider"
- [ ] Vérification accès iCloseit / Zoho / Supersales / DocuSign (plans payants)
- [ ] Création du Google Sheet de tracking
- [ ] Récupération photos sales + replays Tip Talent pour validation Alec/Aziz
- [ ] Boris envoie one-pager process aux 3 agences (draft)

### Week-end (10-11 mai)

- [ ] **Coaching commun 3 agences** (format à confirmer selon Lucas + Axel)
- [ ] Présentation Entrepreneurs.com par Aziz
- [ ] Présentation contexte Kelly et sensibilité audience
- [ ] Brief sales sur l'offre, la posture, les moyens de paiement
- [ ] Discussion explicite Aziz/Julien sur la politique moyens de paiement (avant ou pendant le coaching)

### Avant le 15 mai (départ Marrakech)

- [ ] Intervention possible Alec dans un coaching (13 ou 14)
- [ ] Validation finale Alec/Aziz de la posture des sales
- [ ] Setup tech complet (toutes les automations Make construites et testées)
- [ ] Tests à blanc du funnel
- [ ] Signature contrats de partenariat (3 agences)

### Event (17 mai +)

- [ ] Monitoring rapproché les 24-48 premières heures
- [ ] Daily Boris ↔ Julien (et référents Lucas + Axel)
- [ ] Reporting H+24, H+48 partagé Aziz et Alec

## Liens connexes

- [[People-RH - Process recrutement Aikho v1]] — note : les sales externes ne passent **pas** par ce process, ils sont recrutés via leurs sales teams partenaires
- [[Alec Henry - Garant de la vision]] — le pilier 2 (prédictibilité revenue par triptyque + récurrence) est directement servi par ce projet

## Historique

- 2026-05-07 — Création du hub projet, livraison de l'architecture v1
- 2026-05-07 — Call de cadrage Alec/Aziz/Romain (Tip Talent), GO partenariat Tip Talent confirmé
- 2026-05-07 — Création des fiches partenaires (Tip Talent + vue d'ensemble 3 agences) et archivage du transcript source
