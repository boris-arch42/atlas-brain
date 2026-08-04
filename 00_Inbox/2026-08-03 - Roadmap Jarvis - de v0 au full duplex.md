---
type: note
date: 2026-08-03
source: jarvis
owner: "[[Boris Arduy]]"
tags: [jarvis, roadmap, atlas, cockpit]
---

# 🎩 Roadmap Jarvis — étapes concrètes

> Capture déposée par Claude (session Cowork du 03/08). Référence complète : blueprint HTML du 23/07 + `JARVIS.md` dans le repo ops-cockpit. À trier vers 05_Projects si tu en fais un projet suivi.

## Phase 0 — aujourd'hui (15 min) · goûter au résultat
- [ ] Activer le mode vocal de l'app Claude (FR, Opus/Sonnet) et parler à Notion/Agenda via connecteurs → c'est le niveau de confort minimum que Jarvis devra dépasser.

## Phase 1 — cette semaine (~2 h) · boucle vocale + interconnexion vivante
- [ ] Nettoyer les 5 projets du **seed** dans la base cockpit (garder uniquement le réel)
- [ ] `npm run atlas:sync:dry` puis `npm run atlas:sync` (depuis `ops-cockpit/ops-cockpit`) → vérifier cartes + [[🗼 Tour de contrôle - Projets en cours]]
- [ ] Poser `cockpit_id` sur les cartes non appariées (listées par la sync) · `--creer` pour les projets sans carte
- [ ] Installer la sync auto 7h15 : `cp launchd/*.plist ~/Library/LaunchAgents/ && launchctl load …`
- [ ] Importer `n8n/jarvis-cockpit-mcp.json` dans n8n (credential Postgres pooled + Bearer) → activer → tester `etat_cockpit`
- [ ] Importer `jarvis-v1-telegram.json` (BotFather + credentials + 4 réglages des notes jaunes) → premier échange vocal
- [ ] Ajouter le nœud **MCP Client Tool** à l'agent Jarvis v1 → « Jarvis, l'état du cockpit ? » à la voix
- [ ] Ajouter le serveur MCP cockpit comme connecteur dans Claude desktop

## Phase 2 — semaines 2-3 · mémoire, personnalité, proactivité
- [ ] Créer `85_Jarvis/` dans le vault : `Personnalite.md` (copier le system prompt du workflow et l'affiner), `Regles.md`, `Journal/`
- [ ] n8n : Schedule 7h30 → **brief du matin poussé** en note vocale Telegram (agenda multi-fuseaux + synthèse cockpit + emails saillants)
- [ ] n8n : alerte immédiate si blocage **P0** créé dans le cockpit
- [ ] Étendre les outils de l'agent : Gmail (lecture + brouillons), résumé de replays, relances
- [ ] **Critère de passage** : utiliser Jarvis v1 tous les jours pendant 2 semaines — les usages réels dicteront les outils du daemon

## Phase 3 — mois 1 · v2, le daemon Mac (sessions Cowork avec Claude)
- [ ] Session 1 : squelette **Claude Agent SDK** (Python/TS) + MCP `atlas-brain` en local + push-to-talk (raccourci clavier) + STT + TTS ElevenLabs Flash
- [ ] Session 2 : brancher MCP n8n cockpit + Google Workspace · mémoire persistante dans `85_Jarvis/` · confirmations vocales pour l'irréversible
- [ ] Session 3 : daemon résident (launchd) + notifications macOS + brief 7h30 en local · journal d'actions dans le vault

## Phase 4 — mois 2-3 · v3, l'ambiant
- [ ] Pipeline **Pipecat** local : Gladia Solaria-3 streaming + interruptions (barge-in)
- [ ] Wake word « Jarvis » (openWakeWord) → conversation continue mains libres
- [ ] Sous-agents de fond (« prépare le dossier, préviens-moi ») + filtrage des sollicitations multi-boîtes
- [ ] Extensions optionnelles : numéro SIP/WhatsApp Calling, enceinte Home Assistant Voice

## Liens
- `JARVIS.md` (repo ops-cockpit) — interconnexion Cockpit ↔ Atlas
- Blueprint Jarvis (23/07) — architecture, budget, cas d'usage
- [[🗼 Tour de contrôle - Projets en cours]]
