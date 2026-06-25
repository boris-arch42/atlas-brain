---
type: rapport-consolidé
domaine: ENT
projet: "[[Partenariat Aikho]]"
date: 2026-06-24
seance: "Jour 1 — intégral (07:43 → 15:54)"
participants:
  - "[[Hugues Pringault]] (CEO Aikho — vente/business)"
  - "Julien (co-fondateur Aikho — produit/tech, build V2)"
  - "[[Boris Arduy]] (facilitateur — structure/ops/doc)"
  - "[[Alec Henry]] (co-facilitateur — positionnement/réseau)"
  - "Mentionnés : Jonathan (dev V1/Echo), Antoine, Gaël, Joe, Franck (BD France), Gilles"
source: "Synthèse des 5 enregistrements Sembly du Jour 1 (matin ×3 + après-midi ×2)"
statut: rapport-de-séance
sensitivity: confidential
tags: [aikho, seminaire, rapport, strategie, jour1]
---

# Aikho — Séminaire stratégique · **Rapport Jour 1** (24 juin 2026)

> **Cadre (Alec)** : *« sur ces deux jours, j'agis comme si on était déjà associé »* — focus création de valeur ; le deal capital se traite à part.
> **Objet du séminaire** : passer d'une boîte « build + itération permanente, aucun process, aucun positionnement acté » à des **décisions figées** sur 7 axes : vision · positionnement · focus produit · pricing · géographie · motion GTM · objectifs 12 mois.
> **Lexique** : *Aiko/Echo/Aéco/ICO = Aikho* · **V1 = Echo** (produit actuel) · **V2 / ICO2 = nouvelle plateforme « journeys »**.

---

## 1. Executive summary — la décision en une page

Aikho choisit le **pari go-big asymétrique** (pas la petite cash machine), sur un **cœur unique : l'AI hiring assessment**. La promesse figée : *« tu apportes les talents, on t'aide à les évaluer et à décider — et on s'adapte à ton process pour le rendre meilleur. »*

Le produit bascule sur la **V2 single-tenant** (1 déploiement/client, ~15 s via Cloud Code), qui rend la **customisation profonde cheap** (marge ~80 %) et débloque l'**agnostique / data residency** indispensable aux grands comptes. La **V1 est gelée** (cash-cow), migration plus tard.

Deux motions GTM en parallèle : **(A) GCC / grands comptes** (sales-led, compte par compte, EN+AR) et **(B) TPE-PME francophone** via la channel entrepreneurs.com (presque B2C). Pricing **annuel** sur l'unité « candidats managés » : **~2 400 / 6 000 / 12-15 000 $/an**. Tout passe par un **call Sales/OBM** (pas de pur self-serve), closing externalisable via Alchimie.

Trois renoncements nets : **on arrête de vendre le sourcing** (pas notre métier), **on ne scale pas le candidat avec du paid maintenant** (la base se construit gratuitement via les clients), **on arrête d'ajouter des features** (la complexité tue l'usage). Exécution en **mode pirate** (scraping Apollo, A/B email, closing visio).

**Moat** = équipe + data verticale d'interviews qui améliore l'algo + customisation par client + rétention. **Cible intermédiaire** : 250 000 candidats au 1er sept. (vs 28 000).

---

## 2. Vision & ambition (Bloc 0)

| Acteur | Moteur | Position |
|---|---|---|
| **Julien** | Construire un grand produit / réalisation perso | Cible valo **~milliard** (min ~100 M€ pour ses ~25 %) ; une petite boîte 20 M€/20 % « le fait chier ». Lucide : *« on n'a pas encore cette stratégie »* ; concurrents ont levé 15-30 M€, Aikho est resté bootstrap. |
| **Hugues** | Entreprendre, taper fort et vite | Reconnaît que **le scale / la levée = précisément ce qu'ils ne savent pas exécuter**. Fallback : service RH automatisé par l'IA si ça ne scale pas. |
| **Alec** | — | Pose le binaire : *« une stratégie à 95 % d'échec mais 5 % de valoir un milliard à 18 mois, ça ira »*. Une boîte tech qui ne tape pas fort = un échec. |

→ **D1 — Convergence : pari go-big asymétrique.** Nuance : Hugues garde un fallback service-RH défensif.

---

## 3. Positionnement & promesse (figé)

- **D14 — Promesse** : *« AI hiring assessment — Aikho s'adapte à ton process de recrutement et le rend meilleur ; tu apportes les talents, on t'aide à les évaluer et à prendre la meilleure décision. »*
- Les **4 questions client** auxquelles le pitch doit répondre : on y arrive ? en combien de temps ? combien ça coûte ? quelles ressources ?
- **D8 — Narratif** : vendre **un système / une promesse**, **jamais « des agents »**.
- **Verticalisation = levier de vente** (pas une contrainte) : *« leader hospitality, portail dédié »* → le client sent que l'outil connaît son métier. Réplicable tech/pétrole/immobilier.

