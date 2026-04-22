---
type: org-chart
last-updated: 2026-04-22
---

# 🏢 Org chart — Entrepreneurs.com

> Structure de l'équipe au <% tp.date.now("YYYY-MM-DD") %>. À mettre à jour à chaque mouvement RH.

---

## C-Level

- **CEO** : [[]]
- **COO** : [[]]
- **CFO** : [[]]
- **CTO** : [[]]
- **CMO** : [[]]

## Direction

### Sales
- Directeur Sales : [[]]
  - [[]]
  - [[]]

### Customer Success
- Directeur CS : [[]]
  - [[]]

### Marketing
- Directeur Marketing : [[]]
  - [[]]

### Product / Tech
- VP Product : [[]]
  - [[]]
- VP Engineering : [[]]
  - [[]]

### Ops / Finance / RH
- [[]]

---

## Recherche par expertise

```dataview
TABLE role AS "Rôle", team AS "Équipe"
FROM "40_People"
WHERE type = "person" AND status = "active"
SORT team ASC, role ASC
```

---

## Schéma Excalidraw

_Crée un schéma visuel avec Excalidraw ici — plus lisible qu'une liste pour les parties prenantes externes._

![[OrgChart.excalidraw]]
