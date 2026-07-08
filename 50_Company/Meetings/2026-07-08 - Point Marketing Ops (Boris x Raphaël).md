---
type: meeting
date: 2026-07-08
date_call: "≈ semaine du 7 juillet 2026 (date exacte à confirmer — même batch que le Point SDR Ops & le CRO Cash & Growth)"
participants: ["[[Boris Arduy]]", "Raphaël Dalleau", "Alexandre (lead SDR) — mentionné/actionné", "[[Anisse Rbibe]] (Anis) — actionné"]
contexte: "ENT — Point hebdomadaire Marketing Ops : automatisation des funnels de réservation, règles de séquencement email, livraison/tracking de l'e-book (Final Book), écarts de leads funnels ↔ iClose, workflow SDR & notifications temps réel, compte/API IA dédié (Ortea), landing page partenariat Papa In Shape."
source: "Export Sembly AI (PDF, archivé via Claude) — speakers renormalisés"
sensitivity: internal
tags: [meeting, ent, ops, marketing, automatisation, funnel, email, sms, whatsapp, e-book, iclose, tracking, ortea, landing-page, papa-in-shape, q3-2026]
status: inbox
---

# Point Marketing Ops — Boris × Raphaël (≈ 08/07/2026)

> [!note] Normalisations transcription : « Raphael » = **Raphaël Dalleau** (marketing/funnels). « Alex » = **Alexandre**, lead SDR. « Anis » = **[[Anisse Rbibe]]** (CPO Perf Humain/IA). « Ortea », « Final Book / Final DM », « Betonio », « Papa In Shape », « Pierre » = noms outils/produits/partenaires tels que transcrits (à fiabiliser). Date exacte à confirmer.

## TL;DR
Réunion centrée sur l'**automatisation des funnels** et la fiabilisation du tracking leads/données. Décisions clés : (1) **automatiser le funnel de réservation** — séquences email+SMS pour les non-acheteurs, email+appels SDR pour les acheteurs, avec **règle d'arrêt conditionnelle** dès qu'un appel est réservé ; (2) livrer l'e-book **Final Book** via un hébergement permettant de **tracker l'engagement lecteur** (% lu) pour déclencher des relances ; (3) résorber un **écart de 45 %** entre leads funnels et appels/bookings remontés dans **iClose** ; (4) créer un **compte/API IA dédié (Ortea)** pour isoler l'usage de tokens et les coûts ; (5) **dupliquer la landing Betonio** pour le partenariat **Papa In Shape** (livraison cible **vendredi**). Cadre général : rendre le marketing plus orienté résultats via syncs hebdo + KPI mesurables.

---

## 1 — Objectifs & cadence
- Objectif récurrent : marketing **plus efficace et orienté résultats** via **syncs hebdo + KPI mesurables** (organisateur : **Boris**).
- Détecter les **pertes opérationnelles**, proposer des corrections, **itérer Ops ↔ Marketing**.
- Les réunions hebdo suivent l'avancement + les ajustements (améliorations incrémentales).

## 2 — Automatisation du funnel de réservation & séquence Final Book
- **Raphaël** demande des automatisations pour le **funnel de réservation** :
  - **Non-acheteurs** → séquences **email + SMS**.
  - **Acheteurs** → séquences **email + appels SDR**.
- **Boris** : vérifie la demande bot, revoit **landing page + parcours de checkout**, valide **enchaînement + timing**.
- **Raphaël** donne **l'accès en modification** au document pour que Boris implémente/ajuste les flows.

