<%*
const title = await tp.system.prompt("Nom du framework");
await tp.file.rename(title);
await tp.file.move(`/30_Frameworks/${title}`);
-%>
---
type: framework
created: <% tp.date.now("YYYY-MM-DD") %>
author: 
source: 
tags: 
---

# Framework — <% title %>

## En une phrase
_Le framework en 1 ligne. Si tu n'y arrives pas, tu ne l'as pas compris._



## Quand l'utiliser
_Situations typiques où ce framework aide à décider / analyser._

- 
- 

## Le framework

### Étape / Composant 1
_Description_

### Étape / Composant 2

### Étape / Composant 3

## Exemple d'application
_Un cas concret de notre boîte où on l'a appliqué._



## Limites et pièges
_Quand ce framework ne marche pas, ou induit en erreur._

- 
- 

## Sources
- 

## Notes et décisions liées
- [[]]
