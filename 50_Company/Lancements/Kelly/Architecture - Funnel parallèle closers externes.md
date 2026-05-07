---
type: technical-spec
project: "[[_Index|Lancement Kelly]]"
owner: "[[Boris Arduy]]"
created: 2026-05-07
status: draft-v1
deadline: 2026-05-12
tags: [lancement, kelly, funnel, automation, hubspot, zoho, make, technical-spec, closers-externes]
sensitivity: internal
---

# Funnel parallèle Closers Externes — Architecture et plan de déploiement 5 jours

> Document de cadrage technique et opérationnel pour la mise en place d'un funnel parallèle dédié aux closers externes lors du prochain challenge.
>
> **Owner** : Boris Arduy
> **Deadline go-live** : J+5
> **Volume cible** : ~30 closers répartis sur 3 sales teams externes + 3 managers

---

## 1. Vision en une phrase

Dupliquer le funnel existant (Tally → Calendly → HubSpot → Claap → OneFlow) en un funnel parallèle (Tally → iCloseit → Zoho → Supersales → DocuSign → rapatriement HubSpot) qui isole les leads "sub-50K€ / sans activité" pour traitement par 30 closers externes, sans toucher au système interne actuel et en bénéficiant des automatisations HubSpot post-signature.

---

## 2. Architecture globale

### 2.1. Schéma logique des deux funnels

```
                    ┌──────────────┐
                    │ Tally (live) │
                    └──────┬───────┘
                           │
              ┌────────────┴────────────┐
              │                         │
      CA ≥ 50K€ ou avec activité    CA < 50K€ ou sans activité
              │                         │
              ▼                         ▼
        ┌──────────┐              ┌──────────────┐
        │ Calendly │              │ Page booking │
        └────┬─────┘              │  iCloseit    │
             │                    └──────┬───────┘
             ▼                           │
        ┌──────────┐                     ▼
        │ HubSpot  │              ┌──────────────┐
        │ (interne)│              │ Zoho CRM     │
        └────┬─────┘              │ (externe)    │
             │                    └──────┬───────┘
             ▼                           │
        ┌──────────┐                     ▼
        │ Claap    │              ┌──────────────┐
        │ (record) │              │ Supersales   │
        └────┬─────┘              │ (record)     │
             │                    └──────┬───────┘
             ▼                           │
        ┌──────────┐                     ▼
        │ OneFlow  │              ┌──────────────┐
        │ (contrat)│              │ DocuSign     │
        └────┬─────┘              └──────┬───────┘
             │                           │
             ▼                           ▼
       Deal "gagné"                Deal "gagné"
       sur HubSpot                 sur Zoho
             │                           │
             │                           │
             │                           ▼
             │                    ┌──────────────┐
             │                    │ Push Zoho    │
             │                    │ → HubSpot    │
             │                    │ (automation) │
             │                    └──────┬───────┘
             │                           │
             ├───────────────────────────┘
             ▼
   ┌──────────────────────────────┐
   │ Automatisations existantes   │
   │ (facture, plateforme, mail)  │
   └──────────────────────────────┘
```

### 2.2. Principe directeur

**Tout deal externe finit dans HubSpot.** HubSpot reste la source de vérité business — Zoho est un CRM opérationnel temporaire pour les closers externes uniquement. Cela garantit qu'on n'a qu'un seul système de facturation, de delivery et de reporting global.

---

## 3. Périmètre Zoho ↔ HubSpot — mapping de champs

### 3.1. Stratégie de mapping

Récupérer **le maximum d'informations possibles** côté Zoho, au-delà des champs strictement business, pour ne perdre aucune donnée client. Inclut champs Tally + champs saisis par closer + données comportementales (date de booking, durée d'appel, statut DocuSign).

### 3.2. Champs à mapper Tally → Zoho (à la création de la fiche)

| Champ Tally | Champ Zoho | Obligatoire | Notes |
|---|---|---|---|
| Prénom | First Name | Oui | — |
| Nom | Last Name | Oui | — |
| Email | Email | Oui | Clé de déduplication |
| Téléphone | Phone | Oui | Format international |
| CA actuel | Custom: Revenue Range | Oui | Doit être < 50K€ ou "pas d'activité" pour arriver ici |
| Type d'activité | Custom: Business Type | Oui | — |
| Source du lead | Lead Source | Oui | "Challenge [nom]" ou "Webinar [nom]" |
| Date du booking | Custom: Booking Date | Auto | Depuis iCloseit |
| URL replay challenge / webinar | Custom: Source URL | Auto | — |
| UTM source / medium / campaign | Custom: UTM fields | Auto si présents | — |
| Toutes réponses Tally complémentaires | Custom: Tally Raw | Auto | Stocker le JSON brut en backup |

