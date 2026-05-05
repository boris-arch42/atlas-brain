---
type: framework
date-created: 2026-05-05
status: V1 — opérationnel
owner: Boris Arduy
context: mandat audit IT Mohamed (29/4) + sortie Mohamed 31/5 + matérialisation publique mandat IT Boris (call 5/5)
sensitivity: confidential
tags: [framework, cadre, inventaire-saas, audit-it, mohamed, methode-poles, registre-rgpd, cybersec]
related-resources: "[[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]], [[Ressource - Replay Ops IT Tech Data IA 5 mai 2026]], [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]], [[Mohamed]], [[Cadre - Process IT-SaaS-Cybersec]]"
---

# 🗂️ Cadre — Inventaire SaaS Entrepreneurs.com (Méthode pôles)

> **Pourquoi ce cadre existe** : Mohamed (IT/Cybersec) doit auditer tous les SaaS de la boîte avant le 4 juillet 2026. Plutôt qu'un audit centralisé qui dépend de la mémoire de Mohamed (et qui partira avec lui le 31 mai si non documenté), on construit un **inventaire distribué par pôle** que Boris consolide.
>
> **Asset transverse** : cette méthode produit aussi le socle du **registre RGPD** (que la boîte n'a pas, identifié comme angle aveugle Fabrice au bilatéral 4 mai), et devient le **process pérenne** d'audit annuel SaaS.

---

## ⚡ Synthèse en 30 secondes

- **Problème** : 100-200 SaaS probables, 70-100K€/an d'économies identifiables (cf. replay Mohamed 5/5), 6 vulnérabilités cybersec critiques. Mémoire des heads ≠ réalité (40% d'oubli).
- **Solution** : 4 sources convergentes (flux financiers + Google SSO + audit Mohamed existant + heads), inventaire distribué par pôle, consolidation Boris.
- **Règle d'or** : un SaaS = un seul (a) Payeur sur l'ensemble des sheets pôles. Neutralise le doublon à la source.
- **Délai cible** : 7 jours pour l'inventaire complet. Rentre dans la phase 1 du plan Mohamed (45 jours).
- **Output** : Master Sheet exploitable par Mohamed + cadre pérenne pour audit annuel + base registre RGPD.

---

## 🎯 Les 4 sources convergentes (méthode pyramidale)

L'erreur classique = demander aux gens leur liste de SaaS. C'est faux à 40%. La méthode efficace inverse l'ordre : on part de ce qui paye, pas de ce que les gens disent utiliser.

### Source #1 — Flux financiers sur 12 mois (90% du volume)

C'est la source qui ne ment jamais.

**Quoi sortir** :
- Relevés CB d'entreprise (toutes cartes : Alec, Fabrice, ops, marketing, etc.) sur 12 mois minimum
- Statements Stripe / virements sortants sur le même horizon
- Factures fournisseurs dans la compta (Pennylane / Qonto)

**Pourquoi 12 mois** : capture les abonnements annuels (souvent les plus chers et les plus oubliés), pas seulement les mensuels. Cas concret : ScoreUp prélève chaque mois alors que désactivé depuis 2024 (replay Mohamed 5/5).

**Comment l'obtenir** : export Excel des transactions sortantes catégorisées "Logiciels / Abonnements / SaaS / Services en ligne" sur 12 mois. ~30 min côté compta. Donne un squelette de 80-150 lignes minimum.

**Owner de la demande** : Boris → Sabrina ou Compta directe.

### Source #2 — Google Workspace third-party apps (couverture SSO)

Console admin Google Workspace → **Security > API controls > Domain-wide delegation** + **Third-party apps**. Liste tous les SaaS qui ont un "Sign in with Google" ou un accès OAuth. Couvre la majorité des SaaS modernes (Notion, Slack, Figma, Zapier, etc.).

**Owner de la demande** : Boris → Mohamed (admin actuel) ou via Wassim si Mohamed indisponible.

### Source #3 — Ce que Mohamed a déjà (couverture opérationnelle)

Ne pas refaire le travail qui existe. Récupérer **avant le 31 mai** :

| Document | Status |
|---|---|
| Audit Slack analyzed (qui utilise quoi / nb jours / messages) | ✅ Livré à Fabrice il y a 2 semaines (sur Slack) — à demander |
| Audit de sécurité fait à l'arrivée Boris | ✅ Existe — à transmettre |
| Doc onboarding/offboarding scripting Google | ✅ Existe — à transmettre |
| Contenu de Keeper (mots de passe enregistrés) | ✅ En place — extraction inventaire |

**Owner de la récupération** : Boris → Mohamed (point hebdo jeudi 17h désormais).

### Source #4 — Ping bref aux heads (couverture métier — en dernier)

