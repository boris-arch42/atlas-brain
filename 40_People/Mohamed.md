---
type: person
full-name: "Mohamed [nom de famille à compléter]"
role: "IT externe / Sécurité & infrastructure — Entrepreneurs.com"
team: "Externe / prestataire"
manager: "[[Alec Henry]] (en direct historiquement) / [[Fabrice Jaeger]] (interlocuteur opérationnel) / [[Boris Arduy]] (co-superviseur audit mai 2026)"
reports: 
started: "antérieur à 2024 (à confirmer)"
status: "departure-acted"
departure-date: "2026-05-31 (acté par vocal Alec 29/4)"
source: entrepreneurs-com
sensitivity: rh-nominatif
tags: [it, cybersec, infrastructure, presta-externe, departure-acted, fin-mai-2026, lien-tang-historique, codename-haiti]
---

# Mohamed

> 🔴 **IT externe en sortie actée au 31 mai 2026** — décision Alec confirmée par vocal direct à Boris le 29/4. **Tout le mois de mai** = co-supervision Boris + Mohamed sur l'audit IT consolidé (cybersec + SaaS + rapatriement docs). Boris devient owner permanent du périmètre IT/cybersec post-31 mai.
>
> 🔑 **Codename Alec** : dans le jargon Alec, *"Haïti"* = IT. Donc *"audit Haïti"* = audit IT, *"Mohamed Haïti"* = Mohamed-IT (sa fonction). Pas une référence géographique. Cf. [[Alec Henry]] glossaire jargon.

## 🟢 MAJ 2026-05-05 J4 — Audit IT démarré : 6 vulnérabilités critiques + plan transmission cadré

> Cf. [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] pour le replay complet (31 min, 5 mai 10h34-11h05).
>
> **Premier point Boris↔Mohamed depuis le mandat 29/4**. Ce qui devait être un kick-off d'audit SaaS s'est révélé être un **diagnostic cybersécurité d'urgence**.

### 🟢 Mohamed beaucoup plus mature et lucide que prévu

Le replay révèle un acteur **lucide, structuré, en attente d'un interlocuteur sérieux** — vs la lecture initiale ("pirate" Alec / Mohamed pas 100% confiance) qui suggérait un acteur opportuniste.

Verbatim clôture Mohamed 18:47 :
> *"Parfait, c'est magnifique. C'est ce que j'attendais, c'était de l'action."*

→ **Capital relationnel acquis dès ce 1er point**. Mohamed va utiliser Boris comme levier de déblocage sur les 27 jours qui restent.

→ **Implication** : la lecture Alec ("pirate") n'invalide pas la collaboration, mais **doit être tempérée par la réalité opérationnelle observée**. Mohamed fait son boulot consciencieusement et **bute sur des blocages structurels** (direction qui ne va pas dans la même direction sur la sécurité).

### 🟢 Audit SaaS partiel déjà livré — mais non remonté à Alec

Verbatim Mohamed 01:23 :
> *"Fabrice, qui m'avait demandé l'audit de tous les SaaS il y a 2 semaines [...] j'ai sorti déjà sur Slack, j'ai sorti une audit complète de qui utilise, combien de jours c'est ouvert, combien de jours il a utilisé, combien de messages il a envoyé, combien de messages il a reçu."*

→ L'audit Slack existe depuis ~2 semaines. **Non synthétisé, non remonté à Alec**. Boris doit le récupérer + faire monter politiquement.

→ Mohamed manque les accès aux outils non-Slack pour compléter (chasse les infos auprès de Cédric, Océane).

### 🔴 6 vulnérabilités cybersécurité critiques identifiées

C'est le vrai contenu du replay — le sujet IT n'est **pas qu'un problème de coût** (70-100K€/an), c'est un **risque opérationnel grave + existentiel**.

| # | Vulnérabilité | Statut |
|---|---|---|
| 1 | **Pas de 2FA** sur les comptes critiques — Mohamed a essayé de l'activer, on lui a demandé de la désactiver | 🔴 Critique |
| 2 | **Boîtes mail critiques partagées** entre 4-5 personnes (Revenu, Drive, etc.) | 🔴 Critique |
| 3 | **12 leaks de mots de passe** sur le domaine entrepreneurs.com (récents 2026) probablement non changés | 🔴 Critique |
| 4 | **Accès non révoqués ex-collaborateurs** — cas démontré par Boris : il accède encore à alec@entrepreneurs.com 18 mois après son départ | 🔴 Critique |
| 5 | **APIs orphelines** d'ex-collaborateurs jamais désactivées | 🔴 Critique |
| 6 | **Prélèvements SaaS continus** sur outils désactivés depuis 2024 (ex. ScoreUp) | 🟠 Élevé |

