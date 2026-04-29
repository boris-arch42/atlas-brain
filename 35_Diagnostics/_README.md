# 35_Diagnostics — Diagnostics opérationnels Entrepreneurs.com

> Diagnostics structurés et **vivants** sur la boîte. Famille de documents posés en pré-prise de poste, révisés à J+14, J+30, J+90.

## Différence avec les autres dossiers

| Dossier | Contenu | Réutilisable hors contexte ? |
|---|---|---|
| `30_Frameworks/` | Méthodes / modèles mentaux maison | ✅ Oui (transposable) |
| **`35_Diagnostics/`** | **Analyses spécifiques Entrepreneurs.com** | ❌ Non (contextuel) |
| `60_Retros/` | Bilans figés post-projet | ❌ Non (figé) |

Les **Diagnostics** sont vivants : ils encapsulent les hypothèses, angles morts et questions qui orientent l'action et qui se résolvent (ou se renforcent) avec le terrain. Ils sont **datés**, **versionnés**, et **revérifiés** à intervalles fixes.

## Convention de nommage

`Diag - [Sujet].md`

Exemples :
- `Diag - Hypothèses que j'ai sur la boîte (à vérifier).md`
- `Diag - Angles morts (ce que je ne sais PAS encore).md`
- `Diag - Personnes que je dois débriefer en priorité.md`

## Front-matter type

```yaml
---
type: diagnostic
date: YYYY-MM-DD
source: entrepreneurs-com
sensitivity: confidential
tags: [diagnostic, ...]
related-decisions: "[[YYYY-MM-DD - Titre]]"
---
```

## Cadence de revue

- **J+14** : statut de chaque hypothèse (confirmée / infirmée / partielle / données insuffisantes)
- **J+30** : ajustement des hypothèses opérationnelles qui tiennent encore
- **J+90** : intégration des apprentissages dans le DR Operating Partner

## Liens cascade attendus

Chaque diagnostic doit pointer vers :
- Les **décisions** (`20_Decisions/`) qu'il informe ou qu'il a déclenchées
- Les **personnes** (`40_People/`) impliquées dans la confirmation/infirmation
- Les **resources** (`15_Resources/`) qui ont permis sa formulation (replays, transcripts)
- D'autres **diagnostics** liés (cross-references entre HO)
