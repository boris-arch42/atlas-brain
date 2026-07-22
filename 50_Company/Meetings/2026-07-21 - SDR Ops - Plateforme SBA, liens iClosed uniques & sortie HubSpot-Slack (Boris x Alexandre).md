---
type: meeting
date: 2026-07-21
date_call: "21/07/2026, 11:02–11:32 (Google Meet) — horodatage confirmé par l'export Sembly « Alexandre X Boris - SDR Ops »."
participants: ["[[Boris Arduy]]", "Alexandre (Alexandre Gauthier, lead SDR)"]
contexte: "ENT — Point hebdo Ops/SDR : bascule des SDR de HubSpot + Slack vers la plateforme SBA (« fil du pôle »), fiabilisation du tracking (transactions iClosed manquantes sur ~100 RDV pris via liens UTM), décision de liens iClosed uniques par SDR, formation SDR 2 mois (16 modules) et son hébergement (School vs Wiki Works), intégration d'un nouveau SDR (Romane, Evergreen/Dubaï), reconnaissance/rémunération d'Alexandre, réactivation du power dialer Minari, et besoin de sourcing SDR avant le Challenge Bourbon."
source: "Export Sembly AI (PDF, archivé via Claude) — speakers renormalisés"
sensitivity: confidential
tags: [meeting, ent, ops, sdr, plateforme-sba, sales-bis, iclosed, hubspot, slack, utm, attribution, tracking, formation-sdr, minari, power-dialer, recrutement, bourbon, remuneration, q3-2026]
status: inbox
---

# SDR Ops — Plateforme SBA, liens iClosed uniques & sortie HubSpot/Slack — Boris × Alexandre (21/07/2026)

> [!warning] **Sensibilité.** Contient un ressenti de rémunération nominatif (Alexandre : fix 1 200 €, comparaison aux team leaders) et un impayé fournisseur (Minari). À ne pas relayer.

> [!note] **Normalisations transcription.** « SBA » = **plateforme Sales Bis** (« fil du pôle » où tombent les leads, cf. [[Kelly Launch — infra commerciale & Sales Bis]]). · « Elclose / iClose / en très close » → **iClosed**. · « Alkimi / Alchimie » → **Alkimiy**. · « Roman / Romane » = **Romane** (nouveau SDR, Dubaï). · « Raph » = **Raphaël** (marketing ops). · « Anis » → **[[Anisse Rbibe]]** (School / Wiki Works). · « Minari / Powerjaller » = **Minari** (power dialer, à confirmer). · « School » = LMS interne ; « Works / Work » = intranet/wiki. · « Alex » = **Alexandre Gauthier**, lead SDR (à ne pas confondre avec Alexandre Richard, SDR).

