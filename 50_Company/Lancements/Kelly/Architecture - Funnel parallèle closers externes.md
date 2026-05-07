---
type: technical-spec
project: "[[_Index|Lancement Kelly]]"
owner: "[[Boris Arduy]]"
created: 2026-05-07
last-updated: 2026-05-07
status: draft-v2
deadline: 2026-05-17
tags: [lancement, kelly, funnel, automation, hubspot, zoho, make, technical-spec, closers-externes, short-io, multi-agences]
sensitivity: confidential
---

# Funnel parallèle Closers Externes — Architecture et plan de déploiement

> Document de cadrage technique et opérationnel pour la mise en place d'un funnel parallèle dédié aux closers externes lors du Lancement Kelly.
>
> **Owner** : Boris Arduy
> **Deadline go-live** : 17 mai 2026 (event)
> **Volume cible** : 2500-3000 calls sur l'avatar sub-50K€ / sans activité
> **Effectifs** : ~40 closers répartis sur 3 sales teams externes + 3 managers + jusqu'à 10 setters backup

## Changelog

- **v1 (7 mai)** — Architecture initiale, single-agency
- **v2 (7 mai, post-call Momentum)** — Intégration Short.io pour routing multi-agences, mise à jour effectifs et volume confirmé, ajout setup adresses mail

---

## 1. Vision en une phrase

Dupliquer le funnel existant (Tally → Calendly → HubSpot → Claap → OneFlow) en un funnel parallèle (Tally → Short.io → iCloseit → Zoho → Supersales → DocuSign → rapatriement HubSpot) qui isole les leads "sub-50K€ / sans activité" pour traitement par 3 sales teams externes (~40 closers), sans toucher au système interne actuel et en bénéficiant des automatisations HubSpot post-signature.

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
        │ Calendly │              │  Short.io    │
        └────┬─────┘              │  (routing)   │
             │                    └──────┬───────┘
             ▼                           │
        ┌──────────┐         ┌───────────┼───────────┐
        │ HubSpot  │         │           │           │
        │ (interne)│         ▼           ▼           ▼
        └────┬─────┘    ┌─────────┐ ┌─────────┐ ┌─────────┐
             │          │ Tip     │ │Momentum │ │  Axel   │
             ▼          │ Talent  │ │         │ │ Greiber │
        ┌──────────┐    │  ~25%   │ │  ~50%   │ │  ~25%   │
        │ Claap    │    └────┬────┘ └────┬────┘ └────┬────┘
        │ (record) │         │           │           │
        └────┬─────┘         └─────┬─────┴─────┬─────┘
             │                     │           │
             ▼                     ▼           ▼
        ┌──────────┐         ┌──────────────────┐
        │ OneFlow  │         │     iCloseit     │
        │ (contrat)│         │   (1 calendrier  │
        └────┬─────┘         │    par closer)   │
             │               └─────────┬────────┘
             ▼                         │
       Deal "gagné"                    ▼
       sur HubSpot              ┌──────────────┐
             │                  │  Zoho CRM    │
             │                  │ (tagging par │
             │                  │   agence)    │
             │                  └──────┬───────┘
             │                         │
             │                         ▼
             │                  ┌──────────────┐
             │                  │ Supersales   │
             │                  │  (record)    │
             │                  └──────┬───────┘
             │                         │
             │                         ▼
             │                  ┌──────────────┐
             │                  │  DocuSign    │
             │                  └──────┬───────┘
             │                         │
             │                         ▼
             │                   Deal "gagné"
             │                   sur Zoho
             │                         │
             │                         ▼
             │                  ┌──────────────┐
             │                  │ Push Zoho    │
             │                  │ → HubSpot    │
             │                  │ (automation) │
             │                  └──────┬───────┘
             │                         │
             ├─────────────────────────┘
             ▼
   ┌──────────────────────────────┐
   │ Automatisations existantes   │
   │ (facture, plateforme, mail)  │
   └──────────────────────────────┘
