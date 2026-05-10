---
type: sop
domain: Tech
owner: "[[Mohamed]]"
owner-post-31-mai: "[[Boris Arduy]]"
status: draft
last-reviewed: 2026-05-10
frequency: par-mouvement-rh
related-decisions:
  - "[[2026-04-30 - Operating Partner chez Entrepreneurs.com]]"
related-frameworks:
  - "[[Cadre - Process IT-SaaS-Cybersec]]"
related-sops:
  - "[[People-RH - Onboarding-Offboarding collaborateurs]]"
tags: [it, accès, gouvernance, zero-trust, mfa, scripting, mohamed, transmission, pilier1-cybersec]
source: entrepreneurs-com
sensitivity: confidential
---

# SOP — Process création-transmission accès

## Pourquoi ce process existe

Volet **technique** du cycle de vie collaborateur. Pendant du SOP RH [[People-RH - Onboarding-Offboarding collaborateurs]] : ce que l'IT exécute concrètement à chaque arrivée, mouvement et sortie.

Le diagnostic Mohamed du 5 mai 2026 (cf. [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]]) a identifié **6 vulnérabilités cybersécurité critiques**, dont 4 sont directement adressées par ce SOP :
- ❌ Pas de 2FA → MFA d'office à la création
- ❌ Boîtes mail critiques partagées entre 4-5 personnes → comptes uniques
- ❌ Accès non révoqués ex-collaborateurs → révocation H+24 systématisée
- ❌ APIs orphelines → audit + révocation au départ

Il matérialise opérationnellement le **Pilier 1 (gouvernance des accès)** du [[Cadre - Process IT-SaaS-Cybersec]] et préfigure ce que Boris hérite comme owner permanent post-31 mai.

