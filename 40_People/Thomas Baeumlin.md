---
type: person
full-name: "Thomas Baeumlin"
role: "Data Engineer — Entrepreneurs.com (BigQuery / DBT / Looker)"
team: "DataOps — sous Support infra (Boris) cible, manager fonctionnel actuel Fabrice"
manager: "[[Fabrice Jaeger]] (sujets structurants + gros projets) — cible : [[Boris Arduy]] (DataOps Support infra)"
reports: 
started: "~jan 2026 (Q1-Q2 2025 mentionné dans son bilan — à confirmer)"
status: active
source: entrepreneurs-com
sensitivity: rh-nominatif
tags: [data-engineer, bigquery, dbt, looker, dataops, support-infra, pilier-technique, allie-fort, dashboard-comex, surcharge]
---

# Thomas Baeumlin

> 🟢 **Pilier technique data — allié fort à valoriser, pas à auditer.** Profil mature, structurant, documenté. Découvert via 2 docs de cartographie livrés le 28/5. À l'opposé exact du profil [[Nicolas Farolfi]] (fragile, homme-clé non documenté). **L'un des meilleurs atouts techniques du pôle Support infra.**
>
> ⚠️ Orthographe : "Baeumlin" (signature de ses docs) — le vault mentionnait par erreur "Beaumelin" / "Robillet" ailleurs. **Thomas Baeumlin = le Data Engineer BigQuery. À ne pas confondre avec Thomas Robillet** (ex-collab, parti — cf. fiche Nicolas).

## ⚡ Synthèse en 30 secondes

- **Data Engineer** — owne toute la stack data warehouse : ingestion (Stitch/Fivetran/Python) → BigQuery → transformation DBT → dashboards Looker Studio
- **Infrastructure mature** : Git complet + CI/CD, 150+ tests automatisés, alerting proactif, 8 sources réconciliées, 40 modèles DBT, 1M+ lignes
- **Manager actuel** : [[Fabrice Jaeger]] (sujets structurants). **Cible triptyque** : sous Boris (DataOps Support infra)
- **Surcharge réelle** : auto-évaluée **8-9/10** — build 65% (COMEX approche), bugs 25%, run 10%
- **Homme-clé mitigé** : seul à maîtriser toute la stack DW + Looker, MAIS dépendance atténuée par doc Git + versioning
- **Dépendance amont critique** : dépend de la connaissance des flux campagnes (orchestration Nicolas/Yohan) pour modéliser — **risque indirect du départ Nicolas**
- **Projet phare en cours** : Dashboard COMEX (objectif Q2) = exactement le cordon sanitaire opérationnel d'Alec (chantier C3)
- **Posture Boris** : valoriser, décharger, embarquer comme pilier. **PAS auditer.**

## 🟢 Pourquoi Thomas est un atout majeur (analyse 28/5)

### Infrastructure data déjà au niveau industrie

Cf. [[Ressource - Cartographie Data Thomas Baeumlin 28 mai 2026]] pour le détail complet.

