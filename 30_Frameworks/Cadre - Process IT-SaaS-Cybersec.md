---
type: framework
status: V1 préliminaire (à enrichir post-livraison plan Mohamed)
last-updated: 2026-05-05
sensitivity: confidential
tags: [framework, it, cybersec, saas, process, mohamed, transmission, gouvernance-it]
---

# Cadre — Process IT / SaaS / Cybersécurité

> **Statut** : V1 préliminaire posée à partir du diagnostic Mohamed du 5 mai 2026. Cf. [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]]. Cadre **à enrichir** quand Mohamed livrera son plan d'action complet (sous quelques jours).
>
> **Objectif** : poser un cadre minimal de référence sur la gouvernance IT/SaaS/Cybersec d'Entrepreneurs.com, pour que Boris ait une base structurée pour piloter le sujet en owner permanent post-31 mai.

## 🎯 Pourquoi ce cadre existe

Le sujet IT chez Entrepreneurs.com a longtemps été géré en mode opérationnel-réactif sans gouvernance formalisée. Conséquences observables :

- **6 vulnérabilités cybersécurité critiques** identifiées par Mohamed (leaks mots de passe, pas de 2FA, accès non révoqués, APIs orphelines, comptes partagés, prélèvements SaaS continus sur outils désactivés)
- **70-100K€/an d'économies SaaS identifiables** (cible mandat Alec)
- **Pas de garde-fou sur les accès** : les heads donnent des accès en direct sans IT Manager
- **Direction qui ne va pas dans la même direction** sur la sécurité (verbatim Mohamed)

Ce cadre pose les **5 piliers** d'une gouvernance IT/SaaS/Cybersec saine pour une boîte de la taille d'Entrepreneurs.com (80+ personnes, 100% remote, 100% digitalisée).

## 🏛️ Pilier 1 — Gouvernance des accès (zero trust)

### Principe directeur
**Aucun accès ne doit transiter par un canal informel**. Toute demande d'accès passe par l'IT (post-31 mai = Boris ou successeur), avec traçabilité complète.

### Composantes
- **Onboarding structuré** : formulaire dédié à chaque arrivée listant les outils nécessaires par fonction
- **Comptes utilisateurs uniques** (jamais de partage de credentials)
- **Logging systématique** : qui accède à quoi, quand
- **Offboarding propre** : à la sortie, désactivation systématique de tous les accès dans les 24h
- **MFA / 2FA obligatoire** sur tous les outils critiques (mail, drive, HubSpot, BigQuery, etc.)

### État actuel (5 mai 2026)
- ❌ Onboarding : pas de formulaire structuré, accès donnés ad hoc par heads
- ❌ Comptes uniques : 4-5 personnes partagent les boîtes mail Revenu et Drive
- ❌ Logging : pas de visibilité IT sur les accès donnés
- ❌ Offboarding : cas Boris démontre la faille — accès `alec@entrepreneurs.com` actif 18 mois après départ
- ❌ MFA : Mohamed a essayé d'activer 2FA Google, on lui a demandé de la désactiver

### Cible 31 mai 2026
- ✅ MFA activée sur tous les comptes critiques
- ✅ Comptes uniques pour boîtes mail critiques (Revenu, Drive)
- ✅ Tous les accès ex-collaborateurs identifiés et révoqués
- ✅ Process onboarding/offboarding documenté (scripting Google déjà en place avec Wassim)

## 🏛️ Pilier 2 — Gouvernance des SaaS

### Principe directeur
**Une licence = un usage actif et régulier**. Pas d'accès "au cas où".

