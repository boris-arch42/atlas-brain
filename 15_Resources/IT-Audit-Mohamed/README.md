---
type: dossier-readme
status: actif
priority: critique (transmission Mohamed → Boris avant 31 mai)
last-updated: 2026-05-10
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

## 🔴 MAJ 2026-05-10 — Action prioritaire activée : déblocage accès Mohamed

> **Origine** : réflexion carnet 2026-05-10 — *"Permettre à Mohamed d'obtenir tous les accès aux outils pour actionner le plan de sécurité"*.
>
> Cette action existait déjà comme item #2 ci-dessus (Pinger Cédric et Océane) mais n'était ni datée ni traquée. **Elle bascule en priorité absolue** car sans les accès, Mohamed bute sur l'audit SaaS complet et le plan de sécurité ne peut pas s'exécuter dans la fenêtre du mois de mai.

### Périmètre des accès à débloquer

| Pôle | Owner | Outils concernés | Statut accès Mohamed |
|---|---|---|---|
| Marketing | [[Cédric De Saint Jean]] | HubSpot admin, Data Studio, outils créa, outils acquisition (Apollo, autres) | ❌ À débloquer |
| Communication / BRO | [[Océane De Queiros]] | Outils com, médias, partenariats | ❌ À débloquer |
| Sales | [[Aziz Sfaihi]] | Aircall admin, HubSpot Sales admin | ❓ À vérifier |
| CS | [[Sabrina Dahel]] | Zendesk admin (déjà en cours via restructuration) | 🟡 Partiel |
| Plateforme | [[Quentin]] | BigQuery, infra, scripts | ❓ À vérifier |
| Data | Thomas Baumelin | Data Studio, BigQuery | ❓ À vérifier |
| IA / Auto | [[Anisse Rbibe]] / [[Wassim]] | n8n, OpenAI/Claude APIs, Supabase | 🟡 Partiel via Wassim |

### Action Boris (cette semaine — S2 mai)

1. **DM individuels** à Cédric + Océane pour validation des accès admin à donner à Mohamed (avec deadline explicite : J+3)
2. **Si pas de réponse en 48h** : escalade en COMEX hebdo (lundi) avec sponsor Alec
3. **Vérifier avec Aziz, Quentin, Thomas, Anisse** le statut des accès — étendre le déblocage si besoin
4. **Tracer dans le journal** : qui a donné quoi à Mohamed et à quelle date — alimente la cartographie SaaS finale

### Pourquoi le blocage actuel

Verbatim Mohamed 5 mai (replay) : audit Slack fait depuis 2 semaines, mais pour les outils **non-Slack**, il chasse les infos auprès de Cédric/Océane qui ne répondent pas (ou tardivement). Le pattern est cohérent avec le diagnostic HO29 (cycle vicieux d'exécution) : pas de cadre, pas de SLA, pas de priorisation venue d'un échelon transverse → l'IT externe attend.

→ Boris est l'échelon transverse manquant. Le déblocage = effet de levier majeur sur le chantier audit IT entier.

### Articulation avec le SOP en cours de construction

Une fois ce blocage levé une bonne fois, le pattern ne doit plus se reproduire. Le [[Tech - Process création-transmission accès]] (créé 10/5) institutionnalise la chose : **plus jamais d'audit IT freiné par des accès qui dorment chez les heads**.

## 🔗 Notes liées

- [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] (replay source)
- [[Mohamed]] (fiche personne)
- [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] (HO40 sécurité IT en mode catastrophe)
- [[Wassim]] (contact pour audit APIs + onboarding/offboarding scripting)
- [[Cédric De Saint Jean]] (à pinger pour SaaS marketing)
- [[Océane De Queiros]] (à pinger pour SaaS communication)
- [[Prep - Call Ops IT Tech Data IA 5 mai]] (angle IT prêt à mobiliser)
