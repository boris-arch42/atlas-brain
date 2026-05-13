---
type: playbook
source: doc transmissible aux équipes Entrepreneurs.com
date-created: 2026-05-13
status: V1.0 — prêt à diffuser
audience: ["équipes Kelly Launch (closers, admin, compta)", "admin technique pour réplication futur lancement"]
context: "Playbook complet du funnel commercial Lancement Externe. Doc transférable pour opérer l'existant ET répliquer le système pour un nouveau lancement (Marc Launch, Sophie Launch, etc.) sans dépendance à Boris."
sensitivity: confidential
tags: [playbook, doc-transferable, kelly-launch, funnel, ops, transmission, J12]
related: "[[Ressource - Automation Zoho-DocuSign Contrats BOSS-ENERGY - 2026-05-13]] (note technique V1.3 référence), [[Kelly Launch]], [[BOSS-ENERGY]]"
---

# 📘 Playbook — Funnel Commercial Lancement Externe V1.0

> **Voir contenu complet dans `/mnt/user-data/outputs/Playbook_Funnel_Commercial_Lancement_Externe.md`** (livrable principal)
>
> Cette note est un pointeur Atlas-Brain vers le playbook officiel. Le fichier outputs est la source de vérité — toute modification doit y être faite et la version Atlas-Brain re-synchronisée.

---

## ⚡ Synthèse 30 sec

Playbook structuré en 3 parties pour 2 audiences distinctes :

**Partie 1 — Comprendre le système (commun)**
- Vision & objectif (problème résolu, promesse, 4 étapes du funnel)
- Architecture globale (diagramme système, briques techniques, coûts)
- Rôles & responsabilités (closer, admin, compta, manager, admin tech)

**Partie 2 — Opérer au quotidien (audience: équipes Kelly Launch)**
- Process closer : du Tally au Engagé (16 champs à remplir)
- Process admin : de Engagé à Signé (relances + bascule Fermé Gagné)
- Process compta : Date 1er paiement saisie manuelle
- Dashboard analytics : URL, accès, KPIs, refresh
- Gestion des incidents courants (avec arbres de décision)

**Partie 3 — Répliquer pour un nouveau lancement (audience: admin tech)**
- Pré-requis (accès comptes, skills techniques, infos à collecter)
- Setup Zoho CRM (pipeline + 24 champs + 2 workflow rules)
- Setup template DocuSign
- Setup Google Sheets (4 onglets avec headers exacts)
- Setup scénarios Make (5 modules + 3 modules)
- Setup dashboard analytics (Apps Script + Vercel)
- Tests & validation bout-en-bout (3 tests à passer)

**Annexes** : Glossaire · Checklist closer imprimable · Mapping champs Zoho↔DocuSign · IDs critiques Kelly Launch · Liens externes

---

## 🎯 Utilisation prévue

### Court terme (avant Marrakech 20-25 mai)
- Diffuser la **Partie 1 + 2** à Kelly + équipe closers (Slack #kelly-launch)
- Diffuser la **Partie 2 chapitres 5-6** à l'admin pour cadrer son workflow
- Garder la **Partie 3** pour Boris (admin tech actuel) en cas de réplication

### Moyen terme (Q3 2026)
- Si lancement d'un nouveau programme (Oscar, ou autre) → la Partie 3 permet à un freelance no-code de répliquer pour ~500-1000€

### Long terme
- Si Boris quitte le rôle d'admin tech → un successeur peut tout reprendre en lisant la Partie 3 + la note technique V1.3

---

## 📤 Prochaines actions

- [ ] Convertir le markdown en Google Doc partageable (équipe Entrepreneurs.com a des Google Workspace)
- [ ] Ou bien : convertir en Notion page dans le workspace ops d'Entrepreneurs.com
- [ ] Ou bien : laisser en markdown sur le GitHub repo `kelly-dashboard` (visible aux dev futurs)
- [ ] Annoncer la doc à Alec + Kelly + équipe sur Slack
- [ ] Faire une review en mode "challenge" avec Alec sous 7 jours (avant Marrakech)
- [ ] Compléter le contact compta dans l'annexe E (placeholder actuellement)

---

## 📝 Méta

- **Auteur** : Boris × Claude, 13 mai 2026 (après-midi)
- **Version doc** : 1.0
- **Source de vérité** : `/mnt/user-data/outputs/Playbook_Funnel_Commercial_Lancement_Externe.md`
- **Référence technique** : [[Ressource - Automation Zoho-DocuSign Contrats BOSS-ENERGY - 2026-05-13]] (V1.3)
- **Confidentialité** : interne Entrepreneurs.com — pas de diffusion externe