```

### 2.2. Principe directeur

**Tout deal externe finit dans HubSpot.** HubSpot reste la source de vérité business — Zoho est un CRM opérationnel temporaire pour les closers externes uniquement. Cela garantit qu'on n'a qu'un seul système de facturation, de delivery et de reporting global.

### 2.3. Nouveauté v2 : routing multi-agences via Short.io

Avec **40 closers répartis sur 3 sales teams**, iCloseit seul ne peut pas gérer correctement la répartition. Solution proposée par Lucas (Momentum) en call : utiliser **Short.io** comme couche de routing entre Tally et iCloseit.

Short.io permet de définir des proportions de répartition fixes (ex : 25% / 50% / 25%) qui dirigent les leads vers la page de booking iCloseit spécifique de chaque agence. Chaque agence a sa propre URL iCloseit avec ses propres calendriers et ses propres closers.

**Avantage** : routing déterministe, traçabilité complète (chaque lead est tagué dès le départ avec son agence d'origine), pas de mélange entre agences.

**Proportions proposées** (à valider avec Aziz) :
- Tip Talent : 25% (10 closers / 40 = 25%)
- Momentum : 50% (20 closers / 40 = 50%)
- Axel Greiber : 25% (10 closers / 40 = 25%)

---

## 3. Périmètre Zoho ↔ HubSpot — mapping de champs

### 3.1. Stratégie de mapping

Récupérer **le maximum d'informations possibles** côté Zoho, au-delà des champs strictement business, pour ne perdre aucune donnée client. Inclut champs Tally + champs saisis par closer + données comportementales (date de booking, durée d'appel, statut DocuSign) + agence d'origine.

### 3.2. Champs à mapper Tally → Zoho (à la création de la fiche)

| Champ Tally | Champ Zoho | Obligatoire | Notes |
|---|---|---|---|
| Prénom | First Name | Oui | — |
| Nom | Last Name | Oui | — |
| Email | Email | Oui | Clé de déduplication |
| Téléphone | Phone | Oui | Format international |
| CA actuel | Custom: Revenue Range | Oui | Doit être < 50K€ ou "pas d'activité" pour arriver ici |
| Type d'activité | Custom: Business Type | Oui | — |
| Source du lead | Lead Source | Oui | "Challenge Kelly" |
| **Agence assignée (via Short.io)** | **Custom: External Agency** | **Oui** | **Tip Talent / Momentum / Axel** |
| Date du booking | Custom: Booking Date | Auto | Depuis iCloseit |
| URL replay challenge / webinar | Custom: Source URL | Auto | — |
| UTM source / medium / campaign | Custom: UTM fields | Auto si présents | — |
| Toutes réponses Tally complémentaires | Custom: Tally Raw | Auto | Stocker le JSON brut en backup |

### 3.3. Champs à mapper Zoho → HubSpot (à la signature DocuSign + deal gagné)

| Champ Zoho | Champ HubSpot | Notes |
|---|---|---|
| Tous les champs ci-dessus | Mêmes champs HubSpot | Recréer les custom properties HubSpot si manquantes |
| Closer assigné (Zoho) | Custom: External Closer | Pour traçabilité |
| **External Agency** | **Custom: External Agency** | **Pour reporting et calcul des commissions différenciées** |
| Sales team / manager | Custom: External Sales Team | Pour reporting par team |
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
- Les **custom properties** ci-dessus si elles n'existent pas (notamment `External Agency`)
- Un **stage de pipeline dédié** "External Won — À valider" (avant le stage "Won" final)
- Une **vue HubSpot filtrée** sur ce stage pour l'assistante (cf. section 6)
- Une **vue HubSpot par agence** pour le reporting et le calcul des commissions différenciées

---

## 4. Setup des comptes et accès — nouveauté v2

### 4.1. ~70 adresses mail dédiées à créer

Volume estimé :
- **40 closers** (10 Tip Talent + 20 Momentum + 10 Axel)
- **20 setters** (10 Momentum + 10 SDR EC déjà existants, à confirmer si setters Axel)
- **3 head of sales** (1 par agence)
- **3 managers/team leaders** (1 par agence)
- **= ~66-70 adresses**

Décisions à prendre :
- **Domaine** : @entrepreneurs.com ou un sous-domaine type @kelly.entrepreneurs.com (recommandation : sous-domaine pour bien isoler et faciliter la suppression post-event)
- **Provider** : Workspace Google (cohérent avec le reste de l'écosystème EC)
- **Durée de vie** : actives uniquement pour la durée du challenge + queue R2/R3 (jusqu'à fin juin par sécurité)
- **Process de suppression** : à scripter pour batch suppression post-event

### 4.2. Comptes iCloseit

- **3 calendriers iCloseit dédiés** (un par agence)
- Chaque calendrier configuré avec les closers de l'agence
- Plan payant à valider (volume challenge)

### 4.3. Comptes Zoho CRM

- **Permissions par agence** : chaque closer ne voit que ses propres deals (pas ceux des autres agences)
- **Tags ou pipelines séparés** par agence pour le reporting
- **Audit log activé** pour traçabilité (RGPD)

### 4.4. Comptes Supersales

- À cadrer : 1 enregistrement par call ou seuils différents par agence ?
- Plan payant à valider

### 4.5. Comptes DocuSign

- Templates de contrats à préparer (offre Kelly 5 700€)
- Workflow de signature à automatiser

---

## 5. Les automatisations à construire

### 5.1. Vue d'ensemble (mise à jour v2)

| # | Automatisation | Déclencheur | Action principale | Outil |
|---|---|---|---|---|
| A0 | **Routing Short.io** | **Soumission Tally avec critère sub-50K€** | **Redirection vers iCloseit de l'agence assignée selon proportions définies** | **Short.io** |
| A1 | Routing Tally interne vs externe | Soumission Tally | Redirection conditionnelle (Calendly direct ou Short.io) | Tally + page de redirection |
| A2 | Création fiche Zoho | Booking confirmé iCloseit | Création contact + deal Zoho avec champs Tally + tag agence | Make / Zapier |
| A3 | Synchro données call | Fin de call Supersales | Mise à jour fiche Zoho avec recording + durée | Make / Zapier |
| A4 | Génération + envoi DocuSign | Closer clique "envoyer contrat" sur Zoho | Génération contrat avec champs client + envoi DocuSign | Zoho + DocuSign |
| A5 | Push Zoho → HubSpot | Deal Zoho passé en "gagné" **ET** DocuSign statut "completed" | Création fiche contact + deal HubSpot stage "External Won — À valider" + tag agence | Make / Zapier |
| A6 | Filet de sécurité | DocuSign "completed" depuis > 24h sans deal Zoho gagné | Alerte Slack manager closer concerné + Boris | Make / Zapier |
| A7 | Filet de sécurité 2 | Deal HubSpot stage "External Won — À valider" depuis > 48h | Alerte Slack à l'assistante + Boris | Make / Zapier |
| A8 | Tracking sheet | Push Zoho → HubSpot réussi | Ajout d'une ligne dans le Google Sheet de tracking avec colonne agence | Make / Zapier |
| A9 | **Reporting volume par agence** | **Cron horaire** | **Mise à jour dashboard avec calls / deals / closing rate par agence** | **Make + Google Sheets** |

### 5.2. Détail des automatisations critiques

#### A0 — Routing Short.io (NOUVEAU v2)

- Lien Short.io maître type `https://link.entrepreneurs.com/kelly-external` qui redirige vers les 3 URLs iCloseit selon proportions
- **Configuration des proportions** dans Short.io (interface admin) : 25% / 50% / 25%
- Tracking : Short.io enregistre l'agence d'attribution et passe l'info en paramètre URL à iCloseit
- **iCloseit prefill** : email + prénom + nom du Tally + tag agence transmis via paramètres URL

