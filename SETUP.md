# 🔧 SETUP — Installation et configuration

Guide pas-à-pas pour mettre en route Atlas-Brain, de zéro à opérationnel avec Claude connecté.

Temps estimé total : **45 min à 1h**.

---

## Étape 1 — GitHub privé (5 min)

1. Sur github.com, créer un **nouveau repo privé** : `atlas-brain` (ou nom de ton choix).
2. **Ne pas initialiser** avec README / gitignore / license — le vault en contient déjà.
3. Noter l'URL SSH : `git@github.com:TON_USER/atlas-brain.git`

---

## Étape 2 — Push initial du vault (5 min)

Dans le dossier où tu as dézippé `Atlas-Brain/` :

```bash
cd Atlas-Brain
git init
git add .
git commit -m "Initial vault structure"
git branch -M main
git remote add origin git@github.com:TON_USER/atlas-brain.git
git push -u origin main
```

Si tu n'as pas de clé SSH configurée, utilise l'URL HTTPS + un Personal Access Token.

---

## Étape 3 — Installer Obsidian (2 min)

1. Télécharger depuis [obsidian.md](https://obsidian.md)
2. Lancer l'app
3. `Open folder as vault` → sélectionner le dossier `Atlas-Brain`
4. Accepter les permissions de lecture/écriture

---

## Étape 4 — Installer les plugins (10 min)

`Settings → Community plugins → Turn on community plugins` puis `Browse`.

Installer et activer ces 5 plugins :

### 1. Templater
- Configurer : `Settings → Templater`
- `Template folder location` : `_Templates`
- `Trigger Templater on new file creation` : activer
- `Enable folder templates` : activer (optionnel mais utile)

### 2. Dataview
- Pas de config nécessaire, les requêtes dans les MOC fonctionneront automatiquement.
- Vérifier que `Enable JavaScript queries` est activé si tu veux utiliser dataviewjs plus tard.

### 3. Obsidian Git
- `Settings → Obsidian Git`
- `Vault backup interval (minutes)` : 30 (commit automatique toutes les 30 min)
- `Auto pull interval (minutes)` : 30
- `Auto-push after commit` : activer
- Authentification : même méthode que l'étape 2 (SSH ou HTTPS+PAT)

### 4. Local REST API
- Utile uniquement si tu veux utiliser le MCP Obsidian avancé (cf. Étape 6, Option B)
- Si tu l'installes : `Settings → Local REST API` → activer HTTP (port 27123 par défaut)
- Noter la clé API qui est générée

### 5. Excalidraw
- Pas de config nécessaire. Créer un fichier `.excalidraw` via Command Palette (`Cmd/Ctrl+P` → `Excalidraw: Create new drawing`).

---

## Étape 5 — Tester les templates (5 min)

Vérifier que Templater fonctionne :

1. `Cmd/Ctrl + P` → taper "Templater: Create new note from template"
2. Choisir `Decision`
3. Saisir un titre test (ex : "Test initial")
4. Le fichier doit être créé dans `20_Decisions/2026/` avec la date du jour en préfixe et le front-matter prérempli.

Si ça fonctionne → supprime la note de test. Si ça ne fonctionne pas → revérifie le dossier template dans Settings Templater.

---

## Étape 6 — Connecter Claude (15 min)

Deux options, par ordre de simplicité.

### Option A — Filesystem MCP (recommandé pour commencer)

**Prérequis** : Claude Desktop installé ([claude.ai/download](https://claude.ai/download)).

1. Ouvrir le fichier de config MCP de Claude Desktop :
   - **macOS** : `~/Library/Application Support/Claude/claude_desktop_config.json`
   - **Windows** : `%APPDATA%\Claude\claude_desktop_config.json`

2. Ajouter (ou compléter) la configuration :

```json
{
  "mcpServers": {
    "atlas-brain": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/chemin/absolu/vers/Atlas-Brain"
      ]
    }
  }
}
```

⚠️ Remplace `/chemin/absolu/vers/Atlas-Brain` par ton vrai chemin (ex : `/Users/boris/Documents/Atlas-Brain`).

3. Redémarrer Claude Desktop (quitter complètement, relancer).

4. Tester : dans un nouveau chat, demander _"Liste les fichiers dans mon vault Atlas-Brain"_. Claude doit les lister.

### Option B — MCP Obsidian dédié (avancé)

Utilise l'API Local REST d'Obsidian pour un accès plus "conscient" du vault (liens, templates respectés).

1. Activer le plugin Local REST API (étape 4)
2. Installer un serveur MCP Obsidian comme [mcp-obsidian](https://github.com/smithery-ai/mcp-obsidian) ou équivalent
3. Dans `claude_desktop_config.json` :

```json
{
  "mcpServers": {
    "obsidian": {
      "command": "npx",
      "args": ["-y", "@smithery-ai/mcp-obsidian"],
      "env": {
        "OBSIDIAN_API_KEY": "TA_CLE_LOCAL_REST_API",
        "OBSIDIAN_HOST": "127.0.0.1:27123"
      }
    }
  }
}
```

4. Redémarrer Claude Desktop.

**Recommandation** : commence par l'Option A. Tu passes à B seulement si tu as besoin des fonctions avancées.

---

## Étape 7 — Premier run (5 min)

1. Ouvre `00_Inbox/START-HERE.md` dans Obsidian → lis-le.
2. Crée ta première note de capture : `00_Inbox/Diag - Ce qui me frappe comme étrange ou inefficace.md` et commence à écrire.
3. Dans Claude Desktop, nouveau chat, teste :

> "Lis le fichier README.md de mon vault et résume-moi les conventions principales."

Si Claude répond correctement avec les conventions du README, l'intégration fonctionne.

---

## Étape 8 — Backup et multi-machines (optionnel, 5 min)

Grâce à Git, tu peux cloner le vault sur une autre machine :

```bash
git clone git@github.com:TON_USER/atlas-brain.git
```

Puis ouvrir le dossier comme vault dans Obsidian sur la nouvelle machine, activer les mêmes plugins, et c'est synchro.

⚠️ **Évite d'éditer sur 2 machines en même temps** sans pull/push au milieu. Git Obsidian gère les conflits mais ce n'est pas du temps réel comme Notion.

---

## Dépannage rapide

### Templater ne crée pas les fichiers au bon endroit
→ Vérifier `Settings → Templater → Template folder location = _Templates` (sans slash, sans point).

### Dataview affiche des erreurs dans les MOC
→ Attendre quelques secondes après ouverture du vault, l'index se construit.
→ Vérifier que le front-matter des notes est bien au format YAML valide (3 tirets au début et à la fin).

### Claude Desktop ne voit pas le vault
→ Redémarrer complètement l'app (Quit, pas juste close window).
→ Vérifier le chemin absolu dans `claude_desktop_config.json`.
→ Dans les logs Claude Desktop, chercher les erreurs MCP.

### Git Obsidian ne pousse pas
→ Vérifier l'authentification SSH/HTTPS en ligne de commande d'abord.
→ Regarder le panneau de logs du plugin (`Settings → Obsidian Git → Open log`).

---

## Prochaine étape

Une fois tout ça en place, va dans `00_Inbox/START-HERE.md` et suis la routine pré-prise de poste.
