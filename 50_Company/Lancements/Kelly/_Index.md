---
type: project-hub
status: active
phase: cadrage-technique-et-partenariats
owner: "[[Boris Arduy]]"
created: 2026-05-07
last-updated: 2026-05-10
deadline-go-live: 2026-05-17
event-dates: "17 mai (3 days + jour bonus + 2 jours plus tard, ~8 jours d'absorption des calls)"
event-location: Marrakech (Alec présent du 15 au 24 mai)
tags: [lancement, kelly, sales, closers-externes, funnel, hubspot, zoho, automation, project]
sensitivity: confidential
---

# Lancement Kelly — Project Hub

> Hub d'accueil du projet. Point d'entrée unique pour la navigation, le statut et les actions en cours.

## Statut au 7 mai 2026

**Phase actuelle** : cadrage technique + partenariats sales
**Prochaine milestone** : coaching commun 3 agences (mardi 12 mai à 11h)
**Go-live event** : 17 mai 2026 (Marrakech)

## Contexte business

Le Lancement Kelly est un événement type challenge avec un volume d'inscrits exceptionnel : **50 000 à 60 000 inscrits** projetés (vs 20 000 sur les lancements habituels), grâce à un CPL exceptionnellement bas (~5€ vs 17€ habituels — certaines campagnes à 12 centimes).

Conséquence : les leads sont d'une **typologie différente** (B2C orienté business, sub-50K€, sans activité ou en lancement) que l'équipe sales interne ne traite pas habituellement (équipe interne sur cycle B2B / R1-to-close avec posture business coach).

