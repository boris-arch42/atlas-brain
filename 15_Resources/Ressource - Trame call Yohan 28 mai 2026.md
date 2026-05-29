---
type: ressource
sous-type: trame-call
date: 2026-05-28
participants: [Boris Arduy, Yohan]
duree-prevue: 60 min
contexte: Extraction info Archi 2.0 + flux tech — sous couvert prise de poste, réorg NON annoncée, départ Nicolas NON révélé
source: entrepreneurs-com
sensitivity: rh-sensible-confidentiel
tags: [trame-call, yohan, archi-2.0, extraction, dataops, support-infra, depart-nicolas-non-revele]
---

# Trame call — Yohan (Archi 2.0 & flux tech)

> ⚠️ **Cadre de confidentialité strict** : la réorg n'est PAS annoncée. Le départ [[Nicolas Farolfi]] n'est PAS révélé. Ne jamais mentionner : nouveau modèle, 1er juillet, titre Co-COO, départ Nicolas. Cadre de légitimation = **prise de poste + compréhension de la stack**.

## 🎯 Objectifs réels (non dits)

1. Comprendre l'état **réel** de l'Archi 2.0 (vs roadmap théorique)
2. Évaluer si Yohan peut **reprendre seul** l'Archi 2.0 + flux si [[Nicolas Farolfi]] part
3. Cartographier ce que Yohan owne en propre (ETL, hébergement, scripts)
4. Capter les signaux relation Yohan ↔ Nicolas (qui dépend de qui)

## Objectif annoncé à Yohan
*"Je prends le temps de bien comprendre la stack tech depuis mon arrivée — aujourd'hui je veux creuser l'Archi 2.0 et la partie technique des lancements avec toi."*

## Déroulé 1h

### 0-5 min — Ouverture
> *"Salut Yohan, merci pour ton temps. Depuis que je suis arrivé je prends le temps de comprendre comment toute la partie tech tourne. L'Archi 2.0 c'est un gros morceau et je veux bien saisir où on en est, ce qui marche, ce qui reste à faire. N'hésite pas à être franc, je suis là pour aider, pas pour juger."*

### 5-20 min — État réel de l'Archi 2.0
- *"Concrètement, où on en est sur l'Archi 2.0 aujourd'hui ? Qu'est-ce qui est en prod, en test, encore à construire ?"*
- *"Les OKR Q2 (1 lancement VSL en test + 1 Webinar branché) — tenable dans les délais ou il y a du retard ?"*
- *"C'est quoi les plus gros risques techniques restants sur le projet ?"*
- *"Le datamodel couvre déjà 100% des cas d'usage (VSL, Webinar, LeadMagnet) ou il reste des trous ?"*

→ **Signal** : projet sain et avancé, ou chantier en retard dépendant critiquement de Nicolas ?

### 20-35 min — Ce que Yohan owne en propre
- *"Les scripts ETL et l'hébergement (Vercel, Railway, CloudFlare) — c'est toi qui gères tout ça ? Tu es seul dessus ?"*
- *"Le tracking frontend (UTM, webhooks, detail_funnel côté front) — ta zone ou celle de Nicolas ?"*
- *"Les 2-3 trucs sur lesquels tu es le seul à savoir faire, c'est quoi ?"*

→ **Signal** : périmètre Yohan vs Nicolas + bus factor de Yohan lui-même.

### 35-50 min — Répartition Yohan ↔ Nicolas (zone sensible, doigté)
- *"Comment vous vous répartissez le boulot avec Nicolas concrètement ? Qui fait quoi sur les lancements ?"*
- *"Il y a des zones où vous vous marchez dessus, ou des trous entre vous deux ?"*
- *"Sur l'Archi 2.0 — c'est plutôt toi qui portes la partie technique et lui la partie ops, ou c'est mélangé ?"*

→ **Signal critique** : si Nicolas partait, Yohan tiendrait-il l'Archi 2.0 et les flux ? **NE JAMAIS poser frontalement** *"si Nicolas part tu fais quoi ?"* — déduire de la répartition.

### 50-58 min — Ouverture & besoins
- *"De ton côté, qu'est-ce qui te bloque ou te ralentit le plus aujourd'hui ?"*
- *"Si tu avais une baguette magique pour améliorer un truc dans la stack, ce serait quoi ?"*
- *"Il y a des sujets sur lesquels tu aimerais plus de support ou d'arbitrage ?"*

### 58-60 min — Clôture
Reconnaissance + *"On se refait un point quand tu veux. Si tu penses à des trucs après le call, envoie-moi un mot."*

## ⚠️ Pièges à éviter
- Ne pas révéler le départ Nicolas (même par allusion type *"au cas où Nicolas serait moins dispo"*)
- Ne pas révéler réorg / titre / 1er juillet
- Ne pas le faire critiquer Nicolas frontalement (s'il le fait, noter, ne pas valider)
- Si Yohan se demande pourquoi tant de questions → revenir à *"je découvre la stack"*

## ⚡ Signaux à observer

| Signal | Lecture |
|---|---|
| Archi 2.0 plus avancée que prévu, Yohan autonome | 🟢 Départ Nicolas gérable côté Archi |
| Archi 2.0 en retard, Yohan dépend de Nicolas | 🔴 Risque orphelinage majeur — escalader |
| Yohan owne ETL + hébergement seul | 🟠 Nouveau bus factor à documenter |
| Yohan tendu sur la relation Nicolas | 🟡 Capter, ne pas creuser |
| Yohan demande lui-même plus de cadre/support | 🟢 Allié potentiel post-Nicolas |

## Si on demande frontalement "il y a une réorg ?"
> *"Rien de spécial à annoncer à ce stade — je prends juste le temps de bien comprendre la stack depuis mon arrivée pour être utile. Si des choses évoluent, tu seras au courant en temps voulu comme tout le monde."*

## 🔗 Liens
- [[Nicolas Farolfi]] — départ acté (non révélé), transfert flux critique
- [[Thomas Baeumlin]] — pendant data, réceptacle durable
- [[Ressource - Trame call Thomas Baeumlin 29 mai 2026]] — call suivant
- [[Diag - Nouvel Organigramme & Cordon Sanitaire 2026-05-27]] — inventaire DataOps (Archi 2.0 ligne à clarifier)