## TL;DR
Point de bascule opérationnelle des SDR : Boris a démontré la **plateforme SBA** (le « fil du pôle » où tombent tous les leads, avec source/lead magnet/contact, **cloisonnement par SDR** — chacun ne voit que ses leads —, dispositions nouveau→à rappeler→contacté→qualifié→RDV booké→perdu, notes & historique, mise en RDV booké automatique dès qu'un lien est utilisé). Objectif : **détacher les SDR de HubSpot et de Slack** et tout piloter depuis la plateforme. Blocage identifié : les RDV pris via **liens UTM ne créent pas de transaction dans iClosed** pour les sales → **~100 appels récents non tracés** (remonté par Léa). ✅ **Décision : remplacer la forêt de ~140 liens UTM par un lien iClosed unique par SDR** (Boris les crée le 22/07, mise en place le lendemain), la segmentation se faisant côté plateforme ; **next step** = afficher le step d'avancement du lead (R1, R2…) sur la plateforme, en synchro avec le CRM iClosed. En parallèle : **formation SDR de 2 mois** finalisée par Alexandre (**16 modules d'1 h**, format interactif storytelling/théorie/roleplay/mise en application/auto-éval) → à héberger sur **School** ou le **Wiki Works** (arbitrage avec Anisse) ; intégration d'un **nouveau SDR, Romane** (Evergreen only, école à Dubaï, pas de challenges) ; **Minari** (power dialer) à re-tester sur 2 profils (Lisa & Raph) pendant les challenges → d'abord régler l'**impayé géré par Jordan** (compte coupé) via forward du mail ; **besoin de sourcing SDR** avant Bourbon (Alkimiy est-il censé en fournir ? → Boris vérifie). Alexandre soulève un **sujet de reconnaissance/rémunération** (se sent solo vs team leaders augmentés) → Boris s'en saisit.

---

## 1 — Plateforme SBA : le « fil du pôle » et la sortie de HubSpot/Slack
- Tous les leads tombent dans le **fil du pôle** avec leurs infos (source, lead magnet d'entrée, téléphone, mail, assignation).
- **Cloisonnement / sécurité** : chaque SDR ne voit **que ses propres leads** (Lisa voit Lisa, Achille voit Achille) → moins de données exposées ; Boris gère l'**allocation** par lead magnet.
- **Dispositions** gérées directement par le SDR : nouveau · à rappeler · contacté · qualifié · no-show · RDV booké · perdu ; + **notes & historique** par lead.
- Canaux d'action (appel / WhatsApp / e-mail / SMS) horodatés automatiquement dans l'historique ; dès qu'un SDR utilise **son lien** et que le client book, le lead passe **automatiquement en « RDV booké »** et sort du fil (mais reste consultable).
- **Cible** : sortir les SDR de **HubSpot** et de **Slack** pour tout piloter depuis la plateforme → moins de friction (aujourd'hui ils jonglent entre 3-4 outils). Alexandre veut fermer les canaux Slack de leads une fois la bascule faite (Raphaël peut garder le sien).

## 2 — Tracking cassé : transactions iClosed manquantes (~100 RDV)
- Les RDV pris via **liens UTM ne créent pas de transaction iClosed** côté sales → **~100 appels récents sans traçage** (remonté par Léa ; découvert avec une semaine de retard).
- Impact : perte de visibilité data juste avant le pic de volume du **Challenge Bourbon**.
- Correctif en cours : Boris finalise l'**automatisation iClosed** ; en attendant, création des transactions **à la main** pour les cas signalés (au moins quand ça passe en R2/R3/engagé).

## 3 — ✅ Décision : un lien iClosed unique par SDR (fin des 140 UTM)
- Plutôt que **~140 liens UTM** (un par funnel → source d'erreurs humaines côté SDR), Boris crée **un lien iClosed dédié par SDR**.
- La **segmentation** (d'où vient le lead) se fait **côté plateforme** via l'e-mail du prospect, plus besoin d'UTM par funnel.
- **Timing** : Boris prépare les liens **le 22/07** pour mise en place le lendemain, avant la montée de volume.

## 4 — Next step : steps d'avancement (R1/R2) sur la plateforme + CRM iClosed
- Prochaine évolution du volet leads : afficher **où en est le lead dans le funnel** (R1, R2, engagé…), comme on met déjà à jour « nouveau » / « RDV booké ».
- Bénéfice : les SDR récupèrent la visibilité qu'ils avaient sur HubSpot (savoir ce que devient un lead transmis, les sales ne faisant « zéro retour »).
- Livré en même temps que la mise en place du **CRM sur iClosed** → statut en temps réel une fois tout le monde basculé.

## 5 — Formation SDR : 16 modules, où l'héberger ?
- Alexandre a bouclé une **formation SDR sur 2 mois** : **16 modules d'1 h** (2 sessions/semaine), format interactif — mini-storytelling, théorie, exercices, **roleplay**, mise en application (envoi d'au moins un call de preuve), auto-évaluation.
- Question d'hébergement : sur **School** (onboarding) ou directement sur le **Wiki Works** → **arbitrage à demander à [[Anisse Rbibe]]** (peu de process SDR documentés aujourd'hui → forte valeur).

## 6 — Nouveau SDR : Romane (Evergreen / Dubaï)
- **Romane** intégrée comme SDR supplémentaire, **Evergreen uniquement** (école à Dubaï → pas de challenges), déjà dans la formation (a rattrapé le replay du vendredi).
- Connaît déjà un peu le business → montée en compétence via la formation.
- Boris vérifie l'**allocation** : 5 SDR bien présents côté plateforme, à activer + régler les % de répartition.

## 7 — Minari (power dialer) : re-test après impayé
- Alexandre veut **re-tester Minari** d'abord sur **2 profils (Lisa & Raph)** pendant les challenges (fort volume de leads), pour mesurer volume **et** qualité avant de le déployer à toute l'équipe — vigilance : l'outil ne doit pas faire **baisser le nombre d'appels** (il l'avait coupé pour ça à 6 SDR).
- Préalable : un **impayé** chez Minari (compte coupé), **géré par [[Jordan Leroux]]** → Alexandre **forwarde le mail à Jordan** pour connaître la situation avant de réactiver.

## 8 — Sourcing SDR avant Bourbon
- Besoin de renforts SDR (funnels multiples + celui de Raph + challenges) hors période creuse.
- Question ouverte : **Alkimiy** est-il censé fournir du **sourcing SDR** ? → **Boris fait le point avec eux** (normalement oui). Alexandre peut aussi activer son **réseau perso**.
- 🔗 Cohérent avec le recadrage du 08/07 : **Alkimiy = audit/optimisation, pas équipe d'exécution** ; les recrutements locaux restent à cadrer.

## 9 — Reconnaissance & rémunération d'Alexandre ⚠️
- Alexandre soulève, sans « quémander », un besoin de **justification** de son investissement : il se vit **solo** (formation, ops, structuration) alors que les **team leaders ont été augmentés** ; il évoque un **fixe de 1 200 €** + récup.
- **Boris s'en saisit** : « tu fais bien de me le dire », il va **regarder et réfléchir** au sujet.

---

## Actions consolidées

| # | Action | Owner | Échéance |
|---|---|---|---|
| 1 | Créer les **liens iClosed uniques par SDR** (remplacent les UTM) | **[[Boris Arduy]]** | **22/07 (mise en place J+1)** |
| 2 | Finaliser l'**automatisation iClosed** (transactions manquantes) + créer à la main les cas signalés | **[[Boris Arduy]]** | Immédiat |
| 3 | Ajouter les **steps d'avancement du lead (R1/R2…)** sur la plateforme, en synchro CRM iClosed | Boris | Court terme |
| 4 | Arbitrer l'**hébergement de la formation SDR** (School vs Wiki Works) | Boris ↔ [[Anisse Rbibe]] | Court terme |
| 5 | **Forwarder le mail Minari** à Jordan (situation de l'impayé) avant réactivation | Alexandre → [[Jordan Leroux]] | Court terme |
| 6 | **Vérifier avec Alkimiy** le sourcing SDR possible | **[[Boris Arduy]]** | Court terme |
| 7 | Activer les 5 SDR côté plateforme + régler les **% de répartition** | Boris / Alexandre | Court terme |
| 8 | Sortir **progressivement** les SDR de HubSpot & Slack une fois les liens en place | Alexandre (feu vert Boris) | Au fil de la bascule |
| 9 | **Réfléchir à la reconnaissance/rémunération** d'Alexandre | **[[Boris Arduy]]** | À traiter |

## Décisions clés
- **Un lien iClosed unique par SDR** remplace les ~140 liens UTM ; segmentation côté plateforme.
- **Bascule cible : pilotage 100 % plateforme SBA**, sortie de HubSpot et Slack — mais **progressive**, on assume une semaine « floue » (déperdition de traçage) jusqu'à Bourbon.
- **Formation SDR (16 modules) validée** — reste l'hébergement.
- **Minari re-testé sur 2 profils seulement** (Lisa & Raph), après régularisation de l'impayé.

## Points de vigilance
- **Trou de traçage (~100 RDV)** : tant que l'automatisation iClosed n'est pas finalisée, les métriques SDR restent faussées — critique juste avant Bourbon.
- **Conduite du changement** : les SDR jonglent déjà entre Slack / HubSpot / 500k / Quiz → ajouter la plateforme crée de la friction court terme ; séquencer et communiquer « une fois tout basculé, c'est beaucoup plus simple ».
- **Single-point-of-failure** : le volume repose surtout sur Achille & Lisa (cf. 08/07).
- **Minari** : ne pas re-déployer largement sans preuve que le **volume d'appels double** (risque que l'outil serve à en faire moins).
- **Reconnaissance Alexandre** : sujet RH à ne pas laisser « traîner » (risque de démobilisation d'un profil très investi).

## Liens
- [[Boris Arduy]] · [[Anisse Rbibe]] · [[Jordan Leroux]] · [[Océane De Queiros]] (lead magnet Checklist) · [[Aziz Sfaihi]] · [[Alec Henry]]
- Réunions sœurs : [[2026-07-08 - Point SDR Ops (Boris x Alexandre x Raphaël)]] · [[2026-07-18 - Onboarding Alkimiy Campagne Bourbon - Stack, Parité & Passation (Boris x Théodoric x Aziz x Romain)]] · [[2026-07-10 - Point hebdo 1-1 (Boris x Alec)]]
- SOP / process : [[Sales - SOP Pipeline contrats clients Sales Bis (Lancement Kelly)]]
- Projets : [[Kelly Launch — infra commerciale & Sales Bis]] · [[Refonte verticale Data-IA-Tech-Ops]] · [[🗼 Tour de contrôle - Projets en cours]]
