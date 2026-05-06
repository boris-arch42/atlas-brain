---
type: sop
domain: People-RH
owner: "[[Boris Arduy]]"
status: draft
last-reviewed: 2026-05-06
frequency: par-recrutement
related-decisions:
  - "[[2026-04-30 - Operating Partner chez Entrepreneurs.com]]"
tags: [recrutement, hiring, aikho, process, heads, entrepreneurs-com]
source: entrepreneurs-com
sensitivity: internal
---

# SOP — Process recrutement Aikho v1

## Pourquoi ce process existe

Le recrutement chez Entrepreneurs.com souffrait de deux pathologies classiques : (1) les fiches de poste étaient rédigées par les RH à partir de briefs flous des heads, ce qui produisait des annonces génériques peu différenciantes ; (2) le pipeline était fragmenté entre plusieurs outils, créant des pertes en ligne et des SLA qui dérivaient.

Ce process consolide **tout le cycle dans Aikho** et **rend la fiche de poste au head** — qui sait mieux que personne ce qu'il cherche. L'IA fait le travail rédactionnel, le head fait l'arbitrage, Boris valide la cohérence, le pipeline avance dans un seul outil.

## Quand le déclencher

À chaque ouverture de poste validée par le head et l'Operating Partner. Pas de poste ouvert sans étape 1 documentée.

## Qui est impliqué

- **Owner du process** : [[Boris Arduy]] (Operating Partner)
- **Driver d'un recrutement donné** : le head qui ouvre le poste
- **Validation fiche de poste** : Boris (J+2 max)
- **Support sourcing/screening** : RH (si dispo) + Aikho
- **Outil unique** : [[Aikho]]

## Étapes

### 1. Expression du besoin — J+0
- **Owner** : Head
- **Action** : remplir le template `Business-Case-Recrutement.md` (cf. `_Templates/`)
- **Livrable** : 1 page max — contexte équipe, scope du rôle, séniorité visée, budget, urgence
- **Output attendu** : doc partagé à Boris pour validation du go/no-go

### 2. Création de la fiche de poste — J+1
- **Owner** : Head
- **Outil** : Aikho (génération + itération)
- **Action** : alimenter Aikho avec le business case → générer une première version → itérer en conversationnel ("rends-le plus senior", "ajoute la dimension internationale", "supprime cette responsabilité") → personnaliser au ton Entrepreneurs.com
- **Livrable** : fiche de poste finalisée dans Aikho, prête à valider
- **Temps estimé** : 15 min première fois, 5 min ensuite

### 3. Validation — J+2
- **Owner** : Boris (Operating Partner)
- **Outil** : review async dans Aikho
- **Critères** :
  - Cohérence niveau / scope / fourchette salariale
  - Alignement avec le scope réel de l'équipe
  - Ton et formulation employer brand Entrepreneurs.com
  - Absence de red flags (responsabilités contradictoires, séniorité incohérente, etc.)
- **Output** : approbation ou demande de retouche (1 round max attendu)

### 4. Publication, sourcing et screening — J+3 à J+10
- **Owner** : Head + RH
- **Outil** : Aikho (publication multi-jobboards, sourcing, screening, scoring)
- **Action** : publier la fiche, lancer le sourcing, suivre le pipeline candidats dans Aikho
- **Livrable** : shortlist de candidats qualifiés à présenter au head pour entretiens finaux

### 5. Entretiens finaux et décision — J+10 à J+20
- **Owner** : Head + 1 tiers (peer head ou Boris pour les rôles seniors)
- **Outil** : suivi pipeline et notes dans Aikho
- **Livrable** : décision d'embauche + offre

## SLA récapitulatif

| Étape | Owner | SLA |
|---|---|---|
| 1. Besoin | Head | J+0 |
| 2. Fiche poste | Head | J+1 |
| 3. Validation | Boris | J+2 |
| 4. Sourcing & screening | Head + RH | J+3 → J+10 |
| 5. Entretiens & décision | Head + tiers | J+10 → J+20 |

**Cycle total cible** : 20 jours du besoin à la décision.

## Pièges connus

- **Le head saute l'étape 1** parce que "le besoin est évident" → résultat : fiche de poste qui dérive en étape 2 et validation refusée. Toujours formaliser le business case, même en 5 lignes.
- **Le head sur-itère sur Aikho** en cherchant la version parfaite → 3 itérations max, ensuite c'est Boris qui tranche en validation. La fiche n'a pas besoin d'être parfaite, elle doit être *juste*.
- **Validation traitée comme une formalité** → Boris doit *vraiment* lire et challenger. Si la fiche passe en automatique, le process devient théâtral.
- **Sourcing qui démarre avant validation** → coûte des candidats grillés sur une fiche qui change. Pas de publication tant que J+2 n'est pas validé.
- **Aikho utilisé comme un wizard sans réflexion** → l'IA produit ce qu'on lui donne. Si l'input du head est pauvre, l'output sera pauvre. Le business case en étape 1 n'est pas optionnel.

## Ressources liées

- Template : `_Templates/Business-Case-Recrutement.md`
- Diagramme du flow : voir `00_Inbox/2026-05-06 - Call Heads — Process recrutement Aikho.md`
- Outil : [[Aikho]]

## Décisions stratégiques rattachées

- [[2026-04-30 - Operating Partner chez Entrepreneurs.com]]

## Historique

- 2026-05-06 — Création v1, présentation aux heads en call de 1h ([[2026-05-06 - Call Heads — Process recrutement Aikho]])
