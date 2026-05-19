---
type: scope
status: en-cours-critique
date-created: 2026-05-19
deadline-livrable-v0: 2026-05-21 (avant départ Marrakech)
deadline-déploiement-phase1: 2026-05-23 → 2026-05-25 (post-lancements)
deadline-consultation-Alec: avant 2026-05-25 (départ Alec Dubai)
owner-principal: "[[Boris Arduy]]"
co-owner-technique: "[[Mohamed]]"
sponsor: "[[Alec Henry]]"
consult-list: ["[[Mohamed]]", "[[Boris Arduy]]", "Greg", "Mehdi (éventuel)"]
related-replay-déclencheur: "[[Ressource - Replay Weekly Fabrice × Alec 18 mai 2026]]"
related-audit: "[[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]]"
tags: [cybersec, sprint, 48-72h, fichiers-publics, email-redirects, iclose, slug, nas, rgpd, mohamed, audit-it]
source: entrepreneurs-com
sensitivity: confidential-max
---

# Scope — Sprint Cybersec 48-72h (mai 2026)

> **🚨 Sprint d'urgence** déclenché par l'audit Mohamed (avril-mai 2026) qui a révélé une **dette de gouvernance cybersécurité massive** sur EC.
>
> **3 vecteurs d'exposition critiques** :
> 1. **~82 000 fichiers publiquement accessibles** sur la plateforme (parts importantes des documents entreprise, pas seulement isolés)
> 2. **Redirections email entreprise → boîtes privées** (Yahoo, Outlook) — supprimées immédiatement par Boris au 18/5
> 3. **Slug iClose modifiable** par 6-7 super-admins → vecteur d'incident majeur démontré (crash lancement Kelly, perte estimée Alec >1M€)
>
> **Mandat Alec en weekly 18/5** : *"verrouillage par défaut de toute la plateforme, accès public uniquement si explicitement nécessaire"* + **plan d'action structuré sous 48-72h** + **owner + échéance plan NAS** avant son départ Dubai (25-30/5).
>
> **Verbatim Boris en séance** : *"Pour une activité entièrement numérique servant majoritairement des clients français et soumise au RGPD, une faille de sécurité majeure pourrait être existentielle."*

---

## Pourquoi ce scope existe

Ce scope cadre le **sprint cybersec d'urgence** demandé par Alec, **distinct mais articulé** avec :
- L'**audit IT Mohamed** en cours (deadline 31/5 — KR3.3 Plan Q1)
- Le **plan cybersec long terme** (cadre [[Cadre - Process IT-SaaS-Cybersec]] en construction)
- La **cartographie SaaS** pour l'audit dépenses (KR2.2)

Le sprint cybersec adresse **l'exposition immédiate** (verrouillage + plan NAS + investigation iClose), pendant que l'audit IT consolide la photo globale et que le plan SaaS pilote les économies.

---

## 🎯 Objectifs du sprint

### Objectif 1 — Verrouillage par défaut de la plateforme (méthode dossier par dossier)

Cible : **fichiers publiquement accessibles ramenés à <500** (seulement contenus clients explicitement nécessaires).

**Précédent à éviter** (Fabrice en séance) : un audit similaire passé avait abouti à un verrouillage complet qui a **cassé des flux clients légitimes** + généré des centaines de tickets support + impacté Cédric en session live (plus de vidéos, plus de workbooks).

**Méthode arbitrée Boris** : remise à plat **dossier par dossier, sous-dossier par sous-dossier**. Pas d'action globale "tout privé".

**Timing** : **post-lancement Kelly**, idéalement **vendredi 23 → dimanche 25 mai** (Boris en route Marrakech mais reste joignable). Première vague pilotée par Mohamed avec validation Boris à distance.

### Objectif 2 — Plan transfer NAS avec owner et échéance

Cible : **document Slack structuré** (méthode CAPS LOCK + titre validée Fabrice) partagé à Alec avant son départ Dubai (avant 25/5).

**Contenu** :
- ~70 To de vidéos à sauvegarder
- Owner désigné nommément (à proposer Alec : Mohamed lead, Boris architecte, Greg/Mehdi consult)
- Échéance claire (proposer : V0 inventaire 31/5, déploiement Phase 1 juin, complet août)
- Articulation avec migration outils INPA → DOODU mentionnée par Fabrice
- Budget estimé (achat NAS physique + setup) — cohabite avec KR2.2 (économies Google ~20K€/an si NAS perso)

**Consultations préalables (avant doc à Alec)** : Mohamed + Boris + Greg + éventuellement Mehdi.

### Objectif 3 — Investigation slug iClose

Cible : **identifier qui a changé le slug et quand**, avec preuves logs.

