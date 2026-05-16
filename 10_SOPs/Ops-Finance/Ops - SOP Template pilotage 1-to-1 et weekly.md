---
type: sop
domain: Ops-Finance
owner: "[[Boris Arduy]]"
status: draft
last-reviewed: 2026-05-16
frequency: par-1to1-ou-weekly
related-decisions:
  - "[[Ressource - Replay Weekly Alec × Boris 12 mai 2026]]"
related-frameworks: []
related-sops: []
tags: [pilotage, 1-to-1, weekly, template, communication, suivi, comex, demande-alec]
source: entrepreneurs-com
sensitivity: internal
---

# SOP — Template pilotage 1-to-1 et weekly

> **Origine** : weekly Alec × Boris du 12 mai 2026. Alec a explicitement demandé que Boris partage la structure de ses calls comme template réplicable, notamment à Fabrice. Verbatim Alec :
>
> *"En 30 minutes, on a évoqué plus de sujets et plus de décisions que parfois dans des calls d'une heure que certains font en one-on-one dans l'ensemble de l'entreprise. [...] Et limite, ça peut se faire avec un template."*
>
> Cf. [[Ressource - Replay Weekly Alec × Boris 12 mai 2026]].

## Pourquoi ce process existe

La majorité des 1-to-1 et weekly dans l'entreprise souffrent de deux patterns identifiés par Alec :
- **Surface vs densité** : beaucoup de temps de discussion, peu de décisions actées
- **Pas de suivi** : les sujets sont traités mais ne génèrent pas de traçabilité ni de cascade

Ce SOP code la structure d'un call de pilotage **dense, traçable et orienté décision**, validée empiriquement le 12/5 (28 min, 5 arbitrages tranchés + 4 partages d'info structurants + feedback méta explicite d'Alec).

L'objectif n'est pas la rigueur procédurale pour elle-même, c'est de produire des **décisions sortantes** pour chaque créneau de temps senior mobilisé.

## Quand le déclencher

