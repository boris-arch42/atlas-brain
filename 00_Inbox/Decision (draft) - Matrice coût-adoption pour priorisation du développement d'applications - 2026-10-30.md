---
type: decision
statut: draft
date: 2026-10-30
source: jarvis
call: "[[2026-10-30 - Anisse x Boris Ai priorités]]"
tags: [decision, draft]
---

# Matrice coût/adoption pour priorisation du développement d'applications

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

L'équipe développe de nombreuses applications internes avec des taux d'adoption très variables (de 31% pour le reporting à quasi 100% pour certains outils métier). Le coût de développement moyen est estimé à 400€ par application (environ 5 jours de dev). Alec a demandé une analyse du ROI et des priorités de développement.

## Décision

Création d'un tableau de bord croisant le taux d'adoption avec le coût par application pour identifier les applications à coût élevé et faible adoption. Cette matrice guidera les décisions d'investissement futures en inversant la pyramide des priorités.

Mise en place d'une métrique 'Héroïe' calculant le ROI via le temps économisé par utilisateur multiplié par un coût horaire de référence (fourni par Jordan). Seuil de rentabilité : environ 35 minutes économisées par utilisateur/mois pour justifier le coût de développement.

## Conséquences

- Priorisation data-driven des développements futurs
- Capacité à justifier économiquement l'équipe IA/outils
- Identification des applications sous-utilisées nécessitant soit un abandon, soit un effort d'adoption
- Besoin de nettoyer les listes d'utilisateurs actifs et de maintenir des métriques précises
- Introduction d'un prompt Agentique pour calcul automatisé du ROI des nouvelles demandes

## À valider

Boris doit valider la méthodologie finale et les seuils de décision pour arrêter/poursuivre le développement d'une application.