**❌ Ne PAS envoyer** : "envoie-moi la liste de tes SaaS" (ils oublieront 40%).

**✅ Envoyer** : la liste consolidée des sources 1+2+3 **pré-remplie**, demande de :
1. **Compléter** ce qui manque (CB perso remboursée, comptes freemium devenus payants, essais gratuits oubliés, comptes ChatGPT/Claude perso utilisés pour le boulot)
2. **Confirmer** qui est l'owner métier de chaque outil
3. **Donner avis franc** : Conserver / Tuer / Arbitrer

10× plus rapide pour eux. On utilise leur cerveau pour la valeur ajoutée (catégorisation + ce qui échappe aux flux financiers), pas pour faire un travail de mémoire.

**Heads à pinger** : 7 personnes max → format Slack court avec deadline 48-72h.

---

## 🏗️ Architecture des Sheets

### Pourquoi distribué par pôle plutôt que centralisé

- **Responsabilise** les heads sur leur propre périmètre
- **Plus rapide** à collecter en parallèle qu'un audit centralisé séquentiel
- **Production de connaissance métier** que Mohamed n'a pas (criticité, owner réel, utilisateurs actifs)
- **Renouvellement annuel** trivial : chaque head met à jour sa sheet

### Le piège majeur : le dédoublonnage inter-pôles

Notion, Slack, Google Workspace, Zapier, ChatGPT, Claude, Loom, Calendly, Pennylane, etc. — utilisés par plusieurs pôles mais payés par un seul. Sans règle, on a Notion qui apparaît 5 fois et Mohamed ne sait pas où couper.

**La règle qui sauve** :

> **UN SEUL pôle peut déclarer 'Payeur' (statut a) pour un SaaS donné.**
>
> Les autres pôles qui l'utilisent déclarent :
> - **(b) Utilisateur seul** — si seul ce pôle l'utilise (ex : Apollo pour le marketing)
> - **(c) Utilisateur partagé** — si plusieurs pôles l'utilisent (ex : Notion, Slack, Loom)

À la consolidation, on filtre sur "(a) Payeur" → 1 ligne par SaaS. Et on agrège en colonne "Pôles utilisateurs additionnels" les pôles qui ont déclaré (b) ou (c).

### Structure recommandée

| Onglet | Owner | Rôle |
|---|---|---|
| 📖 **Instructions** | Boris | Mode d'emploi + règle d'or + FAQ |
| ✏️ **Template (à dupliquer)** | — | Modèle vide à dupliquer pour chaque pôle |
| 🎯 **Exemple - Marketing** | Boris | Pré-rempli pour montrer le format aux heads |
| 🔄 **Master Consolidée** | Boris | Vue Boris × Mohamed avec filtres/dashboard |
| 🏷️ **Référentiels** | Boris | Listes déroulantes (catégories, criticité, etc.) |
| Sheets pôles | Heads | 1 par pôle, dupliquées du template |

### Pôles à diffuser

| Pôle | Owner Sheet | Particularité |
|---|---|---|
| Marketing | Cédric | Volume élevé probable (Apollo, ScoreUp, Mailchimp, outils acquisition) |
| Sales | Aziz | HubSpot, Aircall, outils prospection |
| CSM / Customer Success | Sabrina | Outils onboarding, support clients |
| Communication | Océane | Outils SaaS communication, RP, Loom |
| Ops Auto / IA | Anisse | Stack IA (Marcus, Pepper, Cervo, Aiko, Naïma), Zapier, n8n, APIs (OpenAI, Anthropic, ElevenLabs, Twilio) |
| Tech / Plateforme | Quentin (transitoire) | Hébergement, monitoring, dev tools, repos — Quentin sort en 3 mois donc à capter avant |
| Data | Thomas | BigQuery, Looker, ETLs, sources data |
| Finance / Compta | Sabrina ou Compta | Pennylane, Qonto, Stripe, paie |
| Recouvrement | Jordan | Outils dunning, contentieux |
| **Transverse / Company-wide** | **Boris (puis Mohamed)** | Google Workspace, Slack, Notion, ChatGPT/Claude entreprise, Loom, Calendly, etc. |

**Note importante** :
- **Fabrice n'a PAS de sheet** — il est COO/superviseur, pas owner d'un pôle SaaS spécifique
- **Alec n'a PAS de sheet non plus** — ses outils perso pro tombent dans Transverse
- **Mohamed n'a PAS de sheet** — il est bénéficiaire de la consolidation, pas producteur (politiquement important : on lui livre la matière, il ne quémande pas)

### Pourquoi une sheet "Transverse / Company-wide"

Le découpage par pôle ne couvre PAS les SaaS company-wide qui n'ont pas d'owner métier (Google Workspace, Slack, Notion plan entreprise, Qonto, Pennylane, outils Alec). Ces outils tombent dans le no man's land si pas couverts → c'est exactement là que se cachent les leaks.

