---
type: ressource
sous-type: cartographie-technique
date: 2026-05-28
auteur-source: Thomas Baeumlin (Data Engineer)
contexte: Démarche inventaire cross-pôle ops/tech (préparation nouveau modèle 1er juillet)
source: entrepreneurs-com
sensitivity: technique-interne
tags: [cartographie, data-engineering, bigquery, dbt, looker, dataops, inventaire, support-infra]
---

# Ressource — Cartographie Data (Thomas Baeumlin, 28 mai 2026)

> Deux documents livrés par [[Thomas Baeumlin]] dans le cadre de la démarche d'inventaire cross-pôle ops/tech :
> 1. **Questionnaire de cartographie technique - DATA** (réponses structurées au template)
> 2. **État des lieux - DATA / Gouvernance & Infrastructure BigQuery** (bilan Q1-Q2, format présentation)
>
> PDF sources : `Cartographie_des_tech_Entrepreneurs_com_-_Thomas_-_DATA.pdf` + `Etat_des_lieux_-_DATA.pdf`

## ⚡ Ce qu'il faut retenir

**L'infrastructure data d'Entrepreneurs.com est mature, gouvernée, testée et scalable.** C'est une fondation solide pour le pôle Support infra, à l'opposé du système ops fragile cartographié par [[Nicolas Farolfi]].

## 🏗️ Architecture data (chiffres clés)

- **8 sources** intégrées et réconciliées
- **40 modèles DBT** actifs (staging → intermediate → marts)
- **1 000 000+** lignes ingérées dans le data warehouse
- **150+** tests automatisés (plusieurs fois par jour)
- **Stack** : Stitch + Fivetran + Python (ingestion) → BigQuery/GCP (stockage) → DBT (transformation) → Looker Studio (dashboards)
- **Git + CI/CD** : déploiement auto au merge via GCP runners

### Les 8 sources

| Source | Contenu | Département | Volume |
|---|---|---|---|
| HubSpot (CRM) | Leads, contacts, deals | CRM | 277 000 |
| Google Ads | Dépenses pub journalières | Marketing | 150 000 |
| Meta Ads | Dépenses pub journalières | Marketing | 20 000 |
| LinkedIn Ads | Dépenses pub journalières | Marketing | 1 000 |
| Tally | Formulaires | Acquisition | 87 000 |
| WebinarJam | Participants & conversions | Acquisition | 800 000 |
| La Plateforme (App) | Données coaching & clients | Delivery | 80 000 |
| Odoo | Données financières & facturation | Finance | 29 000 |

### Réconciliation cross-sources (le detail_funnel data)

Le funnel complet reconstruit côté data warehouse :
WebinarJam (lead) → HubSpot (capté) → Meta/Google/LinkedIn (CPL réel) → transaction Closed win → client Plateforme → Odoo (impayés, facturation)

→ **C'est la version data warehouse du detail_funnel que [[Nicolas Farolfi]] se déclarait seul à maîtriser.** Couverture partielle de la dépendance Nicolas.

## 📊 Dashboards (statut 28/5)

| Dashboard | Statut | Description |
|---|---|---|
| Marketing | ✅ Livré | Leads HubSpot dédoublonnés (remplace GSheets) |
| Base client | ✅ Livré | Remplace Airtable |
| Sales | 🔄 En cours | HubSpot deals & pipeline retraités DBT |
| Finance | À venir Q2 | Intégration Odoo (facturation, impayés) |
| Delivery | À venir Q2 | Métriques Plateforme, coaching |
| Customer Journey | À venir | — |
| **COMEX** | **Objectif Q2** | Vue synthétique unifiée + deep dive par département |

→ **Le COMEX dashboard = le cordon sanitaire opérationnel d'Alec (chantier C3).** Déjà en route.

### KPIs dashboard Marketing (exemple réel, jan-avr 2026)

Leads 58 389 · Ads spend 879 182 € · Call booked 4 309 · CA signé 4 476 643 € · CPL 15,06 € · CPL paid 18,63 € · CPCB 204,03 € · ROAS 5,09 · Taux conversion 0,55 % · Earning/lead 76,67 €

## 🟢 Points forts structurels

- **Gouvernance data résolue** : avant = données non centralisées (GSheets/Airtable/CSV), doublons, pas d'ownership, fuite sécu HubSpot, outillage fragile. Après = BigQuery source de vérité unique, dédupliqué, sécurisé, testé.
- **Data cleaning robuste** : déduplication par email normalisé, exclusion domaines internes (@entrepreneurs.com), détection bots/fraude
- **Cas concret attaque bots Tapie (avril 2026)** : 5000+ faux leads détectés et exclus → KPIs recalculés sur vrais leads
- **Sécurité** : accès BigQuery strictement réglementé (vs exports GSheets non maîtrisés d'avant)

## 🟠 Points d'attention

- **Surcharge Thomas 8-9/10** (build 65% / bugs 25% / run 10%)
- **Pas d'environnements séparés formels** — isolation via dataset de test BigQuery (pragmatique mais à monitorer)
- **Dépendance amont** : Thomas dépend de la connaissance des flux campagnes (Nicolas/Yohan) pour modéliser → risque indirect départ Nicolas
- **Chaîne validation dashboards** : owners département (Cédric Marketing, Aziz Sales) → se grippe avec départ Cédric + triangulation Aziz
- **Manque doc Notion overview** (Thomas le propose lui-même comme priorité)
- **1 incident critique / 2 semaines** — principalement changements API externes (ex: HubSpot)

## 🎯 Implications stratégiques

1. **Thomas = pilier à valoriser**, pas zone à auditer. Posture Boris : décharger, embarquer.
2. **COMEX dashboard = chantier C3 déjà lancé** — Boris cadre le besoin (8-12 KPIs Alec), Thomas construit.
3. **Transfert Nicolas → Thomas** sur l'orchestration flux = plus important que Nicolas → Boris (Thomas est le réceptacle durable).
4. **Articulation tech cible à trancher** : BigQuery/DBT (Thomas) vs Make/n8n (Nicolas→remplaçant) vs Archi 2.0 Laravel (Yohan). Décision structurante du pôle.

## 🔗 Liens

- [[Thomas Baeumlin]] — fiche stakeholder
- [[Nicolas Farolfi]] — départ acté, transfert flux amont critique
- [[Diag - Nouvel Organigramme & Cordon Sanitaire 2026-05-27]] — inventaire DataOps mis à jour avec ces données
- [[Ressource - Cartographie tech Nicolas Farolfi]] — pendant ops (système fragile)
