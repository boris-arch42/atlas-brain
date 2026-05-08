---
type: technical-setup-log
project: "[[_Index|Lancement Kelly]]"
owner: "[[Boris Arduy]]"
created: 2026-05-08
last-updated: 2026-05-08
status: en-cours
tags: [lancement, kelly, infrastructure, technical-setup, zoho, short-io, tally, make]
sensitivity: confidential
---

# Infrastructure Lancement Kelly — Log de setup

> Document de suivi du build de l'infrastructure technique du funnel parallèle Kelly. Mise à jour au fur et à mesure de la construction des briques.

## État global au 8 mai 2026

| Brique | Statut | Notes |
|---|---|---|
| Tally → Google Sheets (Make) | ✅ Fonctionnel | Scenario Make en place, données stockées dans Sheet de tracking |
| Google Sheet de tracking | ✅ Créé | ID : `1XTVJvuabrKtScKaLNFl9bBo3n-75Gz7O2C3WyU0H0aI` |
| Zoho CRM — compte | ✅ Créé | Plan Professional Trial 30 jours, expire ~7 juin 2026 |
| Zoho CRM — Profiles (4) | ✅ Créés | Administrator, Manager, Team Leader, Sales External |
| Zoho CRM — Roles (7) | ✅ Créés | Hiérarchie 4 niveaux, étanchéité par agence |
| Zoho CRM — Data Sharing | ✅ Configuré | Tous modules critiques en mode Privé |
| Zoho CRM — Custom fields | 🟡 En attente | Bloqué tant que pas d'accès admin HubSpot |
| Zoho CRM — Pipeline Deal | 🟡 En attente | Idem, à reproduire à l'identique de HubSpot |
| Short.io — compte | ✅ Créé | Plan Free, domaine `kelly-ec.short.gy` |
| Short.io — Splitter | ✅ Créé et testé | Lien `kelly-ec.short.gy/kelly-route`, routing 25/50/25 |
| Short.io — Forward parameters | ✅ Validé | Fonctionne par défaut, pas d'activation manuelle nécessaire |
| iCloseit — calendriers (3) | 🔴 À faire | Chantier suivant |
| Make scenario A2 (booking → Zoho) | 🔴 À faire | Dépend de iCloseit + Zoho custom fields |
| Make scenario A5 (Zoho → HubSpot) | 🔴 À faire | Dépend de HubSpot |
| Adresses mail dédiées (~70) | 🔴 À faire | Sujet IT, à cadrer cette semaine |

## Détail Zoho CRM

### Configuration générale
- **URL d'accès** : compte Zoho EU (zoho.eu)
- **Édition** : Professional Trial 30 jours
- **Devise** : EUR
- **Fuseau horaire** : Europe/Paris
- **Format date** : DD/MM/YYYY
- **Format heure** : 24h
- **Business Hours** : Lundi-Samedi 06:00-23:00

### Profiles créés

