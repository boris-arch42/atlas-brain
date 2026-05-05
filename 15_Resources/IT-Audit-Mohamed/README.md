---
type: dossier-readme
status: actif
priority: critique (transmission Mohamed → Boris avant 31 mai)
last-updated: 2026-05-05
sensitivity: confidential-max
tags: [it-audit, mohamed, transmission, cybersecurite, saas, transmission-knowledge]
---

# 📁 IT-Audit-Mohamed — dossier de transmission

> **Objectif** : centraliser **toute la matière IT/cybersécurité** que Mohamed va transmettre à Boris d'ici son départ le 31 mai 2026. Sans ce dossier, le savoir-faire de Mohamed disparaît avec lui le 31 mai et les vulnérabilités identifiées restent ouvertes.
>
> **Origine** : kick-off audit IT du 5 mai 2026 (cf. [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]]).

## 🎯 Contenu attendu (à recevoir de Mohamed)

| # | Document | Délai annoncé | Statut |
|---|---|---|---|
| 1 | **Audit SaaS partiel** (déjà sur Slack : qui utilise / nb jours / nb messages) | Aujourd'hui ou demain | ⏳ À recevoir |
| 2 | **Audit de sécurité fait à l'arrivée Boris** | Aujourd'hui ou demain | ⏳ À recevoir |
| 3 | **Plan d'action sécurité avec deadlines** | Quelques jours | ⏳ Demande Boris explicite |
| 4 | **Doc onboarding/offboarding scripting Google** | Aujourd'hui ou demain | ⏳ À recevoir |
| 5 | **Cartographie SaaS complète** (post-récupération accès Cédric/Océane) | 2-3 semaines | ⏳ En cours côté Mohamed |
| 6 | **Audit APIs** (côté Wassim) | À préciser | ⏳ Demandé par Mohamed à Wassim |

## 🔴 6 vulnérabilités critiques à traiter (priorité absolue)

Identifiées au replay du 5 mai 2026 — cf. [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] section "6 vulnérabilités critiques" pour le détail.

| # | Vulnérabilité | Risque | Owner | Délai cible |
|---|---|---|---|---|
| 1 | **Pas de 2FA** sur les comptes critiques | Compromission massive | Mohamed → Boris (post 31/5) | Avant 31 mai |
| 2 | **Boîtes mail critiques partagées** (Revenu, Drive, etc.) entre 4-5 personnes | Pas de traçabilité, risque insider | Mohamed → Boris | Avant 31 mai |
| 3 | **12 leaks mots de passe** non changés (Apollo 2024) | Accès directs possibles | Mohamed | Cette semaine |
| 4 | **Accès non révoqués ex-collaborateurs** (cas Boris démontré 18 mois après départ) | Vol de données / sabotage | Mohamed → Boris (process post 31/5) | Avant 31 mai |
| 5 | **APIs orphelines** d'ex-collaborateurs jamais désactivées | Vol de données silencieux + facturation invisible | Wassim + Mohamed | 2-3 semaines |
| 6 | **Prélèvements SaaS continus** sur outils désactivés depuis 2024 | Cash sortant inutile (~70-100K€/an) | Mohamed | 1 mois |

## 🚨 Cas concret de faille démontré (à mémoriser)

Boris accède encore à `alec@entrepreneurs.com` 18 mois après son départ initial d'Entrepreneurs.com :
- Mot de passe encore enregistré sur ordi perso Boris
- Aucune demande, aucune alerte, aucun blocage
- Accès Drive idem
- **Faille systémique** : applicable à tous les ex-collaborateurs

## 📋 Plan de transmission proposé (à valider avec Mohamed)

### Cadence
- **Point hebdo Boris↔Mohamed** sur les 4 semaines (5/5 → 31/5) — 30 min/semaine
- **Format** : revue avancement + livrables documentés à chaque point
- **Owner cadence** : Boris

### Jalons
| Date | Livrable |
|---|---|
| 5-11 mai (S1) | Réception docs 1-2-4 + plan d'action V1 + démarrage chantiers urgents (2FA + leaks Apollo + accès Boris) |
| 12-18 mai (S2) | Cartographie SaaS complétée (post-déblocage Cédric/Océane) + audit APIs lancé avec Wassim |
| 19-25 mai (S3) | Process onboarding/offboarding documenté + comptes uniques pour boîtes critiques |
| 26-31 mai (S4) | Bouclage + transition propre + dossier complet remis à Boris |

### Actions Boris cette semaine (5-9 mai)
1. **Demander à Mohamed** : audit SaaS partiel + audit sécurité Boris-arrivée + doc onboarding/offboarding
2. **Pinger Cédric et Océane** pour qu'ils donnent à Mohamed la liste exhaustive des SaaS qu'ils gèrent + accès admin
3. **Caler point hebdo Boris↔Mohamed** (jeudi 30 min, jusqu'au 31/5)
4. **Valider la campagne phishing interne** que Mohamed avait proposée à Fabrice
5. **Remonter à Alec en 1 message** la dimension sécurité critique du sujet IT (pas juste coût)

## 🔗 Notes liées

- [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] (replay source)
- [[Mohamed]] (fiche personne)
- [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] (HO40 sécurité IT en mode catastrophe)
- [[Wassim]] (contact pour audit APIs + onboarding/offboarding scripting)
- [[Cédric De Saint Jean]] (à pinger pour SaaS marketing)
- [[Océane De Queiros]] (à pinger pour SaaS communication)
- [[Prep - Call Ops IT Tech Data IA 5 mai]] (angle IT prêt à mobiliser)