À chaque préparation de :
- 1-to-1 récurrent avec un stakeholder Comex (CEO, COO, head de pôle)
- Weekly de pilotage avec sponsor exécutif
- Call de cadrage ponctuel sur sujet structurel (montant > 50K€ d'enjeu, ou décision RH structurante)

**Pas approprié pour** :
- Calls relationnels (premier 1-to-1, accueil d'un nouveau profil)
- Calls de débrief émotionnel
- Calls de résolution d'incident à chaud (format crisis management distinct)

## Qui est impliqué

- **Owner** : porteur du call (celui qui prépare et structure)
- **Stakeholder** : interlocuteur principal (CEO, COO, head)
- **Filet de sécurité** : suppléant nominal si owner indisponible, désigné en amont sur les rituels critiques

## La structure (5 blocs)

### 1. Posture d'ouverture — assumer la trame

Annoncer dès l'ouverture :
- Combien de sujets vont être traités
- Distinction entre **arbitrages** (besoin de décision) et **partages d'info** (pas de décision attendue)
- Estimation de temps cible

Verbatim Boris 12/5 ouverture (à adapter) :
> *"On va essayer de faire ça structuré parce que c'est quand même le but. Je vais avoir en tout 5 sujets à voir avec toi à arbitrer, et 4 sujets à te partager. Sujet arbitré = vraiment des réflexions et des éléments qu'on doit voir ensemble. Les autres c'est plus pour que tu sois au courant de manière globale."*

→ **Pourquoi ça marche** : pose la trame avant que l'interlocuteur ne dérive. Permet à Alec (ou tout stakeholder structuré) d'embarquer la cadence.

### 2. Bloc Arbitrages — 1 décision par sujet

Pour chaque arbitrage, structure interne en 4 temps :
1. **Contexte minimal** (1-2 phrases, pas de récap historique)
2. **La question à arbitrer** posée explicitement
3. **Fallback préparé** (que faire si l'arbitrage donne tel ou tel résultat)
4. **Décision actée** + qui exécute, quand

Format idéal côté préparation : matrice papier avec colonnes "Sujet | Position recommandée | Fallback si blocage". Cette matrice n'est **pas partagée à l'interlocuteur** — elle reste support owner.

### 3. Bloc Partages — info structurée, pas de décision attendue

Sujets de mise à jour, signaux faibles, observations. Format :
- 30 secondes max par sujet
- Nommer le statut (validé / en cours / à monitorer / risque)
- Si l'interlocuteur veut creuser, basculer en arbitrage 4e bloc

### 4. Espace ouvert — sujets entrants stakeholder

Laisser 5-10 min en fin de call pour ce que l'interlocuteur veut amener. Souvent les sujets les plus importants (signaux faibles RH, intuitions stratégiques) sortent ici.

### 5. Synthèse + actions — 60 secondes de clôture

Reformuler en clôture :
- Décisions actées (les répéter pour ancrage)
- Actions sortantes par owner
- Prochain point (date / format)

## Pièges connus

| Piège | Symptôme | Mitigation |
|---|---|---|
| **Dérive en bavardage** | Sujet attendu en 5 min prend 15 min | Recadrer en mode "on note pour creuser après si besoin, on continue" |
| **Décision floue** | Sortie en mode "ouais on verra" | Insister sur **qui fait quoi, quand**. Pas de décision = pas avancée |
| **Surcharge de partages** | 10 partages en fin de call, plus de bande passante | Limiter à 3-4 partages max par call. Le reste va en Slack ou au prochain call |
| **Pas de traçabilité** | Décisions du call qui s'oublient en 48h | Écrire un récap dans les 24h (Slack, mail, fichier vault). Sans trace = pas de décision |
| **Reproduction du pattern "nourrir la bête"** | Le call devient un défouloir | Cadrer poliment : "ce sujet, on le traite à part. Ici on est sur le pipeline d'arbitrages" |

## Adaptation par typologie de stakeholder

### Avec CEO (Alec)
- Density forte requise — la structure protège de la dispersion naturelle
- Cadre temporel serré (28 min observé efficace, jusqu'à 45 min max)
- Suivi écrit indispensable post-call (replay vault + récap Slack si décision RH ou financière structurante)

### Avec COO (Fabrice, Jordan post-stabilisation)
- Plus d'espace pour les sujets opérationnels longs (top 10 process, audit)
- Format mensuel + weekly Slack court entre les deux
- Cadence des sujets de fond plus régulière, moins de "shoots arbitrages"

### Avec head de pôle (Aziz, Sabrina, Cédric, Anisse, Océane)
- Format 30 min toutes les 2 semaines acquis (cadre validé avec Aziz 28/4)
- Structure plus légère : 2-3 sujets max
- Plus d'écoute, moins de décisions descendantes

## Comment partager ce SOP

**À ne pas faire** : envoyer à Fabrice (ou tout autre head) comme correction de pratique.

**À faire** : positionner comme outil de pilotage Comex, partageable, à challenger ensemble. Format suggéré pour le partage à Fabrice :
- Mention en weekly Boris × Fabrice : *"Alec m'a demandé de partager la structure que j'utilise sur les 1-to-1, je te file le truc — dis-moi ce que t'en penses, c'est à itérer ensemble si utile"*
- Si bien reçu : élargir au Comex
- Si mal reçu : laisser tomber, ne pas insister

## Cas de référence

Le call qui a validé empiriquement cette structure : [[Ressource - Replay Weekly Alec × Boris 12 mai 2026]].

5 arbitrages + 4 partages en 28 minutes. Feedback Alec immédiat à reproduire : *"C'est bam bam bam bam bam, ce serait top."*

## Notes liées

- [[Ressource - Replay Weekly Alec × Boris 12 mai 2026]] — cas de référence empirique
- [[Alec Henry]] — demandeur du SOP, source du feedback méta
- [[Fabrice Jaeger]] — cible explicite de partage demandée par Alec
- [[Charte de fonctionnement Boris ↔ Fabrice — V1 (à envoyer)]] — cadre de travail relationnel

## Décisions stratégiques rattachées
```dataview
LIST
FROM "20_Decisions"
WHERE contains(related-sops, this.file.link)
SORT date DESC
```