---

## 4. Produit — V1, V2, architecture

### 4.1 État (V1 / Echo)
Recrutement IA, **assessment-first** : interview vocale + scoring + screening CV. Traction : **~29 000 users**, **~9 000 interviews**, **~10 clients payants**, majorité **F&B / hôtellerie / GCC / multilingue**. Avantage perçu = l'**interview conversationnelle agréable** (vs concurrents « boring ») ; mais **moat fragile** → le vrai moat = **data verticale + user base**.

### 4.2 V2 (plateforme « journeys »)
- **D7 — Socle = V2** : *kernel* d'abstractions → des **journeys** (DAG de nœuds : sign-up, upload CV, scoring vs mandat, *Voice Conversation*…). Hiring journey ≈ **5 % de la code base** ; from scratch ≈ **6-12 h**.
- **D12 — Single-tenant retenu** : 1 déploiement/client, **spin-up ~15 s** (« create company » → URL dédiée). Customisation profonde **sans l'enfer de config multi-tenant** de la V1. **Pas de multi-tenant maintenant**, ne pas maintenir les deux. Customisation = **value stream facturé** (junior ~50/j produit ~800/j → marge ~80 %).
- **D13 — Agnostique** : modèles souverains, **data residency** client, API OpenAI-compatible → *« sans ça, 50 % du marché bloqué »* (grands comptes/gouv).
- **D18 — Agent-first / plugin Claude (MCP)** : piloter Aikho via Claude, sans UI (voix/texte), tokens du client, capacités adjacentes (« Excel des 10 meilleurs »). **UI secondaire.** Aikho exposable à d'autres agents (HRMS). Slack testé = top.

### 4.3 Scorecard (process V2)
Générée du brief, **itérable avec l'agent**. Dimensions : skills fonctionnels/techniques + background + **checks binaires** (XP, salaire, start date…), **criticalité par check** ; max = **« blocking »** → pilote les **rejets auto** (corrige l'opacité V1). Journey user simplifiée : upload CV → interview → contact. Vue : pipeline / rejetés / qualifiés (Kanban) / shortlist / message / hire-reject. **Pas** de calendrier, JD, ni image/vidéo en base (vitesse 35 s vs 2 min).

### 4.4 UX
*« Pas un problème de produit, un problème de marketing & d'UX. »* Complexité **exposée** → 1-2 h pour mettre une offre en ligne, cible = **5 min** (« Chantal, 50 ans, RH »). Référence : **PipeDrive** (ultra-visuel, 2-3 features, reste en back-end). Surface agentique = *« Ask ICO »*.

---

## 5. GTM — deux motions

| | **Motion A — GCC / grands comptes** | **Motion B — TPE/PME francophone** |
|---|---|---|
| **Cible** | Grands comptes terrain : hospitality + real estate, construction, pétrole | Base entrepreneurs.com, presque B2C |
| **Langues** | EN + AR | FR |
| **Motion** | **Sales-led, compte par compte** (marché ultra-concentré : ~15 acteurs = 80 %) | Marketing + channel ENT, masse |
| **Marketing** | SEO/affiliation peu pertinents | Copy/landing/pricing adaptés à l'avatar |
| **Tickets** | Gros (Dubai Holding, gouv Abu Dhabi) | 2 400-6 000/an |

**D9 — Les deux motions sont actées.** Risque hospitality (≈20 % du marché, reprise incertaine) → diversifier les avatars.

### Timeline motion B (entrepreneurs.com)
- **Juillet-août** : atelier d'ajustement avatar (pricing, null-churn, UX, copy).
- **Août** : test interne clients ENT (masterclass) + **offre beta newsletter** (20-50 boîtes, gratuit contre data+feedback).
- **Septembre** : exposition publique massive — podcasts, **épisode Le Déclic**, gros lancement (30-50 k inscrits), webinaires partenaires.
- **Octobre** : **Dubaï, speaking scène entrepreneurs.com** (~300), démo live, tokens offerts.
- **Puis** : affiliation selon la data.

---

## 6. Pricing (figé — D10)

- **Abonnement annuel**, fixe, **up-front** privilégié.
- **Unité = candidats managés/mois** (~200 cand ≈ ~200/mois ; ~1 $/candidat fully interviewé ; ~30-35 % vont jusqu'à l'interview).

| Palier | Prix/an | Profil |
|---|---|---|
| Entrée | **~2 400 $** | TPE/PME (3-5 recrutements/an) |
| Médian | **~6 000 $** (~500/mois) | volume + besoins particuliers |
| TA | **~12 000-15 000 $** | structuré, gros volume, custom |

