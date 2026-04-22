<%*
const title = await tp.system.prompt("Nom du projet / événement");
const date = tp.date.now("YYYY-MM-DD");
const filename = `${date} - ${title}`;
await tp.file.rename(filename);
await tp.file.move(`/60_Retros/${filename}`);
-%>
---
type: retro
date: <% date %>
participants: 
project: 
outcome: [success | partial | failure]
tags: 
---

# Retro — <% title %>

## Résumé
_En 3 lignes : c'était quoi, objectif, résultat réel._



## Ce qui a marché
_Factuels, pas des généralités. "Notre process X a permis Y" pas "bonne ambiance"._

- 
- 
- 

## Ce qui n'a pas marché
_Idem. Honnête mais sans chasse aux sorcières._

- 
- 
- 

## Leçons à garder
_Ce qu'on veut capturer pour les prochains projets. Souvent, ça devient un framework ou une modification de SOP._

- 
- 

## Actions concrètes
- [ ] SOP à créer / modifier : [[]]
- [ ] Decision à ouvrir : [[]]
- [ ] Personne à débriefer : [[]]

## Décisions / SOPs liés
- [[]]