⚠️ **Point critique à valider** : iCloseit doit accepter les paramètres URL pour tag agence en custom field. À tester en J+1.

#### A1 — Routing Tally interne vs externe

- Si CA ≥ 50K€ ET activité existante → URL de redirection = page Calendly habituelle (funnel interne)
- Sinon → URL de redirection = lien Short.io maître (funnel externe)
- **Implémentation** : logique conditionnelle dans Tally (variables) ou via une page intermédiaire qui lit les paramètres URL

#### A2 — Création fiche Zoho au booking iCloseit

- Webhook iCloseit → Make → Zoho API "create contact" + "create deal"
- Le deal est créé au stage "Booked" du pipeline Zoho de l'agence
- **Tag agence obligatoire** : récupéré depuis les paramètres URL passés via Short.io
- Toutes les données Tally doivent suivre via un identifiant commun (email comme clé)

#### A5 — Push Zoho → HubSpot

- Déclencheur composé : `deal.stage = "Won"` ET `docusign.status = "completed"` (les deux conditions doivent être vraies)
- Action : création fiche contact HubSpot (si email pas déjà existant — sinon update) + création deal HubSpot stage "External Won — À valider" + **tag agence pour le calcul des commissions différenciées**
- **Gestion des doublons** : avant création, vérifier si email existe déjà dans HubSpot. Si oui, ne pas dupliquer, juste créer le deal lié au contact existant et logger un avertissement.
- **Idempotence** : s'assurer que la même donnée poussée deux fois ne crée pas deux deals (vérifier sur un identifiant unique Zoho deal ID stocké dans un custom field HubSpot).

