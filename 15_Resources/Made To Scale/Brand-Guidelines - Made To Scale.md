---
type: resource
topic: "Charte graphique Made To Scale"
domaine: MTS
version: "V1"
last-updated: 2026-09-29
owner: "[[Boris Arduy]]"
sensitivity: internal
tags: [mts, made-to-scale, branding, charte-graphique, template, pdf]
---

# 🎨 Charte graphique — Made To Scale

> Branding validé par Boris le 2026-09-29 (cadrage technique Snob Dog Academy).
> **À appliquer à tout document produit pour Made To Scale** (propositions, cadrages techniques, livrables clients, PDF, slides).
> Inspiration : univers bleu / noir de Sonaar.

## Couleurs

| Rôle | Hex | Usage |
|---|---|---|
| Noir profond | `#0A0C11` | Fond page de garde, en-têtes de tableaux, blocs « Prochaines étapes », encadrés clés |
| Encre (titres) | `#0B0D12` | Titres, texte fort |
| Texte courant | `#3A3F4B` | Corps de texte |
| Gris secondaire | `#6B7280` | Légendes, en-têtes / pieds de page |
| Filets | `#E3E6EC` | Bordures, séparateurs de tableaux |
| **Bleu accent** | `#2563EB` | Numéros de section, mots clés du titre, puces, barre de couverture |
| Bleu foncé | `#1E40AF` | Titres de cartes KPI, libellés dans encadrés |
| Bleu clair | `#EEF3FE` | Fond des cartes KPI et encadrés « note » |

## Typographies

- **Titres** : Space Grotesk (Bold 700) — Google Fonts
- **Corps** : Inter (400 / 600) — Google Fonts
- Taille corps ≈ 9,5 pt (PDF A4), interlignage 1,55

## Mise en page (documents PDF)

- **Page de garde** pleine page fond noir `#0A0C11`, barre verticale bleue à gauche (6 mm), halo bleu radial à droite
- Wordmark en haut : `MADE TO SCALE` (Space Grotesk, espacement large, **SCALE en bleu**)
- Pastille arrondie (type de document · durée) puis grand titre blanc dont la 2e partie est en bleu
- Bandeau bas de couverture : Client · Prestataire · Date · Durée (libellés gris en petites capitales)
- Pages intérieures : en-tête `MADE TO SCALE` à gauche + « Client · Type de doc » à droite ; pied de page « Document confidentiel — contact@madetoscale.fr » + pagination `n / total`
- Sections numérotées `01`, `02`… (numéro en bleu + titre Space Grotesk)
- Composants : cartes KPI bleu clair, tableaux à en-tête noir et lignes zébrées, encadrés « note » (liseré bleu gauche + fond bleu clair), schéma de flux en 3 colonnes (sources → orchestration en blocs noirs → destinations en bleu clair), timeline avec pastilles bleues (dernière étape en noir), bloc final « Prochaines étapes » fond noir
- Pas de logo image pour l'instant (wordmark texte uniquement)

## Production

- HTML + CSS → PDF via **WeasyPrint**
- Polices téléchargées depuis `github.com/google/fonts` (Inter, SpaceGrotesk variables), installées dans `~/.local/share/fonts/` + `fc-cache -f`
- Gabarit de référence : [[Template - Document client MTS.html]] (même dossier)

## Liens
- [[MTS — Made To Scale]]
