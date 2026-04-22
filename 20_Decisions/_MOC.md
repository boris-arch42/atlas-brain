---
type: moc
domain: decisions
---

# 🧭 MOC — Decision Records

Cartographie des décisions C-level de la boîte. Les listes se mettent à jour automatiquement.

---

## 🔥 Décisions high impact actives

```dataview
TABLE 
  date AS "Date",
  deciders AS "Deciders",
  next-review AS "Prochaine revue"
FROM "20_Decisions"
WHERE type = "decision" AND impact = "high" AND status = "accepted"
SORT date DESC
```

---

## 🚨 Décisions critical (impact maximal)

```dataview
TABLE 
  date AS "Date",
  deciders AS "Deciders",
  next-review AS "Prochaine revue"
FROM "20_Decisions"
WHERE type = "decision" AND impact = "critical"
SORT date DESC
```

---

## ⏰ Décisions à revoir (next-review dépassée)

```dataview
TABLE 
  date AS "Date prise",
  next-review AS "Revue prévue",
  impact AS "Impact"
FROM "20_Decisions"
WHERE type = "decision" AND date(next-review) <= date(today) AND status = "accepted"
SORT next-review ASC
```

---

## 📋 Toutes les décisions par domaine

```dataview
TABLE 
  date AS "Date",
  impact AS "Impact",
  status AS "Status"
FROM "20_Decisions"
WHERE type = "decision"
GROUP BY domain
SORT domain ASC, date DESC
```

---

## 🔄 Décisions superseded (remplacées)

```dataview
TABLE 
  date AS "Date",
  superseded-by AS "Remplacée par"
FROM "20_Decisions"
WHERE type = "decision" AND status = "superseded"
SORT date DESC
```

---

## 💭 Décisions proposées (en attente d'arbitrage)

```dataview
LIST
FROM "20_Decisions"
WHERE type = "decision" AND status = "proposed"
```

---

## Comment créer un nouveau Decision Record

1. `Ctrl/Cmd + P` → "Templater: Create new note from template"
2. Sélectionner `Decision`
3. Saisir le titre → le fichier est créé dans `20_Decisions/YYYY/`

**Règles de base** :
- La section "Hypothèses sous-jacentes" n'est JAMAIS vide
- Les critères de succès sont toujours mesurables
- Si la décision supersede une autre, lier les deux dans `supersedes` / `superseded-by`
