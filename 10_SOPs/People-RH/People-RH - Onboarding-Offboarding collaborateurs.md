---
type: sop
domain: People-RH
owner: "[[Boris Arduy]]"
co-owner: "[[Fabrice Jaeger]]"
status: draft
last-reviewed: 2026-05-10
frequency: par-mouvement-rh
related-decisions:
  - "[[2026-04-30 - Operating Partner chez Entrepreneurs.com]]"
related-frameworks:
  - "[[Cadre - Process IT-SaaS-Cybersec]]"
related-sops:
  - "[[Tech - Process création-transmission accès]]"
  - "[[People-RH - Process recrutement Aikho v1]]"
tags: [onboarding, offboarding, cycle-de-vie, rh, accès, contrats, gouvernance, pilier1-cybersec]
source: entrepreneurs-com
sensitivity: internal
---

# SOP — Onboarding-Offboarding collaborateurs

## Pourquoi ce process existe

Aujourd'hui chez Entrepreneurs.com (cf. [[Cadre - Process IT-SaaS-Cybersec]] pilier 1) :
- Les arrivées se font sans formulaire structuré, accès donnés ad hoc par les heads
- 4-5 personnes partagent les boîtes mail critiques (Revenu, Drive)
- Aucune visibilité IT sur les accès donnés
- Les départs ne déclenchent pas de révocation systématique — cas démontré par Boris : accès `alec@entrepreneurs.com` actif **18 mois** après départ
- Les contrats prestataires ne sont pas centralisés ni revus périodiquement
- Mohamed (IT) demande à chaque fois les infos après-coup, en mode rattrapage

Ce SOP **ferme la boucle** côté RH : à chaque arrivée et chaque départ, un parcours déterministe se déclenche, l'IT (Mohamed jusqu'au 31/5, Boris ensuite) est dans la boucle dès le J-7, et les accès suivent le cycle de vie du collaborateur — pas l'inverse.

Le pendant technique (création/révocation effective des accès, MFA, comptes uniques, logging) est porté par [[Tech - Process création-transmission accès]]. Les deux SOPs **doivent être lus ensemble**.

## Quand le déclencher

- **Onboarding** : dès qu'une offre est signée (J-7 minimum avant l'arrivée). Pas d'accès donné sans étape 1 de ce SOP validée.
- **Offboarding** : dès qu'un départ est connu (démission, fin de période d'essai, fin de mission prestataire, rupture). Au plus tard J-7 du dernier jour effectif. **Cas spécial sortie immédiate** : déclenchement à H+0, voir section dédiée.

## Qui est impliqué

- **Owner global du process** : [[Boris Arduy]]
- **Co-owner sur volet décharge management** : [[Fabrice Jaeger]] (transition vers GM Dubai, dernier mot tant que la transition n'est pas finalisée)
- **Driver d'un mouvement donné** : le head qui recrute / qui voit partir
- **Owner accès IT** : [[Mohamed]] jusqu'au 31/5/2026, [[Boris Arduy]] ensuite (cf. mandat permanent vocal Alec 29/4)
- **Support exécution scripting Google** : [[Wassim]] (scripts onboarding/offboarding déjà en place via n8n)
- **Validation contractuelle** : Fabrice (transitoire) → Jordan (cible post-stabilisation pôle Finance/RH)

## Étapes — Onboarding

### 1. Préparation arrivée — J-7
- **Owner** : Head qui recrute
- **Action** : remplir le **kit d'onboarding** (à industrialiser dès Q1 — cf. mandat sortant Alexis sur l'onboarding RH) :
  - Identité complète (nom, prénom, email perso, téléphone, adresse postale, date de naissance, IBAN)
  - Type de contrat (CDI / CDD / freelance / portage / consultant offshore)
  - Date de début + période d'essai éventuelle
  - Manager direct (un seul nom) + RACI 30 jours
  - Liste outils nécessaires (par fonction — voir matrices `Tech - Process création-transmission accès`)
  - Équipement à fournir (laptop, écran, casque) ou déclaration "PC perso" (à éviter, voir pilier 3 du Cadre IT-SaaS-Cybersec)
- **Output** : kit complété → IT (Mohamed/Boris) + RH + Manager + Boris en CC

