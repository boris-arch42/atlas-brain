<%*
const domain = await tp.system.suggester(
  ["Sales", "Customer-Success", "Marketing", "Product", "Ops-Finance", "People-RH", "Tech"],
  ["Sales", "Customer-Success", "Marketing", "Product", "Ops-Finance", "People-RH", "Tech"]
);
const processName = await tp.system.prompt("Nom du process");
const folder = `10_SOPs/${domain}`;
const filename = `${domain} - ${processName}`;
await tp.file.rename(filename);
await tp.file.move(`/${folder}/${filename}`);
-%>
---
type: sop
domain: <% domain %>
owner: 
status: draft
last-reviewed: <% tp.date.now("YYYY-MM-DD") %>
frequency: ad-hoc
related-decisions: 
tags: 
---

# SOP — <% processName %>

## Pourquoi ce process existe
_2-3 lignes. Le "pourquoi" avant le "comment". Si tu ne sais pas pourquoi, le process est mort._



## Quand le déclencher
_Événement, condition, fréquence_



## Qui est impliqué
- **Owner** : [[]]
- **Exécutant(s)** : 
- **Validation** : 

## Étapes

### 1. [Action]
- Détail concret
- Outil utilisé : 
- Output attendu : 

### 2. [Action]
- 
- 

### 3. [Action]
- 
- 

## Pièges connus
_Ce que les nouveaux ratent systématiquement. Section la plus précieuse du doc._
- 
- 

## Ressources liées
- Templates : 
- Docs : 
- Outils : 

## Décisions stratégiques rattachées
- [[]]

## Historique
- <% tp.date.now("YYYY-MM-DD") %> — Création ([[]])
