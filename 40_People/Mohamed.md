---
type: person
full-name: "Mohamed [nom de famille à compléter]"
role: "IT externe / Sécurité & infrastructure — Entrepreneurs.com"
team: "Externe / prestataire"
manager: "[[Alec Henry]] (en direct historiquement) / [[Fabrice Jaeger]] (interlocuteur opérationnel)"
reports: 
started: "antérieur à 2024 (à confirmer)"
status: "departure-planned"
departure-target: "31 mai 2026 (acté par vocal Alec du 29/4)"
source: entrepreneurs-com
sensitivity: rh-nominatif
codename-alec: "Mohamed Haïti (jargon Alec : Haïti = IT)"
tags: [it, cybersec, infrastructure, presta-externe, departure-31-mai, lien-tang-historique, mandat-direct-alec, codename-haiti]
---

# Mohamed

> 🔴 **Stub passation IT/cybersec critique** — IT externe en sortie planifiée au **31 mai 2026** (mandat direct Alec à Boris au vocal du 29/4 + acté au replay Alec/Fabrice du 27/4). Boris pilote l'audit IT consolidé (SaaS + cybersec + rapatriement docs) sur **tout le mois de mai** en supervisant Mohamed.

## ⚡ Synthèse en 30 secondes

- **Profil** : IT externe / sécurité & infrastructure d'Entrepreneurs.com depuis avant 2024
- **Statut au 29/4** : départ acté au **31 mai 2026** (mandat direct Alec via vocal du 29/4)
- **Codename Alec** : *"Mohamed Haïti"* — où **"Haïti" = IT** dans le jargon Alec (pas une info géographique, c'est un codename interne)
- **Mandat Boris** : audit IT consolidé sur **tout le mois de mai** en supervision active de Mohamed (pas en passation post-départ)
- **Économie** : 2 000€/mois confirmés post-Mohamed (24K€/an)
- **Position Alec** : *"pirate"* (compétent technique) mais *"pas 100% confiance"*, *"pas dans l'intérêt de l'entreprise"*. Plus dur que Fabrice. **Divergence latente Alec/Fabrice à NE PAS relayer**.
- **Promotion implicite Boris** : *"tu centralises sous ton scope"* + *"100% confiance"* + *"banger"*. L'IT/cybersec devient une **zone permanente Boris** post-mai.

## 🎖️ Mandat direct Alec — vocal du 29/4

> Cf. [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]] pour le contenu complet du vocal et l'analyse politique.

### Verbatim Alec (29/4) — extraits clés

> *"Sur tout le mois de mai, le but c'est que tu fasses l'audit de sécurité Haïti avec Mohamed."*

> *"Tu centralises sous ton scope. T'as les compétences, t'es un banger. J'ai 100% confiance en toi."*

> *"Mohamed, c'est un pirate, mais il est pas là dans l'intérêt de l'entreprise, il a son intérêt. J'ai pas 100% confiance en lui."*

### Périmètre élargi consolidé

Le mandat consolide en un seul chantier deux mandats antérieurs (audit SaaS du 27/4 + passation cybersec du 28/4) :

1. **SaaS** : abonnements à négocier / annuler / mutualiser / remplacer par solution interne
2. **Fichiers externes** : rapatriement vers infra interne (cohérent NAS 1K€ déjà acté)
3. **Accès admin** : audit + révocation comptes Mohamed
4. **MFA** : déploiement sur tous les outils critiques
5. **Anciens collaborateurs** : audit accès résiduels (Tang, Mélissa, Olivia, Nolwenn, Alexis sortant, Axel sortant juin)
6. **Comptes individuels** : fin du partage d'accès, attribution individuelle systématique

## 📅 Calendrier de l'audit IT — tout le mois de mai

> ⚠️ **Recalibrage important** : l'audit n'est pas une passation post-départ comme initialement estimé (S2-S4). C'est un **co-travail sur 4 semaines** avec Mohamed, suivi du départ au 31/5.

| Phase | Dates | Objectif |
|---|---|---|
| **S1** | 1-5 mai | Prise de contact directe avec Mohamed + cartographie initiale infra/SaaS/accès |
| **S2** | 5-12 mai | Audit accès admin + inventaire SaaS complet + identification docs externes à rapatrier |
| **S3** | 12-19 mai | Marrakech 20-25 (préparation) — audit en parallèle, supervision à distance possible |
| **S3bis** | 20-25 mai | Marrakech (pause sur le terrain — Mohamed continue en autonomie supervisée) |
| **S4** | 26-31 mai | Exécution rapatriements + rotation credentials + bascule complète sous scope Boris |
| **Post-31/5** | Juin | Boris owner permanent IT/cybersec (cf. promotion implicite Alec) |

## 🔧 Plan d'audit cybersec à conduire