**Action Boris** :
- Examiner les logs iClose (qui a accédé + horodatage du changement)
- Croiser avec la liste des 6-7 super-administrateurs
- **Important** : ne **pas attribuer à Nicolas Farolfi sans preuve** (cf. décision sortie 18/5)
- Préparer note factuelle pour Alec post-investigation

**Cible livrable** : note investigation **avant 25 mai** (avant départ Alec Dubai).

### Objectif 4 — Email redirections (déjà actées, à fermer proprement)

Cible : **cartographie complète des redirections résiduelles** + **fermeture confirmée** + **note de communication interne** pour rappeler la règle (pas de redirection vers boîtes privées).

**Action Boris** :
- Cartographie exhaustive auprès de Mohamed (qui voit les logs Google)
- Si redirections résiduelles → suppression immédiate
- Doc règle interne : "Les emails entreprise restent dans l'environnement entreprise" — à diffuser COMEX

### Objectif 5 — Domaines/licences séparés pour collaborateurs externes (cadrage seulement)

**Recadrage Alec en séance** : *"Est-ce qu'un domaine ou une structure de nommage est réellement nécessaire ? Le vrai sujet pourrait simplement être le plan de transfert NAS."*

→ **Décision domaine subordonnée au plan NAS** (Objectif 2). Ne pas l'avancer en parallèle, le réintroduire après si le plan NAS le justifie économiquement.

**Cadrage pour mémoire** :
- Domaine principal pour équipe cœur (~30 personnes)
- Sous-domaine pour coachs, closers, prestataires externes (~100+ utilisateurs)
- Bascule sur **licences Google moins coûteuses** (vs licences entreprise) — économie potentielle à chiffrer pour KR2.2

---

## 📅 Calendrier du sprint

| Date | Jour | Action | Owner |
|---|---|---|---|
| **Mar 19/5** | Hoy | Création scope + brief Mohamed | Boris |
| **Mer 20/5** | J+1 | Session 2-3h Boris × Mohamed (cadrage plan) | Boris + Mohamed |
| **Mer 20/5** | J+1 | Consultation Greg + éventuel Mehdi (NAS) | Boris |
| **Mer 20/5** | J+1 | Démarrage investigation logs iClose | Boris |
| **Jeu 21/5** | J+2 | Livrable V0 plan cybersec partagé à Alec (Slack) | Boris |
| **Jeu 21/5** | J+2 | Briefing pré-Marrakech avec Alec (inclut validation plan) | Boris |
| **Ven 22/5** | J+3 | Sortie Nicolas (coordination accès cybersec) | Boris + Mohamed |
| **Ven 23/5 → Dim 25/5** | J+3-5 | Phase 1 verrouillage fichiers (dossier par dossier) | Mohamed (Boris valide à distance Marrakech) |
| **Lun 26/5** | J+6 | Note investigation iClose finalisée | Boris |
| **Lun 26/5** | J+6 | Doc plan NAS final partagé à Alec (avant Dubai) | Boris |
| **Sam 31/5** | J+11 | Reporting consolidé audit IT + cybersec pour mensuel 1/6 | Boris + Mohamed |

---

## 🟢 Phase 1 — détails de la méthode "dossier par dossier"

**Principe** : verrouillage progressif avec validation business avant chaque passe.

**Découpage en blocs** :
1. **Bloc admin interne** (RH, finance, légal) — verrouillage immédiat possible, peu d'impact client
2. **Bloc opérationnel interne** (process, SOPs, brainstorms) — verrouillage immédiat possible
3. **Bloc enregistrements d'appels clients** — verrouillage critique RGPD, à prioriser
4. **Bloc contenus clients live** (formations, workbooks, vidéos) — **dernier**, valider avec Sabrina + Cédric avant chaque passe
5. **Bloc archives** (>12 mois) — verrouillage immédiat possible

**Cadence visée** : 1 bloc/jour, validation par Boris (à distance Marrakech) avant déploiement bloc suivant.

**Rollback** : si un flux client casse, retour à l'état précédent **dans l'heure** + identification précise du dossier problématique.

---

## 📊 KPIs du sprint

| KPI | Baseline (19/5) | Cible J+11 (31/5) |
|---|---|---|
| Fichiers publics | ~82 000 | <500 (uniquement clients) |
| Redirections email résiduelles | Inconnu (à cartographier) | 0 |
| Tickets support liés au verrouillage | 0 | <10 (cible <0.1% utilisateurs) |
| Plan NAS partagé à Alec | Non | Oui, avec owner + échéance |
| Investigation slug iClose | Non démarrée | Note factuelle livrée |
| Doc règle "emails entreprise" diffusé | Non | Oui (COMEX) |

---

## 🔍 Signaux faibles & considérations

