---
type: meeting
date: 2026-07-21
date_call: "21/07/2026, 10:31–11:14 (Google Meet) — horodatage confirmé par l'export Sembly « Raphaël X Boris - Marketing Ops »."
participants: ["[[Boris Arduy]]", "Raphaël (Raphaël Dalleau, marketing ops)"]
contexte: "ENT — Point Marketing Ops technique : fiabilisation du tracking des funnels quiz (embeds iClosed + UTM), remontée des données de RDV vers le Hub SDR (comme Océane & Charlotte), correction du double calendrier/embed non traqué sur le funnel « rencontre avec un expert », app UTM/Embed Generator de Boris, débogage d'une campagne Customer.io (trigger cassé) et process d'onboarding des funnels au marketing."
source: "Export Sembly AI (PDF, archivé via Claude) — speakers renormalisés"
sensitivity: internal
tags: [meeting, ent, marketing, ops, funnel, quiz, tracking, utm, embed, iclosed, customer-io, scoreapp, looker, hub-sdr, bourbon, q3-2026]
status: inbox
---

# Marketing Ops — Tracking funnels, embeds & UTM — Raphaël × Boris (21/07/2026)

> [!note] **Normalisations transcription.** « Raph » = **Raphaël Dalleau** (marketing ops). · « iClose » → **iClosed**. · « score-up / Scorab / score app » → **Scoreapp** (outil de quiz). · « Customario / Custom RIO » → **Customer.io**. · « WAP » = WhatsApp (à confirmer). · « Hub SDR / plateforme SDR » = plateforme SBA. · « Transgeek » = prestataire externe (champ dynamique/préfill). · « MetaPay quiz funnel » = nom de campagne UTM. · Beaucoup d'échanges en partage d'écran (débogage live) → reconstitution au contexte.