### 2. Création accès + contrat — J-3
- **Owner accès** : IT (Mohamed → Boris)
- **Owner contrat** : Fabrice (transitoire) → Jordan (cible)
- **Action accès** : exécution scripting Google (compte unique, pas de partage de credentials), MFA activé d'office, attribution outils selon liste fonction, ajout password manager Keeper. Détail dans [[Tech - Process création-transmission accès]].
- **Action contrat** : envoi contrat + annexes (NDA, charte IT, RGPD, charte de fonctionnement applicable au rôle), signature électronique avant J-1.
- **Output** : kit accès prêt à l'emploi à J-1 + contrat signé archivé.

### 3. Premier jour — J0
- **Owner** : Manager direct
- **Action** : remise des accès + équipement + brief de bienvenue + planning de la première semaine + intégration au kit d'arrivée (chartes culture, Slack, agendas récurrents).
- **Brief sécurité minimal** (intégré au parcours) : phishing, MFA, partage credentials interdit, navigateur perso interdit pour usages pro critiques, signaler tout mail suspect à l'IT.
- **Output** : checklist J0 signée par le collaborateur.

### 4. Suivi 30/60/90 — J+30, J+60, J+90
- **Owner** : Manager direct, sponsorisé Boris
- **Action** : 1-to-1 cadré à chaque jalon. Confirmation période d'essai à J+60 (CDI) ou date contractuelle. Audit accès résiduels et inutilisés à J+90 (un compte non-utilisé = compte à clôturer ou licence à libérer, pilier 2).
- **Output** : note de suivi dans `40_People/{Prénom Nom}.md`.

## Étapes — Offboarding

### 1. Annonce départ — H+0 (au plus tard J-7 du dernier jour)
- **Owner** : Manager direct
- **Action** : signalement à Boris + IT + Fabrice (transitoire) + Jordan (cible). Calage entretien de sortie + plan de passation. Si **sortie immédiate** (rupture, démission instant), passer directement à étape 3 dans l'heure.
- **Output** : ticket offboarding ouvert dans le canal Slack dédié + entrée dans le journal de mouvements RH.

### 2. Plan de passation — J-5
- **Owner** : Manager direct + sortant
- **Action** : cartographie des dossiers/comptes/automatismes/scripts portés par le sortant + qui hérite de quoi + dump de connaissance (Loom, doc, rendez-vous de transmission). Inventaire des **APIs** créées par le sortant (cf. pilier 4 du Cadre) — celles à révoquer, celles à transférer.
- **Output** : doc de passation archivé. Pas d'angle mort sur les automatismes (cf. pattern Mohamed : *"les gens arrivent, font des trucs, ils partent, ils documentent rien"*).

