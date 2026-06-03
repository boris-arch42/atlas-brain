---
type: project-detail
date: 2026-06-02
owner: "[[Boris Arduy]]"
parent: "[[Pôle Tech & Ops interne — structuration]]"
sensitivity: confidential
tags: [pole-tech, couts, budget, internationalisation, n8n, dubai, offshore, economies]
---

# Pôle Tech Ops — modèle de coûts (juin → sept 2026)

> Vision de structuration du pôle Tech/Ops portée par Boris (02/06). Deux leviers : **internationalisation/offshore de l'équipe** + **effondrement de la stack outils sur N8N auto-hébergé + la plateforme interne**. Cible : **−51,45 %** sur le pôle.

## Équipe

| Rôle | Juin 2026 | €/mois | Septembre 2026 (cible) | €/mois | Scope |
|---|---|---|---|---|---|
| Responsable Cybersécurité | Mohamed Guendouzi | 2 000 | Mohamed Guendouzi *(inchangé)* | 2 000 | Accès, alertes, sécu données, on/offboarding, fuite mdp, licences |
| OPS Marketing | Nicolas Farolfi | 4 100 | OPS Marketing International (full-time) | 1 200 | Automatisations lancements, contrats clients, CRM HubSpot |
| Rev OPS | Yohan Bourgogne | 4 000 | Rev OPS International | 1 500 | Architecture 2.0 / Laravel |
| Dev / Plateforme | Quentin Hugot (Amea, externe) | 20 000 | CTO (Dubaï) + Dev Senior International | 10 000 | Plateforme client Entrepreneurs |
| Data Ingénieur | Thomas Baeumlin | 5 000 | Data Ingénieur International | 2 500 | Data dashboard / architecture data |
| **Coût effectif équipe** | | **35 100** | | **17 200** | **−17 900/mois** |

## Outils

| Outil | €/mois (juin) | Changement opéré | €/mois (sept) |
|---|---|---|---|
| Make | 1 528,00 | → N8N / système auto-hébergé | 100,00 |
| Zapier | 25,71 | Suppression | 0 |
| 0codekit | 21,44 | Suppression | 0 |
| Short.io | 18,52 | Via N8N | 0 |
| Oneflow | 598,50 | — | 598,50 |
| Minari | 260,00 | — | 260,00 |
| HubSpot | 3 262,70 | — *(conservé : source unique)* | 3 262,70 |
| Claap.io | 3 525,59 | Quasi-suppression, intégration via plateforme | 500,00 |
| Calendly | 685,73 | Migration vers iClosed | 0 |
| Aircall | 1 464,34 | Deal Aircall + event Scale | 0 |
| Clickfunnels | 214,79 | — | 214,79 |
| Airtable | 352,90 | Suppression à terme | 0 |
| **Coût outils** | **10 493,88** | | **4 935,99** *(−5 557,89)* |

## Total pôle

| | Juin 2026 | Septembre 2026 | Δ |
|---|---|---|---|
| Coût mensuel | 45 594 € | 22 136 € | −23 458 € |
| Coût annuel | 547 127 € | 265 632 € | **−281 495 €** |
| Économie sur le pôle | | | **−51,45 %** |

## Lecture / risques (cf. analyse Boris 02/06)
- **Levier n°1 = Quentin** : 20 000 → 10 000 = la moitié de l'économie équipe. Plus haut risque (il détient la plateforme client). Dépend de I11/G11 (piloté Fabrice/Alec).
- **N8N auto-hébergé = pivot des économies outils** (~1 593 €/mois) mais transfère la charge d'uptime/maintenance/sécu en interne → single point of failure.
- **Dépendance circulaire** : les économies outils (Claap, Calendly) reposent sur la plateforme, qui est elle-même en cours de re-staffing moins cher.
- **HubSpot conservé** → tranche de fait E3 (on garde le CRM, on ne le rouvre pas).
- **Cohérence cyber** : offshore + N8N auto-hébergé = surface d'attaque que traque ton dashboard sécu (2FA, accès, APIs orphelines, super-admins) → H1/H4 deviennent non négociables.

## Liens
- [[Pôle Tech & Ops interne — structuration]]
- [[Refonte verticale Data-IA-Tech-Ops]] (KR3.3 — réconcilier la baseline 45,6K vs 52K)
- [[Roadmap stratégique 6 mois (Fabrice) - juin-déc 2026]] (G11, I11, G7, G9)
- [[🗼 Tour de contrôle - Projets en cours]]
