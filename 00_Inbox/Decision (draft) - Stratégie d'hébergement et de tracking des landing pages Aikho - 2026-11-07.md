---
type: decision
statut: draft
date: 2026-11-07
source: jarvis
call: "[[2026-11-07 - Update Aikho]]"
tags: [decision, draft]
---

# Stratégie d'hébergement et de tracking des landing pages Aikho

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Le lancement commercial d'Aikho nécessite des landing pages optimisées pour la conversion, avec capacité de tester rapidement différentes variantes (CTA, couleurs, messages). Le tracking UTM et l'analytics doivent être préservés pour mesurer l'efficacité des campagnes.

## Décision

- Boris hébergera les landing pages sur un sous-domaine du domaine ICO
- La page d'inscription redirigera vers le domaine ICO pour conserver le tracking UTM
- Les demandes de réservation de démo seront routées vers Arnaud avec notifications configurables
- Tests A/B prioritaires : landing pages orientées "réserver une démo" vs "s'inscrire", car une inscription suivie d'appel convertit mieux qu'une inscription brute

## Conséquences

**Positives :**
- Contrôle total sur les tests A/B et ajustements rapides sans dépendance technique
- Préservation du tracking marketing et de la donnée analytics
- Réduction de friction pour les leads chauds au moment de l'intérêt maximal

**Négatives :**
- Complexité technique légèrement accrue avec redirection cross-domaine
- Nécessite coordination entre équipes Boris et Julien pour la configuration initiale

**À valider par Boris :** Faisabilité technique finale du sous-domaine et configuration du routage des notifications.
