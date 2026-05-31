---
type: dashboard
date-created: 2026-05-31
owner: "[[Boris Arduy]]"
sensitivity: confidential
tags: [dashboard, tour-de-controle, supervision, projets, pilotage]
cssclasses: [wide-page]
---

# 🗼 Tour de contrôle — Projets en cours

> **Couche de supervision, pas d'exécution.** Cette note n'héberge aucun travail : elle agrège le statut des cartes projet de `05_Projects/`. L'exécution réelle vit là où elle doit vivre (Notion madetoscale, Linear Mithril, scopes du vault) — chaque carte pointe dessus via le champ `execution`.
>
> **Rituel** : passe de supervision hebdo de ~20 min (caler sur le weekly Fabrice ou le call hebdo à 4). On ne fait que : mettre à jour `sante`, déplacer les `echeance` dépassées, trancher les `bloqué`, et bumper `revue: {{date}}`. Les revues de fond restent les J+30 / J+60 / J+90 du [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)|Plan Q1]].
>
> **Légende santé** : 🟢 sous contrôle · 🟠 à surveiller · 🔴 bloqué/à risque · ⚪ en pause / dormant.

---

## ✅ Passe hebdo — 20 min (rituel)

*Quand* : adossée au weekly Boris↔Fabrice (jeudi) ou au call hebdo à 4. *But* : tenir la vue à jour, **pas** faire le travail. 4 gestes, dans l'ordre :

1. **Balayer les alertes** (section 🚨) — pour chaque 🔴/🟠, vérifier que le champ `prochaine` est toujours la bonne action. Sinon, le corriger.
2. **Replanifier les échéances dépassées** (section ⏰) — déplacer chaque `echeance` passée, ou passer le projet en `statut: terminé`.
3. **Trancher les bloqués + réveiller les dormants** (sections 🕸️ >14j et ⚪) — pour chaque `bloqué`, une décision ce jour (qui débloque quoi, ou on abandonne) ; pour chaque dormant, on relance, on délègue, ou on assume la pause explicitement. Un bloqué qui traîne 2 semaines = un sujet qu'on se cache.
4. **Bumper `revue: <date du jour>`** sur chaque carte touchée — c'est ce geste qui vide la liste ">14j" et fait vivre le filet.

> 🔒 **Règle d'or (boucles fermées)** : pas de nouveau projet ouvert tant qu'un projet actif n'est pas fermé ou explicitement mis en pause. (cf. Anisse, 26/4)

---

## 🚨 Alertes — à traiter en priorité (🔴 + 🟠)

```dataview
TABLE WITHOUT ID
  sante AS "Santé",
  file.link AS "Projet",
  statut AS "Statut",
  prochaine AS "Prochaine action",
  echeance AS "Échéance"
FROM "05_Projects"
WHERE type = "project" AND (sante = "🔴" OR sante = "🟠")
SORT echeance ASC
```

## ⏰ Échéances dépassées (à replanifier)

```dataview
TABLE WITHOUT ID
  file.link AS "Projet",
  echeance AS "Échéance",
  prochaine AS "Prochaine action"
FROM "05_Projects"
WHERE type = "project" AND echeance AND echeance < date(today) AND statut != "terminé"
SORT echeance ASC
```

## 📋 Vue complète — par échéance

```dataview
TABLE WITHOUT ID
  sante AS "Santé",
  file.link AS "Projet",
  domaine AS "Domaine",
  statut AS "Statut",
  owner AS "Owner",
  echeance AS "Échéance"
FROM "05_Projects"
WHERE type = "project" AND statut != "terminé"
SORT echeance ASC
```

## 🗂️ Par domaine

```dataview
TABLE WITHOUT ID
  file.link AS "Projet",
  sante AS "Santé",
  statut AS "Statut",
  prochaine AS "Prochaine action"
FROM "05_Projects"
WHERE type = "project"
SORT echeance ASC
GROUP BY domaine AS "Domaine"
```

## 🕸️ À revoir — pas touché depuis >14 jours

> Le filet anti-cimetière : ce qu'on a laissé dormir sans le décider.

```dataview
TABLE WITHOUT ID
  file.link AS "Projet",
  revue AS "Dernière revue",
  statut AS "Statut"
FROM "05_Projects"
WHERE type = "project" AND revue AND (date(today) - revue) > dur("14 days") AND statut != "terminé"
SORT revue ASC
```

## ⚪ En pause / dormant

```dataview
TABLE WITHOUT ID
  file.link AS "Projet",
  domaine AS "Domaine",
  prochaine AS "Condition de réveil"
FROM "05_Projects"
WHERE type = "project" AND statut = "en-pause"
```

---

## 🔗 Notes liées
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] — objectifs ENT (revue de fond J+30/60/90)
- [[Index - Sides]] — règles d'allocation ventures
- [[Boris Arduy]] — page owner
- Modèle de carte : [[_Templates/Template - Carte Projet]]
