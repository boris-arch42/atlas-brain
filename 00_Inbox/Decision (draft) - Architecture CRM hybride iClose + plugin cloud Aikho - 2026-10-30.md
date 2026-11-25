---
type: decision
statut: draft
date: 2026-10-30
source: jarvis
call: "[[2026-10-30 - Connection tools Aikho]]"
tags: [decision, draft]
---

# Architecture CRM hybride iClose + plugin cloud Aikho

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Aikho doit structurer son workflow commercial pour gérer les leads pré-inscription et qualifier/convertir les prospects. Deux systèmes coexistent : ICO (plateforme produit) et iClose (CRM commercial). Risque de dispersion des données et friction pour les commerciaux.

## Décision

- **Court terme** : iClose centralise tous les leads pré-inscription (CSV import + transferts landing pages)
- **Moyen terme** : développement d'un **plugin cloud** (MCP/Claude) qui :
  - Lit de manière sécurisée les données ICO
  - Fournit recommandations, contexte et réponses aux objections aux commerciaux
  - S'intègre Gmail/calendrier pour automatiser prises de RDV et analyses
  - Préserve l'intelligence produit Aikho sans multiplier les outils
- ICO remonte dans iClose les informations de réservation et d'usage pour enrichir le contexte lead
- Approche manuelle pour les 20-30 premiers appels (enregistrement Google Meet/Gemini) avant automatisation

## Conséquences

**Positives :**
- Préserve flexibilité et intelligence produit tout en outillant les commerciaux
- Réduit friction commerciale vs navigation multi-outils
- Permet apprentissage terrain avant automatisation lourde
- Coûts maîtrisés vs multiplication abonnements iClose

**Négatives :**
- Coût développement plugin cloud (opportunité)
- Intégrations iClose/ICO à construire progressivement
- Risque de dette technique si les deux systèmes dérivent

## À valider par Boris

- Priorisation développement plugin cloud (Julien propose livraison week-end)
- Budget/ressources pour intégrations iClose/ICO
- Seuils de bascule entre gestion manuelle et automatisation
