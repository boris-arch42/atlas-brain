---
type: person
full-name: "Maryam"
role: "Développeuse — équipe Automation IA"
team: "Verticale Ops/IT/Tech/Data/IA (sous Anisse)"
manager: "[[Anisse Rbibe]]"
reports:
started: "~2026-05-19 (annonce COMEX 19/5)"
last-updated: 2026-05-19
status: active-onboarding
location: "Maroc (offshore)"
source: entrepreneurs-com
sensitivity: confidential
tags: [dev, maroc, offshore, automation-ia, anisse, bot-slack, notion, process-internes]
---

# Maryam

> **🟢 Nouvelle arrivée annoncée au COMEX 19/5** par [[Anisse Rbibe]]. Cf. [[Ressource - Replay COMEX hebdo 19 mai 2026]].
>
> Développeuse basée au Maroc, rattachée à l'équipe Automation IA d'Anisse. **Première mission concrète déjà cadrée**.

## Rôle actuel

- **Poste** : Développeuse
- **Équipe** : Automation IA (sous Anisse), verticale Ops/IT/Tech/Data/IA
- **Manager** : [[Anisse Rbibe]]
- **Reports directs** : aucun
- **Localisation** : Maroc (offshore) — cohérent avec stratégie sourcing Maroc validée call 5/5

## Mission 1 — Bot Slack process internes (en cours)

**Objectif** : bot Slack répondant aux questions sur **process internes** en s'appuyant sur :
- Wiki Notion de l'entreprise
- Autres documents centralisés

**Logique** : réduire les **interruptions ad hoc** + améliorer la **cohérence** des réponses sur process.

**Demande COMEX** (Anisse → équipe) : si certains process ne sont pas dans Notion, envoyer **liens/sources** à Maryam pour qu'ils soient ajoutés à la base de données partagée **dans la semaine**.

→ **Action Boris** : identifier les process Atlas-Brain qui pourraient nourrir le bot Slack. Critères :
- Process publics (pas confidential-max)
- SOPs déjà documentés (Onboarding/Offboarding, Process IT-SaaS-Cybersec, etc.)
- À envoyer à Maryam (canal à clarifier — probablement Slack ou via Anisse)

## Articulation avec le Plan trimestriel Q1

**KR1.2 (top 10 process avec head owner + adoption mesurée via logs)** :
- Le bot Slack Maryam = **levier d'adoption mesurée** des process top 10
- Méthode Anisse "logs d'utilisation" applicable nativement (qui pose quelle question, quelle réponse, quelle satisfaction)
- → Boris peut **mesurer l'adoption** de chaque SOP en suivant les requêtes Slack qui lui sont liées

**KR3.3 (stack équipe verticale)** : Maryam s'ajoute à la stack verticale, dans la dynamique sourcing Maroc cohérente avec :
- Nicolas Farolfi remplaçant (Ops auto Maroc, 3 profils Aikho)
- 2-3 dévs offshore plateforme (cible Q3)
- PMO local francophone

## Contexte transverse — sourcing offshore Maroc

Maryam s'inscrit dans la stratégie **offshore Maroc** posée au call 5/5 :
- Coût ~50% France
- Profils techniques compétents
- Lien naturel avec Hamid (référence Anisse) et autres agences Maroc d'automatisation

**Verbatim Anisse 5/5** (27:47) : *"On peut aller chercher comme ils recrutent, Hamid ou d'autres agences au Maroc qui font de l'automatisation."*

## ⚠️ Champs à compléter (carnet de bord)

- [ ] Nom complet (Maryam = prénom probable, nom à confirmer)
- [ ] Date d'arrivée exacte
- [ ] Type de contrat (prestataire / salarié local)
- [ ] Tarif / package (cohérent stratégie ~900€/mois offshore Maroc ?)
- [ ] Canal de communication direct avec Boris (Slack, mail)
- [ ] Stack technique principale (Python, n8n, autres ?)
- [ ] Périmètre exact missions 2 et au-delà
- [ ] Rapport hiérarchique formel (Anisse uniquement ou matriciel ?)

## Posture Boris

- **Pas en relation directe quotidienne** — Maryam est dans l'équipe Anisse
- **Levier pour KR1.2** : process Atlas-Brain à pousser dans la base bot Slack
- **Cas applicatif HO39** : si le bot Slack réduit effectivement les interruptions ad hoc, c'est un **quick win adoption** mesurable

## Notes liées

- [[Anisse Rbibe]] — manager direct
- [[Ressource - Replay COMEX hebdo 19 mai 2026]] — source annonce
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] — KR1.2 + KR3.3
- [[Ressource - Replay Ops IT Tech Data IA 5 mai 2026]] — stratégie sourcing Maroc

## SOPs dont elle est owner
```dataview
LIST
FROM "10_SOPs"
WHERE contains(owner, this.file.link)
```
