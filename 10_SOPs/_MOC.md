---
type: moc
domain: sops
---

# 🧭 MOC — SOPs

Carte d'entrée de tous les SOPs du vault. Les listes ci-dessous se mettent à jour automatiquement via Dataview.

---

## Tous les SOPs par domaine

```dataview
TABLE 
  owner AS "Owner",
  status AS "Status",
  last-reviewed AS "Dernière revue"
FROM "10_SOPs"
WHERE type = "sop"
GROUP BY domain
SORT domain ASC
```

---

## ⚠️ SOPs à revoir (pas de review depuis 180j)

```dataview
TABLE 
  owner AS "Owner",
  last-reviewed AS "Dernière revue",
  status AS "Status"
FROM "10_SOPs"
WHERE type = "sop" AND (date(today) - date(last-reviewed)).days > 180
SORT last-reviewed ASC
```

---

## 📝 SOPs en draft

```dataview
LIST
FROM "10_SOPs"
WHERE type = "sop" AND status = "draft"
```

---

## 🗑️ SOPs deprecated

```dataview
LIST
FROM "10_SOPs"
WHERE type = "sop" AND status = "deprecated"
```

---

## Comment créer un nouveau SOP

1. `Ctrl/Cmd + P` → "Templater: Create new note from template"
2. Sélectionner `SOP`
3. Répondre aux prompts (domaine, nom du process)
4. Le fichier est créé automatiquement dans le bon dossier.

**Règles de base** :
- Un SOP a toujours un `owner`
- La section "Pièges connus" n'est jamais vide
- Toute décision stratégique liée est linkée dans "Décisions stratégiques rattachées"
