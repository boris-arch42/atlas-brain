---
type: decision
statut: draft
date: 2026-08-24
source: jarvis
call: "[[2026-08-24 - 🧠 Core Meeting]]"
tags: [decision, draft]
---

# Déploiement Data 2.0 : instrumentation complète des funnels et delivery

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

L'organisation souffre de deux problèmes majeurs de données :
- Absence de granularité par funnel liant événements, closers, conversions et revenus
- Données manquantes ou incohérentes sur plusieurs périmètres (communications, evergreen, SDR)
- Impossibilité de calculer CAC/LTV fiables par funnel, ICP ou produit
- Delivery identifiée comme goulot d'étranglement du modèle économique, non instrumentée

Les dashboards actuels offrent des vues générales mais pas actionnables pour itérer semaine après semaine.

## Décision

Lancement du projet « Data 2.0 » pour étendre le tracking du funnel Evergreen à tous les périmètres :

**Périmètre** : tracer leads, appels, annulations, achats et conversions par closer, par événement, par funnel

**Livrables** :
- Dashboards visuels montrant ce qui est bon/moyen/faible pour itération hebdomadaire
- Métriques funnel : audits, appels réservés, non annulés, ventes, revenu par jour
- Taux de conversion par closer pour identification des meilleurs performeurs
- Intégration dépense publicitaire pour ROAS et coût par appel
- Métriques de delivery réconciliées (taux, NPS, sessions livrées, no-show)
- Réconciliation globale permettant calcul CAC/LTV par axe stratégique

**Calendrier de déploiement** :
- Evergreen : 5 septembre 2026
- Webinars : 19 septembre 2026
- Organique : 25 septembre 2026
- Partenaires : 30 septembre 2026
- Livraison globale et réconciliation : 30 septembre 2026

**Rythme de revue** : Boris consacre 5-10 minutes lors des calls hebdomadaires du mardi à la revue des dashboards avec chaque pôle pour alignement données/décisions.

**Responsabilité** : Boris (coordination), Paul (delivery technique), responsables de pôles (validation métriques)

## Conséquences

**Positives** :
- Visibilité complète sur performance par funnel, ICP, closer, événement
- Identification rapide des fuites, bugs et axes d'amélioration
- Calcul fiable CAC/LTV permettant optimisation budgétaire et stratégique
- Instrumentation de la delivery pour réduire friction client et améliorer ops
- Culture data-driven renforcée avec revues hebdomadaires ritualisées

**Risques/contraintes** :
- Charge projet significative sur équipe data (Paul) jusqu'à fin septembre
- Risque de retard si dépendances techniques ou qualité sources bloquent
- Nécessite discipline des pôles pour valider métriques et utiliser dashboards
- Réconciliation des données historiques peut révéler incohérences nécessitant nettoyage

## Validation

À valider par Boris : priorisation ressources équipe data, arbitrages si conflits calendrier, validation dashboards finaux par pôle.
