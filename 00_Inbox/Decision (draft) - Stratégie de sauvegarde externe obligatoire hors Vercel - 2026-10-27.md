---
type: decision
statut: draft
date: 2026-10-27
source: jarvis
call: "[[2026-10-27 - Mohamed X Boris - Cybersecurity]]"
tags: [decision, draft]
---

# Stratégie de sauvegarde externe obligatoire hors Vercel

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Actuellement, il n'existe aucune sauvegarde externe en dehors des backups hébergés chez Vercel. Cela crée un risque majeur de point de défaillance unique (single point of failure) : si Vercel ou ses sauvegardes sont compromis, l'organisation perd toutes ses données sans possibilité de restauration.

## Décision

Mise en place obligatoire et urgente de sauvegardes externes chez un autre fournisseur et dans une autre région géographique (par exemple Hostinger ou un stockage basé en Allemagne/France) afin de garantir une capacité de restauration en cas de sinistre.

## Conséquences

- Mohamed doit rechercher et proposer des solutions de sauvegarde externes
- Boris doit soutenir et approuver l'achat
- Mohamed doit créer le projet dans Work et ouvrir un canal Slack si nécessaire pour coordonner avec Quentin et Wassim
- Élimination du risque de perte totale de données
- Coût additionnel de stockage et d'infrastructure à prévoir

## Statut

🔴 Action urgente — En attente de proposition de Mohamed