## TL;DR
Call très technique de fiabilisation du **tracking marketing**. Les funnels de Raphaël **performent fort** (22 calls bookés hier, 7 le matin) mais souffrent de **trous d'attribution**. Cause identifiée en live : sur la result page du quiz, une **logique conditionnelle** affiche **deux calendriers/embeds selon le score** (>50 vs <50), et l'embed **« rencontre avec un expert » (avec aimant) n'avait pas d'UTM** → RDV non traqués. ✅ **Correctif : Boris régénère un embed unique (sans question, avec UTM) que Raphaël réintègre partout**, via la nouvelle **app UTM/Embed Generator** de Boris (colle l'embed + source/canal/campagne → génère embed + lien). Les **RDV remontent dans le Hub SDR** (comme pour **Océane & Charlotte** : leads / contacts / RDV / taux RDV / close / CA par funnel & par source) grâce à la connexion **iClosed**, sans besoin d'UTM pour les lead magnets. Reste : **connecter Scoreapp** au Hub SDR (accès non filé par **Cédric**) et **débugger une campagne Customer.io** dont le **trigger était cassé** (0 mail envoyé sur « précall email ») → une fois réparé, ça **amplifie encore les relances**. Enseignement process : **impliquer l'Ops dès la conception du funnel** (poser les codes HTML/automatisations en amont), pas en bout de chaîne.

---

## 1 — Intégration & tests avant lancement
- Ajout d'un **bout de code HTML masqué** sur une page de Raphaël pour envoyer les données ; **WhatsApp, iClosed, Customer.io connectés**, tags en place, données qui remontent.
- Synchro en cours (équipe de Boris + le gars Customer.io) pour **tests**. Vérifier la **bonne livraison de l'ebook par email** (éviter le « vous avez scam 27 € » côté client — ex. Pierre) avant d'élargir.

## 2 — Trous d'attribution : double calendrier & embed non traqué 🔧
- Funnels performants (**22 calls bookés hier**, 7 le matin) mais **~une centaine de calls sans traçage** (récurrent, cf. SDR Ops).
- Cause : la **result page** a une **logique conditionnelle** → **plusieurs embeds** ; **2 calendriers selon le score** (>50 → un calendar, <50 → un autre). L'embed **« rencontre avec un expert » (avec aimant)** posé au début **n'avait pas d'UTM** → trous.
- ✅ **Correctif** : **reprendre l'embed « sans question » (avec UTM) et le mettre partout**. Boris **régénère un code d'intégration** que Raphaël **réintègre sur toutes les pages** + test en temps réel.

## 3 — Remontée des données dans le Hub SDR
- Boris pousse les données de Raphaël dans le **Hub SDR / plateforme** comme pour **[[Océane De Queiros]] & Charlotte** : par funnel & par source → **leads, contacts, RDV générés, taux de RDV, close, CA**.
- Avantage : avec **iClosed déjà connecté**, dès qu'un lead opt-in via un funnel puis book (par son mail), le RDV est **rattaché au bon lead magnet** — plus besoin d'UTM sur iClosed pour les lead magnets.
- Reste à **connecter le funnel Scoreapp** au Hub SDR → **accès Scoreapp non filé par [[Cédric De Saint Jean]]** (à débloquer). Raphaël **n'a pas accès à la plateforme SDR**.

## 4 — App UTM / Embed Generator (Boris)
- Boris a construit une **app UTM Generator + Embed Generator** : coller l'embed + renseigner **source / canal / campagne** → génère **l'embed et le lien traqués**. À intégrer dans **Works** (via Wassim).
- Fonctionne **uniquement avec des embeds** (prendre l'embed iClosed, pas le lien simple).

## 5 — Débogage campagne Customer.io (trigger cassé)
- Raphaël reçoit l'invitation mais **pas le mail Customer.io** du quiz final → la campagne **« précall email » a 0 mail à envoyer** → **trigger cassé** (pas un problème de connexion).
- Il n'avait que **2 campagnes** (s'ils bookent / s'ils ne bookent pas). Une fois le trigger réparé → **amplifie la capacité de relance** (perfs déjà bonnes « sans que rien ne parte »).
- ⚠️ **Prefill puissant** (préfill des champs) — Boris a hâte de le tester sur le **lancement Bourbon** (partie CRM iClosed).

## 6 — Process : onboarder les funnels dès la conception
- Constat : on est arrivé **en bout de chaîne** sur la partie code/HTML alors qu'il faudrait être là **dès le début**.
- ✅ **Nouveau process** : dès que Raphaël a la **structure/logique d'un funnel**, faire un **point avec l'Ops** pour poser en amont les codes HTML / automatisations / tracking (éviter le ping-pong).
- **DMA** : Raphaël ne collecte pas de lead direct (que du booking call), calendrier dédié « sans question DMHATS final ».

---

## Actions consolidées

| # | Action | Owner | Échéance |
|---|---|---|---|
| 1 | **Régénérer l'embed unique** (sans question + UTM) et le fournir à Raphaël | **[[Boris Arduy]]** | Immédiat |
| 2 | **Réintégrer l'embed** sur toutes les pages du funnel + test temps réel | Raphaël | Immédiat |
| 3 | **Connecter Scoreapp** au Hub SDR → obtenir l'accès de **Cédric** | Boris ↔ [[Cédric De Saint Jean]] | Court terme |
| 4 | **Débugger la campagne Customer.io** (trigger « précall email ») | Boris (+ Raphaël) | Court terme |
| 5 | Intégrer l'**app UTM/Embed Generator** dans Works | Boris (+ [[Wassim]]) | Court terme |
| 6 | Vérifier le **mapping data** (Looker) avec Thomas / Nicolas | Boris | Court terme |
| 7 | Mettre en place le **process « point Ops dès la structure du funnel »** | Boris + Raphaël | Prochain funnel |
| 8 | Donner à Raphaël un **accès à la plateforme SDR** | Boris | Court terme |

## Décisions clés
- **Un embed unique traqué (sans question + UTM) partout** → fin des trous d'attribution du double calendrier.
- **Remontée des funnels de Raphaël dans le Hub SDR** (par funnel & source), via iClosed.
- **Impliquer l'Ops dès la conception du funnel** (codes/automatisations en amont).

## Points de vigilance
- **Trous de traçage récurrents** (~100 calls) : à solder avant le pic **Bourbon** (cf. SDR Ops).
- **Dépendances d'accès** : Scoreapp (Cédric), plateforme SDR (Raphaël) → bloquants pour finir le tracking.
- **Campagnes Customer.io à triggers** : vérifier que chaque campagne **part réellement** (0 mail = trigger cassé, pas « perf naturelle »).

## Liens
- [[Boris Arduy]] · [[Cédric De Saint Jean]] · [[Océane De Queiros]] · [[Thomas Baeumlin]] · [[Nicolas Farolfi]] · [[Hubert Smolen]] · [[Wassim]]
- Réunions sœurs : [[2026-07-08 - Point Marketing Ops (Boris x Raphaël)]] · [[2026-07-21 - SDR Ops - Plateforme SBA, liens iClosed uniques & sortie HubSpot-Slack (Boris x Alexandre)]] · [[2026-07-21 - Océane x Boris - Ops Marketing, NAS Shade & onboarding]] · [[2026-07-21 - Thomas x Boris - Data Ops (passation)]]
- Projets : [[Kelly Launch — infra commerciale & Sales Bis]] · [[Refonte verticale Data-IA-Tech-Ops]] · [[🗼 Tour de contrôle - Projets en cours]]
