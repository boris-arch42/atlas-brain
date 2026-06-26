---
type: project
domaine: ENT
statut: actif
sante: 🔴
owner: "[[Boris Arduy]] + [[Jordan Leroux]]"
prochaine: "Refaire la migration Odoo proprement (3 devis FR sur cahier des charges) — bloque tout le reste"
echeance: 2026-06-30
revue: 2026-06-26
execution: "Objectif 2 du Plan Q1 — suivi BigQuery"
sensitivity: confidential
tags: [projet, ent, finance, tresorerie, recouvrement, odoo, lettrage, decaissement, budget]
---

# Trésorerie & Finance

> Regroupe : recouvrement post-Jordan + bascule prélèvement auto 350K€ (KR2.1), matrice de jurisprudence financière pour déléguer les tickets de Fabrice (KR2.3). Cible : 2-3M€ d'impayés en récupération active + autonomie Sabrina/CFO.

> [!warning] **MAJ 2026-06-26 (point Jordan × Boris)** — La **migration comptable Pennylane → Odoo est le goulot n°1** et rend la **compta non fiable** (InPay faux → blocages clients injustifiés + recouvrement à l'aveugle). Tout le reste (recouvrement, commissions, budget) en dépend. Décision : **repartir proprement** avec un migrateur Odoo français (3 devis). Cf. [[2026-06-26 - Jordan x Boris - Finance (migration Odoo, lettrage, controles, budget)]] pour le détail complet.

## 🗺️ Cartographie des chantiers Finance (point 26/06)

### 1. 🔴 Migration Pennylane → Odoo (goulot critique — débloque tout)
- Chantier décorrélé : achats sur Odoo / ventes + banques sur Pennylane jusqu'au 10/6, **non connectés**. **InPay** (recouvrement, blocage plateforme > 30 j d'impayé) **faux** → clients bloqués à tort + impayés réels invisibles.
- Cause : migration sous-estimée/sous-budgétée (prestataire indien Tejas à 900 $, ne maîtrise pas les comptes auxiliarisés / logique *partenaires* Odoo). Proba migration propre par Tejas ~20 %.
- **Décision** : 3 cabinets FR → 3 devis (cahier des charges précis) → négo (~2 000 € + contrepartie) → relancer. Devis en main : 4 500 / 5 000 / 5 005 €.
- Sujet diplomatique : dossier géré par Fabrice → à porter factuellement (intérêt boîte).

### 2. 🟠 Lettrage des encaissements (paiement ↔ deal)
- 20-50 règlements/j (Woop : CB + SEPA), e-mail comme seul identifiant → ~20-30 % de non-match. **Clé = n° de deal HubSpot** ; cible à terme = n° de tracking client `0001/ID-HubSpot` dès le lead.
- Solution en place : export CSV banques → agent Claude (Excel date/libellé/montant/deal) → Indien type le deal (700 AED/mois, flux tendu quotidien). Vérif humaine obligatoire (incident commissions le mois dernier).
- Aval : **Looker Studio Finance** ([[Thomas Baeumlin]], ~1 mois) sourcé sur ce fichier.

### 3. 🟠 Contrôle des premiers prélèvements (Ring the Bell)
- SEPA validé à ~J+10 ; 1ʳᵉ échéance peut sauter alors que les accès plateforme sont déjà délivrés → besoin **alerte + coupure d'accès** (J+11). Sales externes (CGM/Kelly) sans outil.
- **Ring the Bell** (Slack auto HubSpot à chaque signature) : dynamisme + support de contrôle quotidien. Alec 👍 / Fabrice réticent. Exclure les coachs.
- Complément : **agent IA d'alerte** (type Marcus) qui relance le sales sur les « non » → à voir avec [[Anisse Rbibe]]. Lien base **Tally** (colonne Finance + onglet 1ᵉʳ prélèvement).

### 4. 🟠 Décaissements & circuit de validation (IbanFirst)
- Virements actuellement par Fabrice, tout à la main (pas de batch). Proposition Jordan : **il exécute** / **Fabrice valide 100 %** / **Alec valide > 50 000 AED (ou 10 000 — seuil Alec à figer)**. Argument sécurité = organe de contrôle, pas défiance.
- Organes de contrôle visés : chaque pôle valide ses propres factures (Excel + clic owner) puis circuit IbanFirst.

### 5. 🟡 Budget par owner & gouvernance tools
- Budget 6 mois, 1 onglet/catégorie (~10), 1 owner/onglet (pré-rempli par Jordan, ajusté par l'owner). Revue mensuelle réalisé vs budgété.
- **Boris = owner unique des tools** (tout nouvel outil validé par Boris). Parc société ~150-500 outils, accès non centralisés. Cf. [[Audit SaaS-IT — économies]]. Masse réelle à challenger = **delivery + sales** (marge brute, cible ~18 % frais delivery/CA).

## 📋 Actions roadmap (doc Fabrice, chantier B)
- [ ] **B2** Reprendre le recouvrement comme chantier contrôlé : owner, chiffres, suivi, escalade (+ [[Jordan Leroux]]) — *P1 · immédiat* (⚠️ conditionné à la fiabilisation Odoo/InPay)

## Liens
- [[2026-06-26 - Jordan x Boris - Finance (migration Odoo, lettrage, controles, budget)]] — point source complet
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] (Objectif 2)
- [[Audit SaaS-IT — économies]] — gouvernance tools / économies
- [[Jordan Leroux]]
- [[Thomas Baeumlin]] — Looker Studio Finance
- [[Anisse Rbibe]] — agents IA (Ring the Bell, alerte prélèvement)
- [[🗼 Tour de contrôle - Projets en cours]]