→ **Détail complet** dans [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] section "6 vulnérabilités critiques".

### 🟠 Pattern de gouvernance IT défaillante (au-delà du sujet IT)

Verbatim Mohamed 12:51 (pivot critique) :
> *"Pour que ça marche, il faut que le socle, tu vois, la direction, elle va dans la même direction. Parce que si on a des failles, ça lui dit A, l'autre il dit B, l'autre il dit C, l'audit ça va jamais marcher."*

→ **Même diagnostic qu'Alec** dans son Slack tripartite (1er mai) : décisions distribuées qui ne convergent pas. Mohamed est victime du même système que la verticale Data/IA/Tech/Ops doit résoudre.

→ Verbatim Mohamed 06:00 (sur Keeper) : *"On a mis en place Keeper. Je me bats à chaque fois, je me bats à chaque fois."*

### 🎯 Distribution des rôles posée en séance

Verbatim Boris 11:07 :
> *"Moi, comme ça, on collabore ensemble là-dessus pour que moi je fasse la partie, on va dire, politique, pour m'assurer que tu es bien tout ce qu'il te faut, les accès, les machins, les trucs."*

Verbatim Boris 11:52 :
> *"Et toi, tu peux gérer la partie sécurité, accès, machin, ce qui fait ta force et ta spécialité aujourd'hui."*

Validation Mohamed 11:58 : *"Ouais, c'est parfait."*

→ **Distribution acquise sans friction** : Boris = orchestration politique + déblocage / Mohamed = expertise technique + livraison.

→ Mohamed accepte que Boris devienne owner permanent post-31 mai sans perdre la main sur les 27 jours qui restent.

### 📦 Plan de transmission Mohamed → Boris (4 semaines)

Mohamed va envoyer (à archiver dans `15_Resources/IT-Audit-Mohamed/`) :

| Document | Délai | Action |
|---|---|---|
| Audit SaaS partiel (sur Slack) | Aujourd'hui ou demain | À demander explicitement |
| Audit sécurité fait à l'arrivée Boris | Aujourd'hui ou demain | À demander explicitement |
| Plan d'action sécurité avec deadlines | Quelques jours | 🟢 Demande Boris explicite — base de travail |
| Doc onboarding/offboarding scripting Google | Aujourd'hui ou demain | À demander explicitement |
| Cartographie SaaS complète (post-déblocage Cédric/Océane) | 2-3 semaines | En cours |

→ **Cadence proposée** : point hebdo Boris↔Mohamed sur les 4 semaines (5/5 → 31/5) — 30 min/semaine.

### 🟡 Bonus : infos nouvelles tirées du replay

**Wassim plus impliqué que prévu sur les sujets transverses** — verbatim Mohamed 16:38 : *"J'ai bossé avec Wassim sur toute la partie onboarding [...] scripting pour Google [...] N8N qui fonctionne aujourd'hui."*

→ Cohabitation Mohamed-Wassim observée. Wassim porte plus que de l'IA pure. Cf. [[Wassim]] pour MAJ.

**Audit APIs en cours côté Wassim** — demandé par Mohamed, en cours.

**Campagne phishing interne proposée à Fabrice** — refusée/ignorée — Boris a validé en séance (incarne le mandat de challenge constructif).

**Convention nommage adresses mail non posée** — verbatim Mohamed 13:04 sur les prénoms vs prenom.nom — à intégrer dans le plan.

### 🎯 Actions Boris cette semaine (5-9 mai)

