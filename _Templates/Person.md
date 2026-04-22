<%*
const name = await tp.system.prompt("Prénom Nom");
await tp.file.rename(name);
await tp.file.move(`/40_People/${name}`);
-%>
---
type: person
role: 
team: 
manager: 
reports: 
started: 
status: active
tags: 
---

# <% name %>

## Rôle actuel
- **Poste** : 
- **Équipe** : 
- **Manager** : [[]]
- **Reports directs** : 

## Expertise / Zone de génie
_Ce pour quoi cette personne est la meilleure ressource interne._

- 
- 

## Historique dans la boîte
- **Arrivée** : 
- **Postes précédents** : 
- **Jalons** : 

## Contexte perso utile (pro)
_Préférences de travail, contraintes, modes de communication qui marchent._



## SOPs dont elle/il est owner
```dataview
LIST
FROM "10_SOPs"
WHERE contains(owner, this.file.link)
```

## Décisions auxquelles elle/il a participé
```dataview
LIST
FROM "20_Decisions"
WHERE contains(deciders, this.file.link)
SORT date DESC
```
