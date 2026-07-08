---
type: meeting
date: 2026-07-08
date_call: "≈ semaine du 7 juillet 2026 (date exacte à confirmer — appel Alchemy prévu à 16h00 heure de Paris le jour même, 4 recrues Ops attendues l'après-midi)"
participants: ["[[Boris Arduy]]", "Alexandre (lead SDR)", "Raphaël (Raphaël Dalleau)"]
contexte: "ENT — Point hebdomadaire Ops/SDR : fiabilisation du tracking leads Tally → HubSpot → iClosed, propriété des relances SDR, couverture des leads « League Magnet » et inscrits événements/concours, mise en place d'un reporting hebdo et d'un cadre UTM/attribution par SDR."
source: "Export Sembly AI (PDF, archivé via Claude) — speakers renormalisés"
sensitivity: internal
tags: [meeting, ent, ops, sdr, crm, hubspot, iclosed, tally, tracking, utm, attribution, league-magnet, reporting, alchemy, q3-2026]
status: inbox
---

# Point SDR Ops — Boris × Alexandre × Raphaël (≈ 08/07/2026)

> [!note] Normalisations Sembli/transcription : « Alchemy / Alchimie » → **Alkimiy** (structure de Romain/Solveo — audit + delivery SDR Maroc, cf. [[2026-06-30 - Aziz - Fin de collaboration & transition pôle Sales]]). « Alex / Alexandre » = **lead SDR** (à ne pas confondre avec Alexandre Richard, SDR, ni Alexandre/Clover). « JAG » et « Aliknou » = termes/noms non tranchés (artefacts de transcription probables). Date exacte du call à confirmer.

## TL;DR
Le suivi des leads est cassé à plusieurs endroits après la migration **CloudMark de Zoho → HubSpot** : beaucoup de prospects n'ont plus de **lien Tally**, ce qui casse l'attribution SDR et fausse le crédit des deals. Décision structurante de **Boris** : **retirer Tally et centraliser tout l'amont dans iClosed** (un lien iClosed dédié par setter + questions de qualif obligatoires avant réservation), avec un **tracking UTM incluant le nom du SDR** pour un reporting par SDR (appels / bookings / RDV). En parallèle : effectif SDR très réduit (**Achille & Lisa portent l'essentiel**), besoin de renforts/couverture week-end, leads « **League Magnet** » à restreindre à Achille & Lisa, reporting hebdo (leads / closed-won / closed-lost) à standardiser, et un **outil de génération d'UTM + SOP** à livrer. Le CRM est reconnu comme désordonné → refonte, voire nouveau CRM, à envisager. **Alkimiy = auditeur, pas équipe d'exécution.**

---

## 1 — Cadence Ops/Branding & pilotage
- Mise en place de **calls hebdomadaires** pour revoir le pôle Ops, l'avancement des actions, les outils et les process ; objectif : **supprimer les « fuites » de l'architecture legacy** qui dégradent la performance.
- Finalité : identifier les problèmes récurrents, définir des solutions, produire des **plans d'action exploitables** par l'Ops et la direction.
- **Boris** organise ces points, avec relais attendu des leads Ops et **suivi partagé avec Raphaël** pour les sujets à approfondir.
- **Renfort Ops : 4 nouvelles recrues** attendues dans l'après-midi (compensent un départ récent + augmentent la capacité).

## 2 — Liaisons Tally manquantes (post-migration Zoho → HubSpot)
- Après la migration des leads **CloudMark**, beaucoup de prospects **n'ont plus de lien Tally** → impossible d'identifier quel SDR est à l'origine des RDV.
- Conséquence : **erreurs d'attribution** sur les deals conclus, métriques SDR faussées, **contestations sur le crédit** des résultats.
- **Alexandre** fournit des exemples précis ; **Boris + Raphaël** investiguent pour corriger la chaîne de suivi et les règles d'attribution.

