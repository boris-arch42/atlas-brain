---
type: ressource
sous-type: cartographie-technique
date: 2026-05-27
auteur-source: Nicolas Farolfi (Ops automatisations — départ acté)
contexte: Démarche inventaire cross-pôle ops/tech (livrable de passation, Nicolas non encore notifié de son départ)
source: entrepreneurs-com
sensitivity: technique-interne-rh-sensible
tags: [cartographie, ops, automation, make, n8n, archi-2.0, dataops, fragile, passation, depart-nicolas]
---

# Ressource — Cartographie tech Nicolas Farolfi (27 mai 2026)

> Document de cartographie opérationnelle et technique livré par [[Nicolas Farolfi]] dans le cadre de la démarche d'inventaire cross-pôle ops/tech.
>
> ⚠️ **Contexte sensible** : Nicolas **ne sait pas qu'il part** au moment de la livraison (licenciement acté en interne le 18/5, non encore notifié). Ce document est donc sincère et non contraint — à lire comme la photographie de l'état réel du système ops, et comme base pour la passation. Cf. [[Nicolas Farolfi]].
>
> PDF source : `_Nicolas_-_Ops__Cartographie_des_tech_Entrepreneurs_com.pdf`

## ⚡ Ce qu'il faut retenir

**Le système ops automation est fragile et concentré sur une personne.** À l'opposé exact de l'infra data mature de [[Thomas Baeumlin]]. Le départ Nicolas crée des zones aveugles opérationnelles immédiates si la passation n'est pas sécurisée.

## 🗂️ Périmètre Nicolas (4 axes)

| Axe | % temps | Contenu |
|---|---|---|
| **Archi 2.0** (x Yohan) | 25% | Refonte architecture tech lancements (Make/n8n → PHP/Laravel). Objectifs : coût €, gestion bugs, scalabilité, modularité, sécurité webhooks, monitoring |
| **Lancements Webinar/Challenge (3D/5D)** | 35% | Ops & automation des lancements live |
| **Lancements Evergreen** (x Raphael) | 15% | VSL, LeadMagnet, ops & automation |
| **Support Sales & Marketing** | 25% | Data, ops, automation : no-show R1, dashboard/BigQuery (x Thomas), campagnes email/SMS, contrats OneFlow, produits HubSpot, liens paiement Whop, onboarding sales |

**Charge auto-évaluée** : équilibrée. Build 60% / run 25% / bugs 15%.

## 🔴 Fragilités structurelles majeures

| Problème | Verbatim / détail | Risque |
|---|---|---|
| **Homme-clé absolu** | "Seul à maîtriser" : vision end-to-end, archi Make/n8n, detail_funnel, diagnostic bugs, conception Archi 2.0 | Zones aveugles immédiates au départ |
| **Tests en prod** | "Environnements peu formalisés, tests réalisés directement en production" | Bug = lancement entier cassé (200-500K€) |
| **Pas de versioning Make/n8n** | Git uniquement sur ETL + Laravel, "peu ou pas" sur scénarios Make/n8n | Pas de rollback, pas d'audit |
| **Monitoring partiel** | "Monitoring manuel, alertes limitées ou inexistantes, dépendance détection humaine" | Bugs détectés quand quelqu'un les voit |
| **Pas de double validation** | "Mise en production directe, pas de validation formelle" | Antithèse doctrine Alec "on garde le contrôle" |
| **Lancements sous-marin** | "Préparés la veille pour le lendemain, briefs incomplets/tardifs" | Diagnostic indirect du pôle marketing (briefs) |
| **SPOF abonnements** | "Compte Make en pause → blocage global des automatisations" | Make = point de défaillance unique non monitoré |

## 🟢 Points positifs

- A produit un document structuré et factuel avant de partir (à son crédit)
- Autodiagnostique honnêtement ses propres failles (5 zones seul à maîtriser, validation absente, monitoring partiel)
- Propose des solutions concrètes : Tally point d'entrée unique, checklists, monitoring centralisé, MCP+GPT pour la doc
- A mené un travail de standardisation récent : "lancement 5D Challenge Avril réalisé sans bug critique" (vs 2-3 bugs critiques en déc/jan)

## 🔗 Stack technique

**Automation** : Make (scénarios principaux), n8n (logiques avancées, agents IA, auto-hosté owner Wassim), workflows HubSpot, webhooks (ClickFunnels, Tally, Calendly)
**Data/tracking** : BigQuery (owner Thomas), CustomerIO, HubSpot, Airtable, Google Sheets, scripts ETL frontend
**Hébergement** : ClickFunnels, HubSpot, Customer.io, Tally, Calendly, WebinarJam/StreamYard (SaaS) + Make (cloud) + n8n (auto-hosté Wassim) + BigQuery (Thomas) + scripts ETL (GitHub/CloudFlare, owner Yohan) + Archi 2.0 (Vercel/Railway, owner Yohan)
**Profil dev** : Node/TS, PHP/Laravel, Python, Angular/React, Make/n8n/Zapier, Docker, agents IA, vector DB (Qdrant)

## 🎯 Implications passation (cf. fiche Nicolas pour le détail)

1. **Transfert Nicolas → [[Thomas Baeumlin]]** sur orchestration flux + detail_funnel frontend (réceptacle durable)
2. **Relai Make/n8n** → remplaçant Aikho + équipe Mithril
3. **Archi 2.0** → Yohan (co-pilote), statut à clarifier (orphelinage ?)
4. **SPOF Make** → monitoring d'urgence à mettre en place (qui surveille le compte ?)
5. **Vérifier la doc effectivement laissée** au-delà de ce PDF macro (Looms ? Notion à jour ?)

## 🔗 Liens

- [[Nicolas Farolfi]] — fiche stakeholder, départ acté + plan passation
- [[Ressource - Cartographie Data Thomas Baeumlin 28 mai 2026]] — pendant data (système mature)
- [[Diag - Nouvel Organigramme & Cordon Sanitaire 2026-05-27]] — inventaire DataOps (2 couches)
- [[Thomas Baeumlin]] — réceptacle durable de la connaissance tracking/attribution