| Domaine | À auditer | Risque si non-fait |
|---|---|---|
| **Accès admin** | Comptes admin Google Workspace, AWS/cloud, Stripe, Cloudflare, etc. — révocation accès résiduels Mohamed | Backdoor possible, accès résiduels |
| **MFA / 2FA** | Comptes critiques avec MFA configuré — sur device de qui ? | Lockout / accès non-autorisé post-départ |
| **Certificats SSL/TLS** | Renouvellement, qui a la clé privée | Perte certificat = sites HS |
| **DNS** | Qui contrôle les enregistrements DNS (Cloudflare ? OVH ?) | Perte contrôle domaines |
| **Backups** | Stratégie backups (NAS Dubai, Google Drive, Blackbaize) — credentials de restauration | Pas de DR possible si fail |
| **Scripts cron / automatisations** | Hébergés où, accès à qui | Bombes potentielles |
| **Comptes services / API keys** | Inventory des secrets stockés où, sur quel compte | Fuite credentials post-départ |
| **Documentation** | Doc cyber actuelle ? À demander/exiger pendant le co-travail | Aucune transmission de savoir |
| **Anciens accès collaborateurs** | Audit Tang / Mélissa / Olivia / Nolwenn / Alexis / Axel / etc. | Comptes dormants exploitables |
| **Subs / abonnements** | Inventory + qui paye + sur quel compte | Doublons + paiements après départ |

## 🟠 Position Alec vs Position Fabrice — divergence latente

**À NE PAS relayer ni à Mohamed ni à Fabrice. Boris exécute au niveau de paranoïa Alec.**

| Aspect | Fabrice (call 28/4) | Alec (vocal 29/4) |
|---|---|---|
| Compétence technique | Implicitement OK | *"C'est un pirate"* (= très compétent) |
| Loyauté pendant Tang | Mohamed à Fabrice : *"Mon job c'est la sécurité, j'interviens pas dans vos trucs"* — rassurant | *"Pas là dans l'intérêt de l'entreprise, il a son intérêt"* — réservé |
| Confiance | Implicitement OK | *"Pas 100% confiance"* (formulé 2x) |
| Recommandation | Audit standard suffisant | Audit serré, surveiller "accès dérobés" |

### Lecture stratégique

La réserve d'Alec semble **récente, pas tang-historique**. Probable lien avec l'épisode NAS/Shade/Blackbaize (cf. HO15 / replay Alec/Fabrice 27/4) où Alec a balancé *"vous êtes des couillons"* à Mohamed et Océane après comparaison hâtive avec Amine. La friction a peut-être laissé une trace dans la relation Alec/Mohamed.

→ **Posture Boris** : 
- Audit serré (niveau Alec)
- Sans accusation explicite à Mohamed
- Sans relayer la lecture Alec à Fabrice
- Surveiller les *"accès dérobés"* mentionnés par Alec en restant pro

## 🟠 Contexte historique sensible — lien Tang

### Boris a un historique pro avec Mohamed

Au moment où ça se passait encore bien avec [[Tang]], Boris a travaillé personnellement avec Mohamed **hors d'Entrepreneurs.com** sur un micro-projet IA confié par Tang. Boris connaît Mohamed à titre personnel et avait un pied dans son réseau professionnel via Tang.

→ **Ne pas en faire un sujet politique** avec Alec sauf si Alec amène lui-même la question. C'est un détail biographique, pas un signal d'alerte.

### Position Fabrice rassurante (call 28/4)

Fabrice a parlé frontalement avec Mohamed au moment du conflit Tang. Réponse Mohamed à l'époque (rapportée par Fabrice) :
> *"Mon job c'est la sécurité, la confidentialité, c'est mon métier. Je vais pas me cramer auprès de... je me tire pas une balle dans le pied."*

Fabrice signale aussi que la dégradation récente de la dynamique Mohamed/Alec vient des projets empilés sans sens (cas NAS/Shade), pas d'un problème de loyauté Tang.

→ **Lecture Boris** : Mohamed est probablement un pro qui veut partir proprement, pas un acteur hostile. Mais l'audit doit être au niveau de paranoïa Alec, pas Fabrice.

## 🟢 Cohérence avec autres décisions Alec

Au replay Alec/Fabrice du 27/4, Alec a posé son mandat audit SaaS structurel à Boris avec **fin Mohamed IT au 30 mai** comme l'un des leviers d'économie (24K€/an). Le vocal du 29/4 **consolide ce mandat avec la passation cybersec** en un seul chantier piloté par Boris sur tout le mois de mai. L'économie est confirmée à 2 000€/mois (24K€/an).

Cf. :
- [[Ressource - Replay Alec Fabrice 27 avril 2026]] — mandat audit SaaS initial
- [[Ressource - Replay Boris Fabrice 28 avril 2026]] — mandat passation cybersec via Fabrice
- [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]] — consolidation directe