## 3 — Remplacer Tally par iClosed (formulaires centralisés + tracking par SDR)
- **Retirer Tally**, faire d'**iClosed le système unique en amont** : chaque setter ouvre un **lien iClosed dédié**, remplit les questions de qualification, réserve le RDV → centralisation données + prise de RDV.
- Suivi via **UTM** (source, medium, campagne) **+ un champ UTM/campagne contenant le nom du SDR** → reporting par SDR (appels, bookings, RDV générés).
- La centralisation supprime les **entrées Tally incomplètes** et garantit la collecte des **questions de qualif obligatoires** avant réservation.
- **Boris** pilote la config technique ; **Ops + managers SDR** font respecter le circuit.

## 4 — Effectif SDR réduit, priorisation & ressources événements live
- Effectif SDR en forte baisse → très petite équipe (**Achille & Lisa** génèrent l'essentiel) → impossible d'appeler **tous les inscrits aux lives** ET de tenir le volume de prospection normal.
- Besoin de **ressources temporaires** ou de personnes **dédiées aux leads quiz** pour ne pas perdre d'élan entre génération du lead et date de l'événement.
- Proposition court terme : **couverture week-end** avec 1 SDR supplémentaire pour absorber les leads du week-end (éviter l'accumulation du lundi).
- **Alexandre** en discute avec **Julien** (réunion ressources) et négocie si possible avec **Lucas (manager SDR)**.

## 5 — Restreindre les leads « League Magnet » à Achille & Lisa
- Demande d'**Alexandre** : seuls **Achille & Lisa** traitent les leads League Magnet → suivi homogène, moins de routages vers **RAF** ou d'autres SDR (perte de réactivité + trous de tracking).
- Aujourd'hui l'assignation peut envoyer ces leads vers RAF ou un **calendrier générique** → traçabilité perdue, propriété SDR floue.
- **Ops + Sales** modifient la logique d'assignation (attribution claire + vitesse de réponse).

## 6 — Reporting hebdo incomplet & visibilité métriques
- **Alexandre** compile encore **manuellement** ; difficile de retrouver les **leads inconnus** et d'attribuer les appels → reporting hebdo peu fiable.
- Demande : **mise à jour hebdo** du nb de leads, **closed-won**, **closed-lost** (santé du funnel).
- Plus simple une fois iClosed + règles d'attribution en place → **Boris + Alexandre** définissent un **format standard**.

## 7 — Leads HubSpot sans fiche contact ni attribution SDR
- Certains leads « Magnet » récemment appelés (ex. **Marie Plissono**, **Elodie Fromo**) apparaissent **sans fiche contact et/ou sans SDR assigné** → appels depuis HubSpot impossibles, tracking cassé.
- Sans attribution SDR renseignée, les **closers ne voient pas le SDR source** → données de perf inexactes.
- **Alexandre** liste les cas concrets → **Boris + Raphaël + admin CRM** corrigent le mapping et les règles d'assignation.

## 8 — Process quiz League Magnet incomplet & circulation des données
- Le process proposé par **Raphaël** pour les leads issus du **quiz League Magnet** n'est **pas encore implémenté** par Alexandre (doit revoir le message + le détail du flux).
- **Raphaël** veut que les SDR aient accès, dans leur vue, à **l'ensemble des données quiz** (problèmes du lead, score, réponses clés) pour personnaliser la relance et préparer les ressources avant l'appel.
- Le flux actuel ne pousse pas de manière fiable les infos **quiz + JAG** vers les vues SDR/sales → **Tech/CRM** doit corriger la synchro.

## 9 — Préparation SDR via données quiz
- **Raphaël** insiste : SDR doivent voir **réponses + scores** avant les appels → adapter le pitch, envoyer les bons supports → plus de bookings/conversion.
- Relance plus ciblée (ressources spécifiques) + meilleur alignement des incentives pour obtenir des RDV de découverte.
- **Managers SDR + admin CRM** rendent la visibilité opérationnelle.

## 10 — Capacité SDR, propriété des relances, canaux tel/SMS/WhatsApp
- Équipe = **3 SDR basés en Afrique** ; **contraintes légales/techniques** empêchent certains messages clients et le stockage externe des données leads.
- Ajouter du **nurturing** à ces SDR **réduirait fortement le volume d'appels** (outbound global).
- **Raphaël** : il faut **un responsable unique des relances** → consolider les activités pré-clôture sous la fonction SDR (relances cohérentes).
- **Alexandre** : besoin d'un **manager follow-up** avec **accès global** pour coordonner les relances entre SDR.
- **Boris** : accueille tout profil SDR supplémentaire (plus de ressources = meilleure visibilité) ; conserve les propositions dans une **base centrale** pour traitement ultérieur.

## 11 — Couverture tel/SMS/WhatsApp pour SDR offshore
- **Boris** propose **Aircall** (appels + flux de validation SMS) pour opérer avec des **numéros non français**.
- **Alexandre** alerte : intégration **Aircall/WhatsApp** + envoi SMS par SDR offshore **peu fiable** → à vérifier (essais précédents ayant échoué).
- Si les SDR envoient du nurturing entre deux appels → volume d'appels en baisse → tâche peut-être mieux portée par le **closer** ou une **ressource follow-up dédiée**.

## 12 — Centralisation HubSpot & détection des pertes de données
- **Boris** : tous les leads entrants arrivent-ils bien dans **la même base HubSpot** ? Propose de comparer **opt-ins par funnel vs enregistrements HubSpot** pour identifier les pertes.
- **Raphaël** dispose des **données de funnels** (peut fournir les volumes de comparaison).
- Souhait Boris : **reporting visuel par funnel** → opt-ins → nb transformé en leads HubSpot → nb arrivé directement aux appels → repérer où les leads sont perdus.
- Vérifier les écarts par funnel (ex. **250 opt-ins vs 230 leads HubSpot → tracer les 20 manquants**).

## 13 — Nommage funnels incohérent & tracking UTM
- **Alexandre** : plusieurs appellations pour un **même funnel** dans HubSpot → requêtes et suivi compliqués.
- **Boris** révise les **conventions UTM** → fournira filtres + approche standardisée pour identifier les funnels de façon fiable.
- Idée : créer un **pipeline HubSpot dédié SDR** pour réduire le bruit.
- **Constat partagé (Raphaël + Boris)** : CRM désordonné → **refonte, voire nouveau CRM**, potentiellement nécessaire pour un tracking fiable.

## 14 — Périmètre Alkimiy & prépa du prochain call
- **Boris** clarifie : **Alkimiy = audit + optimisations proposées**, **pas** équipe d'exécution.
- **Alexandre** espérait des **ressources SDR** via Alkimiy → accepte le rôle d'auditeur mais **maintient le besoin de recrutements locaux**.
- **Raphaël** partage le doc envoyé à Alexandre & « Aliknou » pour aligner les objectifs du call Alkimiy.
- **Alexandre** : call Alkimiy prévu **16h00 (Paris)** pour revoir les améliorations Ops + le système de nurturing.

## 15 — Conversion inscrits concours & tracking temporaire
- **Alexandre** dispose d'un Google Sheet ≈ **100 inscrits au concours** (hors gagnant) → à importer dans HubSpot et **attribuer à Lisa** (a déjà contacté certains).
- Prioriser les appels aux **répondants** + proposer un **audit stratégique** aux qualifiés.
- **Boris** : passage prochain sur iClosed + **tags de tracking par SDR & par événement** (savoir qui a réservé quoi).
- Règle : pour **chaque nouveau funnel/lancement**, mettre à jour les **UTM** et **informer l'Ops** (tracking exact).

## 16 — Outil de génération d'UTM & SOP liens trackés
- **Raphaël** demande une **SOP** pour créer liens trackés + UTM des campagnes.
- **Boris** confirme : livrera une **interface générant automatiquement les UTM** à partir d'un lien collé + **SOP** + filtres au fil du temps.
- Bénéfice : simplifier les futurs lancements de funnels, réduire les erreurs de tracking.

---

## Actions consolidées

| # | Action | Owner | Échéance |
|---|---|---|---|
| 1 | Investiguer les liaisons Tally manquantes post-migration CloudMark + corriger règles d'attribution | **Boris + Raphaël** | Court terme |
| 2 | Fournir des exemples précis de deals mal attribués | Alexandre | Court terme |
| 3 | Configurer **iClosed** en système unique amont (lien dédié/setter, questions qualif, UTM + nom SDR) | **Boris** | Court terme |
| 4 | Faire respecter le circuit iClosed | Ops + managers SDR | Continu |
| 5 | Restreindre l'assignation **League Magnet → Achille & Lisa** (retirer routage RAF/générique) | Ops + Sales | Court terme |
| 6 | Négocier renforts SDR + **couverture week-end** | Alexandre (↔ Julien, Lucas) | Réunion ressources |
| 7 | Définir un **format de reporting hebdo** (leads / closed-won / closed-lost) | **Boris + Alexandre** | Court terme |
| 8 | Corriger fiches contact / attribution SDR manquantes (ex. Plissono, Fromo) | Boris + Raphaël + admin CRM | Court terme |
| 9 | Corriger la synchro **données quiz + JAG → vues SDR/sales** | Tech / CRM | Court terme |
| 10 | Trancher la **propriété des relances** (manager follow-up / accès global) | Boris (arbitrage) | À cadrer |
| 11 | Vérifier fiabilité **Aircall / WhatsApp / SMS offshore** | Boris (+ Alexandre) | À tester |
| 12 | Comparer **opt-ins par funnel vs leads HubSpot** + reporting visuel des pertes | Boris (données : Raphaël) | Court terme |
| 13 | Standardiser **conventions UTM** + filtres + envisager pipeline SDR dédié | **Boris** | En cours |
| 14 | Partager le doc de cadrage du call Alkimiy | Raphaël | Avant call 16h |
| 15 | Importer ~100 inscrits concours dans HubSpot + attribuer à **Lisa** | Alexandre | Court terme |
| 16 | Livrer **interface génération UTM + SOP** liens trackés | **Boris** | Au fil de l'eau |

---

## Points de vigilance
- **Attribution SDR = nerf de la guerre** : tant que Tally/iClosed + UTM par SDR ne sont pas verrouillés, les contestations de crédit et les métriques faussées persistent.
- **Sur-dépendance Achille & Lisa** : deux personnes portent l'essentiel du résultat → risque single-point-of-failure ; les tâches nurturing rognent directement le volume d'appels.
- **Fiabilité Aircall/WhatsApp offshore non prouvée** (essais passés échoués) → ne pas industrialiser sans test.
- **CRM désordonné** : nommage funnels incohérent + fiches manquantes → la refonte/nouveau CRM est un chantier de fond, pas un patch.
- **Alkimiy ≠ exécution** : attente d'Alexandre (ressources SDR) à recadrer → les recrutements locaux restent à sa charge.

## Liens
- [[Boris Arduy]]
- Réunion sœur : [[2026-07-08 - Point Marketing Ops (Boris x Raphaël)]]
- [[2026-07-08 - CRO Cash & Growth (Alec x Boris x Aziz x Cédric x Océane x Fabrice)]]
- [[2026-06-30 - Aziz - Fin de collaboration & transition pôle Sales]] (Alkimiy / SDR Maroc)
- [[2026-07-04 - Romain (Solveo) x Alec x Christele - Pole Coaching Physique Casablanca]] (Alkimiy / Romain)
- Projets : [[Refonte verticale Data-IA-Tech-Ops]] · [[Kelly Launch — infra commerciale & Sales Bis]] · [[🗼 Tour de contrôle - Projets en cours]]
