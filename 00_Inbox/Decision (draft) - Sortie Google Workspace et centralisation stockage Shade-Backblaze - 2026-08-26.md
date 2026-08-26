---
type: decision
statut: draft
date: 2026-08-26
source: jarvis
call: "[[2026-08-26 - Point NAS - Transfert Data Shade]]"
tags: [decision, draft]
---

# Sortie Google Workspace et centralisation stockage Shade/Backblaze

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

L'entreprise gère actuellement ~100 To de contenus vidéo répartis entre Shade, Google Drive et supports locaux. Les licences Google Business représentent un coût récurrent élevé et une dispersion des données qui nuit à la sécurité et à la gouvernance.

Grégoire et Samuel cumulent ~80 To sur Google Drive, et environ 40-45 personnes dépassent le quota Basic de 5 Go.

## Décision

**Réduction drastique des licences Google Business à ~10 licences réservées aux utilisateurs clés, rétrogradation de tous les autres comptes en Basic (5 Go), avec date cible de coupure au 30 septembre 2026.**

**Centralisation du stockage :**
- **Production (2026 + rushes réutilisés)** → Shade production (~60-90 To contractuels)
- **Archive court terme (2025)** → Shade Vault (~40 To contractuels)
- **Archive long terme (2019-2023)** → Backblaze ou disques externes

**Processus obligatoire :** les monteurs doivent archiver les rushes des projets après livraison pour éviter la dérive des volumes.

## Conséquences

**Positives :**
- Économies récurrentes sur les licences Google Business
- Centralisation et sécurisation des données critiques
- Visibilité sur les volumes réels de production par année
- Gouvernance améliorée du cycle de vie des contenus

**Négatives / Risques :**
- Charge de migration importante (40-45 personnes, ~100 To) sur 5 semaines
- Risque de perte de données si les utilisateurs ne migrent pas avant la coupure
- Résistance au changement (travail non productif à court terme)
- Nécessité d'un processus strict et d'une discipline d'archivage continue

**Validation Boris requise** sur : calendrier d'escalade, périmètre des 10 licences conservées, mécanisme de récupération en cas d'urgence post-coupure.