| Critère | État Thomas |
|---|---|
| **Versioning** | ✅ Git complet (scripts + modèles DBT) |
| **CI/CD** | ✅ Déploiement auto au merge via GCP runners |
| **Tests automatisés** | ✅ 150+ tests (unicité IDs, non-null, valeurs acceptées, relations tables) |
| **Monitoring/alerting** | ✅ Automatisé par mail (fail script / crash DBT / test échoué) |
| **Documentation** | ✅ GitHub + in-model (manque juste overview Notion, qu'il propose lui-même) |
| **Architecture** | ✅ ELT standard (staging → intermediate → marts) |
| **Stabilité** | ✅ Auto-évaluée "élevée", 1 incident/2 sem (dû aux API externes, pas dette interne) |

→ **C'est l'inverse exact du profil Nicolas.** Là où Nicolas teste en prod sans versioning, Thomas a une infra propre, testée, versionnée.

### La réconciliation cross-sources est déjà construite

Thomas a reconstruit proprement le funnel complet côté data warehouse :
> *"Un lead arrive via WebinarJam → capté dans HubSpot → dépenses pub (Meta/Google/LinkedIn) pour CPL réel → converti en transaction Closed win → client Plateforme → facturation Odoo pour impayés."*

→ **C'est le detail_funnel que [[Nicolas Farolfi]] se déclarait "seul à maîtriser".** Thomas en a la version data warehouse, versionnée et testée. **La dépendance critique Nicolas sur l'attribution est donc partiellement déjà couverte par Thomas.** Reste à valider l'écart tracking frontend (Nicolas/Yohan) vs tracking data (Thomas).

### Le Dashboard COMEX = cordon sanitaire opérationnel déjà en route

Statut des dashboards (28/5) :
- Marketing ✅ livré
- Base client ✅ livré (remplace Airtable)
- Sales 🔄 en cours
- Finance → à venir Q2 (Odoo : facturation, impayés)
- Delivery → à venir Q2 (Plateforme, coaching)
- Customer Journey → à venir
- **COMEX → objectif Q2** (vue synthétique Marketing + Sales + Finance + Delivery + deep dive par département)

→ **Le COMEX dashboard de Thomas EST le chantier C3 (cordon sanitaire Alec).** Boris n'a pas à le construire de zéro — à **cadrer le besoin** (8-12 bons KPIs pour qu'Alec arrête d'appeler 10 personnes) et **accélérer**.

### Preuve de valeur concrète — attaque bots Tapie

Campagne Tapie avril 2026 : **5000+ faux leads injectés** (attaque bots), détectés et exclus par le cleaning BigQuery+DBT. KPIs recalculés sur vrais leads. → L'infra data protège déjà les décisions business. Argument à garder pour défendre la valeur du pôle DataOps auprès d'Alec.

### Sécurité data déjà adressée

Thomas a identifié + traité la fuite sécurité HubSpot (accès larges non contrôlés) et mis en place un accès BigQuery *"strictement réglementé, privé et sécurisé"*. → Morceau du chantier C5 (audit IT/SSI/RGPD) déjà entamé côté data.

## 🟠 Points d'attention réels

### Surcharge (8-9/10)

Build 65% / bugs 25% / run 10%. **25% en bugs/urgences = beaucoup.** Le COMEX approche, charge intense. **Risque** : ralentissement ou épuisement sur le COMEX.

→ **Ne PAS lui reporter la charge ops orpheline du départ Nicolas.** Thomas fait du data engineering, pas de l'ops automation. Deux métiers distincts. Ne pas les confondre dans la réorganisation.

### Homme-clé mitigé

Verbatim : *"Toute la stack Data Warehouse & Looker — maîtrise complète de bout en bout, seul à maîtriser."* Bus factor de 1 sur la couche data warehouse.

→ **Moins urgent que Nicolas** (dépendance atténuée par Git + DBT docs : quelqu'un pourrait reprendre). À traiter en P2 dans C6 (disaster recovery). La doc Notion overview qu'il propose lui-même est exactement le bon livrable — **l'encourager à la produire**.

### Dépendance amont = maillon faible réel

Thomas le pointe lui-même (très lucide) :
> *"Manque de documentation claire sur comment les campagnes sont orchestrées de A à Z, dans quels outils passe un lead → ralentit la modélisation."*

> *"Où perds-tu le plus de temps ? Compréhension du fonctionnement de chaque département → reconstituer ce contexte à chaque nouvelle intégration."*

→ **Thomas modélise bien, mais dépend de la connaissance des flux amont (Nicolas/Yohan).** Quand Nicolas part, Thomas perd sa source de contexte sur l'orchestration campagnes. **Risque indirect critique du départ Nicolas sur Thomas.** Cf. action transfert ci-dessous.

### Chaîne de validation dashboards qui se grippe

Verbatim : *"Délais de retour et de validation des owners de département."* Cédric valide le dashboard Marketing, Aziz le Sales. Avec **[[Cédric De Saint Jean]] qui part** + **[[Aziz Sfaihi]] en triangulation/incompatibilité moyen terme**, la chaîne de validation va se gripper. À anticiper dans la gouvernance.

### Flou de périmètre à cadrer proprement

Thomas dit *"garantir l'ownership de la donnée chez entrepreneurs.com"* = ton scope DataOps. **Pas un conflit, une complémentarité** : Thomas owne la réalisation technique du data warehouse, Boris owne la gouvernance stratégique DataOps. À clarifier pour qu'il ne se sente pas dépossédé (il est fier de son travail, à juste titre).

## 🎯 Actions Boris concernant Thomas

### 🔴 Sous 48h
1. **Message de reconnaissance + cadrage** (ton différent des autres : pilier, pas audité) — cf. à drafter
2. **Sécuriser le transfert [[Nicolas Farolfi]] → Thomas** sur l'orchestration des flux campagnes AVANT le départ Nicolas. Thomas est le meilleur réceptacle durable (il documente + versionne).

### 🟠 Sous 7 jours
3. **Bilatéral Boris × Thomas** : cadrer la complémentarité de scope (lui = réalisation DW, moi = gouvernance DataOps) sans le déposséder
4. **Cadrer le besoin COMEX** : quels 8-12 KPIs pour le cordon sanitaire Alec ? Boris cadre le besoin, Thomas construit
5. **Évaluer la décharge possible** : 25% de bugs, comment réduire ? (priorisation, second profil data junior offshore via Mithril ?)

### 🟡 Sous 14-30 jours
6. **Encourager la doc Notion overview** (qu'il propose lui-même) — livrable parfait pour C6 disaster recovery
7. **Anticiper la gouvernance de validation dashboards** post-départ Cédric + triangulation Aziz
8. **Articulation tech cible** : trancher comment BigQuery/DBT (Thomas) s'articule avec Make/n8n (Nicolas→remplaçant) et Archi 2.0 (Yohan)

## 🏗️ Stack technique (référence)

**Ingestion** : Stitch, Fivetran, scripts Python custom (GitHub + GCP)
**Transformation** : DBT (40 modèles, SQL) — couches staging / intermediate / marts
**Stockage** : BigQuery / GCP (data warehouse central)
**Dashboarding** : Looker Studio
**Versioning/CI-CD** : GitHub + GCP runners (déploiement auto au merge)
**Langages** : Python (ingestion), SQL (transformation DBT)

**8 sources intégrées** : HubSpot (277K), Google Ads (150K), Meta Ads (20K), LinkedIn Ads (1K), Tally (87K), WebinarJam (800K), La Plateforme/App (80K), Odoo (29K)

## 🔗 Liens

- [[Ressource - Cartographie Data Thomas Baeumlin 28 mai 2026]] — les 2 docs sources
- [[Nicolas Farolfi]] — départ acté, transfert flux amont → Thomas critique
- [[Fabrice Jaeger]] — manager actuel (sujets structurants), owner BigQuery historique
- [[Diag - Nouvel Organigramme & Cordon Sanitaire 2026-05-27]] — inventaire DataOps
- [[Anisse Rbibe]] — collaboration IA × data (intégration IA dashboards à venir)
- [[_Org-chart]] — position DataOps sous Support infra
- [[Cédric De Saint Jean]] / [[Aziz Sfaihi]] — owners validation dashboards (chaîne à risque)
