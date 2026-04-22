# Atlas Brain — Cerveau central Entrepreneurs.com

> **Objectif** : centraliser les SOPs opérationnels et la mémoire stratégique C-level de l'entreprise, dans un système lisible par un humain ET par une IA (Claude).
>
> **Principe** : un savoir qui n'est pas écrit n'existe pas. Un savoir écrit mais non lié est à moitié perdu.

---

## Pour qui, pour quoi

- **Pour les C-level** : mémoire institutionnelle qui survit aux départs, onboarding accéléré, détection de décisions contradictoires, retour d'expérience sur les paris passés.
- **Pour les managers et opérationnels** : SOPs à jour, réponses aux questions récurrentes, contexte stratégique derrière chaque process.
- **Pour l'IA (Claude)** : base de connaissance structurée, requêtable, avec liens sémantiques explicites.

---

## Les deux briques centrales

### 1. SOPs (`10_SOPs/`)
Le "comment on fait". Un SOP = un process documenté avec son owner, ses étapes, ses pièges connus, sa dernière revue.

### 2. Decision Records (`20_Decisions/`)
Le "pourquoi on l'a décidé". Inspirés des ADR (Architecture Decision Records) du monde tech. Chaque décision structurante capture : contexte, options envisagées, choix retenu, hypothèses sous-jacentes, critères de succès.

**Ces deux briques sont reliées** : un SOP "Recrutement Sales" doit pointer vers la décision "Profil commercial cible Q2 2026". Sans ce lien, le SOP est du folklore.

---

## Arborescence

```
00_Inbox/           Captures brutes non triées. Vide régulièrement.
10_SOPs/            Standard Operating Procedures par domaine.
20_Decisions/       Decision Records C-level par année.
30_Frameworks/      Méthodes et modèles mentaux maison.
40_People/          Trombinoscope, expertises, rôles.
50_Company/         Vision, mission, métriques, positionnement, histoire.
60_Retros/          Post-mortems, leçons, bilans de projets.
70_Watch/           Veille concurrents, marché, tendances.
90_Archive/         Notes obsolètes conservées pour historique.
_Templates/         Templates Templater pour nouveaux contenus.
```

---

## Conventions

### Nommage des fichiers

- **Decisions** : `YYYY-MM-DD - Titre court.md`  
  → `2026-05-03 - Abandon du canal outbound chasseurs de tête.md`
- **SOPs** : `Domaine - Nom du process.md`  
  → `Sales - Qualification BANT d'un lead entrant.md`
- **Frameworks** : `Nom du framework.md`
- **People** : `Prénom Nom.md`
- **Retros** : `YYYY-MM-DD - Nom du projet.md`

### Liens

**Toujours préférer `[[wikilink]]` à la référence texte.** L'intérêt du vault vient des liens, pas du contenu isolé.

```markdown
Cf. décision [[2026-05-03 - Abandon du canal outbound chasseurs de tête]]
Owner : [[Boris Dupont]]
Process rattaché : [[Sales - Qualification BANT d'un lead entrant]]
```

### Tags

Minimaux. Le front-matter YAML fait le gros du travail. Si tu hésites à créer un tag, ne le crée pas — fais un lien vers une note MOC à la place.

### Front-matter

Toutes les notes "de contenu" (pas l'Inbox) ont un front-matter YAML. C'est ce qui permet à Dataview et à Claude de requêter proprement. Les templates le préremplissent.

### Langue

Français par défaut (contexte entreprise). Anglais accepté pour les frameworks issus de littérature anglo-saxonne.

---

## Workflow quotidien

### Capture (30 sec)
Tu as une info, une question, une décision qui vient d'être prise ? → note rapide dans `00_Inbox/`. Ne cherche pas à bien structurer. L'objectif c'est de ne pas perdre.

### Triage (2x/semaine, ~15 min)
Tu ouvres l'Inbox, tu traites chaque note :
- Poubelle si périmé
- Déplacement dans le bon dossier avec application du template
- Ajout de liens vers les notes existantes

### Revue trimestrielle (1h)
- SOPs : chaque owner revoit ses SOPs, met à jour `last-reviewed`, archive les périmés.
- Decisions "high impact" : revue contre les critères de succès. Si hypothèses cassées → rouvrir la décision.

---

## Règles de gouvernance non-négociables

1. **Pas de décision C-level sans Decision Record.** Zéro exception.
2. **Un SOP sans `owner` est mort.** Pas d'owner = pas de SOP.
3. **Un SOP qui n'a pas été revu depuis 6 mois passe en statut `stale`** (requête Dataview dans `10_SOPs/_MOC.md`).
4. **La section "Pièges connus" d'un SOP n'est jamais vide.** Si elle l'est, le SOP n'est pas fini.
5. **La section "Hypothèses sous-jacentes" d'une Decision n'est jamais vide.** C'est elle qui permet de savoir quand rouvrir la décision.

---

## Plugins Obsidian requis

À installer au premier lancement :

| Plugin | Rôle |
|---|---|
| **Templater** | Templates dynamiques avec variables (date, titre, prompts) |
| **Dataview** | Requêtes SQL-like sur le front-matter (utilisé dans les MOC) |
| **Obsidian Git** | Versioning auto + push GitHub |
| **Local REST API** | Exposition API pour connexion Claude via MCP Obsidian |
| **Excalidraw** | Schémas et diagrammes (org chart, process flow) |

Voir `SETUP.md` pour la configuration détaillée.

---

## Connexion Claude

Deux options décrites dans `SETUP.md` :

- **Filesystem MCP** (simple) : Claude Desktop lit/écrit directement les `.md`.
- **MCP Obsidian** (avancé) : utilise l'API Local REST, respect des liens et templates.

Le vault est conçu pour que Claude puisse :
- Chercher dans les SOPs et Decisions ("Quelles décisions concernent le pricing ?")
- Rédiger de nouvelles notes dans le bon format (templates)
- Détecter les incohérences entre SOPs et Decisions
- Préparer les revues trimestrielles (notes stale, décisions à revoir)

---

## Par quoi commencer

Si c'est ton premier jour avec le vault :

1. Lis `00_Inbox/START-HERE.md`
2. Remplis les 4 fichiers de `50_Company/` (Vision, Metrics, Positioning, History)
3. Ajoute ta fiche dans `40_People/`
4. Capture ta première décision dans `20_Decisions/2026/`
5. Documente ton premier SOP dans `10_SOPs/`

Pas besoin d'être exhaustif. La valeur vient de l'usage quotidien, pas du remplissage initial.
