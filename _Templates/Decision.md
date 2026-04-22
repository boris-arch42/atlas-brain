<%*
const title = await tp.system.prompt("Titre de la décision (court et clair)");
const year = tp.date.now("YYYY");
const date = tp.date.now("YYYY-MM-DD");
const filename = `${date} - ${title}`;
await tp.file.rename(filename);
await tp.file.move(`/20_Decisions/${year}/${filename}`);
-%>
---
type: decision
date: <% date %>
status: proposed
deciders: 
domain: 
impact: medium
supersedes: 
superseded-by: 
next-review: <% tp.date.now("YYYY-MM-DD", 180) %>
tags: 
---

# Decision — <% title %>

## Contexte
_Quelle était la situation ? Quels signaux nous ont amenés à trancher ? Sans ce contexte, impossible de juger la décision 2 ans plus tard._



## Options envisagées

### Option A — 
- **Pros** : 
- **Cons** : 
- **Coût / effort** : 

### Option B — 
- **Pros** : 
- **Cons** : 
- **Coût / effort** : 

### Option C — 
- **Pros** : 
- **Cons** : 
- **Coût / effort** : 

## Décision retenue
_Une phrase claire. Puis la justification en 3-5 lignes._



## Hypothèses sous-jacentes
_Ce qu'on croit être vrai au moment de la décision. Si ces hypothèses changent, la décision doit être rouverte. Section critique — ne jamais la laisser vide._

- 
- 
- 

## Critères de succès / d'échec
_Comment on saura dans 3 / 6 / 12 mois si c'était le bon choix. Métriques concrètes._

- **3 mois** : 
- **6 mois** : 
- **12 mois** : 

## Conséquences attendues

**Positives** :
- 

**Négatives acceptées** :
- 

**SOPs à créer ou modifier** :
- [[]]

## Revue

- **Prochaine revue prévue** : <% tp.date.now("YYYY-MM-DD", 180) %>
- **Résultats réels** : _(à remplir lors de la revue)_

## Historique
- <% date %> — Décision prise ([[]])