## 🎖️ Promotion implicite Boris — owner permanent IT/cybersec

Le vocal Alec acte plusieurs choses simultanément :
- **Validation compétence** : *"T'as les compétences, t'es un banger"*
- **Confiance maximale** : *"J'ai 100% confiance en toi"*
- **Centralisation** : *"Tu centralises sous ton scope"*

→ **L'IT/cybersec devient une zone permanente de Boris**, pas juste un mandat ponctuel. À acter dans la **charte V2 Boris/Fabrice** : zone IT/cybersec = Boris owner explicite. Cohérent avec posture Co-COO + rôle "general manager de fait" (cf. HO31).

## 🔗 Liens contextuels

- **NAS / Shade / Blackbaize** : Mohamed est acteur central de cette saga (cf. [[Ressource - Replay Boris Fabrice 28 avril 2026]] section "Épisode NAS/Shade/Blackbaize"). Solution structurelle = NAS physique 1K€ à Dubaï pour archiver 2023-2025 + baisser licences Google. À déployer pendant l'audit (S2-S4).
- **Cas d'école HO15** : la dynamique Alec → Mohamed est un cas d'école parfait du mécanisme HO15 (impulsivité + scuds sans contexte spec). Probable origine de la réserve récente d'Alec.
- **Zendesk** : Sabrina restructure Zendesk avec Mohamed (cf. replay Sabrina 28/4). À voir si la restructuration est terminée avant son départ ou si Boris doit reprendre le sujet.

## ⚠️ Signaux à observer

| Signal | Lecture | Action immédiate |
|---|---|---|
| Mohamed accepte la supervision et livre la doc | 🟢 Pro standard | Continuer audit normal |
| Mohamed fait traîner / livre une doc partielle | 🟠 Frustration latente | Boris pilote en direct, escalade Fabrice |
| Mohamed propose des "extensions de mission" | 🟠 Ne veut pas partir | Tenir 31 mai, polite mais ferme |
| Détection accès résiduels post-départ | 🚨 Risque cyber | Rotation immédiate + alerte Fabrice + Alec |
| Mohamed apparaît dans des conversations Alec après départ | 🟠 Lien informel persiste | Capter, ne pas alerter |
| Mohamed pose des questions sur la position Alec à son égard | 🟠 Il sent qu'Alec se méfie | Réponse neutre, ne PAS relayer la position Alec |

## 📝 À mettre à jour pendant l'audit

- [ ] Nom de famille
- [ ] Date d'arrivée historique chez Entrepreneurs.com
- [ ] Inventory complet des accès admin (Google Workspace, AWS/cloud, Stripe, Cloudflare, etc.)
- [ ] Inventory MFA / device d'authentification
- [ ] Liste scripts cron / automatisations actifs
- [ ] Doc cyber transmise (oui/non/partielle)
- [ ] Audit cyber externe nécessaire (oui/non) + budget
- [ ] Rotation credentials critiques (date d'exécution)
- [ ] Successeur / outil de remplacement identifié pour chaque zone
- [ ] Inventory SaaS complet avec économies négociées
- [ ] Inventory anciens collaborateurs avec accès résiduels révoqués

## ✅ Vérifications préalables au call Alec 1er mai

- [ ] **Vérifier alignement Fabrice** : *"Alec m'a envoyé un vocal sur l'audit IT avec Mohamed sur mai. Tu es au courant du calendrier ?"* — neutre, sans relayer la position Alec sur Mohamed
- [ ] **Préparer accusé de réception** au call : *"J'ai bien reçu ton vocal. Je prends. Démarrage 5 mai (S1) avec cartographie."*
- [ ] **Préparer 2-3 questions de cadrage** : budget audit cyber externe possible (CASES type) ? Modalités com à Mohamed (Alec parle direct ou Fabrice annonce) ?

## 🔗 Notes liées

- [[Fabrice Jaeger]] — interlocuteur opérationnel actuel + à vérifier alignement avant call 1er mai
- [[Alec Henry]] — décideur direct du mandat (vocal 29/4) + position personnelle réservée sur Mohamed
- [[Tang]] (à créer si pas existant — référence historique uniquement)
- [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]] — mandat direct
- [[Ressource - Replay Boris Fabrice 28 avril 2026]] — contexte mandat passation initial via Fabrice
- [[Ressource - Replay Alec Fabrice 27 avril 2026]] — décision Alec audit SaaS (24K€/an)
- [[Sabrina Dahel]] — restructuration Zendesk en cours avec Mohamed
- [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] — HO15 (cas d'école NAS/Shade, probable origine de la réserve Alec)
- [[Charte de fonctionnement Boris ↔ Fabrice — V1 (à envoyer)]] — V2 doit acter zone IT/cybersec = Boris owner permanent
