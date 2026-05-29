---
type: ressource
sous-type: plan-action-externe
date: 2026-05
prestataire: "GDZ IT Services (go.gdz-it.ch) = société de [[Mohamed]]"
entite-emettrice: "ARIES CONSULTING FZCO"
destinataire: direction Entrepreneurs.com
owner-cote-ec: "[[Boris Arduy]] (supervision) + [[Mohamed]] (exécution)"
sponsor: "[[Alec Henry]]"
statut: à-déployer
sensitivity: confidential-max
tags: [cybersec, phishing, gdz, mohamed, remediation, mfa, riot, fraude-virement, fraude-president, vecteur-humain]
related-scope: "[[Scope - Sprint Cybersec 48-72h - mai 2026]]"
source: entrepreneurs-com
---

# Ressource — Plan d'action Cybersec / Phishing GDZ (mai 2026)

> 📄 **Source** : document PDF "Plan d'action Cybersécurité — Renforcement de la sécurité des collaborateurs", préparé par **GDZ IT Services** (société de [[Mohamed]], go.gdz-it.ch) pour Entrepreneurs.com.
>
> 📍 Le PDF original est à déposer manuellement dans `15_Resources/IT-Audit-Mohamed/` (hors périmètre d'écriture de Claude — autre filesystem).
>
> 🟢 **Décision Boris (28/5)** : GDZ = société de Mohamed → ce plan est **mandaté à GDZ comme extension du mandat cybersec existant de Mohamed**, pas un prestataire tiers. Cohérent avec le maintien de Mohamed (cf. [[Mohamed]]).

## ⚡ Le constat — campagne de simulation de phishing

Une simulation de phishing a été menée pour mesurer l'exposition réelle aux attaques par email.

| Métrique | Valeur |
|---|---|
| Collaborateurs testés | **173** |
| Identifiants compromis | **29** |
| Taux de compromission | **17 %** |

→ En quelques heures, 29 collaborateurs ont saisi leurs identifiants Google sur une fausse page de connexion.

### 🔴 Deux profils critiques compromis

1. **Responsable Administratif & Financier (RAF)** — accès paiements, virements, données bancaires → exposition directe à la **fraude au virement**.
2. **Assistante personnelle du fondateur** — accès correspondance + agenda direction → permet la **fraude au président** (usurpation d'identité de la direction).

## 🎯 Positionnement dans le dispositif cybersec global

Ce plan adresse le **vecteur HUMAIN** (phishing / ingénierie sociale). Il complète le sprint cybersec existant qui couvrait le vecteur **TECHNIQUE** :

| Vecteur | Couverture |
|---|---|
| Fichiers publics (~82K → ~67K) | Sprint cybersec (technique) |
| Redirections email → boîtes privées | Sprint cybersec (technique) |
| Slug iClose modifiable | Sprint cybersec (technique) |
| **Phishing / compromission identifiants (vecteur 4)** | **Ce plan GDZ (humain)** |

## 📋 Plan d'action — 3 temps + pilotage récurrent

### 1. Actions immédiates (sous 7 jours)
- **MFA obligatoire** sur tous les comptes Google Workspace ⚠️ *non négociable, rapide*
- Réinitialisation des mots de passe des 29 comptes compromis
- Communication interne dédramatisante, **sans sanction individuelle**
- Canal de signalement simple pour les emails suspects

### 2. Remédiation des 29 collaborateurs concernés (sous 2 semaines)
- Session de formation ciblée
- Décryptage du scénario d'attaque (indices manqués)
- 3 réflexes clés : vérifier l'expéditeur, survoler les liens, ne jamais saisir ses identifiants hors page officielle
- Guide de bonnes pratiques permanent

### 3. Protections techniques transverses (sous 1 mois)
- Renforcement anti-usurpation messagerie (**SPF, DKIM, DMARC**)
- Bannière d'avertissement automatique sur emails externes
- Politique mots de passe renforcée + gestionnaire de mots de passe

### Accompagnement spécifique profils critiques
- **RAF** : double validation paiements au-delà d'un seuil + vérification téléphonique systématique de tout changement de coordonnées bancaires fournisseur
- **Assistante fondateur** : procédure de vérification des demandes urgentes "venant du fondateur" + **clé de sécurité matérielle**

### 4. Pilotage & suivi récurrent (GDZ / Mohamed)
- Déploiement + paramétrage plateforme
- Campagnes de simulation variées toute l'année
- Analyse mensuelle + reporting direction
- **Test futur de la direction et du fondateur** (cibles privilégiées des attaques réelles)

## 🟠 Arbitrage ouvert — plateforme Riot (tryriot.com)

GDZ recommande une **plateforme de sensibilisation continue payante** (type Riot) : simulations automatiques, modules interactifs, tableau de bord par collaborateur/département, score de risque mesurable, onboarding sécurité auto.

→ **À trancher** : déploiement Riot (coût récurrent) vs sensibilisation internalisée via Mohamed. À arbitrer en cohérence avec l'audit SaaS (KR2.2 cherche des économies, mais la cybersec est un poste de risque existentiel — cf. verbatim Boris "faille existentielle pour activité RGPD").

## 🎯 Prochaines étapes recommandées (par GDZ)

1. Déployer les **actions immédiates dès cette semaine** (MFA en tête)
2. Définir avec GDZ le **périmètre + calendrier** de la plateforme de sensibilisation

## 🔗 Notes liées

- [[Scope - Sprint Cybersec 48-72h - mai 2026]] — vecteur technique (ce plan = vecteur humain)
- [[Mohamed]] — GDZ = sa société, exécution
- [[Alec Henry]] — sponsor
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] — KR3.3 (gouvernance cybersec) + KR2.2 (arbitrage coût Riot)
- [[Cadre - Process IT-SaaS-Cybersec]] — pilier cybersec long terme
