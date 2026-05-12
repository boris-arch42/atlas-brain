---
type: product-catalog
project: "[[_Index|Lancement Kelly]]"
owner: "[[Boris Arduy]]"
created: 2026-05-10
last-updated: 2026-05-10
status: ready-to-import
tags: [lancement, kelly, produit, zoho, catalogue, boss-energy]
sensitivity: confidential
related-docs: ["[[Scenario A2 - iClosed vers Zoho]]", "[[Closers - Liste opérationnelle Kelly]]", "[[Infrastructure - Setup en cours]]"]
---

# Méthode Boss Energy — Catalogue produit Zoho

> Source of truth pour le produit vendu lors du challenge Kelly Launch (17-25 mai 2026) par les agences externes Tip Talent / Momentum / Next Sales.

## Vue d'ensemble

**Produit unique** : Méthode Boss Energy
**Prix** : 5 700 € HT
**Plans de paiement** : 1 à 6 fois (au choix du client, négocié avec le closer)
**Architecture catalogue Zoho** : 1 produit unique dans le module Products.

## Pourquoi 1 produit unique (pas 6 variantes)

Le produit vendu est le même (la prestation Méthode Boss Energy à 5 700 € HT). Seules les **modalités de paiement** varient — c'est une variable propre à chaque Deal (négociation client), pas une variable produit.

Modèle conceptuel :
- **Produit** (catalogue) = la prestation = constante (5 700 €, accompagnement 6 mois, modules, etc.)
- **Deal** (négociation) = les modalités spécifiques d'une vente = variables (nb mensualités, date démarrage, statut contrat, etc.)

C'est aussi plus simple côté closer :
- Pas de confusion entre 6 variantes au moment du picker produit
- 1 seule option à sélectionner
- Les modalités de paiement se renseignent à part dans les custom fields Deal qu'on a déjà créés (`Nb_mensualites`, `Modalites_paiement`, etc.)

## Catalogue détaillé

| Product Name | Product Code | Unit Price HT | Statut |
|---|---|---|---|
| Méthode Boss Energy | BOSS-ENERGY | 5 700 € | Actif |

**Convention naming SKU** : `BOSS-ENERGY` (simple, mémorisable).

## Description commerciale

Description tirée de la plaquette officielle Méthode Boss Energy (Entrepreneurs.com). Stockée dans le champ "Description" Zoho.

```
MÉTHODE BOSS ENERGY — Programme d'accompagnement entrepreneurial

Construis une activité rentable, crédible et structurée — même si tu pars 
de zéro aujourd'hui.

PLAN DE PAIEMENT : Paiement comptant ou échelonné de 1 à 6 mensualités 
(au choix du client). Total : 5 700 € HT.

INCLUS DANS LE PROGRAMME (6 mois d'accompagnement) :
• Onboarding stratégique personnalisé par IA dès l'entrée
• 24 sessions stratégiques en petits groupes animées par la core team 
  entrepreneurs.com
• 2 rendez-vous individuels avec un expert
• Sessions exclusives avec Kelly Massol tous les 45 jours
• Plateforme de pilotage & IA intégrée
• Bibliothèque business complète
• Accès offert à l'événement SCALE 2027
• Accès à un réseau de partenaires et prestataires sélectionnés

MODULES DU PROGRAMME :
• Module 0 — Fondations psychologiques
• Module 1 — Identité & Positionnement
• Module 2 — L'offre irrésistible
• Module 3 — Présence en ligne & contenu
• Module 4 — Premiers clients
• Module 5 — Système, trafic & consolidation

LIVRABLES CONCRETS :
• Charte entrepreneuriale personnelle
• Carte d'identité de marque validée
• Document d'offre complet
• 12 contenus planifiés + profil optimisé
• Premiers RDV de vente + premier client signé
• Tunnel actif + plan de croissance sur 6 mois

CIBLE : entrepreneurs débutants ou early-stage souhaitant structurer leur 
activité avec une méthode éprouvée.
```

## Référence pricing (calcul des mensualités selon plan)

Pour aide-mémoire des closers lors des négociations :

| Plan | Mensualité | Total |
|---|---|---|
| Comptant (1x) | 5 700 € | 5 700 € |
| 2 fois | 2 850 € / mois | 5 700 € |
| 3 fois | 1 900 € / mois | 5 700 € |
| 4 fois | 1 425 € / mois | 5 700 € |
| 5 fois | 1 140 € / mois | 5 700 € |
| 6 fois | 950 € / mois | 5 700 € |

⚠️ Le total reste constant à **5 700 € HT** (pas de majoration pour fractionnement).

## Procédure d'import dans Zoho