#### A6 — Filet de sécurité DocuSign signé sans deal gagné

- Déclencheur : DocuSign webhook "envelope.completed"
- Attendre 24h
- Vérifier dans Zoho si le deal correspondant est passé en "gagné"
- Si non → alerte Slack au manager closer (selon agence) + Boris : *"Le deal de [client] a un contrat signé depuis 24h mais n'est pas marqué gagné dans Zoho. Action requise du closer [nom]."*

#### A7 — Filet de sécurité validation HubSpot

- Cron quotidien (par exemple à 9h)
- Lister les deals HubSpot en stage "External Won — À valider" depuis > 48h
- Alerte Slack à l'assistante + Boris

#### A9 — Reporting volume par agence (NOUVEAU v2)

- Cron horaire pendant le challenge
- Pour chaque agence : compteurs de calls bookés / calls réalisés / deals gagnés / closing rate
- Mise à jour d'un Google Sheet partagé avec Aziz + Alec
- Permet de monitorer en temps réel la performance comparative des 3 agences

---

## 6. Le sheet de tracking pour l'assistante

### 6.1. Format proposé

Google Sheet avec une ligne par deal externe poussé vers HubSpot. Colonnes :

| Colonne | Source | Notes |
|---|---|---|
| Date de push HubSpot | Auto (A8) | Timestamp de création |
| **Agence** | **Auto** | **Tip Talent / Momentum / Axel** |
| Email client | Auto | Clé |
| Nom client | Auto | — |
| Closer | Auto | Pour escalade éventuelle |
| Sales team / manager | Auto | — |
| Montant | Auto | — |
| URL deal HubSpot | Auto | Lien direct vers le deal pour l'assistante |
| Statut HubSpot | Auto / manuel | "À valider" → "Validé" |
| Date validation | Manuel (assistante) | Date à laquelle l'assistante a validé |
| Commentaire | Manuel | Si rejeté ou anomalie |

### 6.2. Process quotidien assistante

Inchangé par rapport à v1.

### 6.3. Sécurité

Inchangé par rapport à v1.

---

## 7. Effets de bord et risques identifiés

### 7.1. Risques techniques (mise à jour v2)