**Pourquoi inclure Mohamed dans la boucle systématiquement** (jusqu'au 31/5) : aujourd'hui les heads donnent des accès en direct sans IT Manager. Mohamed apprend les arrivées/départs après-coup et chasse les infos. Ce SOP **inverse le flux** : aucun accès n'est créé ni révoqué hors de l'IT.

## Quand le déclencher

À chaque déclenchement d'une étape du SOP RH onboarding/offboarding qui nécessite une action technique :
- **Onboarding étape 2 (J-3)** — création des accès
- **Offboarding étape 3 (J0 / H+24 max)** — révocation des accès
- **Mouvement interne** — extension/retrait d'accès partiel
- **Détection de leak** ou alerte cybersec — rotation immédiate des credentials concernés

## Qui est impliqué

- **Owner** : [[Mohamed]] jusqu'au 31/5/2026 → [[Boris Arduy]] ensuite (mandat permanent vocal Alec 29/4)
- **Co-exécutant scripting** : [[Wassim]] (n8n + scripts Google Workspace déjà en place)
- **Demandeur légitime** : uniquement le head qui a déclenché l'étape 1 du SOP RH. **Aucune demande directe d'un collaborateur** — passage obligatoire par le head.
- **Filet de sécurité post-mai** : si Boris est indisponible (Marrakech 20-25/5, congés), désigner un suppléant explicite — ne **jamais** laisser un head donner un accès en direct.

## Étapes — Création d'accès (Onboarding J-3 → J0)

### 1. Réception du kit d'onboarding RH
- **Trigger** : étape 1 du SOP RH validée, kit transmis à l'IT.
- **Action** : vérification de complétude du kit. Si incomplet → renvoi au head, pas de création tant que tout n'est pas là.
- **Output** : ticket création accès ouvert, lié à la fiche `40_People/{Prénom Nom}.md`.

### 2. Détermination du périmètre d'accès
- **Action** : matrice rôle → outils (à construire en S2 mai par Mohamed avec input des heads). Par défaut, accès strict aux outils utilisés au quotidien par la fonction.
- **Outils standard pour 99% des fonctions** : Google Workspace (Drive, Calendar, Gmail), Slack, Notion, Keeper.
- **Outils par fonction** :
  - **Sales/Closeurs** : HubSpot, Aircall, Calendly
  - **CS** : Zendesk, HubSpot (lecture), Loom
  - **Marketing** : HubSpot (admin), Data Studio, outils créa
  - **Ops/Tech** : selon mission (BigQuery, n8n, Supabase, etc.)
  - **Finance** : Pennylane, accès bancaire limité, HubSpot (lecture deals)
- **Règle d'or** : un accès `admin` n'est jamais donné par défaut. Justifier explicitement, tracer dans le ticket.

### 3. Exécution scripting Google
- **Action** : lancement du script Wassim (n8n + Google Workspace API) qui crée :
  - Compte Google Workspace `prenom.nom@entrepreneurs.com` (convention nommage à valider — cf. verbatim Mohamed 13:04 sur prénoms vs prenom.nom, à arbitrer)
  - **MFA activée d'office** — pas d'option de désactivation
  - Mot de passe initial généré aléatoirement, transmis via Keeper (jamais par mail)
  - Ajout aux groupes pertinents (Slack, Notion, etc.) via SSO Google
  - Inscription au password manager Keeper
- **Pas de partage de credentials, jamais.** Si le besoin d'usage est partagé, créer un compte de service dédié.

### 4. Configuration outils tiers (non SSO Google)
- **Action** : créer les comptes individuels sur les outils tiers selon le périmètre étape 2. Privilégier SSO Google quand possible (réduit la prolifération de credentials, pilier 2).
- **API keys éventuelles** : si la fonction nécessite des API keys (dev, automation), création + entrée dans le registre des APIs (pilier 4) avec : qui, pour quoi, depuis quand, date de revue.

### 5. Logging et traçabilité
- **Action** : entrée dans le journal des accès (table maintenue par l'IT) : qui, quoi, quand, pour combien de temps (date de revue), donné par qui.
- **Vérification finale** : tous les outils accessibles, MFA active partout, compte unique partout, password manager OK.

### 6. Remise au manager + brief sécurité
- **Action** : transmission du kit accès au manager qui le donne au collaborateur à J0. Brief sécurité minimal intégré au parcours d'arrivée (cf. SOP RH étape 3).

## Étapes — Révocation d'accès (Offboarding J0 → J+30)

### 1. Réception du ticket offboarding RH
- **Trigger** : étape 1 du SOP RH offboarding (annonce départ).
- **Action** : ouverture ticket révocation, audit préalable des accès du sortant : périmètre Google Workspace, outils tiers, API keys, scripts cron, comptes partagés auxquels il avait accès.
- **Output** : checklist de révocation pré-remplie, prête à exécuter J0.

### 2. Audit des passifs techniques du sortant
- **Action** : avant la révocation, identifier :
  - **APIs créées par le sortant** — à révoquer ou transférer (cf. pilier 4 — APIs orphelines = vulnérabilité critique #5)
  - **Scripts cron / automatismes actifs** sous son identité — à transférer ou désactiver
  - **Comptes partagés** auxquels il avait accès — credentials à roter (même sans suspicion, hygiène standard)
  - **Documents externes / fichiers cloud personnels** liés à des projets pro → cohérent avec mandat rapatriement docs externes (vocal Alec 29/4)
- **Output** : note de passation technique, intégrée au plan de passation RH (étape 2 SOP RH).

### 3. Exécution scripting offboarding (J0, H+24 max)
- **Action** : lancement du script Wassim qui :
  - Désactive le compte Google Workspace (sans le supprimer immédiatement — conservation 30 jours pour récupération éventuelle de données pro)
  - Suspend les accès SSO sur tous les outils tiers
  - Retire des channels Slack et groupes Notion
  - Révoque les API keys identifiées étape 2
  - Désactive les scripts cron sous son identité
- **Rotation des credentials partagés** auxquels il avait accès (même sans suspicion). Cas démontré à éviter : Boris a accès `alec@entrepreneurs.com` 18 mois après son départ.

### 4. Vérification de complétude
- **Action** : test de connexion à chaque outil critique avec les anciens credentials → doit échouer. Test API keys → doit échouer.
- **Output** : checklist révocation signée + horodatée + archivée dans le ticket.

### 5. Audit post-mortem (J+30)
- **Action** : balayage périodique des comptes Google Workspace désactivés non encore supprimés, des scripts cron orphelins, des API keys non utilisées depuis le départ.
- **Output** : compte rendu audit dans le journal RH, validé par Boris (post-31 mai) ou Mohamed (jusqu'au 31/5).

## Étapes — Mouvement interne (extension/retrait partiel)

### Cas extension (promotion, élargissement scope)
- Mêmes étapes que création (étapes 2-5) mais limitées au delta.
- **Pas de cumul automatique** : si une promotion fait perdre un scope, retirer les accès devenus inutiles (pilier 2 — une licence = un usage actif).

### Cas retrait (changement de fonction)
- Mêmes étapes que révocation (étapes 2-4) mais limitées aux outils retirés.
- Ne pas laisser empiler les accès historiques.

## Étapes — Détection leak / alerte cybersec

### Cas leak credentials détecté (outil de surveillance Mohamed)
- **Action H+0** : changement immédiat du mot de passe leaké. Notification au collaborateur. Audit accès récents sur l'outil concerné.
- **Action H+24** : vérification qu'aucun accès non autorisé n'a eu lieu depuis le leak. Si oui, escalade Alec direct.
- **Cas en stock** : 12 leaks Apollo 2024 identifiés, mots de passe **probablement non changés** → action prioritaire S2-S3 mai.

## Cas particuliers

### Prestataire / consultant offshore
- Périmètre d'accès **très restreint** par défaut (pas de boîte mail @entrepreneurs.com sauf justification).
- API keys avec date de revue obligatoire.
- Date de fin contractuelle = trigger auto de la révocation.

### Compte de service / automatisation
- Compte dédié, pas attribué à une personne. Owner = équipe, pas individu.
- Credentials stockés exclusivement dans Keeper, accès limité à l'IT et aux owners techniques.
- Audit annuel obligatoire (pilier 4).

### Sortie immédiate / risque sécurité
- Étapes 3-4 exécutées **dans l'heure**, en parallèle de l'étape 1 (pas séquentiel).
- Boris alerté immédiatement (post-31 mai) ou Mohamed (jusqu'au 31/5) **et** Alec si suspicion de risque.
- Rotation **systématique** de tous les credentials partagés auxquels le sortant avait accès, sans exception.

## SLA récapitulatif

| Action | SLA |
|---|---|
| Création accès (onboarding) | J-3 → J0 |
| Révocation accès (offboarding standard) | J0, H+24 max |
| Révocation accès (sortie immédiate) | H+1 max |
| Audit post-mortem offboarding | J+30 |
| Rotation credentials partagés post-départ | J0, H+24 max |
| Réponse à un leak détecté | H+0 changement mot de passe, H+24 audit complet |

## Pièges connus

- **Demandes d'accès qui passent en direct** par DM Slack à Mohamed/Boris hors process → règle : aucun accès créé sans ticket lié à un kit RH. Renvoyer au head systématiquement.
- **MFA désactivée à la demande "parce que c'est pratique"** → cas vécu, à ne plus jamais reproduire (verbatim Mohamed : *"j'ai essayé d'activer 2FA Google, on m'a demandé de la désactiver"*). MFA non négociable.
- **Comptes partagés créés "temporairement"** → ils restent. Pas de tolérance, compte unique ou compte de service explicite.
- **Révocation partielle** : on désactive Google Workspace mais on oublie les outils tiers, les API keys, les scripts cron. La checklist doit être exhaustive et l'audit J+30 la valide.
- **PC perso avec mot de passe enregistré dans le navigateur** → cas démontré par Boris. À tracer au moment de l'onboarding (kit RH étape 1) et à interdire pour outils critiques.
- **Lacune week-end / vacances** : si une sortie immédiate tombe un samedi soir, qui exécute la révocation ? Désigner suppléant explicite (post-mai : Boris + 1 backup à identifier).
- **Convention nommage non posée** (verbatim Mohamed 13:04) — `prenom@` vs `prenom.nom@`. À arbitrer en S2 mai et figer dans ce SOP. Tant que non figé : par défaut `prenom.nom@`.

## Cadence de revue

- **Hebdo** (jusqu'au 31/5) : point Boris × Mohamed jeudi 17h — revue des mouvements de la semaine, anomalies, leaks détectés.
- **Hebdo** (post-31/5) : point Boris seul (ou avec successeur), même cadence.
- **Mensuel** : audit aléatoire de 5 comptes au hasard pour vérifier l'hygiène (MFA active, accès cohérents avec la fonction, pas de credentials partagés).
- **Trimestriel** : audit complet du registre des accès + cartographie SaaS (pilier 2) + cartographie APIs (pilier 4).

## Articulation avec les autres SOPs et frameworks

- [[People-RH - Onboarding-Offboarding collaborateurs]] → SOP RH qui appelle ce SOP technique aux étapes 2 (onboarding) et 3 (offboarding)
- [[Cadre - Process IT-SaaS-Cybersec]] → ce SOP matérialise le **pilier 1** (gouvernance des accès) et alimente les piliers 2 (SaaS), 4 (APIs), 5 (formation/culture sécurité)
- [[Mohamed]] → owner actuel jusqu'au 31/5
- [[Wassim]] → co-exécutant scripting (n8n + Google Workspace)

## Décisions stratégiques rattachées

- Vocal Alec 29/4 — mandat IT permanent Boris post-31 mai (cf. [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]])
- Call verticale Ops/IT/Tech/Data/IA 5 mai — supervision Mohamed transférée Fabrice → Boris (cf. [[Ressource - Replay Ops IT Tech Data IA 5 mai 2026]])
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] KR3.3 (audit IT consolidé livré 31/5)

## Historique

- 2026-05-10 — Création v1 (Boris). Statut **draft** — à valider avec Mohamed au prochain point hebdo (jeudi 14 mai 17h). Activer en parallèle de la livraison du plan d'action sécurité Mohamed.
- À enrichir : matrice rôle → outils complète (étape 2 création), convention nommage emails arbitrée, suppléant désigné pour absences Boris.
- Prochaine révision : J+30 (10 juin) après premier cycle complet (sortie Mohamed 31/5 inclus = test ultime du process sur le concepteur lui-même).