### 3. Révocation accès — J0 du dernier jour, H+24 max
- **Owner** : IT (Mohamed → Boris)
- **Action** : exécution scripting Google offboarding (désactivation Google Workspace, suspension comptes outils, rotation credentials partagés s'il y en avait, révocation API keys, retrait des channels Slack, suppression Keeper). Détail dans [[Tech - Process création-transmission accès]].
- **Cas démontré à éviter** : Boris a accès `alec@entrepreneurs.com` 18 mois après son départ → **plus jamais**.
- **Output** : checklist révocation signée + horodatée. Reporting hebdo des offboardings effectués.

### 4. Clôture contractuelle + matérielle — J+7
- **Owner** : Fabrice (transitoire) → Jordan (cible)
- **Action** : récupération équipement, soldes de tout compte / facture finale prestataire, archivage du contrat dans la cartographie prestataires (cf. [[Scope - Cartographie contrats prestataires Entrepreneurs.com]]), vérification clauses post-départ (non-concurrence, NDA, propriété intellectuelle).
- **Output** : dossier sortant clos.

### 5. Audit post-mortem — J+30
- **Owner** : Boris
- **Action** : vérification qu'aucun accès résiduel n'a échappé au scripting (test : essayer de se connecter à Google Workspace ex-collaborateur, requêter API keys, vérifier qu'aucun script cron ne tourne encore sous son identité).
- **Output** : signature audit post-mortem dans le journal RH.

## Cas particuliers

### Prestataire externe / freelance / consultant offshore
- Mêmes étapes que CDI mais contrat = devis + bon de commande + lettre de mission. Vérifier référencement dans [[Scope - Cartographie contrats prestataires Entrepreneurs.com]].
- Accès limités au strict périmètre de la mission. Pas de boîte mail @entrepreneurs.com sauf justification (et alors compte unique, pas de partage).
- Date de fin **dans le contrat** = trigger automatique de l'offboarding (pas besoin d'attendre une décision humaine).

### Sortie immédiate / risque sécurité
- Activation simultanée des étapes 1 et 3 dans l'heure.
- Boris alerté immédiatement, peu importe le moment (mandat IT permanent post-31/5).
- Rotation systématique de tous les credentials partagés auxquels le sortant avait accès, même sans suspicion (hygiène standard).

### Promotion / changement de poste interne
- Mini-onboarding sur le nouveau scope (étapes 2 + 3 onboarding) **et** mini-offboarding du scope précédent (étape 3 offboarding sur les outils non plus nécessaires).
- Ne pas laisser empiler les accès — pilier 2 SaaS (une licence = un usage actif).

## SLA récapitulatif

| Mouvement | Étape | Owner | SLA |
|---|---|---|---|
| Onboarding | Préparation kit | Head | J-7 |
| Onboarding | Création accès + contrat | IT + Fabrice/Jordan | J-3 |
| Onboarding | Premier jour | Manager | J0 |
| Onboarding | Suivi 30/60/90 | Manager + Boris | J+30 / J+60 / J+90 |
| Offboarding | Annonce | Manager | H+0 (J-7 idéal) |
| Offboarding | Plan passation | Manager + sortant | J-5 |
| Offboarding | Révocation accès | IT | J0, H+24 max |
| Offboarding | Clôture contrat/matériel | Fabrice/Jordan | J+7 |
| Offboarding | Audit post-mortem | Boris | J+30 |

## Pièges connus

- **Le head considère la création d'accès comme "détail technique"** et n'envoie pas le kit d'onboarding à temps → le J0 est foiré. Règle d'or : **pas de kit, pas d'arrivée**. Le head doit être tenu responsable du kit.
- **Sortie sans révocation accès dans la journée** → cas Boris (18 mois). Tolérance zéro — H+24 max.
- **Comptes partagés "parce que c'est pratique"** → reproduit la dette technique pilier 1. Compte unique systématique, sans exception. Si un usage justifie un compte partagé, il y a un problème de design en amont.
- **Prestataires sans date de fin contractuelle claire** → l'offboarding ne se déclenche jamais et la facturation continue. Le contrat doit toujours porter une date de fin (renouvelable explicitement, jamais tacitement).
- **Audit post-mortem sauté** → on découvre 6 mois plus tard que la révocation était partielle. Le J+30 n'est pas optionnel, c'est lui qui ferme la boucle.
- **PC perso** : demande explicite quand l'arrivée se fait sans équipement fourni. Tracer dans le kit, mettre des garde-fous (pas de mot de passe enregistré navigateur, MFA renforcée, audit usage).
- **Onboarding "à la volée"** quand un head recrute en urgence → pas d'urgence ne justifie le bypass. Si l'urgence est telle, le head escalade à Boris pour arbitrage formel.

## Articulation avec les autres SOPs et frameworks

- [[Tech - Process création-transmission accès]] → volet IT du même cycle de vie (étapes 2 onboarding + 3 offboarding sont exécutées via ce SOP)
- [[People-RH - Process recrutement Aikho v1]] → en amont de l'onboarding (étape 5 du process Aikho = décision d'embauche, qui déclenche l'étape 1 de ce SOP)
- [[Cadre - Process IT-SaaS-Cybersec]] → le pilier 1 (gouvernance des accès) est matérialisé opérationnellement par ce SOP + le SOP Tech
- [[Scope - Cartographie contrats prestataires Entrepreneurs.com]] → la clôture contractuelle (étape 4 offboarding) alimente cette cartographie

## Décisions stratégiques rattachées

- [[2026-04-30 - Operating Partner chez Entrepreneurs.com]] (mandat structurer la boîte)
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] (KR1.2 — top 10 process avec head owner)
- Mandat IT permanent Boris (vocal Alec 29/4)

## Historique

- 2026-05-10 — Création v1 (Boris). Statut **draft** — à valider avec Fabrice + Mohamed avant activation. Première itération à publier en S2-S3 mai. Test sur les prochains mouvements (Tessie onboarding rétroactif, remplaçant Nicolas, RH Dubai, sortie Mohamed 31/5).
- Prochaine révision : J+30 (10 juin) après premier cycle complet observé.
