---
type: decision
statut: draft
date: 2026-08-25
source: jarvis
call: "[[2026-08-25 - Mohamed X Boris - Cybersecurity]]"
tags: [decision, draft]
---

# Architecture de stockage hybride NAS + Backblaze pour optimisation coûts

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Le projet de migration NAS doit dimensionner le stockage entre production, archives récentes et archives long terme. Le devis initial de Fabrice prévoyait 90 To production et 40 To archives, sans distinction entre archives chaudes et froides.

## Décision

Architecture retenue :
- **90 To** : stockage production NAS
- **40 To** : archives récentes (2024-2025) sur NAS, accessibles immédiatement
- **Archives froides** (2022-2023) : stockage long terme sur Backblaze, coût optimisé

Cette approche permet de limiter les coûts de stockage haute performance tout en gardant les données récentes accessibles rapidement.

## Conséquences

**Positif :**
- Réduction significative des coûts de stockage NAS
- Accessibilité rapide préservée pour données récentes
- Scalabilité pour archives long terme via solution cloud économique

**À anticiper :**
- Définir politique de rétention et critères de bascule vers archives froides
- Coordonner avec Océane/Greg la validation finale du dimensionnement
- Documenter procédure de récupération données Backblaze si besoin

**Action requise :** Validation formelle par Océane et décisionnaire final (Greg ?) avant lancement migration.
