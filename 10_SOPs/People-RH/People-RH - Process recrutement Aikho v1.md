---
type: sop
domain: People-RH
owner: "[[Boris Arduy]]"
status: active
last-reviewed: 2026-05-06
frequency: par-recrutement
related-decisions:
  - "[[2026-04-30 - Operating Partner chez Entrepreneurs.com]]"
linked-retro: "[[2026-05-06 - Retro Call Heads Process recrutement Aikho]]"
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
- **Course à la complétude 100%** → à partir de 40% la fiche est déjà très exploitable. Au-delà de 80%, les filtres deviennent contre-productifs (peu de candidats, top 0,01% inaccessible). Sweet spot : 50-70%.

## Exercices techniques (étape 5 enrichie)

Pour les recrutements nécessitant un test pratique (intervient après l'interview IA, sur le top 3% des candidats) :

1. **Pré-requis** : exercice standardisé par type de poste (expert, coach, intégrateur, sales, SDR, CM, etc.) — réutilisable
2. **Envoi** : via la fonction email d'Aikho avec Loom d'instructions du head + lien vers formulaire de retour
3. **Analyse** : automation IA (Claude ou équivalent) qui scoree le retour
4. **Intégration** : score remonté dans les notes du candidat dans Aikho → corrélation avec score interview
5. **Décision** : entretien final humain sur la base interview + exercice + culture fit

**Règle d'or** : standardiser à 100% pour les recrutements récurrents. L'intervention humaine ne doit se concentrer que sur le top 3%.

## Cas particuliers et gouvernance

### Heads absents lors d'un onboarding outil ou d'une mise à jour de process
Visionnage du replay obligatoire dans les 48h + 1-1 court avec Boris pour valider la compréhension et récupérer leurs engagements (mêmes deadlines que les présents). Pas de tolérance prolongée — risque de créer un système à deux vitesses.

### Aikho source unique de vérité
Mandaté explicitement par Alec le 6 mai 2026 : *"100% de tous les entretiens, de tous les recrutements, de toutes les fiches de poste à partir du 7 mai 2026 doivent passer via ce process et via cette plateforme."* Pas de fiche publiée ailleurs, pas de pipeline tracké hors Aikho, pas de double saisie.

### Branding asset central
Les formulations de mise en avant entrepreneurs.com (valeurs, culture, what you get) sont configurées dans le cerveau central d'Aikho par Boris. Les heads héritent automatiquement de ces éléments quand ils créent une fiche — ils n'ont pas à les ré-écrire et ne doivent pas les contredire dans leurs propres formulations.

### Calibrage avec profils internes performants (à tester)
Idée issue du call (Sabrina) : faire passer un CV de collaborateur historiquement performant dans Aikho pour mesurer son score sur la fiche cible → sert soit à valider la fiche, soit à révéler des skills implicites à ajouter. À instruire dès les premiers recrutements post-7 mai.

## Ressources liées

- Template : `_Templates/Business-Case-Recrutement.md`
- Diagramme du flow : voir `00_Inbox/2026-05-06 - Call Heads — Process recrutement Aikho.md`
- Outil : [[Aikho]]

## Décisions stratégiques rattachées

- [[2026-04-30 - Operating Partner chez Entrepreneurs.com]]

## Historique

- 2026-05-06 — Création v1, présentation aux heads en call de 1h ([[2026-05-06 - Call Heads — Process recrutement Aikho]])
- 2026-05-06 — Passé en `active` après call. Ajouts post-call : section Exercices techniques, section Cas particuliers et gouvernance, piège "course à la complétude" ([[2026-05-06 - Retro Call Heads Process recrutement Aikho]])
- Prochaine révision prévue : 20 mai 2026 (après retours Loom des heads et point Marrakech)