### 3.3. Champs à mapper Zoho → HubSpot (à la signature DocuSign + deal gagné)

| Champ Zoho | Champ HubSpot | Notes |
|---|---|---|
| Tous les champs ci-dessus | Mêmes champs HubSpot | Recréer les custom properties HubSpot si manquantes |
| Closer assigné (Zoho) | Custom: External Closer | Pour traçabilité |
| Sales team (Zoho) | Custom: External Sales Team | Pour reporting par team |
| Date du call | Custom: Call Date | — |
| Durée du call | Custom: Call Duration | Depuis Supersales |
| URL replay Supersales | Custom: Call Recording URL | Important pour QA |
| Montant du deal | Amount | Champ HubSpot natif |
| Date de signature DocuSign | Custom: Signature Date | — |
| URL contrat signé | Custom: Contract URL | Depuis DocuSign |
| Notes du closer | Notes | Champ HubSpot natif |
| Stage HubSpot | "External Won — À valider" | Stage dédié au pipeline pour distinguer interne/externe |

### 3.4. Action préalable HubSpot

Avant tout, créer dans HubSpot :
- Les **custom properties** ci-dessus si elles n'existent pas
- Un **stage de pipeline dédié** "External Won — À valider" (avant le stage "Won" final)
- Une **vue HubSpot filtrée** sur ce stage pour l'assistante (cf. section 6)

---

## 4. Les automatisations à construire

### 4.1. Vue d'ensemble

| # | Automatisation | Déclencheur | Action principale | Outil |
|---|---|---|---|---|
| A1 | Routing Tally | Soumission Tally | Redirection conditionnelle (Calendly ou iCloseit) | Tally + page de redirection |
| A2 | Création fiche Zoho | Booking confirmé iCloseit | Création contact + deal Zoho avec champs Tally | Make / Zapier |
| A3 | Synchro données call | Fin de call Supersales | Mise à jour fiche Zoho avec recording + durée | Make / Zapier |
| A4 | Génération + envoi DocuSign | Closer clique "envoyer contrat" sur Zoho | Génération contrat avec champs client + envoi DocuSign | Zoho + DocuSign |
| A5 | Push Zoho → HubSpot | Deal Zoho passé en "gagné" **ET** DocuSign statut "completed" | Création fiche contact + deal HubSpot stage "External Won — À valider" | Make / Zapier |
| A6 | Filet de sécurité | DocuSign "completed" depuis > 24h sans deal Zoho gagné | Alerte Slack manager closer concerné + Boris | Make / Zapier |
| A7 | Filet de sécurité 2 | Deal HubSpot stage "External Won — À valider" depuis > 48h | Alerte Slack à l'assistante + Boris | Make / Zapier |
| A8 | Tracking sheet | Push Zoho → HubSpot réussi | Ajout d'une ligne dans le Google Sheet de tracking | Make / Zapier |

### 4.2. Détail des automatisations critiques

#### A1 — Routing Tally

- Si CA ≥ 50K€ ET activité existante → URL de redirection = page Calendly habituelle
- Sinon → URL de redirection = page de booking iCloseit
- **Implémentation** : logique conditionnelle dans Tally (variables) ou via une page intermédiaire qui lit les paramètres URL

#### A2 — Création fiche Zoho au booking iCloseit

- Webhook iCloseit → Make → Zoho API "create contact" + "create deal"
- Le deal est créé au stage "Booked" du pipeline Zoho
- Toutes les données Tally doivent suivre via un identifiant commun (email comme clé) — donc s'assurer que **les données Tally sont passées à iCloseit dans l'URL de redirection** (paramètres URL ou prefill)

⚠️ **Point critique** : iCloseit doit recevoir au minimum email + prénom + nom du Tally pour faire le matching avec Zoho. Vérifier que la prefill iCloseit accepte ces paramètres URL.

#### A5 — Push Zoho → HubSpot

- Déclencheur composé : `deal.stage = "Won"` ET `docusign.status = "completed"` (les deux conditions doivent être vraies)
- Action : création fiche contact HubSpot (si email pas déjà existant — sinon update) + création deal HubSpot stage "External Won — À valider"
- **Gestion des doublons** : avant création, vérifier si email existe déjà dans HubSpot. Si oui, ne pas dupliquer, juste créer le deal lié au contact existant et logger un avertissement.
- **Idempotence** : s'assurer que la même donnée poussée deux fois ne crée pas deux deals (vérifier sur un identifiant unique Zoho deal ID stocké dans un custom field HubSpot).

#### A6 — Filet de sécurité DocuSign signé sans deal gagné

