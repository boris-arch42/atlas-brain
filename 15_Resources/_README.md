# 15_Resources — Matériaux bruts traités

> Ressources documentaires durables : replays de calls (Sembly), transcripts de réunions, cartographies externes (Miro, Whimsical), exports d'outils, dossiers de presse, plaquettes produits.

## Différence avec les autres dossiers

| Dossier | Contenu | Mutabilité |
|---|---|---|
| `00_Inbox/` | Capture brute non traitée, à trier 2x/semaine | Éphémère |
| **`15_Resources/`** | **Matériaux bruts analysés, références durables** | **Stable** |
| `10_SOPs/` | Process documentés actionables | Vivant (revue 6 mois) |
| `20_Decisions/` | Décisions C-level avec hypothèses | Stable + revues |
| `60_Retros/` | Post-mortems, bilans | Stable |
| `90_Archive/` | Périmé, conservé pour historique | Figé |

## Convention de nommage

`Ressource - [Type] [Personne(s)/Sujet] [Date].md`

Exemples :
- `Ressource - Replay Sabrina 28 avril 2026.md`
- `Ressource - Replay Alec Fabrice 27 avril 2026.md`
- `Ressource - Core Meeting 27 avril 2026.md`
- `Ressource - Miro Fabrice cartographie process.md`

## Front-matter type

```yaml
---
type: ressource-replay  # ou ressource-meeting, ressource-cartographie, etc.
source: Sembly transcript  # ou Miro, Notion, etc.
date-meeting: YYYY-MM-DD
date-analyzed: YYYY-MM-DD
duration: ~XX min
status: analysé  # ou brut, à-traiter, archivé
participants: "Nom 1, Nom 2"
shared-by: "[[Nom]]"
sensitivity: confidential  # ou confidential-max, public
tags: [replay, ...]
---
```

## Pourquoi un dossier dédié

Les ressources sont des **inputs durables** : un replay analysé en avril 2026 reste référencable 18 mois plus tard pour comprendre l'évolution d'une situation. L'Inbox doit rester éphémère (capture rapide, triage hebdo). Mélanger les deux casse le rituel de triage et noie les ressources stables dans le bruit.

Les `[[wikilinks]]` Obsidian ne dépendent pas du chemin — déplacer un fichier ressource depuis `00_Inbox/` vers `15_Resources/` ne casse aucun lien existant.