| Profile | Description | Cible utilisateurs |
|---|---|---|
| Administrator | Tous droits (par défaut Zoho) | Boris uniquement |
| Manager | Voit tout son périmètre, mass actions, exports, rapports | Aziz, Lucas, Romain, Axel, Hélène |
| Team Leader | Voit son équipe, modifications individuelles, pas de mass actions | Team leaders agences, Closer Success Manager, Julien (EC) |
| Sales External | Voit ses propres deals uniquement, restrictions fortes (pas d'export, pas de mass action, pas de suppression, pas de sync contacts persos) | Tous les closers et setters externes |

### Hiérarchie de Roles

```
Entrepreneurs.com
└── Boris (Operating Partner)
    └── Aziz (Head of Sales EC)
        ├── Manager Tip Talent
        │   └── Sales Tip Talent
        ├── Manager Momentum
        │   └── Sales Momentum
        └── Manager Axel
            └── Sales Axel
```

### Data Sharing Settings

| Module | Mode |
|---|---|
| Prospects | Privé |
| Comptes | Privé |
| Contacts | Privé |
| Affaires | Privé |
| Tâches | Privé |
| Réunions | Privé |
| Appels | Privé |
| Visites | Privé |
| E-mails | Privé |
| Produits | Public (lecture seule) — catalogue partagé |

## Détail Short.io

### Configuration

- **URL d'accès** : app.short.io
- **Compte** : boris@entrepreneurs.com
- **Plan** : Gratuit (à upgrader vers Team avant le 14 mai)
- **Domaine** : `kelly-ec.short.gy` (gratuit fourni par Short.io)
- **Domaine custom prévu** : à configurer plus tard via DNS entrepreneurs.com

### Lien splitter principal

- **URL** : `https://kelly-ec.short.gy/kelly-route`
- **Type** : Test A/B (3 destinations)
- **Pondération configurée** :
  - Page d'origine (Tip Talent) : 25%
  - Variante 1 (Momentum) : 50%
  - Variante 2 (Axel) : 25%

### URLs cibles actuelles (temporaires pour tests)

| Destination | URL temporaire | URL définitive prévue |
|---|---|---|
| Tip Talent | `https://httpbin.org/get?destination=tiptalent` | URL iCloseit Tip Talent (à créer) |
| Momentum | `https://httpbin.org/get?destination=momentum` | URL iCloseit Momentum (à créer) |
| Axel | `https://httpbin.org/get?destination=axel` | URL iCloseit Axel (à créer) |

### Tests effectués

**Test 1 — Routing pondéré (8 mai 2026)**
- 20 clics manuels en navigation
- Résultat : 5 Tip Talent / 7 Momentum / 8 Axel
- Conclusion : routing fonctionnel, écart cohérent avec variance statistique sur petit échantillon. Convergence attendue vers 25/50/25 sur volumes >100.

**Test 2 — Forward des paramètres URL (8 mai 2026)**
- URL test : `https://kelly-ec.short.gy/kelly-route?email=test@example.com&name=Boris+Test&phone=%2B33624847394`
- Résultat httpbin.org confirmé : tous les paramètres (`email`, `name`, `phone`) sont transmis intacts à l'URL cible
- Conclusion : forward fonctionne **par défaut**, aucune activation manuelle nécessaire

### Observations

- Lors du premier test, les URLs cibles entrepreneurs.com (`/kelly-test-tiptalent` etc.) déclenchaient une redirection serveur 302 vers `/welcome` ou `/` (pages 404 redirigées). Ce comportement faisait perdre les paramètres URL et empêchait de valider le forward.
- Solution adoptée : utilisation temporaire de httpbin.org comme URLs cibles pour valider le forward proprement. À remplacer par les vraies URLs iCloseit dès qu'elles seront créées.

## Décisions prises pendant le setup

| Date | Décision | Rationale |
|---|---|---|
| 8 mai | Approche "copie absolue HubSpot → Zoho" pour custom fields et pipeline | Évite les erreurs de mapping lors du push Zoho → HubSpot |
| 8 mai | Profiles Zoho construits par clonage en cascade (Standard → Manager → Team Leader → Sales External) | Préserve les ajustements de sécurité à chaque niveau |
| 8 mai | Désactivation des sync Google Contacts + Microsoft Contact sur tous profiles externes | Éviter fuite de données client dans les outils persos des sales partenaires |
| 8 mai | Sales External : pas de droit de suppression, ni d'export, ni de mass actions, ni de sync agenda perso | Sécurité maximale sur le profile le plus diffusé |
| 8 mai | Short.io plan Gratuit pour setup et tests, upgrade Team avant 14 mai | Pas de besoin Team avant les tests à blanc et le go-live |

## Points en attente

### Bloqué par l'accès HubSpot (attendu aujourd'hui 8 mai)

1. Audit complet des custom fields HubSpot (Contact / Deal / Company)
2. Cartographie dans un Sheet de référence
3. Reproduction à l'identique dans Zoho
4. Reproduction du pipeline Deal (stages + probabilités + validation rules)
5. Reproduction des picklists et leurs valeurs

### Indépendant de HubSpot (chantiers suivants)

6. Création des 3 calendriers iCloseit (un par agence)
7. Récupération des URLs iCloseit pour les injecter dans Short.io (remplacement des httpbin.org temporaires)
8. Setup ~70 adresses mail dédiées (40 closers + 20 setters + 3 head of sales + 3 managers + ~5 admin)
9. Configuration domaine custom Short.io via DNS entrepreneurs.com (transmettre les valeurs DNS à la personne qui gère le domaine)
10. Activation numéro de téléphone Short.io (warning affiché, non bloquant pour l'instant)

## Prochaine étape immédiate

**Configuration iCloseit** (si pas encore d'accès HubSpot) ou **audit HubSpot** (si accès reçu).

## Liens

- [[_Index|Hub projet Kelly]]
- [[Architecture - Funnel parallèle closers externes]]
- [[Partenaires - Vue d'ensemble 3 agences]]