- Déclencheur : DocuSign webhook "envelope.completed"
- Attendre 24h
- Vérifier dans Zoho si le deal correspondant est passé en "gagné"
- Si non → alerte Slack au manager closer + Boris : *"Le deal de [client] a un contrat signé depuis 24h mais n'est pas marqué gagné dans Zoho. Action requise du closer [nom]."*

#### A7 — Filet de sécurité validation HubSpot

- Cron quotidien (par exemple à 9h)
- Lister les deals HubSpot en stage "External Won — À valider" depuis > 48h
- Alerte Slack à l'assistante + Boris

---

## 5. Le sheet de tracking pour l'assistante

### 5.1. Format proposé

Google Sheet avec une ligne par deal externe poussé vers HubSpot. Colonnes :

| Colonne | Source | Notes |
|---|---|---|
| Date de push HubSpot | Auto (A8) | Timestamp de création |
| Email client | Auto | Clé |
| Nom client | Auto | — |
| Closer | Auto | Pour escalade éventuelle |
| Sales team | Auto | — |
| Montant | Auto | — |
| URL deal HubSpot | Auto | Lien direct vers le deal pour l'assistante |
| Statut HubSpot | Auto / manuel | "À valider" → "Validé" |
| Date validation | Manuel (assistante) | Date à laquelle l'assistante a validé |
| Commentaire | Manuel | Si rejeté ou anomalie |

### 5.2. Process quotidien assistante

1. Ouvrir le Sheet le matin
2. Trier sur "Statut = À valider"
3. Pour chaque ligne : ouvrir le deal HubSpot, vérifier que les données sont cohérentes (montant, contact, contrat attaché), passer le deal en "Won" sur HubSpot
4. Marquer la ligne du Sheet comme "Validé" + date
5. Si anomalie (donnée manquante, doublon suspect, contrat non joint) → laisser en "À valider" + commentaire + ping manager closer

### 5.3. Sécurité

