---
type: decision-log
domaine: SIDE
projet: "[[Partenariat Aikho]]"
date: 2026-06-24
seance: "Jour 1 — après-midi"
statut: convergé-en-séance-à-confirmer-J2
sensitivity: confidential
tags: [aikho, seminaire, decisions, parking, jour1, apres-midi]
---

# Aikho — Jour 1 (après-midi) · Décisions validées & parking

> **Continuité** : poursuit la numérotation de [[Jour 1 — Décisions validées & parking]] (matin = D1→D8, P1→P8). Ci-dessous **D9→D20** (nouvelles décisions PM) + **mise à jour du parking matin** + **nouveau parking PM (P9→P13)**.
> **⚠️ Statut** : convergences de séance, **gel formel renvoyé au Jour 2** (plan d'action / owners). Solidité indiquée par décision.

## ✅ Décisions validées (après-midi)

| # | Décision | Solidité | Résout / lie | Porté surtout par |
|---|---|---|---|---|
| **D9** | **Deux motions GTM distinctes** : (A) **GCC / grands comptes** EN+AR, sales-led, compte par compte (hospitality + adjacents terrain : real estate, construction, pétrole) ; (B) **TPE/PME francophone** via entrepreneurs.com, presque B2C. | 🟢 Forte | affine D3 ; P3 | Tous |
| **D10** | **Pricing figé** : **abonnement annuel** ; unité = **candidats managés/mois** (~200 cand ≈ ~200/mois) ; **3 paliers** ~**2 400** / ~**6 000** / ~**12-15 000** $/an ; add-ons candidats ; paiement **annuel up-front** privilégié. | 🟢 Forte | **résout P2** | Hugues + Alec |
| **D11** | **Pas de pur self-serve** : chaque client passe par un **call Sales ou OBM** ; **rôle OBM acté** ; closing externalisable via **Alchimie** (FR/EN/AR, commission). | 🟢 Forte | — | Alec / Hugues |
| **D12** | **Architecture single-tenant retenue** (1 déploiement/client, spin-up ~15 s via Cloud Code skills) ; **pas de multi-tenant maintenant** ; ne pas maintenir les deux. Customisation = **value stream facturé** (marge ~80 %). | 🟢 Forte | lie P6 | Julien |
| **D13** | **Plateforme agnostique** (modèles souverains, **data residency** client, API OpenAI-compatible) = capacité clé grands comptes/gouv, **débloquée par le single-tenant**. | 🟢 Forte | **résout P7** | Julien |
| **D14** | **Promesse / positionnement figé** : *« AI hiring assessment — Aikho s'adapte à ton process de recrutement et le rend meilleur ; tu apportes les talents, on t'aide à les évaluer et à prendre la meilleure décision. »* | 🟢 Forte | **résout P1** | Alec / Boris |
| **D15** | **Sourcing externe = arrêté / non marketé.** Feature conservée (tap base interne), **sans promesse ni prix affiché**. Endgame = produit « source » à masse critique. | 🟢 Forte | durcit le débat sourcing ; lie P4 | Julien / Alec |
| **D16** | **Anti-churn = aller « hiring-adjacent »** (onboarding, workforce assessment, etc.) + paiement annuel + switching cost (data/historique). À activer si ça fait du sens. | 🟡 Principe | — | Hugues / Julien |
| **D17** | **V2 = socle d'onboarding** des nouveaux clients ; **V1 gelée** (plus de features), cash-cow en attendant ; **migration V1→V2 = projet ultérieur**. | 🟢 Forte | **résout P6** | Julien (+ tous) |
| **D18** | **Vision produit agent-first / plugin Claude (MCP)** ; **UI secondaire** ; Aikho exposable à d'autres agents. | 🟡 Orientation | — | Julien |
| **D19** | **Mode GTM « pirate »** assumé : scraping Apollo (CEO+HR), campagnes A/B email, LP par catégorie, closing visio via Alchimie, paiement Stripe/GoCardless. | 🟢 Forte (intention) | — | Alec / growth |
| **D20** | **Pas de pilote gratuit ouvert** → **test payant = 7 % du base salary sur 1 job** ; + **offre beta newsletter août** (20-50 boîtes, gratuit contre data + feedback). | 🟢 Forte | — | Hugues |

## 🔄 Mise à jour du parking matin

| # matin | Sujet | Nouveau statut (PM) |
|---|---|---|
| **P1** | Phrase de positionnement | ✅ **Résolu** → D14 |
| **P2** | Modèle de pricing | ✅ **Résolu** → D10 |
| **P3** | 3 avatars / use-cases à tester | 🟡 **Partiel** : remplacé par 2 motions (D9) + 3 paliers (D10) ; le *protocole de test* reste à designer |
| **P4** | Marketplace candidat (two-agents / Muzo-Paraform) | 🅿️ **Toujours parqué** (cohérent avec D15 : attendre masse critique entreprises) |
| **P5** | Objectifs 12 mois chiffrés | 🟡 **Ouvert** (renvoyé J2). Cible **intermédiaire posée** : **250 000 candidats au 1er sept.** (vs ~28 000) |
| **P6** | Migration clients V1→V2 | ✅ **Résolu** → D17 (projet ultérieur, « bon problème ») |
| **P7** | Plateforme agnostique gros comptes | ✅ **Résolu** → D13 |
| **P8** | Benchmark Paraform / Muzo | 🅿️ **Non traité PM** — reste à instruire |

## 🅿️ Nouveau parking (après-midi)

| # | Sujet | Pourquoi en parking |
|---|---|---|
| **P9** | **Humanisation de l'interview** (avatar/visuel vs voix simple type voice-note) | Croyance vs croyance, non tranché — « reste une idée » |
| **P10** | **Channel candidat** (téléphone / WhatsApp vs web-only) | WhatsApp cher + API bloquée ; Telegram écarté ; tendance « upload CV → interview » mais non figé |
| **P11** | **Tracking du succès** (forcer le clic « Hire », instrumenter la conversion pour le narratif investisseurs) | Problème identifié, solution non spécifiée |
| **P12** | **Exposition marketing de la customisation** (éviter « trop de features » / effet « gadget Claude ») | Risque de perception, à arbitrer côté marketing |
| **P13** | **Gouvernance de la customisation** (éviter 1000 systèmes bespoke ingérables) | Garde-fou Hugues, process à cadrer |

## 🔗 Liens
- [[Jour 1 — Synthèse (après-midi)]] · [[Jour 1 — Plan d'action & owners (après-midi)]]
- [[Jour 1 — Décisions validées & parking]] (matin) · [[Partenariat Aikho]] · [[Aikho]]