| Risque | Probabilité | Impact | Mitigation |
|---|---|---|---|
| Doublons HubSpot (lead déjà en base via funnel interne) | Moyenne | Moyen | Dédup par email avant création (cf. A5) |
| Race condition (DocuSign + Zoho gagné simultanés) | Faible | Faible | Logique "ET" dans le déclencheur, idempotence |
| Perte de données Tally → Short.io → iCloseit (paramètres URL cassés) | Moyenne | Élevé | Stocker JSON brut Tally en backup + alerte si lead Zoho créé sans données Tally ou sans tag agence |
| **Short.io ne respecte pas les proportions exactes** | Faible | Moyen | Acceptable variance ±5%, monitoring via A9 |
| API Zoho ou Supersales en panne | Faible | Élevé | Plan B manuel (cf. section 9) |
| Webhook iCloseit non fiable | Faible | Élevé | Polling toutes les 5 min en plus du webhook (double déclencheur) |
| **Mauvaise attribution agence** (lead créé sans tag) | Moyenne | Élevé | Validation obligatoire dans A2, fail si tag manquant |

### 7.2. Risques humains (mise à jour v2)

| Risque | Probabilité | Impact | Mitigation |
|---|---|---|---|
| Closer externe oublie de passer le deal en gagné | Élevée | Élevé | A6 (filet de sécurité 24h) + formation explicite |
| Closer externe saisit mal les champs Zoho | Élevée | Moyen | Champs obligatoires + validation conditionnelle dans Zoho |
| Assistante en congé / malade | Certaine sur la durée | Élevé | A7 (alerte 48h) + backup formé (Boris ou autre) |
| Manager team externe ne suit pas ses closers | Moyenne | Élevé | Reporting hebdo automatisé par team |
| Fuite de leads (closer externe sauvegarde les contacts) | Moyenne | Élevé (RGPD + concurrentiel) | Clause contractuelle + permissions Zoho restrictives |
| **Disparité d'approche entre agences** (Tip Talent nurturing vs Momentum R1-to-close) | Acceptée | Faible | Pas un risque mais un fait — chaque agence garde son mode opératoire (validé Alec) |
| **Bascule de leads entre agences** (Tip Talent / Momentum mêmes locaux) | Faible | Élevé | Permissions Zoho strictes, audit log activé |

### 7.3. Risques RGPD et conformité (mise à jour v2)

- **Mention RGPD sur Tally** doit être explicite : les données peuvent être traitées par des sales teams externes basées au Maroc
- **Contrat de sous-traitance (DPA)** à signer avec **chaque** sales team externe avant d'ouvrir l'accès Zoho (3 DPA distincts)
- **Permissions Zoho** : chaque closer externe ne doit voir que ses propres deals, pas ceux des autres teams ni des autres agences
- **Audit log Zoho** activé pour tracer toute consultation / export de données
- **Suppression post-event** : process de suppression des accès Zoho et adresses mail à programmer (cf. section 4)

---

## 8. Contrôles à mettre en place

### 8.1. Côté système (mise à jour v2)

- **Dashboard Zoho par agence** : nombre de deals créés / par closer / par jour / par stage / **par agence**
- **Dashboard HubSpot par agence** : nombre de deals "External Won — À valider" + temps moyen avant validation + **par agence**
- **Alerte Slack quotidienne** à 18h : récap de la journée par agence (X bookings iCloseit, Y deals Zoho gagnés, Z deals poussés HubSpot, W en attente validation, par agence)
- **Reporting comparatif horaire** (A9) : performance comparative des 3 agences en temps réel pour Aziz + Alec

### 8.2. Côté process

- **Brief obligatoire des closers externes** avant accès Zoho (1h en visio coaching commun mardi 11h, support écrit)
- **Charte de saisie** signée par chaque closer (champs obligatoires, formats, délais)
- **Point hebdo** entre Boris et les 3 managers de teams externes (30 min)
- **QA aléatoire** : Boris écoute 5 calls Supersales / semaine pour vérifier qualité + cohérence saisie
- **Daily** Boris ↔ Julien (Tip Talent) + Hélène (Momentum) + référent Axel pendant l'event

