---
type: journal
date: 2026-08-04
source: jarvis
tags: [jarvis, journal]
---

# 2026-08-04 — Naissance de Jarvis

Première entrée du journal, rédigée par la session Claude qui a assemblé le système.

- **Interconnexion Cockpit ↔ Atlas** en production : 8 projets appariés, sync automatique à 7h15 (launchd), Tour de contrôle alimentée en live.
- **Serveur MCP cockpit** actif sur n8n (4 outils : état, créer/résoudre blocage, créer tâche), sécurisé par Bearer.
- **Jarvis v1 (Telegram)** opérationnel : voix → Whisper → Claude → ElevenLabs → voix. Premier échange réussi, personnalité en place.
- **Premier test d'écriture** : blocage P2 « test d'intégration Jarvis » créé puis clôturé sur Riot, à la voix.
- Première réponse mémorable : « Aucun blocage ouvert pour l'instant, Monsieur. »

Prochaine étape : brief du matin 7h30 + alerte P0 (point 4), puis deux semaines d'usage avant la v2 (daemon Mac).

**Ajout du soir** — journée complète, en fait :
- Brief 7h30 + alerte P0 activés (premier brief reçu, avec le deploy Vercel cassé repéré dedans — corrigé par push du fix local).
- **Ingestion Sembly → Atlas en production** : webhook n8n → table `jarvis_calls` (Neon) → `15_Resources/Calls/`, sync launchd toutes les 30 min. Premier call ingéré : « Anisse & Boris - Weekly IA » — celui-là même où Jarvis est présenté à Anisse.
- À partir d'aujourd'hui, chaque conversation enregistrée nourrit la mémoire sans intervention.

---

*Convention : une note par jour — `AAAA-MM-JJ.md` — dictée le soir via le bot ou écrite ici. Ce qui a aidé, ce qui a agacé, ce qui a manqué : c'est le cahier des charges vivant de la v2.*
