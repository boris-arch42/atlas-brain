---
type: ressource
sous-type: trame-call
date: 2026-05-29
participants: [Boris Arduy, Thomas Baeumlin]
duree-prevue: 60 min
contexte: Sécurisation allié + cadrage COMEX + préparation transfert Nicolas→Thomas — réorg NON annoncée, départ Nicolas NON révélé
source: entrepreneurs-com
sensitivity: rh-sensible-confidentiel
tags: [trame-call, thomas-baeumlin, comex, dataops, allie, transfert-nicolas, support-infra]
---

# Trame call — Thomas Baeumlin (data, COMEX, transfert)

> ⚠️ **Confidentialité** : plus de transparence possible qu'avec Yohan, SAUF sur la réorg et le départ [[Nicolas Farolfi]] (les deux restent non révélés). Cadre = prise de poste + COMEX + utilité concrète.
>
> 🟢 **Posture** : sécuriser un allié, PAS extraire à la dérobée. Thomas est un pilier technique à valoriser. Cf. [[Thomas Baeumlin]] + [[Ressource - Cartographie Data Thomas Baeumlin 28 mai 2026]].

## 🎯 Objectifs réels

1. Construire la relation (allié à sécuriser)
2. Cadrer le COMEX (les bons KPIs pour la direction)
3. Préparer le transfert [[Nicolas Farolfi]] → Thomas (sous angle dashboards, PAS départ)
4. Comprendre sa charge (8-9/10) et où le décharger

## Objectif annoncé
*"Échanger sur la data, le COMEX, et voir comment je peux t'être utile."*

## Déroulé 1h

### 0-8 min — Ouverture + reconnaissance
Reconnaissance ultra-spécifique : Git, CI/CD, 150+ tests, cas attaque bots Tapie. Puis :
> *"Depuis que je suis arrivé je structure ma compréhension de toute la partie data. Tes docs m'ont énormément aidé. Aujourd'hui je veux qu'on parle COMEX, de comment je peux t'aider à cadrer, et de ta charge."*

### 8-25 min — Le COMEX (cœur du call)
- *"Raconte-moi ta vision du COMEX — qu'est-ce que tu veux y mettre, où tu en es ?"*
- *"Sur les KPIs, comment tu as priorisé ? Qu'est-ce qui est déjà branché vs à venir ?"*
- Apport de valeur : *"Côté direction, ce qui compte vraiment c'est un nombre limité de signaux fiables — 8 à 12 KPIs max qui permettent de décider sans appeler 10 personnes. On peut regarder ensemble lesquels sont vraiment décisifs ?"*
- *"C'est quoi le blocage principal pour livrer le COMEX dans les temps ?"*

→ Tu apportes le besoin direction + cadre, lui construit.

### 25-40 min — Transfert Nicolas (angle dashboards)
- *"Tu notes dans ton doc que tu perds du temps à reconstituer la logique d'orchestration des campagnes. Pour les dashboards Customer Journey et COMEX qui ont besoin de cette vue end-to-end, ça vaut le coup qu'on capture ça proprement, non ?"*
- *"Si on organisait 2-3 sessions avec Nicolas pour qu'il t'explique l'orchestration amont (detail_funnel frontend, conventions, cas edge), captées en Loom — ça te ferait gagner combien de temps ?"*
- *"Qu'est-ce que tu aurais besoin de comprendre en priorité de son côté ?"*

→ Valider l'appétence + définir le contenu. **Enchaîner côté Nicolas dès que Thomas dit oui** (fenêtre avant notification départ).

### 40-52 min — La charge
- *"Tu t'es mis à 8-9/10. Où part le temps de bugs/urgences (25%) ? Récurrent ou ponctuel ?"*
- *"Qu'est-ce qui te déchargerait vraiment — priorisation différente, automatisation, un renfort ?"*
- *"Sur la validation des dashboards par les owners département (Cédric, Aziz), tu disais que les délais te ralentissent — c'est un sujet aujourd'hui ?"*

→ **Signal** : chaîne validation dashboards (se grippe avec départ [[Cédric De Saint Jean]] + triangulation [[Aziz Sfaihi]]). Besoin réel de renfort.

### 52-60 min — Complémentarité & clôture
- *"Mon rôle c'est de te donner les moyens de bien bosser et de faire le lien avec la direction. Tu restes maître de ta réalisation technique. Ce qui t'aiderait le plus de ma part, ce serait quoi ?"*
- Caler un rituel léger + reconnaissance finale.

## ⚡ Signaux à observer

| Signal | Lecture |
|---|---|
| Thomas enthousiaste sur le COMEX cadré ensemble | 🟢 Allié engagé |
| Thomas réticent / défensif sur "sa" data | 🟠 Crainte dépossession — rassurer plus |
| Thomas demande du renfort explicitement | 🟢 Besoin réel à porter (budget Alec/Fabrice) |
| Thomas tendu sur validation Cédric/Aziz | 🟡 Confirme risque chaîne validation |
| Thomas pose des questions sur ton rôle exact | 🟠 Esquiver sur "coordination infra", pas de détail réorg |

## ⚠️ Vigilance
- **Ne PAS révéler** réorg / titre / 1er juillet / départ Nicolas
- **Ne PAS survendre** le renfort offshore (engagement non validé budget Alec/Fabrice)
- **Ne PAS** mettre les mains dans son DBT — il reste maître de la réalisation technique

## Si on demande frontalement "il y a une réorg ?"
> *"Rien de spécial à annoncer à ce stade — je prends juste le temps de bien comprendre la stack depuis mon arrivée pour être utile. Si des choses évoluent, tu seras au courant en temps voulu comme tout le monde."*

## 🔗 Liens
- [[Thomas Baeumlin]] — fiche stakeholder (pilier à valoriser)
- [[Ressource - Cartographie Data Thomas Baeumlin 28 mai 2026]] — ses 2 docs
- [[Nicolas Farolfi]] — transfert flux amont → Thomas (réceptacle durable)
- [[Ressource - Trame call Yohan 28 mai 2026]] — call précédent
- [[Diag - Nouvel Organigramme & Cordon Sanitaire 2026-05-27]] — COMEX = chantier C3 / cordon sanitaire
