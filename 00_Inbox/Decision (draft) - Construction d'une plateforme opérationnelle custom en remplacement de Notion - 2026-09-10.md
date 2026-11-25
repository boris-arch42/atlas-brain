---
type: decision
statut: draft
date: 2026-09-10
source: jarvis
call: "[[2026-09-10 - Boris x Mathis]]"
tags: [decision, draft]
---

# Construction d'une plateforme opérationnelle custom en remplacement de Notion

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Notion atteint ses limites pour gérer les workflows commerciaux, delivery et portails clients de l'agence. Les frictions opérationnelles entre sales, PM et créatifs génèrent des pertes d'opportunités. Les vues personnalisables, l'automatisation des relances et l'intégration CRM-projet ne sont pas satisfaisantes. Les coûts de licences SaaS généralistes (HubSpot, etc.) sont jugés excessifs pour des fonctionnalités peu utilisées.

## Décision

Nous décidons de construire une plateforme légère, propriétaire et brandée, développée et maintenue par une équipe offshore (Inde/Pakistan), intégrant :
- Gestion des companies > prestations > batches
- Vues dédiées sales, delivery et portails clients sécurisés
- Automatisation des tâches commerciales depuis les signaux projet et appels
- Centralisation de l'historique client (appels, devis, coaching) interrogeable par IA
- Webhooks et APIs pour connecter Aircall, WhatsApp Business, éventuellement un CRM externe

La démarche :
1. Spécification fonctionnelle consolidée (besoins sales, delivery, portail)
2. Prototypage rapide V1 à partir des données Notion actuelles via Claude/Cloud Code
3. Itérations avec sous-ensemble d'utilisateurs
4. Migration complète et arrêt de Notion une fois la stabilité confirmée

## Conséquences

**Positives :**
- Contrôle total des vues, branding, automatisations
- Réduction drastique des coûts de licences SaaS
- Meilleure sécurité et portails clients professionnels
- Évolutivité rapide via équipe offshore dédiée
- Propriété complète des données et absence de point de défaillance unique SaaS

**Négatives / Risques :**
- Baisse temporaire de productivité pendant la transition
- Nécessité d'un accompagnement terrain fort pour adoption
- Risques de delivery et sécurité offshore (mitigation : comptes GitHub/Vercel/Supabase propriété entreprise, recrutement sélectif)
- Maintenance et évolution à organiser en interne

**À valider par Boris :**
- Budget et timeline du prototype puis du build complet
- Arbitrage CRM intégré vs CRM externe connecté
- Gouvernance du backlog fonctionnel et priorisation des demandes équipes
- Stratégie de conduite du changement et plan de formation