**Owner Transverse** : Boris pendant le build, transition vers Mohamed sur la phase forfait (post-4 juillet).

---

## 📋 Colonnes du template (verrouillées — identiques pour tous)

Pourquoi verrouiller : si chaque head fait à sa sauce, la consolidation devient un cauchemar.

| Colonne | Description | Listes déroulantes ? |
|---|---|---|
| Nom du SaaS | Nom commercial (pas raison sociale) | — |
| URL principale | Pour repérer les variantes | — |
| Catégorie | CRM/Marketing/Comm/Dev/Data-IA/Finance/RH/Productivité/Stockage/Sécurité/Automation/Autre | ✅ |
| Statut payeur | (a) Payeur / (b) Utilisateur seul / (c) Utilisateur partagé | ✅ |
| Plan / Tier | Free/Starter/Pro/Business/Enterprise + nb sièges | — |
| Coût mensuel HT (€) | Si annuel, divise par 12 | — |
| Coût annuel HT (€) | Auto-calculé via formule (×12) | Formule |
| Méthode de paiement | CB Alec/Fabrice / Stripe / Virement / PayPal / Note de frais | — |
| Email du compte admin | Pour identifier accès nominatif | — |
| Nb d'utilisateurs actifs | Personnes qui se connectent ≥ 1×/mois | — |
| Liste des utilisateurs | Prénoms/emails — pour offboarding | — |
| Connexion via Google SSO ? | Oui/Non/Inconnu | ✅ |
| Présent dans Keeper ? | Oui/Non/Inconnu | ✅ |
| Owner métier | Personne du pôle qui décide keep/kill | — |
| Date dernière utilisation | Format AAAA-MM, ou "Jamais" | — |
| Niveau criticité données | Haute (clients/finance/RH) / Moyenne / Basse / Inconnu | ✅ |
| Conserver / Tuer / Arbitrer | Avis franc du head | ✅ |
| Notes | Tout ce qui ne rentre pas ailleurs | — |

---

## 🚨 Pièges spécifiques à anticiper

1. **SaaS payés en USD ou via PayPal** — souvent étiquetés différemment dans la compta, à recroiser
2. **Comptes nominatifs sur cartes perso remboursés en notes de frais** — invisibles dans les CB d'entreprise, n'apparaissent QUE chez les heads
3. **Outils freemium devenus payants** — abonnement à 0€ pendant 11 mois et 1 paiement en mois 12 (renouvellement auto), ne pas filtrer trop tôt sur "montant > 0€"
4. **APIs vs UI** — un SaaS peut être facturé sur l'usage API (ex: OpenAI, Anthropic, Twilio, SendGrid). Catégorie à part dans la liste — Wassim a un audit en cours là-dessus selon le replay matin Mohamed 5/5
5. **Outils gratuits avec data sensible** (Google Drive perso, Dropbox perso, ChatGPT free, Trello free) — à inclure même sans paiement, parce que c'est le risque cybersec qui compte, pas le coût
6. **Variantes de nommage** — "Notion" vs "Notion Labs Inc." vs "Notion.so" — dédoublonner manuellement à la consolidation

---

## 🗓️ Process opérationnel (1 semaine)

### Jour 1 (mardi)
- ✅ Boris : créer le Google Sheets à partir du template (cf. section Output ci-dessous)
- 📤 Boris → Compta : demande export 12 mois CB + virements + Stripe (catégorie SaaS/Logiciels)
- 📤 Boris → Mohamed : récupération des 3 docs (audit Slack + audit sécurité + Keeper export)
- 📤 Boris : extraction Google Workspace third-party apps

### Jour 2-3 (mercredi-jeudi)
- ✅ Boris : remplit sources 1+2+3 dans une "draft master" — ~3-4h de boulot
- ✅ Boris : pré-remplit chaque sheet de pôle avec les SaaS détectés attribués au bon pôle (au feeling, basé sur le nom)
- → Liste "brute" de 100-200 lignes obtenue

### Jour 4 (vendredi)
- 📤 Boris → 9 heads + Anisse en Slack court avec lien Sheet en mode commentaire
- ⏰ Deadline : 48h pour compléter colonnes "Owner métier" + "Utilisé activement" + ajouter manquants + donner avis franc
- 🎯 Format du Slack : court, contexte = "audit Mohamed", lien direct vers leur onglet uniquement (pas vers tout le doc)

### Jour 6-7 (lundi-mardi suivant)
- ✅ Boris : consolide, dédoublonne, catégorise dans la Master Sheet
- ✅ Boris : livre la liste à Mohamed avec colonne "Niveau d'accès Mohamed actuel" qu'il complète au fil de l'eau
- 📊 Premier dashboard : nb SaaS / économies potentielles / criticité / vulnérabilités cybersec