### Étape 1 — Permissions Sales External (à valider AVANT l'import)

Setup → Users and Control → Profiles → **Sales External** → Module Permissions → **Products** :

| Permission | Sales External |
|---|---|
| View | ✅ Yes |
| Read | ✅ Yes |
| Create | ❌ No |
| Edit | ❌ No |
| Delete | ❌ No |

**Justification** : les closers peuvent voir et sélectionner le produit, mais pas en modifier le prix. Évite que des closers négocient des pricings hors politique.

### Étape 2 — Section Product Details sur le Deal

Setup → Modules and Fields → **Deals** → Layout → vérifier que la section **Product Details** est présente.

Si absente, l'ajouter manuellement via le builder de layout (drag-and-drop).

### Étape 3 — Import du CSV catalogue

1. Zoho → naviguer vers le module **Produits**
2. Bouton **Import Products** (icône d'import en haut à droite)
3. Upload le fichier `produits-zoho-boss-energy.csv` (situé dans `/Users/borisarduy/Documents/Atlas-Brain/50_Company/Lancements/Kelly/`)
4. Mapping des colonnes (Zoho devrait auto-matcher) :
   - Product Name → Product Name
   - Product Code → Product Code
   - Unit Price → Unit Price
   - Product Active → Product Active
   - Description → Description
5. Lance l'import
6. Validation : 1 produit créé, 0 échec

Alternative : créer le produit manuellement via l'interface Zoho (Module Produits → + New Product), si l'import CSV pose problème pour 1 seule ligne.

## Usage opérationnel par les closers

Workflow type d'un closer après un call gagné :

1. Ouvre le Deal correspondant dans Zoho (déjà créé automatiquement par le scenario A2)
2. Section **Product Details** du Deal → bouton **+ Add Product**
3. Picker s'ouvre → sélectionne **Méthode Boss Energy** (seule option)
4. Quantité = 1 (par défaut, ne pas modifier)
5. Le prix 5 700 € HT s'auto-remplit
6. Save → le Deal hérite automatiquement de ce montant
7. **Remplir les custom fields Deal** pour le suivi opérationnel :
   - `Nb_mensualites` (nombre) — ex. 3
   - `Modalites_paiement` (currency) — ex. 1 900 € (mensualité calculée)
   - `Date_demarrage` (date)
   - `Statut_contrat` (picklist) → "En préparation" puis "Envoyé" puis "Signé"
   - `Etat_paiements` (picklist) → "Non payé" puis "Acompte" puis "Payé"

## Reporting attendu

Une fois le challenge terminé, Zoho permettra de produire des rapports :

- **Volume de ventes** : nb deals fermés gagnés × 5 700 €
- **Performance par agence** : croisé avec `Agence_Assignee` du Deal
- **Performance par closer** : croisé avec Deal Owner
- **Distribution des plans de paiement** : croisé avec `Nb_mensualites` — combien de ventes comptant vs 3x vs 6x (proxy de la solvabilité de la cible Kelly)
- **Volume ARR généré** : sommation des montants des Deals Kelly fermés

## Liens avec l'écosystème Kelly

- Scenario [[Scenario A2 - iClosed vers Zoho]] crée automatiquement le Deal Kelly dès booking iClosed, mais **ne pré-attribue pas le produit** (V1 simple). Le closer fait cette action manuellement post-call.
- Liste des 38 closers qui vendront ce produit : [[Closers - Liste opérationnelle Kelly]]
- Strategy & architecture globale : [[Architecture - Funnel parallèle closers externes]]

## Roadmap V2 — Pré-attribution automatique du produit ?

Possible amélioration future du scenario A2 : ajouter un appel API Zoho `/Deals_Products` qui pré-attribuerait automatiquement le produit `BOSS-ENERGY` à chaque Deal créé.

**Avantage** : 1 clic en moins pour le closer, totalisation automatique du Deal Amount.

**Inconvénient** : si on ajoute d'autres produits plus tard (upsells, addons), il faudra repenser la logique.

**Décision V1** : pas de pré-attribution. Le closer ajoute le produit consciemment. Acceptable vu qu'il y a un seul produit possible.

## Historique

- **2026-05-10** — Création du catalogue produit Méthode Boss Energy basé sur la plaquette officielle PDF d'Entrepreneurs.com. **1 produit unique** à 5 700 € HT, plans de paiement de 1 à 6 fois gérés via les custom fields du Deal (Nb_mensualites, Modalites_paiement). CSV d'import prêt.
- 2026-05-10 — Version initiale envisageait 6 variantes (1 produit par plan de paiement), pivotée vers 1 produit unique pour simplicité opérationnelle. Plans de paiement = variable Deal, pas variable Produit.
