---
type: config
date-created: 2026-08-04
owner: "[[Boris Arduy]]"
sensitivity: confidential
tags: [jarvis, regles, securite]
---

# 🛡️ Jarvis — Règles & protocoles

> Les garde-fous du blueprint (§07), valables pour toutes les versions (bot Telegram v1 → daemon v2 → ambiant v3). Toute évolution de Jarvis doit rester compatible avec cette page.

## 1. Lecture large, écriture étroite
- **Lecture** : tout l'Atlas, l'agenda, le cockpit, (plus tard : Gmail, Slack).
- **Écriture autorisée** : `00_Inbox/` (captures), `85_Jarvis/` (journal, mémoire, logs), `15_Resources/Calls/` (ingestion Sembly), et le cockpit via les outils journalisés (`creer_blocage`, `creer_tache`, `resoudre_blocage`).
- **Interdit** : modifier silencieusement un SOP, une décision, une carte projet hors bloc `%% cockpit %%`, ou tout fichier hors périmètre.

## 2. Confirmation vocale pour l'irréversible
Envoyer un email, modifier/supprimer une donnée existante, toucher à un paiement : Jarvis énonce l'action et attend un « confirme » explicite. Les brouillons et créations traçables (note, blocage, tâche) sont libres.

## 3. Tout est journalisé
- Côté cockpit : chaque écriture passe par l'Activity (« via Jarvis »).
- Côté vault : les actions notables vont dans `85_Jarvis/Journal/AAAA-MM-JJ.md`.
- Versionné par Obsidian Git → auditabilité complète.

## 4. Secrets & accès
- Tous les tokens/clés vivent dans **Keeper** (jamais dans le vault, jamais dans un prompt) : token bot Telegram, token Bearer MCP, clés Anthropic/OpenAI/ElevenLabs, credential Neon.
- Bot Telegram : `/setjoingroups` désactivé · trigger restreint au chat ID de Boris (`8606822360`).
- Serveur MCP cockpit : Bearer obligatoire · réservé à l'usage personnel de Boris (les écritures sont faites en son nom).
- Webhook Sembly : URL à segment secret, jamais partagée · le payload brut reste en base (`jarvis_calls`) pour audit.
- Rotation : en cas de doute sur un secret, on le régénère (rien d'autre à changer que les credentials n8n).

## 5. Périmètre actuel (à tenir à jour)
| Capacité | Statut | Depuis |
|---|---|---|
| Voix Telegram (STT/TTS) | ✅ actif | 04/08/2026 |
| Agenda (lecture) | ✅ actif | 04/08/2026 |
| Cockpit lecture + écriture journalisée | ✅ actif | 04/08/2026 |
| Sync Cockpit → Atlas (7h15) | ✅ actif | 04/08/2026 |
| Brief 7h30 + alerte P0 | ✅ actif | 04/08/2026 |
| Gmail (lecture dans le brief) | ✅ actif | 04/08/2026 |
| Calls Sembly → Atlas (15_Resources/Calls, 30 min) | ✅ actif | 04/08/2026 |
| Mémoire des calls à la voix (chercher_calls / derniers_calls) | ✅ actif | 04/08/2026 |
| Capture Atlas à la voix | 🔜 v2 (locale) | |
| Gmail outils agent (recherche + brouillons) | 🔜 phase 2 | |