- Sheet en lecture seule pour les closers externes (pas d'accès)
- Sheet en édition pour assistante + Boris
- Sauvegarde automatique quotidienne (Drive history suffit)

---

## 6. Effets de bord et risques identifiés

### 6.1. Risques techniques

| Risque | Probabilité | Impact | Mitigation |
|---|---|---|---|
| Doublons HubSpot (lead déjà en base via funnel interne) | Moyenne | Moyen | Dédup par email avant création (cf. A5) |
| Race condition (DocuSign + Zoho gagné simultanés) | Faible | Faible | Logique "ET" dans le déclencheur, idempotence |
| Perte de données Tally → iCloseit (redirection cassée) | Moyenne | Élevé | Stocker JSON brut Tally en backup + alerte si lead Zoho créé sans données Tally |
| API Zoho ou Supersales en panne | Faible | Élevé | Plan B manuel (cf. section 9) |
| Webhook iCloseit non fiable | Faible | Élevé | Polling toutes les 5 min en plus du webhook (double déclencheur) |

### 6.2. Risques humains (les plus dangereux)

| Risque | Probabilité | Impact | Mitigation |
|---|---|---|---|
| Closer externe oublie de passer le deal en gagné | Élevée | Élevé | A6 (filet de sécurité 24h) + formation explicite |
| Closer externe saisit mal les champs Zoho | Élevée | Moyen | Champs obligatoires + validation conditionnelle dans Zoho |
| Assistante en congé / malade | Certaine sur la durée | Élevé | A7 (alerte 48h) + backup formé (Boris ou autre) |
| Manager team externe ne suit pas ses closers | Moyenne | Élevé | Reporting hebdo automatisé par team |
| Fuite de leads (closer externe sauvegarde les contacts) | Moyenne | Élevé (RGPD + concurrentiel) | Clause contractuelle + permissions Zoho restrictives |

### 6.3. Risques RGPD et conformité

- **Mention RGPD sur Tally** doit être explicite : les données peuvent être traitées par des sales teams externes basées hors UE éventuellement
- **Contrat de sous-traitance (DPA)** à signer avec chaque sales team externe avant d'ouvrir l'accès Zoho
- **Permissions Zoho** : chaque closer externe ne doit voir que ses propres deals, pas ceux des autres teams
- **Audit log Zoho** activé pour tracer toute consultation / export de données

---

## 7. Contrôles à mettre en place

### 7.1. Côté système

- **Dashboard Zoho** : nombre de deals créés / par closer / par jour / par stage
- **Dashboard HubSpot** : nombre de deals "External Won — À valider" + temps moyen avant validation
- **Alerte Slack quotidienne** à 18h : récap de la journée (X bookings iCloseit, Y deals Zoho gagnés, Z deals poussés HubSpot, W en attente validation)

### 7.2. Côté process

- **Brief obligatoire des closers externes** avant accès Zoho (1h en visio, support écrit)
- **Charte de saisie** signée par chaque closer (champs obligatoires, formats, délais)
- **Point hebdo** entre Boris et les 3 managers de teams externes (30 min)
- **QA aléatoire** : Boris écoute 5 calls Supersales / semaine pour vérifier qualité + cohérence saisie

---

## 8. Plan de déploiement sur 5 jours

### J+1 — Setup et préparation (mercredi)

- [ ] Créer les custom properties manquantes dans HubSpot
- [ ] Créer le stage de pipeline "External Won — À valider"
- [ ] Vérifier les comptes / licences iCloseit, Zoho, Supersales (plans payants OK)
- [ ] Créer le Google Sheet de tracking avec template
- [ ] Identifier qui est l'assistante owner du Sheet
- [ ] Cadrage avec les 3 managers de teams externes : process, deadlines, charte

### J+2 — Connexions et automatisations critiques (jeudi)

- [ ] Configurer la redirection Tally conditionnelle (A1)
- [ ] Configurer la prefill iCloseit avec données Tally (URL params)
- [ ] Construire l'automation A2 (booking iCloseit → fiche Zoho)
- [ ] Construire l'automation A4 (génération + envoi DocuSign depuis Zoho)
- [ ] Tester A1 + A2 + A4 avec un compte test

### J+3 — Synchros et filets de sécurité (vendredi)

- [ ] Construire l'automation A3 (Supersales → Zoho)
- [ ] Construire l'automation A5 (Zoho → HubSpot)
- [ ] Construire les automations A6, A7, A8 (filets de sécurité + sheet)
- [ ] Tester le flow complet de bout en bout (1 lead test passe par tout le funnel)

### J+4 — Tests à blanc et corrections (samedi)

- [ ] 5 leads test avec 5 cas différents (lead clean, lead doublon, closer qui oublie de passer en gagné, DocuSign non signé, lead avec champs manquants)
- [ ] Vérifier les alertes Slack
- [ ] Vérifier le Sheet
- [ ] Brief des closers externes (visio 1h)
- [ ] Corrections sur la base des tests

### J+5 — Go live (dimanche / lundi selon date challenge)

- [ ] Activation finale
- [ ] Monitoring rapproché les 24 premières heures (toutes les 2h, vérifier Sheet + alertes + dashboards)
- [ ] Point flash avec les 3 managers à H+24 et H+48

---

## 9. Plan B en cas de panne

### 9.1. Si iCloseit tombe

- Fallback Calendly avec une page d'attribution manuelle
- Les closers externes reçoivent les bookings par email + saisissent manuellement dans Zoho

### 9.2. Si l'automation Zoho → HubSpot échoue

- L'assistante crée manuellement les fiches HubSpot depuis le Sheet (qui reste alimenté)
- Boris et l'assistante débriefent à chaud, restauration du flux dès que possible

### 9.3. Si DocuSign tombe

- Fallback : envoi manuel d'un contrat PDF par email avec demande de signature scan
- Une fois reçu, l'assistante upload manuellement dans HubSpot + passe le deal en gagné

### 9.4. Procédure d'urgence générale

Numéro Slack ou WhatsApp dédié "incident funnel externe" avec Boris + l'assistante + les 3 managers de teams. Tout incident bloquant remonte là, traité en priorité.

---

## 10. Points qui restent à trancher

| # | Sujet | Décideur |
|---|---|---|
| 1 | Outil d'automation principal : Make ou Zapier ? Recommandation : Make (plus puissant pour les flows multi-étapes) | Boris |
| 2 | Qui sera l'assistante owner du Sheet et du process de validation HubSpot ? | Boris + Fabrice |
| 3 | Format précis du brief des closers externes : visio unique ou par team ? | Boris + managers externes |
| 4 | Date exacte du go-live (lundi prochain ou alignée sur le start du challenge ?) | À caler avec marketing |
| 5 | Stratégie de communication interne : qui dans l'équipe doit savoir qu'il y a un funnel parallèle ? | Boris + Alec |

---

## 11. Honnêteté sur le timing

Le délai de 5 jours est tendu mais réaliste **à condition** :
- De n'avoir aucun blocage sur les comptes / licences (déjà OK selon ton input)
- De pouvoir mobiliser un dev / intégrateur Make 2-3 jours pleins (J+2 et J+3 surtout)
- D'avoir l'assistante identifiée et briefée à J+4
- D'avoir les 3 managers externes disponibles pour le brief J+4

Si l'un de ces points cale, le go-live glisse à J+7 minimum. **Mieux vaut décaler proprement que pousser un système instable en pleine campagne.**

---

*Document v1 — 7 mai 2026. Boris Arduy, Operating Partner.*
