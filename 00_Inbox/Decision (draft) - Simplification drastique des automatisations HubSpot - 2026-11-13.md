---
type: decision
statut: draft
date: 2026-11-13
source: jarvis
call: "[[2026-11-13 - Weekly catchup with Boris]]"
tags: [decision, draft]
---

# Simplification drastique des automatisations HubSpot

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

L'équipe disposait de plus de 150 workflows dans HubSpot, créant des frictions et des automatisations inutiles difficiles à maintenir.

## Décision

Réduction à 10-15 workflows actifs maximum. Lancement d'un audit systématique de Make, iClosed et HubSpot pour identifier les automatisations encore utiles et archiver les autres. Les automatisations inutilisées seront déplacées dans un fichier d'archive plutôt que supprimées.

## Conséquences

- Réduction de la complexité technique et de la dette technique
- Maintenance plus simple et prévisible
- Risque temporaire de casser des processus encore utilisés (nécessite audit rigoureux)
- Meilleure lisibilité pour les nouveaux membres de l'équipe

## À valider par Boris

- Périmètre exact de l'audit (priorités)
- Critères de décision pour archiver vs conserver
- Process de validation avant archivage définitif
