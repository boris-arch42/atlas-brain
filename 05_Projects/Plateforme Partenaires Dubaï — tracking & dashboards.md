---
type: project
domaine: ENT
statut: actif
sante: 🟠
owner: "[[Boris Arduy]]"
prochaine: "Débloquer les landing pages partenaires (Raphaël saturé ; landing Odoo → Fabrice) + faire former les équipes aux embeds (Quentin)"
echeance: 
revue: 2026-07-13
execution: "Cloud Code + Next.js/Supabase (dup launch.entrepreneurs.com) + HubSpot + Looker Studio + ClickFunnels (landings)"
sensitivity: confidential
tags: [projet, ent, dubai, partenaires, apporteurs-affaires, plateforme, dashboard, hubspot]
---

# Plateforme Partenaires Dubaï — tracking & dashboards

> Industrialiser le suivi des **partenaires apporteurs d'affaires** de [[Roman Tebenikhin Bonamy]] (Dubaï). Bêta **démontrable au ven 26/06** (after partenaires 15h30–19h). **Front nickel / back perfectible** assumé. Origine : call Roman×Boris du 19/06, sujet remonté par Océane. ⚠️ Build **en solo Cloud Code, infra séparée** pour ne pas heurter le **freeze lancement (22/06) / live 23–25/06**.

## 🎯 Scope cible (architecture)
- **Dashboard global (vue Roman)** : KPI (nb partenaires, total rapporté/partenaire avec drill-down, leads/semaine) + **export facile**.
- **Sous-dashboards par partenaire** : accès limité, **data strictement scopée**, MAJ quasi temps réel (lead *closé* visible immédiatement, encaissé plus tard).
- **Landing dédiée par partenaire** (template ClickFunnels perso-able : photo partenaire + Alec + descriptif ENT, branding tenu par ENT) avec **lien de booking call**.
- **Booking → HubSpot** : pipe **dédié « Apporteurs d'affaires Dubaï »**, leads attribués à Roman → **Looker Studio**.

## ⚠️ Décisions / flags ouverts
- **Hub CRM à trancher avant build** : HubSpot vs CRM custom Supabase existant (Resource Hub / Launch Control) → éviter un 4e silo (Zoho / iClosed / Supabase / HubSpot).
- **Privacy** : scoping strict par partenaire (RLS Supabase / vues HubSpot).
- **Contention freeze** : zéro pull d'équipe tech pendant 22–25/06.

## 🗓️ Plan J-7 → J (19 → 26/06)
- [ ] **Ven 19 (J-7)** — Scope lock · spin up base Next.js+Supabase (dup [[launch.entrepreneurs.com]]) · data model (partenaires/leads/statuts/montants) · wireframe landing · ask Roman (liste 11 + photos + vidéo) · redirige goodies → Fabrice · lance check OneFlow/spam
- [ ] **Sam–dim 20–21** — Build solo : dashboard global + détail partenaire · schéma Supabase + auth accès limité · pipe HubSpot dédié + lien booking iClosed routé Roman · **trancher hub CRM**
- [ ] **Lun 22 (J-4, FREEZE)** — Ne pas toucher l'infra lancement · finaliser template landing (15 min input marketing) · câbler booking → HubSpot → Looker · sous-dashboard partenaire (vue filtrée)
- [ ] **Mar–jeu 23–25 (live)** — Priorité = monitoring lancement · perso landings (photos) · génération des accès partenaires · **test end-to-end** (lead : landing → booking → HubSpot → pipe Roman → dashboard → vue partenaire) · mail d'accès + QR code
- [ ] **Ven 26 (J, 15h30–19h)** — Bêta live · annonce micro + QR « comme à l'école » · drop mail d'accès pendant l'event · démo KPI · onboarding partenaires · collecte feedback v1.1

## 📥 Inputs à débloquer
- [ ] **Roman** : liste 11 signés + coordonnées + photos/logos · lien dernière vidéo · préf nom du pipe
- [ ] **Marketing (Cédric/Océane)** : assets + copy landing + photo Alec + ligne manifesto (ask 15 min, charge lancement respectée)
- [ ] **Fabrice** : PDF contrat apporteur d'affaires + goodies partenaires

## 📆 Point 10/07/2026 (hebdo Alec)
- Plateforme en forme mais **métriques nulles** : CRM + lancement du tracking encore en cours. Chaque partenaire reçoit un **lien de suivi unique** relié au CRM (attribution).
- **Goulot = landing pages** : Raphaël saturé ; landing du partenariat **Odoo transférée à [[Fabrice Jaeger]]** ; duplications type « Bet on You » / « Mindshake » + corrections manuelles par page.
- **[[Quentin]] forme les équipes aux embeds** (autonomie plateforme).
- ✅ Rappel infra : **webhook iClosed live + testé E2E le 12/07** (UTM `utm_term`, idempotence `iclosed_call_id`, fast-ack).
- ⚠️ La **migration CRM → iClosed validée le 10/07** (1:1) rebattra le hub CRM de la plateforme (HubSpot moins central) — à séquencer sans casser le tracking.

## 🔗 Liens
- [[2026-07-10 - Point hebdo 1-1 (Boris x Alec)]]
- [[2026-06-19 - Roman x Boris - Tracking partenaires Dubaï & plateforme]]
- [[Roman Tebenikhin Bonamy]] · [[Fanny Lesprit]]
- [[Kelly Launch — infra commerciale & Sales Bis]]
- [[🗼 Tour de contrôle - Projets en cours]]