- **Add-ons candidats** (~200-500 $) plutôt qu'un saut de palier.
- **Test payant = 7 % du base salary** sur 1 job (fin des pilotes gratuits — D20).
- **Ancrage** vs chasseur de tête / coût d'une erreur de recrutement.

---

## 7. Motion sales & onboarding (D11)

- **Pas de pur self-serve** : chaque client passe par un **call Sales ou OBM**.
- **OBM (Onboarding Manager)** : networking manager + quelques skills Cloud → personnalise l'environnement, sécurise l'adoption, remonte feedback/stats.
- Job du sales/OBM = **vendre l'engagement produit** (« all in ICO »), pas un prix. Annuel privilégié (cash + closing plus fort).
- **Closing externalisable via Alchimie** (FR/EN/AR, payés à la commission → poussent l'annuel).

---

## 8. Sourcing & côté candidat — renoncements stratégiques

- **D15 — Kill du sourcing externe** : *« ce n'est pas notre métier »* ; depuis sa mise en place, *« que des emmerdes »*. Impossible de battre LinkedIn (100× plus engagé) ; crée des attentes intenables (effet scam, churn). **Feature conservée** (tap base interne) mais **non marketée, sans prix**. Prix retirés du site.
- **D4 — B2B-first** : objectif unique = **acquérir des clients**, pas des candidats. La base candidats se construit **gratuitement via les clients**.
- **Côté candidat** non tranché : humanisation (avatar/visuel vs voice-note simple) [P9] ; channel (téléphone > WhatsApp > web ; WhatsApp cher + API bloquée ; Telegram écarté) [P10].
- **Endgame** = à masse critique, produit « source » (futur **« Spyco Source »**) + monétisation de la base. **Thèse** : 1 gros client (1 000 jobs × ~200) → **~150 000 users** captés en un an *tout en étant payé ~150 000*.

---

## 9. Récurrence / anti-churn (D16)

Problème : valeur perçue forte quand on recrute, faible sinon (ex. client à 3 000/mois qui stoppe). Leviers : **paiement annuel** + **switching cost** (couper la carte = perte talent pool + historique) + **modules hiring-adjacent** (onboarding gère 1-3 mois post-recrutement, workforce assessment, culture fit, simulation sales). À activer **si ça fait du sens**.

---

## 10. Moat & narratif investisseurs

- **Moat** = (1) l'équipe (« nous 4 » : produit + marketing) ; (2) growth + rétention ; (3) **data d'interviews** qui améliore l'algo (*« le 1000ᵉ entretien meilleur que le 1ᵉʳ »*) ; (4) **customisation par client** unique.
- **Learning** semi-manuel : un skill Claude remonte les problèmes récurrents → corrigés un par un (les clients **paient ET améliorent l'algo**).
- **Faiblesse** : pas d'incitation à cliquer « Hire » → succès mal mesuré [P11] → besoin d'instrumenter la conversion.
- **Leçon** : produit « parfait » en déc/janv (presque tous les clients signés) puis **trop de features → confusion**. → rester simple, puis **marketing & sales ultra-agressifs**.
- **Champion** : **David Thomas / LPM** — 90-100 % d'usage = shortlist/mini-Kanban ; meilleur ambassadeur.

---

## 11. Marché & clients

- **Modèle des 3 marchés du recrutement** : (1) **bien évaluer** [= cœur Aikho] ; (2) **chasser/trouver la ressource** [l'assessment n'y répond pas] ; (3) **volume/masse** [besoin d'un pool]. → Aikho = #1 ; #2/#3 = endgame base.
- **Clients/signaux** : LPM/David Thomas (~70 k$/an LinkedIn, champion), Dubai Holding (~80 k pers/an, exige agnostique), Paris Society (~1 000 recr./an, propale), Blue Coral, Isabella, Oplax, CXG (FR+GCC), Waterlog Marseille (500 cand/j → ARR ~100 k$, preuve V2/hiring-adjacent), gouv Abu Dhabi (~300 k candidats, pitch J2), GM dentier (Italien, ~500 recr./an terrain multilingue).
- **Benchmarks** : iReview (interview IA générique ~100 M$ ARR), Paraform (US, marketplace headhunting IA, série B ~65 M$ visée, ×40 CA, ultra-niche) / Muzo (équivalent FR) → P8 à instruire.

---

## 12. Décisions consolidées (D1 → D20)

| # | Décision | Solidité |
|---|---|---|
| D1 | Pari **go-big asymétrique** (pas cash machine) | 🟢 (fallback Hugues) |
| D2 | **Rester sur le recrutement** (pas multi-use-case générique) | 🟢 |
| D3 | Focus **recrutement → GCC → terrain** (moat data niche) | 🟡 affiné par D9 |
| D4 | **B2B-first** : acquérir des clients, pas des candidats | 🟢 |
| D5 | Goulot = **marketing/sales + UX**, pas le produit | 🟢 |
| D6 | Chantier prioritaire = **simplification UX** | 🟢 (méthode débattue) |
| D7 | Construire sur la **V2** | 🟢 |
| D8 | Vendre un **système/promesse**, pas « des agents » | 🟡 |
| D9 | **2 motions GTM** : GCC grands comptes / TPE-PME FR | 🟢 |
| D10 | **Pricing annuel** ~2 400 / 6 000 / 12-15 000 $/an | 🟢 |
| D11 | **Pas de self-serve pur** : call Sales/OBM + Alchimie | 🟢 |
| D12 | **Single-tenant** (pas de multi-tenant maintenant) | 🟢 |
| D13 | **Plateforme agnostique** (souverain, data residency) | 🟢 |
| D14 | **Promesse figée** (AI hiring assessment) | 🟢 |
| D15 | **Kill du sourcing** (feature conservée, non marketée) | 🟢 |
| D16 | **Anti-churn = hiring-adjacent** + annuel + switching cost | 🟡 |
| D17 | **V2 socle / V1 gelée** ; migration ultérieure | 🟢 |
| D18 | **Agent-first / plugin Claude (MCP)** ; UI secondaire | 🟡 |
| D19 | **Mode GTM pirate** (Apollo, A/B email, visio) | 🟢 (intention) |
| D20 | **Pas de pilote gratuit** → test payant 7 % + beta août | 🟢 |

---

## 13. Parking consolidé

| # | Sujet | Statut |
|---|---|---|
| P1 Positionnement | ✅ résolu (D14) |
| P2 Pricing | ✅ résolu (D10) |
| P3 3 avatars à tester | 🟡 partiel — protocole de test à designer |
| P4 Marketplace candidat (Muzo/Paraform-bis) | 🅿️ parqué jusqu'à masse critique |
| P5 Objectifs 12 mois | 🟡 ouvert (J2) — cible interm. 250 k candidats au 1er sept. |
| P6 Migration V1→V2 | ✅ résolu (D17) |
| P7 Plateforme agnostique | ✅ résolu (D13) |
| P8 Benchmark Paraform/Muzo | 🅿️ à instruire |
| P9 Humanisation interview | 🅿️ non tranché |
| P10 Channel candidat (tel/WhatsApp/web) | 🅿️ non tranché |
| P11 Tracking du succès (clic « Hire ») | 🅿️ à instrumenter |
| P12 Exposition marketing de la custom | 🅿️ à arbitrer |
| P13 Gouvernance de la customisation | 🅿️ garde-fou à cadrer |

---

## 14. Plan d'action & jalons

**Top 3 immédiats** : (1) plan GTM/sales figé **J2 matin** [Boris+Alec] · (2) **V2 base prête avant le 18 juil** + relais d'absence [Julien] · (3) **machine pirate** lancée cette semaine + nettoyage offre sourcing [Alec/growth + Hugues].

**Frise** :
- **25 juin (J2)** : pitch gouv Abu Dhabi (matin) · plan GTM figé · arbitrages + déploiement (après-midi)
- **~15 juil** : V2 base « definition of done » (avant 18 = congés Julien, puis 3 sem. US)
- **1er août** : launch clients entrepreneurs.com (onboarding direct V2)
- **Août** : test interne + beta newsletter (20-50 boîtes)
- **1er sept.** : cible **250 000 candidats**
- **Septembre** : exposition publique (podcasts, Le Déclic, gros lancement)
- **Octobre** : Dubaï — speaking entrepreneurs.com (~300), démo live

> Détail des actions A1→A24 : [[Jour 1 — Plan d'action & owners]] (matin) + [[Jour 1 — Plan d'action & owners (après-midi)]].

---

## 15. Risques & tensions non résolues
- **Concentration GCC** : marché très concentré → robustesse de la motion A si une verticale tombe (hospitality).
- **Customisation** : risque de dérive (1000 systèmes bespoke) [P13] et de perception marketing « trop de features / gadget Claude » [P12].
- **Tracking** : incapacité actuelle à mesurer les recrutements → faiblesse pour le narratif investisseurs [P11].
- **Dépendance V2 / Julien** : DoD avant le 18 juil puis 3 semaines d'absence → **relais plateforme** non encore nommé.
- **Objectifs 12 mois** non chiffrés (hors cible candidats) [P5].

---

## 🔗 Notes liées
- [[Jour 1 — Synthèse (matinée)]] · [[Jour 1 — Synthèse (après-midi)]]
- [[Jour 1 — Décisions validées & parking]] · [[Jour 1 — Décisions validées & parking (après-midi)]]
- [[Jour 1 — Plan d'action & owners]] · [[Jour 1 — Plan d'action & owners (après-midi)]]
- [[Partenariat Aikho]] · [[Aikho]] · [[🗼 Tour de contrôle - Projets en cours]]