→ **Total : 1 semaine pour avoir la liste complète et auditée**, ce qui rentre dans la phase 1 du plan Mohamed (45 jours).

---

## 📤 Format du Slack à envoyer aux heads (template)

```
Hey [Prénom],

Dans le cadre de l'audit IT/Cybersec de Mohamed avant son départ
le 31 mai, on construit un inventaire complet des SaaS de la boîte.

J'ai pré-rempli ton onglet à partir des flux financiers : tu trouveras
les SaaS que la compta a détectés sur les 12 derniers mois.

Ce que je te demande, c'est :
1. Vérifier que ces SaaS sont bien à toi (pôle [X])
   → Si pas toi qui payes, change le statut en (b) ou (c) (cf. règle dans 📖 Instructions)
2. Compléter les colonnes métier : utilisateurs actifs, criticité, ton avis franc
3. Ajouter en bas ce qui manque (CB perso remboursée, freemium devenu payant,
   essais gratuits oubliés, comptes ChatGPT/Claude perso utilisés pour le boulot)

⏱️  ~30-45 min selon le volume
📅  Deadline : [date à 48-72h]

Lien direct vers ton onglet : [URL]

L'onglet 📖 Instructions explique tout en détail. Pingue-moi si doute.
Merci !
```

---

## 🎯 Output attendu

### Pour Mohamed
- Master Sheet exploitable comme inventaire de référence
- Identification immédiate des SaaS sans Google SSO (risque sécu)
- Identification des SaaS hors Keeper (à intégrer)
- Identification des SaaS criticité Haute (priorité audit)
- Économies potentielles chiffrées (somme des "Tuer")

### Pour Boris (capital structurel)
- Visibilité complète sur les coûts SaaS — base pour l'objectif 52K → 30K€/mois
- Cartographie des dépendances inter-pôles (qui partage quoi)
- Base du rituel annuel d'audit SaaS
- Socle du registre RGPD à venir

### Pour Alec
- Synthèse en 1 dashboard : total SaaS / total mensuel / total annuel / économies identifiées
- Démontre le standard de transparence/reporting attendu (cf. HO41 — vrai problème Alec = visibilité)

---

## 🔁 Renouvellement annuel

Une fois l'inventaire V1 livré, le cadre devient un **process pérenne** :

- **Owner permanent** : Boris (ou successeur IT permanent)
- **Cadence** : revue trimestrielle légère (heads checkent leur sheet) + revue annuelle complète (re-cross avec compta)
- **Trigger événementiel** : tout nouveau SaaS doit être ajouté à la sheet pôle correspondante au moment de la souscription (process à intégrer dans l'onboarding outil)
- **Lien avec process IT-SaaS-Cybersec** : cf. [[Cadre - Process IT-SaaS-Cybersec]] pour le protocole carré (workflow demande d'accès, validation, attribution, revue)

---

## 🔗 Notes liées

- [[Mohamed]] (mandat audit IT — sortie 31 mai puis forfait 1 500€/mois)
- [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] (6 vulnérabilités identifiées + sources existantes Mohamed)
- [[Ressource - Replay Ops IT Tech Data IA 5 mai 2026]] (mandat IT Boris matérialisé publiquement)
- [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]] (origine du mandat)
- [[Cadre - Process IT-SaaS-Cybersec]] (à structurer post-livraison plan Mohamed — ce cadre devient un input)
- [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] (HO40 : sécurité IT en mode catastrophe + HO41 : visibilité = vrai sujet Alec)
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] (Objectif 3 — verticale Data/IA/Tech/Ops avec cible 52K → 30K€/mois)
- [[Hub - Mithril]] (sourcing du remplaçant IT post-Mohamed si besoin de profil dédié)
- [[Cédric De Saint Jean]] / [[Océane De Queiros]] / [[Sabrina Dahel]] / [[Anisse Rbibe]] / [[Aziz Sfaihi]] (heads à pinger pour leurs sheets pôles)

---

## 📂 Fichier template

**Localisation** : à importer dans Google Sheets (Drive Entrepreneurs.com → dossier IT-Audit-Mohamed)
**Fichier source** : `Inventaire_SaaS_Entrepreneurs_Template.xlsx`
**Onglets** : 📖 Instructions / ✏️ Template (à dupliquer) / 🎯 Exemple Marketing / 🔄 Master Consolidée / 🏷️ Référentiels
**Validations** : listes déroulantes pré-configurées sur Catégorie, Statut payeur, SSO, Keeper, Criticité, Décision
**Formules** : Coût annuel auto-calculé, Total mensuel/annuel par pôle (Payeurs uniquement), Dashboard master avec compteurs et économies potentielles