---

## 9. Plan de déploiement (timeline mise à jour)

### J+0 — 7 mai (aujourd'hui)
- ✅ Architecture v2 livrée
- ✅ Fiches partenaires Tip Talent + Momentum créées
- [ ] Hélène contacte Boris avec liste de besoins
- [ ] Boris confirme intégrateur Make
- [ ] Boris cadre setup adresses mail

### J+1 — 8 mai (jeudi)
- [ ] Setup HubSpot : custom properties (notamment `External Agency`) + stage "External Won — À valider"
- [ ] Vérification accès iCloseit / Zoho / Supersales / DocuSign / **Short.io**
- [ ] Création du Google Sheet de tracking avec colonne agence
- [ ] Identification de l'assistante owner du Sheet
- [ ] Cadrage avec les 3 managers de teams externes : process, deadlines, charte
- [ ] **Configuration Short.io** : 3 URLs iCloseit créées, proportions définies à valider avec Aziz

### J+2 — 9 mai (vendredi)
- [ ] Configurer la redirection Tally conditionnelle (A1)
- [ ] **Configurer Short.io** avec proportions et URLs iCloseit (A0)
- [ ] **Tester le routing Short.io** avec quelques leads tests (vérifier les 3 redirections)
- [ ] Configurer la prefill iCloseit avec données Tally + tag agence
- [ ] Construire l'automation A2 (booking iCloseit → fiche Zoho + tag agence)
- [ ] Construire l'automation A4 (génération + envoi DocuSign depuis Zoho)
- [ ] Tester A0 + A1 + A2 + A4 avec un compte test

### J+3 — 10 mai (samedi)
- [ ] Construire l'automation A3 (Supersales → Zoho)
- [ ] Construire l'automation A5 (Zoho → HubSpot avec tag agence)
- [ ] Construire les automations A6, A7, A8 (filets de sécurité + sheet)
- [ ] Construire A9 (reporting volume par agence)
- [ ] Tester le flow complet de bout en bout (1 lead test passe par tout le funnel pour chacune des 3 agences)
- [ ] **Setup ~70 adresses mail créées et distribuées**

### J+4 — 11 mai (dimanche)
- [ ] Tests à blanc avec 5 leads par agence (15 leads tests au total)
- [ ] 5 cas différents : lead clean, lead doublon, closer qui oublie de passer en gagné, DocuSign non signé, lead avec champs manquants
- [ ] Vérifier les alertes Slack
- [ ] Vérifier le Sheet (avec colonne agence)
- [ ] Vérifier le dashboard de reporting comparatif
- [ ] Corrections sur la base des tests
- [ ] **MP Aziz pour cadrer son discours coaching mardi** (cadre commun, pas process unique)

### J+5 — 12 mai (lundi)
- [ ] Vérification finale du setup tech
- [ ] Préparation finale du coaching mardi

### J+6 — 13 mai (mardi)
- [ ] **Coaching commun 3 agences à 11h** (Aziz + Alec, 1h, ~45-50 personnes)
- [ ] Brief des closers externes sur l'écosystème, l'offre, la posture
- [ ] Diffusion finale du one-pager process

### J+7 — 14 mai (mercredi)
- [ ] Intervention possible Alec coaching dédié (dernière fenêtre avant départ Marrakech le 15)
- [ ] Validation finale photos + replays sales (toutes agences) par Alec/Aziz
- [ ] Signature contrats de partenariat (3 agences)

### J+10 — 17 mai (samedi) — GO LIVE EVENT
- [ ] Activation finale
- [ ] Intervention Kelly sur lien non répertorié 1-2h avant le premier live
- [ ] Monitoring rapproché les 24 premières heures (toutes les 2h, vérifier Sheet + alertes + dashboards par agence)
- [ ] Point flash avec les 3 managers à H+24 et H+48

