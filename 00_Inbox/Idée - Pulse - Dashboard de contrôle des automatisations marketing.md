---
type: idea
date: 2026-04-28
source: entrepreneurs-com
domain: marketing
sensitivity: internal
status: à-arbitrer
effort-estimé: 4-6 semaines · 1-2 devs
related-decisions: "[[2026-04-30 - Operating Partner chez Entrepreneurs.com]]"
tags: [idée, marketing, automatisations, pre-prise-de-poste, marketing-ops]
---

# Idée — Pulse : dashboard de contrôle des automatisations marketing

> Idée capturée pendant la phase de cadrage pré-prise de poste. À arbitrer dans les 30-60 premiers jours en fonction du diagnostic terrain.

---

## En une phrase

Une "salle de contrôle" qui rend visible en temps réel la santé de toutes les automatisations marketing (webinars, challenges, séquences) et détecte automatiquement les prospects bloqués avant qu'on les perde.

## Pourquoi c'est pertinent pour ENT

Lien direct avec deux points du [[Diag - Ce qui me frappe comme étrange ou inefficace]] :

- **+150 automations sautées au départ de Thomas Rodier** (section Tech/Data/Produit) — le scénario qu'aucun outil n'a vu venir, et que personne n'a détecté en interne. Pulse aurait alerté immédiatement.
- **Équation marketing cassée** (section 2) — quand le ROAS doit être 11-15 pour être rentable, chaque prospect perdu dans une automatisation qui bug a un coût direct. La fuite silencieuse de leads à mi-funnel est probablement non négligeable et invisible dans le reporting actuel.

Hypothèse à vérifier en S1-S2 avec le HOM : combien de prospects par mois ne reçoivent pas leurs séquences à cause de bugs d'automatisation ? Si la réponse est "on ne sait pas" → confirme le besoin.

## Ce que fait Pulse, concrètement

- **Inventaire vivant** de toutes les automatisations actives (Make, Zapier, HubSpot, ActiveCampaign, etc.) avec statut santé en temps réel.
- **Détection de prospects bloqués** : si un prospect ne transitionne pas d'une étape à l'autre dans le délai attendu, il apparaît dans une file avec action "relancer".
- **Alertes** sur Slack + email quand un scénario tombe ou qu'un drop-off anormal est détecté à une étape (vs. baseline historique).
- **Vues détaillées par événement** (webinar, challenge) : funnel + replay des runs + debug pour l'équipe ops.

Maquette générée : artefact HTML produit pendant la conversation Claude du 28 avril 2026 (palette blanc/noir/rouge, vue Overview du HOM). Récupérable via l'historique Claude → conversation "Dashboard automatisations marketing entrepreneurs.com".

## Stack technique pressentie

- **Front** : Next.js + Tailwind + shadcn/ui
- **Back/data** : Supabase (Postgres + realtime)
- **Ingestion** : n8n + webhooks (Make, Zapier, HubSpot, AC, Livestorm, Calendly, Brevo)
- **Observabilité** : Sentry + logtail (Pulse ne doit pas être l'angle mort qu'il prétend résoudre)

## Coût estimé

- **Build MVP** : 4-6 semaines, 1-2 devs (cadrage + implémentation des 2-3 connecteurs prioritaires + détection blocages + alertes Slack).
- **Run** : hébergement Vercel + Supabase Cloud, ~50-150€/mois pour la volumétrie ENT.
- **Alternative à arbitrer** : faire ça en interne vs. externaliser à MTS (conflit d'intérêt à gérer si je suis Operating Partner — à clarifier avec Alec en transparence).

## Décisions à prendre si on pousse

1. Confirmer la gravité du problème via discussion HOM + Marketing Ops S1-S2.
2. Identifier l'événement pilote (un webinar à venir) pour cadrer la définition d'un parcours attendu.
3. Décider build interne vs. externalisé (les 2 devs ENT à 20K€/mois ont déjà du backlog — cf. [[Diag - Ce qui me frappe comme étrange ou inefficace]] section 6).
4. Définir les KPIs de succès à 3 mois (% prospects récupérés, MTTR sur incident).

## Risques & angles morts

- **Risque "outil qui s'ajoute aux outils"** : si Pulse n'est pas adopté quotidiennement par le HOM et l'équipe ops, c'est un coût sans valeur. Définir le rituel d'usage avant de coder.
- **Question périmètre** : faut-il étendre à toutes les automatisations (sales, delivery, RH) ou rester focus marketing ? Tentation classique de scope-creep — rester focus pour le MVP.
- **Hypothèse à challenger** : l'idée part du principe que les bugs d'automatisations sont un vrai problème quantitatif. Si le diagnostic terrain montre que c'est marginal, l'idée ne tient pas — il faut être prêt à l'enterrer.

## Liens

- [[MOC - Prise de poste Operating Partner]]
- [[Diag - Ce qui me frappe comme étrange ou inefficace]]
- [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] (à enrichir d'une hypothèse "% de prospects perdus dans des automatisations cassées")
- [[Metrics-North-Star]] (impact potentiel sur le ROAS)

## Historique

- **2026-04-28** — idée capturée pendant cadrage Claude (conversation sur le dashboard de contrôle pour HOM ENT). Maquette HTML produite (palette blanc/noir/rouge, vue Overview HOM).
- **À arbitrer** — premier check terrain en S1-S2 avec le HOM.