1. **Récupérer les 4 documents** que Mohamed va envoyer (audit SaaS partiel + audit sécurité + plan d'action + doc onboarding)
2. **Pinger Cédric et Océane** pour qu'ils donnent à Mohamed la liste exhaustive des SaaS qu'ils gèrent + accès admin
3. **Caler point hebdo Boris↔Mohamed** (30 min/semaine jusqu'au 31 mai)
4. **Valider la campagne phishing interne** que Mohamed avait proposée à Fabrice (après avoir l'audit sécurité)
5. **Remonter à Alec en 1 message** la dimension sécurité critique du sujet IT (pas juste coût)

### ⚠️ Implication critique : transmission de connaissance prioritaire

Le sujet IT n'est **pas qu'un audit ponctuel** — c'est une **passation d'expertise sur 4 semaines**. Si Boris ne capte pas la matière avant le 31 mai :
- Le savoir-faire technique disparaît (Mohamed est le seul à comprendre la cartographie SaaS actuelle)
- Les 6 vulnérabilités identifiées restent ouvertes
- Boris hérite du sujet sans matière

→ **Mohamed lui-même a verbalisé ce risque** — verbatim 03:10 : *"Souvent chez Entrepreneurs, les gens arrivent, font des trucs, ils partent, ils documentent rien."* (le pattern qu'il faut casser pour Mohamed).

## ⚡ Synthèse en 30 secondes

- **Profil** : IT externe / sécurité & infrastructure d'Entrepreneurs.com depuis avant 2024
- **Statut au 29/4** : **départ acté au 31 mai 2026** (vocal Alec direct à Boris)
- **Mandat Boris** : co-supervision audit IT **avec** Mohamed pendant tout le mois de mai (pas une passation post-départ — une supervision pendant)
- **Périmètre élargi** : audit cybersec + audit SaaS + rapatriement docs externes + structuration accès (consolidé en un seul chantier)
- **Économie actée** : 2000€/mois post-31 mai (24K€/an)
- **Owner permanent post-mai** : Boris centralise IT/cybersec sous son scope (mandat structurel Alec)
- **Sensibilité** : Boris a un historique pro **personnel** avec Mohamed (projet IA pour Tang, hors entrepreneurs.com)
- **Divergence Alec/Fabrice latente** : Alec plus dur (*"pirate"*, *"pas 100% confiance"*) que Fabrice (rassurant, pragmatique). À ne pas relayer.

## 🔴 Mandat Boris consolidé — Audit IT mai 2026

### Sources du mandat (3 layers convergents)

| Date | Source | Apport |
|---|---|---|
| 27/4 | [[Ressource - Replay Alec Fabrice 27 avril 2026]] | Mandat audit SaaS — cible 70-100K€/an d'économies, Mohamed = 24K€/an inclus |
| 28/4 | [[Ressource - Replay Boris Fabrice 28 avril 2026]] | Mandat passation cybersec à Boris avant départ Mohamed (verbatim Fabrice : *"il faut que tu récupères qu'on soit clean cyber secure"*) |
| 29/4 | [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]] | **Consolidation des 3 chantiers en un seul** + calendrier précis tout le mois de mai + promotion implicite Boris owner permanent |

### Périmètre consolidé (vocal Alec 29/4)

| Domaine | À auditer / faire |
|---|---|
| **Fichiers externes** | Inventaire complet + identification de ceux à rapatrier en interne |
| **Abonnements SaaS** | Inventaire + classification : négocier / annuler / mutualiser / remplacer par solution interne |
| **Accès admin** | Inventaire + révocation des accès résiduels (Mohamed + anciens collaborateurs) |
| **MFA / 2FA** | Activation systématique sur tous les outils critiques |
| **Comptes partagés** | Identification + attribution individuelle (fin du partage de credentials) |
| **Documents** | Rapatriement docs externes en interne |
| **Backups + DR** | Vérification stratégie backups + qui a credentials de restauration |
| **Certificats SSL/TLS / DNS** | Renouvellement + qui contrôle les clés privées et DNS records |
| **Scripts cron / API keys** | Inventaire + audit accès |
| **Anciens collaborateurs** | Suppression accès résiduels (cohérent avec rotation cartes Wayo Fabrice il y a 5 mois) |

### Calendrier précis (5 phases sur le mois de mai)

| Phase | Dates | Focus |
|---|---|---|
| **S1 — Cadrage** | 1er-5 mai | Kick-off Mohamed + cartographie complète outils/accès/coûts |
| **S2 — Accès + MFA** | 6-12 mai | Audit accès admin + activation MFA + identification accès résiduels anciens collab. |
| **S3 — Rapatriement + SaaS** | 13-19 mai | Rapatriement docs externes + premières négos SaaS (HubSpot, Zendesk, Aircall) |
| **S3bis — Marrakech** | 20-25 mai | Supervision à distance, maintien du momentum (Boris partiellement absent) |
| **S4 — Exécution + clôture** | 26-31 mai | Rotation credentials critiques + suppression accès Mohamed + livrable final |

→ **Cohérent avec planning audit SaaS** posé au call 1er mai prep (S1-S4).

### Question à arbitrer avec Alec au call 1er mai

- ✅ Mandat ne se rediscute PAS — déjà acté par vocal 29/4
- 📅 Communication à Mohamed : Alec lui a-t-il déjà dit qu'on arrête au 31 mai ? Ou Boris découvre avec lui le 1er mai ?
- 📊 Format de point d'avancement : Slack récap hebdo (vendredi) ou milestone à mi-mois ?
- 🚨 Escalation : si Boris détecte risque cyber sérieux, remontée directe Alec ou via Fabrice ?

## 🟠 Divergence Alec/Fabrice sur la lecture Mohamed

⚠️ **À garder en interne strict — NE PAS relayer**.

### Position Alec (vocal 29/4)

Verbatim :
- *"C'est un pirate"* (= talent qui joue pour son compte, pas acteur malveillant)
- *"Il est pas là dans l'intérêt de l'entreprise, il a son intérêt"*
- *"J'ai pas 100% confiance en lui"*
- *"C'est pas que j'ai pas confiance, mais j'ai pas 100% confiance"*

→ Réserve nette mais nuancée. Pas une accusation. Plutôt une **demande de vigilance accrue**.

### Position Fabrice (call 28/4)

Verbatim Fabrice rapportant Mohamed :
- *"Mon job c'est la sécurité, la confidentialité, c'est mon métier."*
- *"Je vais pas me cramer auprès de... je me tire pas une balle dans le pied."*
- *"Ça c'est vos trucs, vos problèmes, j'interviens pas là-dessus."*

→ Lecture Fabrice : Mohamed est un pro qui veut partir proprement. Audit standard suffisant.

### Posture Boris

- **NE PAS relayer la lecture Alec à Fabrice** (créerait friction inutile)
- **NE PAS relayer la lecture Alec à Mohamed** (briserait la dynamique du mois de co-supervision)
- **Calibrer la rigueur de l'audit au niveau de paranoïa Alec** : rotation systématique des credentials, vérification MFA exhaustive, traque des accès dérobés et comptes parallèles
- **Sans formuler cette rigueur comme de la défiance** : la présenter comme *"hygiène standard de sortie"*, pas *"on te suspecte"*

## 🟠 Contexte historique sensible — lien Tang

### Boris a un historique pro avec Mohamed

Au moment où ça se passait encore bien avec [[Tang]], Boris a travaillé personnellement avec Mohamed **hors d'Entrepreneurs.com** sur un micro-projet IA confié par Tang. Donc Boris connaît Mohamed à titre personnel et avait un pied dans son réseau professionnel via Tang.

→ **Ne pas en faire un sujet politique** avec Alec sauf si Alec amène lui-même la question. C'est un détail biographique, pas un signal d'alerte. Mais ça donne à Boris une **lecture additionnelle** : Mohamed n'est pas un parfait inconnu, donc le mois de mai sera aussi un moment de re-calibration interpersonnelle.

### Episode NAS/Shade/Blackbaize (cas d'école HO15)

Cf. [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] HO15 + [[Ressource - Replay Boris Fabrice 28 avril 2026]] section "Épisode NAS/Shade/Blackbaize".

Mohamed est un acteur central de cette saga. Alec a balancé *"vous êtes des couillons"* à Mohamed et Océane sans tenir compte de la spec (volumétrie 70 To vs 4 To Amine, lock-in technique Shade, etc.). Solution structurelle = NAS physique 1K€ à Dubaï pour archiver 2023-2025 + baisser licences Google.

→ **À déployer pendant le mois de mai dans le cadre de l'audit**. Cohérent avec mandat "rapatrier docs externes en interne" du vocal 29/4. Le NAS est l'arme de rapatriement.

## 🟢 Cohérence multi-mandats convergents

Le mandat audit IT mai 2026 consolide 3 chantiers initialement dispersés en un seul livrable piloté par Boris :

1. **Audit SaaS** (Alec→Fabrice 27/4 → Boris) — cible 70-100K€/an
2. **Passation cybersec Mohamed** (Fabrice→Boris 28/4) — clean cyber secure avant départ
3. **Rapatriement docs externes + structuration accès** (Alec→Boris 29/4) — nouveau

→ **Implication structurelle** : Boris devient **owner permanent IT/cybersec d'Entrepreneurs.com post-31 mai**. Mandat à acter dans la charte V2 Boris/Fabrice section 3.

## 🔗 Liens contextuels

- **NAS / Shade / Blackbaize** : Mohamed est acteur central. NAS physique 1K€ à déployer en mai. Cf. [[Ressource - Replay Boris Fabrice 28 avril 2026]].
- **Cas d'école HO15** : la dynamique Alec → Mohamed est un cas d'école parfait du mécanisme HO15 (impulsivité + scuds sans contexte spec). À garder en tête : ne pas reproduire le pattern pendant le mois de mai.
- **Zendesk** : Sabrina restructure Zendesk avec Mohamed (cf. replay Sabrina 28/4). À voir si la restructuration est terminée avant son départ ou si Boris doit reprendre le sujet en cours.
- **Charte Boris/Fabrice V2** : ajouter ownership permanent IT/cybersec post-mai pour Boris (acté par Alec en direct le 29/4).

## ⚠️ Signaux à observer pendant le mois de mai

| Signal | Lecture | Action immédiate |
|---|---|---|
| Mohamed accepte la co-supervision et livre une cartographie complète | 🟢 Pro standard | Continuer l'audit normal |
| Mohamed fait traîner / livre une doc partielle | 🟠 Frustration latente | Boris pilote en direct, escalade Fabrice |
| Mohamed propose des "extensions de mission" post-mai | 🟠 Ne veut pas partir | Tenir la deadline 31 mai, polite mais ferme |
| Détection accès résiduels post-rotation | 🚨 Risque cyber | Rotation immédiate + alerte Alec direct |
| Détection comptes parallèles non documentés | 🚨 Confirmation lecture Alec | Alerte Alec direct, audit approfondi |
| Mohamed continue à apparaître dans des conversations Alec après 31 mai | 🟠 Lien informel persiste | Capter, ne pas alerter |
| Mohamed amène lui-même un sujet sensible (Tang, Alec, etc.) | 🟠 Test de loyauté Boris | Écouter, ne pas commenter, ne pas relayer |

## 📝 À mettre à jour pendant le mois (S1-S4)

- [ ] Nom de famille
- [ ] Date d'arrivée historique chez Entrepreneurs.com
- [ ] Date de fin de collaboration confirmée (probablement 31 mai)
- [ ] Inventory complet des accès admin (Google Workspace, AWS/cloud, Stripe, Cloudflare, etc.)
- [ ] Inventory MFA / device d'authentification
- [ ] Liste scripts cron / automatisations actifs
- [ ] Liste docs externes à rapatrier
- [ ] Liste abonnements SaaS à négocier / annuler / mutualiser / remplacer
- [ ] Doc cyber transmise (oui/non/partielle)
- [ ] Audit cyber externe nécessaire (oui/non) + budget
- [ ] Rotation credentials critiques (date d'exécution)
- [ ] Successeur / outil de remplacement identifié pour chaque domaine
- [ ] Liste anciens collaborateurs avec accès à révoquer

## 🔗 Notes liées

- [[Alec Henry]] — décideur de l'arrêt + mandat direct Boris (vocal 29/4) + glossaire jargon Alec (Haïti=IT)
- [[Fabrice Jaeger]] — interlocuteur opérationnel historique, source mandat passation 28/4
- [[Tang]] (à créer si pas déjà existant — référence historique uniquement)
- [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]] — mandat consolidé 29/4
- [[Ressource - Replay Boris Fabrice 28 avril 2026]] — contexte mandat passation + cas NAS/Shade
- [[Ressource - Replay Alec Fabrice 27 avril 2026]] — décision Alec d'arrêter Mohamed (24K€/an d'économie audit SaaS)
- [[Sabrina Dahel]] — restructuration Zendesk en cours avec Mohamed
- [[Charte de fonctionnement Boris ↔ Fabrice — V1 (à envoyer)]] — V2 doit ajouter ownership permanent IT/cybersec
- [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] — HO15 (cas d'école NAS/Shade)
- [[Prep - Call Alec 1er mai - Cartographie noeuds operationnels]] — sujet F1 bascule "à valider" → "déjà acté"
