---
type: playbook
source: doc transmissible aux équipes Entrepreneurs.com
date-created: 2026-05-19
status: V2.0 — post-event Kelly, intégration routing Short.io
audience: ["équipes Kelly Launch (closers, admin, compta)", "managers d'agences (Romain/Lucas/Axel)", "admin technique pour réplication futur lancement"]
context: "Playbook V2.0 — funnel commercial Lancement Externe end-to-end. Évolution majeure vs V1.0 : intégration de toute la partie amont (Tally → Short.io → ClickFunnels → iClosed → Zoho) + routing multi-agences détaillé + 3 scénarios Make + bilan post-event Kelly. Doc transférable pour opérer ET répliquer le système sans dépendance à Boris."
sensitivity: confidential
tags: [playbook, doc-transferable, kelly-launch, funnel, ops, transmission, short-io, routing, multi-agences, V2, J19]
related: "[[Playbook - Funnel Commercial Lancement Externe V1.0 - 2026-05-13]] (version précédente — partie aval uniquement), [[Ressource - Automation Zoho-DocuSign Contrats BOSS-ENERGY - 2026-05-13]] (V1.5 technique), [[Ressource - Scénario Make iClosed-Zoho-Sheets - 2026-05-15]] (V1.2 amont), [[_Index|Hub projet Kelly]], [[BOSS-ENERGY]]"
---

# 📘 Playbook — Funnel Commercial Lancement Externe V2.0

> **Livrables :**
> - PDF stylé (charte Entrepreneurs.com, 72 pages) : `/mnt/user-data/outputs/Playbook_Funnel_Commercial_Lancement_Externe_V2.pdf` ⭐ — version à diffuser
> - Markdown source (2192 lignes) : `/mnt/user-data/outputs/Playbook_Funnel_Commercial_Lancement_Externe_V2.md` — version éditable
>
> Cette note est le pointeur Atlas-Brain vers la V2.0 du playbook officiel.

---

## ⚡ Synthèse 30 sec — évolutions V1.0 → V2.0

V2.0 = couverture **end-to-end** du funnel commercial Kelly Launch (vs V1.0 qui couvrait l'aval `Engagé → Fermé Gagné` uniquement).

### Nouveautés majeures par rapport à V1.0

**1. Toute la partie amont du funnel (sections 12-15) ⭐**
- Setup **Short.io** détaillé : splitter pondéré 25/50/25 entre les 3 agences, configuration du forward des paramètres URL, plan B en cas de panne, maintenance (section 12 — 7 sous-sections)
- Setup **ClickFunnels** : 3 pages d'agence avec embed iClosed, slug workspace `CGM` documenté (le bug récurrent du go-live)
- Setup **iClosed** : 3 events Round Robin, 42 closers en host, convention emails alignée
- Setup **emails dédiés** : ~70 adresses, sous-domaine ou pas, process d'offboarding T+60

**2. Les 3 scénarios Make documentés (section 19) ⭐**
- **Scénario A2** (amont, V1.2) : iClosed → Sheets + Zoho avec Data Store dédup + Tally Lookup + owner dynamique via `/v3/users`
- **Scénario 1** (V1.5) : Zoho Engagé → DocuSign avec **Router multi-produits** (Boss Energy + Incubateur)
- **Scénario 2** : Zoho Fermé Gagné → Sheets

**3. Backfill Tally documenté (section 18.6)**
- 5 champs custom Zoho (Entreprise, Site web/LinkedIn, CA actuel, Pain points, Déjà coaché)
- Scénario Make dédié + script Apps Script avec resume auto
- Process exécuté sur Kelly : 4 533 lignes traitées

**4. Bilan post-event Kelly intégré (annexe E)**
- Chiffres réels : 40K inscriptions, 11.5K spectateurs pic, 1 100+ appels externes
- Pièges majeurs rencontrés et résolus (embed iClosed, 2 webhooks doublons)
- **Décision Option A** confirmée par Alec (réplication systématique)

**5. Annexe D consolidée** — tous les IDs critiques en un seul endroit (Short.io, ClickFunnels, iClosed, 3 webhooks Make, DocuSign, Zoho, Sheets, Dashboard)

---

## 🎯 Utilisation prévue

### Court terme (semaine du 19 mai — pré-Marrakech)
- **Partie 1 + 2** → diffusion à Kelly + équipe closers (Slack `#kelly-launch`)
- **Partie 1 + 2** → diffusion aux managers d'agences (Romain, Lucas, Axel) avec partie sensibilité commission masquée si nécessaire
- **Partie 3** → conservée pour Boris (admin tech actuel) + futur freelance no-code en cas de réplication

### Moyen terme (Q3 2026)
- Si lancement d'un nouveau programme (Oscar, lancement septembre, etc.) → la **Partie 3** permet à un freelance no-code de répliquer le système pour ~500-1500 €
- Le **routing Short.io** (section 12) et le **scénario A2** (section 19.1) sont les briques structurantes à dupliquer en priorité

### Long terme
- Si Boris quitte le rôle d'admin tech → un successeur peut tout reprendre en lisant la **Partie 3** + les notes techniques V1.5 et V1.2
- Capitalisation des apprentissages post-event Kelly dans le **retex SOP `10_SOPs/Sales/`** (cf. [[Scope - Documentation système Sales bis - Lancement Kelly]])

---

## 📤 Prochaines actions

- [ ] Convertir le markdown en Google Doc partageable (Workspace EC) **ou** Notion page workspace ops
- [ ] Annoncer la V2.0 à Alec + Kelly + équipe sur Slack `#kelly-launch`
- [ ] Faire une review en mode "challenge" avec Alec + Aziz sous 7 jours (pendant Marrakech 21-25 mai si possible)
- [ ] Distribuer la **checklist closer V2.0** (annexe B) en format imprimable (cartes plastifiées dans les open spaces des 3 agences)
- [ ] Initier le **debrief structuré T+7** post-event Kelly (atelier 90 min start/stop/continue par agence)
- [ ] Articuler avec [[Scope - Documentation système Sales bis - Lancement Kelly]] pour la phase 2 (retex post-event)

---

## 📝 Méta

- **Auteurs** : Boris × Claude, 19 mai 2026
- **Version doc** : 2.0
- **Source de vérité** : `/mnt/user-data/outputs/Playbook_Funnel_Commercial_Lancement_Externe_V2.md`
- **Référence technique amont** : [[Ressource - Scénario Make iClosed-Zoho-Sheets - 2026-05-15]] (V1.2)
- **Référence technique aval** : [[Ressource - Automation Zoho-DocuSign Contrats BOSS-ENERGY - 2026-05-13]] (V1.5)
- **Version précédente** : [[Playbook - Funnel Commercial Lancement Externe V1.0 - 2026-05-13]]
- **Confidentialité** : interne Entrepreneurs.com — pas de diffusion externe

## 🔗 Liens connexes Atlas-Brain

- [[_Index|Hub projet Kelly Launch]]
- [[Architecture - Funnel parallèle closers externes]] — architecture initiale du 7 mai
- [[Infrastructure - Setup en cours]] — log de setup
- [[Scenario A2 - iClosed vers Zoho]] — spec production-ready
- [[Closers - Liste opérationnelle Kelly]] — 42 closers
- [[Partenaires - Vue d'ensemble 3 agences]] — comparatif Tip Talent / Momentum / Next Sales
- [[Produit - Méthode Boss Energy]] — catalogue produit
- [[Scope - Documentation système Sales bis - Lancement Kelly]] — chantier SOP retex post-event
- [[Ressource - Replay COMEX hebdo 19 mai 2026]] — bilan post-event Kelly
