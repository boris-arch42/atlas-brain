---
type: decision
date: 2026-04-23
status: accepted
deciders: "[[Boris Arduy]]"
domain: ops
impact: high
supersedes: 
superseded-by: 
next-review: 2026-10-23
tags: [atlas-brain, knowledge-management, policy]
confidentiality: private
source: perso
sensitivity: internal
---

# Decision — Atlas-Brain comme dépôt unique de toute info professionnelle

## Contexte

Dans le cadre de ma prise de poste Operating Partner chez Entrepreneurs.com (cf. [[2026-04-30 - Operating Partner chez Entrepreneurs.com]]), la question s'est posée de savoir où stocker les données et notes liées à ce rôle : dans Atlas-Brain (vault personnel) ou dans un système séparé Entrepreneurs.com.

J'opère par ailleurs Mithril, Riven, MTS, Conférences IA. Atlas-Brain est mon "cerveau secondaire" unique et je ne veux pas fragmenter ma réflexion sur plusieurs outils. La continuité de pensée entre ventures (patterns croisés, réutilisation de frameworks, apprentissages transverses) est un asset stratégique personnel que je refuse de sacrifier pour des raisons d'outillage.

## Décision retenue

**Tout va dans Atlas-Brain, sans exclusion.** Y compris les données nominatives salariés, données financières, contrats, évaluations, plans RH sensibles. Pas de workspace séparé Entrepreneurs.com.

## Options rejetées

- **Séparation stricte Atlas-Brain / outils Entrepreneurs.com** : rejetée. Casse l'unicité du cerveau secondaire, force à maintenir deux systèmes, empêche les connexions transverses entre ventures.
- **Atlas-Brain ≠ données identifiantes** (compromis proposé) : rejetée. Même raison : fragmente la réflexion et crée une zone grise constante sur ce qui va où.

## Risques connus et assumés

- **RGPD / données RH** : en tant que possesseur du vault, je deviens de facto responsable de traitement sur des données salariés d'Entrepreneurs.com. DSAR potentiel à gérer si demandé par un salarié.
- **Continuité au départ** : le jour où je quitterai Entrepreneurs.com, je devrai soit purger manuellement tout le contenu lié, soit rester en possession de données qui ne m'appartiennent plus.
- **Partage sélectif rendu plus complexe** : tout partage de dossier Atlas-Brain vers Entrepreneurs.com nécessitera un audit préalable pour éviter les fuites croisées (Mithril / Riven / MTS / autres salariés).
- **Compromission du laptop / sync cloud** : une faille de sécurité expose des données confidentielles multi-entreprises en une seule fois.
- **Double-lien Alec** (cf. [[2026-04-30 - Operating Partner chez Entrepreneurs.com]]) : des notes Entrepreneurs.com sur Alec côtoieront des notes Riven sur Alec dans le même vault. Discipline de tagging critique.

## Mitigations retenues

### 1. Tag `source::` systématique dans le frontmatter
Toute note contenant des données identifiantes ou confidentielles d'une entité tierce doit porter un tag `source` dans son frontmatter. Valeurs acceptées :
- `entrepreneurs-com`
- `mithril`
- `riven`
- `mts`
- `atlas-ventures`
- `conferences-ia`
- `perso` (réflexion personnelle, pas rattachée à une entité)

Permet le filtrage / export / purge ciblée via Dataview quand nécessaire (départ, DSAR, audit avant partage).

### 2. Tag `sensitivity::` pour le niveau de confidentialité
Quatre niveaux :
- `public` : partageable sans restriction (frameworks génériques, DR de politique personnelle non nominatifs).
- `internal` : partageable au sein de l'entité `source` concernée.
- `confidential` : données business sensibles non-nominatives (finances, stratégie, contrats).
- `rh-nominatif` : données identifiantes sur des personnes physiques (salaires, évaluations, plans de sortie, 1-to-1 avec nom).

### 3. Chiffrement au repos du vault
À vérifier : le dossier Atlas-Brain est sur un disque chiffré (FileVault activé sur le Mac).

### 4. Sync cloud sécurisée
À vérifier : si le vault est synchronisé (iCloud / Dropbox / Git), vérifier le chiffrement E2E ou le chiffrement côté client. Si Git privé, vérifier que le repo est bien privé et que les accès sont à jour.

### 5. Aucun partage direct du vault entier
Seuls des exports ciblés et audités (filtrés par `source::` et `sensitivity::`) peuvent sortir. Jamais de partage par lien direct d'un dossier complet sans audit préalable.

## Hypothèses sous-jacentes

**⚠️ Si une de ces hypothèses s'effondre, rouvrir cette décision.**

- **H1** : Je tiendrai effectivement la discipline de tagging `source::` et `sensitivity::` sur **chaque** nouvelle note pertinente. Si dans 3 mois la majorité des notes n'ont pas ces tags, la décision est invalidée dans les faits.
- **H2** : Aucun incident de sécurité (perte de laptop, partage raté, compromission) ne survient pendant la période couverte.
- **H3** : Entrepreneurs.com n'impose pas contractuellement un outil de stockage spécifique pour les données opérationnelles (à vérifier à la prise de poste).
- **H4** : Le volume de données Entrepreneurs.com dans Atlas-Brain reste gérable (pas d'inflation ingérable au point de polluer la recherche / indexation).

## Revue

- **Prochaine revue** : 2026-10-23 (6 mois)
- **Questions à trancher à cette date** :
  - Les tags `source::` et `sensitivity::` sont-ils effectivement appliqués sur toutes les nouvelles notes, ou c'est devenu du laxisme ?
  - Y a-t-il eu un incident (perte de laptop, partage raté, demande légale) qui invaliderait la décision ?
  - Le volume de données Entrepreneurs.com dans Atlas-Brain est-il gérable ou devient-il ingérable ?
  - Le contrat Operating Partner impose-t-il des contraintes de stockage que je n'avais pas anticipées ?

## Historique
- 2026-04-23 — Décision prise et documentée ([[Boris Arduy]])

## Notes liées
- [[2026-04-30 - Operating Partner chez Entrepreneurs.com]] (décision mère qui a déclenché cette réflexion)