1. **🔴 Boris physiquement absent jeudi-dimanche** (Marrakech 21-25). Mohamed doit pouvoir exécuter Phase 1 en autonomie supervisée. **Test critique de la résilience de la verticale.**

2. **🟡 Tension cadence Alec** : Alec a dit *"le sujet NAS est repoussé depuis trop longtemps"* — signal de frustration. Le **doc plan NAS avant son départ Dubai** est un test de crédibilité Boris sur le mandat IT permanent.

3. **🟢 Capital politique Mohamed** : Boris l'a défendu publiquement 2 fois cette semaine (weekly 18/5 + COMEX 19/5). Mohamed doit **livrer** ce sprint — c'est son test de transformation "audit-er" → "exécution-er".

4. **🔴 Risque casse client pendant lancements** : la Phase 1 doit absolument **respecter le tempo des lancements**. Si Sabrina ou Cédric signalent un blocage → arrêt immédiat, rollback, ajustement.

5. **🟡 RGPD comme arme narrative** : le verbatim Boris ("faille existentielle pour activité RGPD") résonne avec Alec. À continuer à utiliser sobrement dans les comms écrites pour donner le poids stratégique au sprint.

---

## 🔗 Articulation avec les autres chantiers

| Chantier | Articulation |
|---|---|
| **Audit IT Mohamed (deadline 31/5)** — KR3.3 | Sprint cybersec = sous-projet urgent de l'audit IT. Reporting consolidé 31/5 inclura les deux. |
| **KR2.2 (audit SaaS 70-100K€/an)** | Économie domaines séparés (~100 licences) à intégrer si le sujet est rouvert post-NAS. |
| **[[Cadre - Process IT-SaaS-Cybersec]]** (V1 en construction) | Le sprint nourrit le pilier 3 (cybersec) du cadre long terme. |
| **Sortie Nicolas Farolfi 22/5** | Coordination accès cybersec lors du retrait — fenêtre jeudi-vendredi nuit. |
| **Mandat onboarding/parcours post-vente sales externes** (Alec 19/5) | Cohérence avec décision de **garder les emails entreprise dans l'environnement entreprise** — pas de redirections vers boîtes privées sales externes. |
| **Plan trimestriel Q1 — KR3.3 + nouveau scope cybersec** | À intégrer comme MAJ majeure du Plan Q1 (audit IT devient audit IT + cybersec). |

---

## 📋 Action plan Boris cette semaine

### Mardi 19/5 (aujourd'hui)
- [ ] Brief Mohamed sur le scope (15 min Slack ou call rapide)
- [ ] Bloquer 2-3h session structuration plan mercredi
- [ ] Caler briefing pré-Marrakech avec Alec (inclut validation plan cybersec)

### Mercredi 20/5
- [ ] Session 2-3h Boris × Mohamed : finaliser plan structuré
- [ ] Consulter Greg + éventuel Mehdi sur NAS (30 min chacun)
- [ ] Démarrer investigation logs iClose (1-2h)
- [ ] Préparer doc Slack V0 plan cybersec

### Jeudi 21/5 (matin avant départ Marrakech)
- [ ] Publier doc Slack V0 (Alec + Fabrice + Mohamed + Anisse)
- [ ] Briefing Alec (inclut validation cybersec + Sophia + observation Marrakech)
- [ ] Brief Mohamed sur exécution Phase 1 en autonomie supervisée

### Vendredi 22/5 → Dimanche 25/5 (depuis Marrakech)
- [ ] Validation à distance Phase 1 (1 bloc/jour, validation Slack par Boris)
- [ ] Coordination retrait accès Nicolas avec Mohamed (vendredi)

### Lundi 26/5 (retour)
- [ ] Finaliser note investigation iClose
- [ ] Finaliser doc plan NAS (partager à Alec avant Dubai)
- [ ] Mensuel reporting consolidé en préparation (audit IT + cybersec + SaaS)

---

## 🔗 Notes liées

- [[Ressource - Replay Weekly Fabrice × Alec 18 mai 2026]] — déclencheur du sprint
- [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] — origine des découvertes
- [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]] — mandat permanent Boris IT/cybersec
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] — KR3.3 (audit IT → audit IT + cybersec)
- [[Mohamed]] — pilier opérationnel cybersec
- [[Nicolas Farolfi]] — coordination retrait accès lors sortie 22/5
- [[Cadre - Process IT-SaaS-Cybersec]] — cadre long terme (V1 en construction)
- [[Scope - Préparation Marrakech (event EC 21-25 mai)]] — absence physique Boris pendant Phase 1
- [[Alec Henry]] — sponsor + mandataire
- [[Fabrice Jaeger]] — co-pilote finance + observateur cybersec