---

## 10. Plan B en cas de panne

### 10.1. Si Short.io tombe (NOUVEAU v2)

- Fallback : routing manuel via 3 URLs iCloseit distinctes affichées sur la page intermédiaire
- L'utilisateur choisit aléatoirement (UX dégradée mais fonctionnelle)
- Boris monitor en temps réel les volumes par agence pour rééquilibrer manuellement si déséquilibre

### 10.2. Si iCloseit tombe

- Fallback Calendly avec une page d'attribution manuelle
- Les closers externes reçoivent les bookings par email + saisissent manuellement dans Zoho

### 10.3. Si l'automation Zoho → HubSpot échoue

- L'assistante crée manuellement les fiches HubSpot depuis le Sheet (qui reste alimenté)
- Boris et l'assistante débriefent à chaud, restauration du flux dès que possible

### 10.4. Si DocuSign tombe

- Fallback : envoi manuel d'un contrat PDF par email avec demande de signature scan
- Une fois reçu, l'assistante upload manuellement dans HubSpot + passe le deal en gagné

### 10.5. Procédure d'urgence générale

Numéro Slack ou WhatsApp dédié "incident funnel externe" avec Boris + l'assistante + les 3 managers de teams (Julien Tip Talent, Hélène Momentum, référent Axel). Tout incident bloquant remonte là, traité en priorité.

---

## 11. Points qui restent à trancher

| # | Sujet | Décideur | Deadline |
|---|---|---|---|
| 1 | Outil d'automation principal : Make ou Zapier ? Recommandation : Make | Boris | 8 mai |
| 2 | Qui sera l'assistante owner du Sheet et du process de validation HubSpot ? | Boris + Fabrice | 8 mai |
| 3 | **Proportions Short.io entre agences** (proposition 25/50/25) | Boris + Aziz | 9 mai |
| 4 | Format précis du brief des closers externes : finalisé pour mardi ? | Boris + Aziz | 11 mai |
| 5 | Domaine pour les ~70 adresses mail (sous-domaine kelly. ?) | Boris | 8 mai |
| 6 | Stratégie de communication interne EC : qui doit savoir ? | Boris + Alec | 9 mai |
| 7 | Commission Axel Greiber (recommandation 10-11%) | Aziz + Alec | 10 mai |
| 8 | Politique moyens de paiement avec Tip Talent (tension Romain ↔ Aziz) | Aziz | Avant coaching mardi |

---

## 12. Honnêteté sur le timing

Le délai de 10 jours est tendu mais réaliste **à condition** :
- D'avoir aucun blocage sur les comptes / licences (a priori OK selon les inputs Aziz/Alec)
- De pouvoir mobiliser un dev / intégrateur Make 2-3 jours pleins (J+2 et J+3 surtout)
- D'avoir l'assistante identifiée et briefée à J+4
- D'avoir les 3 managers externes alignés sur le process avant le coaching mardi
- De compléter le setup ~70 adresses mail dans les 4-5 prochains jours
- D'avoir Short.io paramétré et testé d'ici J+3

Si l'un de ces points cale, certains modules peuvent être dégradés (cf. plans B section 10) mais le funnel critique doit tenir. **Mieux vaut décaler proprement que pousser un système instable en pleine campagne.**

---

## 13. Liens

- Hub projet : [[_Index|Lancement Kelly]]
- Vue d'ensemble 3 agences : [[Partenaires - Vue d'ensemble 3 agences]]
- Tip Talent : [[Partenaires - Tip Talent (Romain Nussmann)]]
- Momentum : [[Partenaires - Momentum (Lucas Cureau)]]
- Source Tip Talent : [[2026-05-07 - Call Alec Aziz Romain Nussmann (Tip Talent)]]
- Source Momentum : [[2026-05-07 - Call Alec Aziz Lucas Cureau Helene (Momentum)]]

---

*Document v2 — 7 mai 2026. Boris Arduy, Operating Partner.*