### Composantes
- **Cartographie SaaS** maintenue à jour (qui paie quoi, qui utilise quoi, fréquence d'usage)
- **Audit annuel** : revue licences/coûts/doublons
- **Critère d'attribution** : si l'outil n'est pas utilisé au quotidien, l'accès n'est pas justifié
- **SSO Google systématique** quand possible (réduit la prolifération de credentials)
- **Pas de prélèvements orphelins** : auditer les facturations vs usage réel

### État actuel (5 mai 2026)
- 🟠 Cartographie partielle : audit Slack fait par Mohamed depuis 2 semaines, en attente accès Cédric/Océane pour autres outils
- ❌ Audit annuel : jamais fait formellement
- ❌ Critère d'attribution : licences données sur demande sans justification
- ❌ Prélèvements orphelins : ScoreUp désactivé depuis 2024, prélèvements continus

### Cible 31 mai 2026
- ✅ Cartographie SaaS complète (post-déblocage Cédric/Océane par Boris)
- ✅ Identification 70-100K€/an d'économies (cible Alec)
- ✅ Suppression prélèvements orphelins
- ✅ Process SSO Google systématisé pour nouveaux outils

## 🏛️ Pilier 3 — Sécurité des données et leaks

### Principe directeur
**Surveiller en continu les leaks de credentials sur le domaine + changer systématiquement les mots de passe leakés.**

### Composantes
- **Outils de cybersécurité** pour surveillance domaine entrepreneurs.com (Mohamed l'a déjà en place)
- **Process de changement de mot de passe** dès qu'un leak est détecté
- **Password manager** obligatoire (Keeper, déjà en place)
- **Pas de mots de passe enregistrés dans navigateur** sur PC perso
- **Pas de PC perso pour usages pro critiques** (à terme)

### État actuel (5 mai 2026)
- ✅ Surveillance domaine : Mohamed a déjà l'outil
- ❌ Process changement post-leak : 12 leaks Apollo 2024 identifiés, mots de passe **probablement non changés**
- ✅ Keeper : mis en place par Mohamed à son arrivée
- ❌ Mots de passe navigateur : cas Boris démontre la faille (mot de passe enregistré sur ordi perso)
- ❌ PC perso : pratique courante chez Entrepreneurs

### Cible 31 mai 2026
- ✅ Tous les mots de passe leakés Apollo 2024 changés
- ✅ Process de changement post-leak documenté
- ✅ Inventaire des outils utilisés sur PC perso pour identifier les zones de risque

## 🏛️ Pilier 4 — Gouvernance des APIs

### Principe directeur
**Chaque API key est attribuée à une personne ou un projet identifié, et révoquée à la sortie ou à la fin du projet.**

### Composantes
- **Cartographie des APIs actives** (qui utilise quelle API, pour quoi, depuis quand)
- **Rotation automatique** des clés sensibles (annuelle minimum)
- **Audit des APIs ex-collaborateurs** : quelles clés ont-ils créées ? Sont-elles révoquées ?
- **Détection d'usage anormal** sur les facturations API (ChatGPT, Claude, autres)
- **Politique de partage des clés API** : interdiction de les partager dans des LLM publics ou des channels Slack

### État actuel (5 mai 2026)
- ❌ Cartographie : inexistante
- ❌ Rotation : pas de process
- 🟠 Audit ex-collaborateurs : demandé par Mohamed à Wassim, en cours
- ❌ Détection usage anormal : aucun mécanisme
- ❌ Politique partage : pas formalisée

### Cible 31 mai 2026
- ✅ Cartographie APIs complète (Wassim + Mohamed)
- ✅ Audit ex-collaborateurs livré
- ✅ Politique partage API documentée

## 🏛️ Pilier 5 — Formation et culture sécurité

### Principe directeur
**La sécurité est l'affaire de tous, pas seulement de l'IT.** Une boîte de 80 personnes 100% digitalisée a besoin d'une culture sécurité minimale chez chaque collaborateur.

### Composantes
- **Onboarding sécurité** intégré au parcours d'arrivée (sensibilisation phishing, gestion mots de passe, MFA)
- **Campagne de phishing interne** annuelle pour mesurer la maturité (proposition Mohamed à Fabrice — refusée/ignorée — Boris valide)
- **Masterclass sécurité** annuelle sur les enjeux IA + cybersec
- **Rappels dans le meeting mensuel** quand un sujet d'actualité émerge
- **Documentation de la politique IT** accessible à tous

### État actuel (5 mai 2026)
- ❌ Onboarding sécurité : non structuré
- ❌ Campagne phishing : proposée par Mohamed, ignorée
- ❌ Masterclass : jamais fait
- 🟠 Rappels : Mohamed fait de la prévention ad hoc quand les gens viennent le voir avec des mails bizarres
- ❌ Documentation politique IT : inexistante

### Cible 31 mai 2026
- 🟡 Première campagne phishing interne lancée (résultats utilisés pour structurer formation)
- ✅ Politique IT documentée V1 (intégrée à l'onboarding RH)

## 🚨 Pattern de gouvernance défaillante observé

Au-delà des 5 piliers, le **vrai problème structurel** identifié par Mohamed est de **gouvernance** :

> Verbatim Mohamed 12:51 : *"Pour que ça marche, il faut que le socle, tu vois, la direction, elle va dans la même direction. Parce que si on a des failles, ça lui dit A, l'autre il dit B, l'autre il dit C, l'audit ça va jamais marcher."*

→ **Même diagnostic qu'Alec** dans son Slack tripartite du 1er mai sur la verticale Data/IA/Tech/Ops : décisions distribuées qui ne convergent pas.

→ La sécurité IT est un **cas d'application directe** du problème HO29 (cycle vicieux d'exécution) + HO31 (trou de management top).

## 🔗 Articulation avec la verticale Data/IA/Tech/Ops

Ce cadre IT/SaaS/Cybersec **alimente directement** la verticale Data/IA/Tech/Ops mandatée par Alec :

| Phase verticale (Fabrice) | Apport IT/Cybersec |
|---|---|
| **Phase 1 — Consolidation data** | Sécurisation des sources data (BigQuery, HubSpot) + accès admin |
| **Phase 2 — Dashboarding statique** | Comptes uniques pour les utilisateurs des dashboards + logs d'accès |
| **Phase 3 — Couche dynamique IA** | Gestion APIs (audit Wassim) + politique partage clés LLM + MFA sur outils IA |

→ Le sujet IT n'est pas "à côté" de la verticale, il est **transverse**.

## 🎯 Roadmap structuration (mai 2026 → 1er août 2026)

### Phase 1 — Diagnostic + transmission (5-31 mai 2026)
- Récupérer toute la matière de Mohamed (audits + plan d'action + scripting onboarding/offboarding)
- Démarrer chantiers urgents : MFA + leaks Apollo + accès Boris révoqué + comptes uniques boîtes critiques
- Cadrage rôle owner permanent Boris post-31 mai

### Phase 2 — Stabilisation (juin 2026)
- Cartographie SaaS complète post-déblocage Cédric/Océane
- Audit APIs livré (Wassim)
- 1ère campagne phishing interne lancée
- Process onboarding/offboarding documenté

### Phase 3 — Optimisation (juillet 2026)
- Suppression prélèvements orphelins (cible 70-100K€/an d'économies)
- Politique IT V1 documentée + intégrée à l'onboarding RH
- Masterclass sécurité 1er semestre H2

### Cible 1er août 2026
- ✅ 5 piliers V1 opérationnels
- ✅ 6 vulnérabilités critiques résolues
- ✅ Cadre formalisé pour la verticale Data/IA/Tech/Ops

## 🔗 Notes liées

- [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] (source du diagnostic)
- [[IT-Audit-Mohamed]] (dossier de transmission)
- [[Mohamed]] (acteur central jusqu'au 31 mai)
- [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] (HO40 sécurité IT en mode catastrophe + HO29 cycle vicieux)
- [[Cadre - Dette de confiance]] (la sécurité IT est un cas applicatif de la dette de confiance Alec → IT)
- [[Prep - Call Ops IT Tech Data IA 5 mai]] (articulation avec verticale)
- [[Wassim]] (porte les sujets infra/IT transverses : onboarding scripting + audit APIs)
- [[Cédric De Saint Jean]] (à pinger pour SaaS marketing)
- [[Océane De Queiros]] (à pinger pour SaaS communication)
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] (KR2.2 = audit SaaS 70-100K€/an + mandat IT structurant)
