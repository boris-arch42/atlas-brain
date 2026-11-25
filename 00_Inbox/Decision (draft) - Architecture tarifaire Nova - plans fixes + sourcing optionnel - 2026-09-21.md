---
type: decision
statut: draft
date: 2026-09-21
source: jarvis
call: "[[2026-09-21 - Meeting Affiliation - Aikho]]"
tags: [decision, draft]
---

# Architecture tarifaire Nova : plans fixes + sourcing optionnel

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Nova (Aikho) doit définir sa stratégie tarifaire avant d'implémenter l'intégration PSP et le programme d'affiliation. L'équipe a analysé l'économie unitaire (coût moyen 0,50$/candidat cible 0,20-0,30$), les taux de conversion par canal (10% email vs 50-60% LinkedIn), et les coûts de sourcing (0,20$/email trouvé, taux de succès 20%).

## Décision

1. **Plans fixes simples au lancement** : 2-3 paliers fixes (exemples discutés : 200€ et 500€/mois) plafonnant postes ouverts simultanément et volumes de candidats, avec petite remise d'échelle (~20% entre paliers)
2. **Sourcing packagé en option** : inclure un minimum de sourcing (15-20 invitations) dans le plan entrée de gamme, proposer des tiers « sourcing plus » en add-on optionnel. Le sourcing complet doublerait environ le prix du package.
3. **Trois piliers produit** : structurer l'offre autour de l'évaluation en entretien (cœur), du sourcing (identification + outreach), et des fonctionnalités post-évaluation.
4. **Coûts suivis par tenant** : appliquer un buffer de 20% sur les coûts par tenant, surveiller les tenants au-dessus du seuil, alertes automatisées.
5. **Métriques clés** : candidat défini comme utilisateur connecté (pas « entretien »), mesurer le drop-off connexion→entretien terminé par canal chaque semaine.

## Conséquences

- Permet de lancer rapidement avec un pricing simple sans surinvestir dans la sophistication tarifaire
- Le sourcing optionnel évite de faire payer tous les clients pour une fonction qu'ils n'utilisent pas tous
- Nécessite de finaliser les prix exacts, les limites par plan et la config PSP avant automatisation complète
- Le positionnement valeur vs LinkedIn (2-3$/clic) et chasseurs de têtes doit être formalisé dans les supports commerciaux
- Le suivi de coût par tenant et les alertes deviennent critiques pour préserver les marges
- Les plans variables et la sophistication tarifaire sont repoussés post-lancement

## Statut

**À valider par Boris** — Finalisation attendue pour la réunion HLD du 8 octobre 2026, avant levée de fonds visée Noël 2026.