Décision business : **externaliser le traitement de ces ~20 000 prospects** vers 3 sales teams partenaires, avec une offre dédiée à 5 700€ sur 6 mois (réactivation d'un produit qui avait cartonné 1 an et demi en arrière, repackagé avec plus de valeur).

## Architecture du dispositif

- **Funnel interne (existant)** : Tally → Calendly → HubSpot → Claap → OneFlow — pour les leads qualifiés (CA ≥ 50K€ + activité)
- **Funnel externe (à construire)** : Tally → Short.io (routing entre agences) → iCloseit → Zoho → Supersales → DocuSign → push HubSpot — pour les leads sub-50K€ ou sans activité, traités par les 3 agences partenaires
- **HubSpot reste source de vérité business** — Zoho est CRM opérationnel temporaire pour les sales externes uniquement

## Volume cible confirmé

- **2500-3000 calls** sur l'avatar externe (validé par Alec en call Momentum)
- ~62 calls par closer sur 8 jours, soit 7-8 calls/closer/jour
- Répartition prévue : ~40 closers au total

## Effectifs sales partenaires

| Agence | Closers | Setters | Statut |
|---|---|---|---|
| Tip Talent | 10 (possiblement 12) | 0 (sales font setting) | ✅ GO |
| Momentum | **20** | jusqu'à 10 (backup) | ✅ GO |
| Axel Greiber | ~10 (estimation) | À confirmer | 🟡 À confirmer |
| **Total** | **~40** | **+ jusqu'à 10** | |

## Documents du projet

### Cadrage technique
- [[Architecture - Funnel parallèle closers externes]] — architecture technique complète + plan de déploiement
- [[Infrastructure - Setup en cours]] — log de setup avec statuts à jour, décisions prises, IDs critiques
- [[Scenario A2 - iClosed vers Zoho]] — spec complète du scenario Make A2 (production-ready depuis le 9 mai)
- [[Closers - Liste opérationnelle Kelly]] — liste des 38 closers par agence, emails, MDP provisoires, CSV import Zoho
- [[Produit - Méthode Boss Energy]] — catalogue produit Zoho (6 variantes pricing 1x à 6x), description, procédure d'import

### Partenariats
- [[Partenaires - Vue d'ensemble 3 agences]] — vue agrégée + comparatifs + écart commission
- [[Partenaires - Tip Talent (Romain Nussmann)]] — fiche partenaire #1 (✅ confirmé)
- [[Partenaires - Momentum (Lucas Cureau)]] — fiche partenaire #2 (✅ confirmé)
- (à créer) Fiche Axel Greiber

### Sources
- [[2026-05-07 - Call Alec Aziz Romain Nussmann (Tip Talent)]] — transcript intégral
- [[2026-05-07 - Call Alec Aziz Lucas Cureau Helene (Momentum)]] — transcript intégral

### À produire
- Brief closers externes (support écrit + structure visio coaching)
- Charte de saisie Zoho
- Kit branding Entrepreneurs.com pour les 3 agences (témoignages, contexte Kelly)
- One-pager process (qui fait quoi à quel moment)
- Cahier des charges Make pour intégrateur
- DPA modèle pour les 3 sales teams
- Setup ~70 adresses mail dédiées
- Calls incubateurs (10 échoués + 10 réussis, validé par Alec)
- Plaquette de l'offre Kelly

## Décisions actées

### Commerciales
- **Commission Tip Talent : 10%** (sans négociation)
- **Commission Momentum : 13%** (2% setting + 11% closing/upsells, négociée vs 15% standard)
- **Commission Axel : à négocier** (recommandation Boris : 10-11%)
- **Approche commerciale** : chaque agence garde son mode opératoire (Tip Talent nurturing R1-R4, Momentum R1-to-close), validé par Alec

### Opérationnelles
- **Boris = pont opérationnel et tech** entre Aziz/Cédric et les 3 agences (mandat explicite Alec, confirmé dans les 2 calls)
- **HubSpot source de vérité** + push automatisé Zoho → HubSpot après deal gagné + DocuSign signé
- **Sheet Google de tracking** pour validation par assistante
- **Plans payants** iCloseit / Zoho / Supersales (pas de cap volume)
- **Coaching commun mardi 12 mai à 11h** (1h, dont 30 min Alec) — toutes agences confondues, ~45-50 personnes
- **Contrat de partenariat rédigé côté Entrepreneurs.com** (vs habituellement côté agences)
- **Adresses mail dédiées** pour les sales externes (quasi-obligatoire selon Aziz/Alec)
- **Julien (team leader Entrepreneurs.com) référent côté EC** pour les agences (intervention si besoin sur les coachings)
- **Tous recrutements liés** ne passent **pas** par Aikho (sales recrutés via leurs sales teams partenaires)

### Stratégiques
- Kelly est un test, pas un one-shot — Alec a explicitement ouvert la porte à des collaborations post-Kelly (notamment lancement septembre)
- Performance des 3 agences sur Kelly = critère pour les futurs lancements

## Points à trancher cette semaine

- Make ou Zapier pour les automations ? (recommandation : Make)
- Qui code les automations (interne / freelance / partenaire ?)
- Identifier l'assistante owner du Sheet de validation HubSpot
- **Proportions de routing Short.io** entre les 3 agences (proposition : 25/50/25 selon les capacités)
- Politique moyens de paiement à aligner avec Tip Talent (tension Romain ↔ Aziz à arbitrer avec Julien avant coaching mardi)
- Format technique des ~70 adresses mail (sous-domaine dédié ?)
- Communication interne : qui dans l'équipe Entrepreneurs.com doit savoir qu'il y a un funnel parallèle ?
- Date de finalisation du contrat avec Axel Greiber

## Risques principaux

- **Comportement des sales externes** (saisie incomplète, oubli de passer le deal en gagné) → mitigations dans automations A6/A7 du doc d'architecture
- **🔴 Écart de commission Tip Talent (10%) vs Momentum (13%)** → confidentiel, à ne jamais documenter en commun
- **RGPD / DPA** à signer avec chaque sales team avant ouverture des accès Zoho
- **Délai 10 jours tendu** sans intégrateur Make dédié 2-3 jours pleins
- **Assistante validation HubSpot** = goulot opérationnel critique si non identifiée à J+4
- **Image Kelly** : c'est sa première fois, elle sera très vigilante sur la qualité des sales (point Alec). Validation finale photos + replays sales avant l'event.
- **Disparité qualité entre les 3 agences** (cf. fiche vue d'ensemble)
- **Setup adresses mail (~70)** = sujet IT/admin non trivial à 10 jours du démarrage

## Stakeholders

| Rôle | Personne | Statut |
|---|---|---|
| CEO / sponsor | [[Alec Henry]] | ✅ Engagé, intervention coaching mardi 12 mai 11h30 |
| Head of Sales | [[Aziz Sfaihi]] | ✅ Owner business du dispositif partenaires |
| CMO | [[Cédric De Saint Jean]] | Lien marketing (challenge, VSL, Kelly) |
| Driver opérationnel et tech | [[Boris Arduy]] | ✅ Mandaté par Alec dans les 2 calls |
| Sabrina (Delivery) | [[Sabrina Dahel]] | Validation package Love post-coaching |
| Julien (Team Leader EC) | Julien (Entrepreneurs.com) | Référent côté EC pour les agences (intervention si besoin) |
| Tip Talent — fondateur | Romain Nussmann | ✅ Confirmé, à Bangkok |
| Tip Talent — opérationnel | Julien (CRO) | ✅ Interlocuteur réel sur le quotidien |
| Momentum — fondateur | Lucas Cureau | ✅ Confirmé |
| Momentum — opérationnel | Hélène (CCM) | ✅ Doit contacter Boris dès ce soir |
| Axel Greiber — agence | Axel Greiber | 🟡 À confirmer cette semaine |
| Marketing Kelly | Anne (en lien avec VSL recrutement) | À confirmer comme contact |
| Intégrateur Make | À identifier | 🔴 Critique J+2 |
| Assistante validation HubSpot | À identifier | 🔴 Critique J+4 |

## Prochaines actions clés

### Aujourd'hui — demain (7-8 mai)

- [ ] Hélène contacte Boris (attendu ce soir 7 mai) avec liste de besoins
- [ ] Romain crée le groupe WhatsApp Tip Talent (Romain + Julien + Aziz + Boris)
- [ ] Aziz crée le groupe WhatsApp Momentum (Lucas + Hélène + Aziz + Boris)
- [ ] Aziz envoie l'offre Kelly finalisée aux partenaires (deadline 8 mai)
- [ ] Aziz cale un call avec Axel Greiber pour confirmer participation
- [ ] Aziz partage le numéro de Julien (team leader EC) à Lucas
- [ ] Boris confirme qui code les automations Make
- [ ] Boris identifie l'assistante owner du Sheet
- [ ] Aziz envoie kit ressources (témoignages, contexte Kelly, calls incubateurs)
- [ ] Boris met à jour l'architecture funnel pour intégrer Short.io
- [ ] Boris cadre le setup adresses mail (~70 adresses)
- [ ] **MP Aziz pour discussion explicite Aziz/Julien sur les moyens de paiement** (avant coaching)

### J+1 (jeudi 8 mai)

- [ ] Setup HubSpot : custom properties + stage "External Won — À valider"
- [ ] Vérification accès iCloseit / Zoho / Supersales / DocuSign / Short.io (plans payants)
- [ ] Création du Google Sheet de tracking
- [ ] Récupération photos sales + replays Tip Talent + Momentum pour validation Alec/Aziz
- [ ] Boris envoie one-pager process aux 3 agences (draft)

### Week-end (10-11 mai)

- [ ] Définition finale des proportions de routing Short.io entre agences
- [ ] Tests à blanc du funnel avec routing entre agences
- [ ] Préparation discours coaching Aziz (cadre commun, pas process unique)

### Mardi 12 mai

- [ ] **Coaching commun 3 agences à 11h** (Aziz + Alec, 1h)
- [ ] Présentation Entrepreneurs.com par Aziz (~30 min)
- [ ] Intervention Alec (~30 min) sur conviction et culture
- [ ] Brief sales sur l'offre, la posture, les moyens de paiement

### Avant le 15 mai (départ Marrakech)

- [ ] Intervention possible Alec dans un coaching dédié (13 ou 14)
- [ ] Validation finale Alec/Aziz de la posture des sales
- [ ] Setup tech complet (toutes les automations Make + Short.io construites et testées)
- [ ] Tests à blanc complet du funnel
- [ ] Signature contrats de partenariat (3 agences)
- [ ] Adresses mail créées et distribuées

### Event (17 mai +)

- [ ] Intervention Kelly sur lien non répertorié 1-2h avant le premier live (proposition Alec)
- [ ] Monitoring rapproché les 24-48 premières heures
- [ ] Daily Boris ↔ Julien (Tip Talent) + Hélène (Momentum) + référent Axel
- [ ] Reporting H+24, H+48 partagé Aziz et Alec

### Post-event

- [ ] Debrief structuré avec chaque agence (data, retours, axes d'amélioration)
- [ ] Évaluation pour collaboration future (lancement septembre)

## Liens connexes

- [[People-RH - Process recrutement Aikho v1]] — note : les sales externes ne passent **pas** par ce process, ils sont recrutés via leurs sales teams partenaires
- [[Alec Henry - Garant de la vision]] — le pilier 2 (prédictibilité revenue par triptyque + récurrence) est directement servi par ce projet

## Historique

- 2026-05-07 — Création du hub projet, livraison de l'architecture v1
- 2026-05-07 — Call de cadrage Alec/Aziz/Romain (Tip Talent), GO partenariat Tip Talent confirmé
- 2026-05-07 — Création des fiches partenaires (Tip Talent + vue d'ensemble 3 agences) et archivage du transcript source
- 2026-05-07 — Call de cadrage Alec/Aziz/Lucas/Hélène (Momentum), GO partenariat Momentum confirmé
- 2026-05-07 — Création de la fiche Momentum, mise à jour vue d'ensemble avec comparatif et écart commission documenté confidentiellement, archivage transcript Momentum
- 2026-05-07 — Mise à jour de l'index avec volume confirmé 2500-3000 calls, 40 closers, coaching mardi 11h, Hélène comme contact technique
- 2026-05-08 — Setup Zoho CRM (Profiles, Roles, Data Sharing) + Short.io Splitter 25/50/25 + Google Sheet de tracking. [[Infrastructure - Setup en cours]] créé.
- 2026-05-09 — Build du scenario Make A2 (booking iClosed → Zoho) en pair-programming. 11 modules en prod, owner dynamique, dédup. Cf. [[Scenario A2 - iClosed vers Zoho]].
- 2026-05-09 — Setup iClosed events (3) + ClickFunnels embed + branchement Short.io vers les pages CF définitives (remplaçant les httpbin.org temporaires). UTMs validés end-to-end.
- 2026-05-09 — Renommage `Axel` → `Next Sales` partout (slug iClosed `kelly-nextsales`, page CF `closer-equipe-no-activity-next-sales`, UTM `nextsales`). Axel reste le nom du closer/contact, Next Sales est le nom commercial de son agence.
- 2026-05-10 — 38 closers ajoutés en host iClosed (10 Tip Talent + 21 Momentum + 7 Next Sales), tous configurés en Round Robin sur l'event de leur agence. Émails `prenom.nom@entrepreneurs.com` créés pour chacun. Cf. [[Closers - Liste opérationnelle Kelly]].
- 2026-05-10 — Renommage des roles Zoho `Sales Axel` → `Sales Next Sales` et `Manager Axel` → `Manager Next Sales`. CSV d'import des 38 users Zoho préparé, import à venir.
- 2026-05-10 — Création du catalogue produit Zoho Méthode Boss Energy : 6 variantes (1x à 6x), prix fixe 5 700 € HT. CSV d'import des produits prêt. Cf. [[Produit - Méthode Boss Energy]].