## 3 — Règles de séquencement email & fenêtres d'envoi
- Envois limités à la plage **09:00–18:00**, **espacement ≈ 3 h** entre deux envois (reco Boris → à implémenter).
- Les séquences **pré-appel** ne doivent **plus envoyer de messages** après réservation d'un appel → **logique conditionnelle** stoppant les workflows quand un appel existe (exigence Raphaël, implém. Boris).
- **Boris** inspecte les séquences actuelles (délais, espacements, **règles d'arrêt**).

## 4 — Livraison & tracking de l'e-book (Final Book)
- Produit = **e-book** (pas physique). Question : **lien de téléchargement direct** vs **page hébergée** ?
- **Boris** recommande un **hébergement traçant l'engagement lecteur** (% lu) → relances quand l'utilisateur stagne.
- **Court terme** : démarrer simple (**lien par email**) → **évoluer** vers un tracking lecteur précis pour des séquences email/SMS avancées (accord Raphaël + Boris).

## 5 — Écarts de leads funnels ↔ iClose
- **Écart de 45 %** signalé entre leads enregistrés dans le funnel et appels/bookings remontés dans **iClose** → à analyser (signalé par Raphaël ; investigation **Boris + Alex**).
- **Boris** : construire un **dashboard temporaire** + se synchro avec **Alex** pour décider si les leads sont gérés **directement dans iClose** ou via les **outils de funnel actuels**.
- **Raphaël** demande un **reporting de fin de semaine par funnel** (total leads + appels) pour suivre les écarts → **Boris confirme faisable**.

## 6 — Workflow SDR, routage leads & notifications temps réel
- Risque : des SDR appellent des contacts **ayant déjà réservé** → **logique conditionnelle** anti-doublon (si RDV réservé → arrêt du workflow) (problème/exigence Raphaël ; implém. Boris/Tech).
- **Boris** met en place un **canal/système dédié** pour les **notifications de nouveaux leads** aux SDR (peut donner l'accès à Raphaël).
- Priorité : **équiper les SDR** avec les bons outils + **données temps réel** → réduire le travail manuel type « démerdez-vous » (Boris + Alex).

## 7 — Tokens IA & compte/API dédié (Ortea)
- Le **Final DM** utilise des **tokens Ortea depuis un compte mutualisé** → **risque de coûts** s'ils ne sont pas séparés.
- **Boris** : contacter **Anis** pour utiliser le **compte de l'équipe IA existant** ou créer une **clé API / un compte dédié** → suivre usage tokens + coûts pour entrepreneurs.com.
- **Décision** : **API/compte séparé** pour attribution précise des coûts (action : Raphaël ↔ Anis ; support Boris).

## 8 — Duplication landing page — partenariat Papa In Shape
- **Boris** demande de **dupliquer la landing Betonio** + adapter le texte pour une approche **orientée appel** dans le cadre du partenariat **Papa In Shape** (cibler leurs **clients entrepreneurs**).
- La page reprend **graphiquement l'exemple fourni**, focalisée sur la **génération de réservations d'appels** sur le segment entrepreneurs de Papa In Shape.
- **Boris** envoie un **brief concis + assets de branding** (drive de **Pierre**) pour accélérer la livraison (tâche : duplication/adaptation par **Raphaël**).

## 9 — Échéances, livrables & prochaines étapes
- **Raphaël** veut de la **clarté sur les deadlines** (éviter que le travail s'éternise) ; **Boris** propose **vendredi** comme cible de livraison de la landing (matériaux à recevoir d'ici là).
- **Boris** envoie un **brief clair** + invite Raphaël à l'**appel SDR** pour synchroniser le passage de relais.
- **Livrables immédiats** :
  1. Finaliser **séquences email + connexions de données** des funnels.
  2. Mettre en place le **reporting hebdo leads vs appels**.
  3. Créer la **landing dupliquée** (texte ajusté, Papa In Shape).
  4. Provisionner un **compte Ortea/API dédié** (suivi tokens).

---

## Actions consolidées

| # | Action | Owner | Échéance |
|---|---|---|---|
| 1 | Implémenter automatisations funnel réservation (email+SMS non-acheteurs / email+appels SDR acheteurs) | **Boris** | Court terme |
| 2 | Donner accès en modification au doc de flows | Raphaël | Immédiat |
| 3 | Régler fenêtres d'envoi 09:00–18:00 + espacement ~3h + **stop-on-booking** | **Boris** | Court terme |
| 4 | Inspecter séquences actuelles (délais, espacements, règles d'arrêt) | Boris | Court terme |
| 5 | Choisir hébergement e-book avec **tracking % lu** (après lancement lien simple) | Boris | 2 temps |
| 6 | Investiguer l'**écart 45 %** funnels ↔ iClose + dashboard temporaire | **Boris + Alex** | Court terme |
| 7 | Reporting **fin de semaine par funnel** (leads + appels) | **Boris** | Hebdo |
| 8 | Logique anti-doublon SDR (arrêt workflow si RDV réservé) | Boris / Tech | Court terme |
| 9 | Canal/système **notifications leads temps réel** SDR (+ accès Raphaël) | **Boris** | Court terme |
| 10 | Créer **compte/API Ortea dédié** (suivi tokens/coûts) | Raphaël ↔ **Anis** (support Boris) | Court terme |
| 11 | **Dupliquer landing Betonio** → Papa In Shape (orientée appel) | Raphaël | **Vendredi** |
| 12 | Envoyer **brief + assets branding** (drive Pierre) | **Boris** | Avant livraison |

---

## Points de vigilance
- **Écart 45 % funnels ↔ iClose** = fuite majeure de leads/attribution → à trancher : leads pilotés dans iClose ou via outils funnel (pas les deux à moitié).
- **Stop-on-booking** : sans logique conditionnelle, le pré-appel continue d'arroser des prospects déjà convertis → nuisance + attribution brouillée (sujet commun avec le Point SDR Ops).
- **Coûts tokens IA (Ortea)** : compte mutualisé = dérive de coûts non attribuables → isoler avant scale.
- **Deadline landing vendredi** dépend de la réception des **assets (Pierre)** + du **brief Boris** → jalon à ne pas laisser glisser.

## Liens
- [[Boris Arduy]] · [[Anisse Rbibe]]
- Réunion sœur : [[2026-07-08 - Point SDR Ops (Boris x Alexandre x Raphaël)]]
- [[2026-07-08 - CRO Cash & Growth (Alec x Boris x Aziz x Cédric x Océane x Fabrice)]]
- Projets : [[Refonte verticale Data-IA-Tech-Ops]] · [[🗼 Tour de contrôle - Projets en cours]]
- Idée liée : [[Idée - Pulse - Dashboard de contrôle des automatisations marketing]]
