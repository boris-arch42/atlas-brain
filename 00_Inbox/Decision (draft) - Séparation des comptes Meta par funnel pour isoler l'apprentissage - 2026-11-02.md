---
type: decision
statut: draft
date: 2026-11-02
source: jarvis
call: "[[2026-11-02 - Kickoff Mediabuy - Sommet IA des E]]"
tags: [decision, draft]
---

# Séparation des comptes Meta par funnel pour isoler l'apprentissage

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Les campagnes événementielles et evergreen partagent actuellement le même compte Meta (USD3), ce qui crée une contamination des données : les pixels et l'historique d'optimisation des événements biaisent les performances des campagnes evergreen, et vice-versa. Les audits ont montré des avis contradictoires sur ce qui fonctionne, rendant difficile l'identification des vrais leviers.

## Décision

- **Séparation nette des comptes** : utiliser USD4/USD5 pour les campagnes événement Sommet IA, conserver USD3 pour l'evergreen (LM, webinar Anis)
- **Nettoyage radical des pixels** : ne conserver que 2 pixels (événement Join + LM) au lieu de multiples pixels historiques
- **Montée progressive sur USD4** : démarrer à 800€/jour puis monter vers 3-5K€/jour au pic événement, pour tester la capacité de dépense sans risquer USD3
- **Objectif evergreen maintenu** : viser 100K€ dépense evergreen en novembre sur USD3 (actuellement ~45K€/mois)

## Conséquences

**Positif :**
- Tests contrôlés sans biais historiques
- Attribution claire par funnel
- Protection de l'apprentissage evergreen warmé sur USD3
- Possibilité de calibrer indépendamment chaque type de campagne

**Négatif / Vigilance :**
- USD4/5 ont des plafonds plus bas : nécessite une montée en charge progressive et surveillée
- Risque de perte de plafonds si on arrête complètement les dépenses sur un compte déjà warmé
- Complexité accrue de gestion multi-comptes

## Validation

À valider par Boris : cette architecture multi-comptes est-elle alignée avec la stratégie acquisition globale et les objectifs de scalabilité ?
