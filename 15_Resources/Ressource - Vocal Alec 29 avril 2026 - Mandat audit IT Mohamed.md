---
type: ressource-vocal
source: vocal Slack/WhatsApp Alec → Boris
date-meeting: 2026-04-29
date-analyzed: 2026-04-29
duration: ~2 min (vocal)
status: analysé
participants: "Alec Henry (émetteur), Boris Arduy (destinataire)"
shared-by: "Alec direct (vocal asynchrone)"
sensitivity: confidential-max
tags: [vocal, alec, mandat-direct, audit-IT, mohamed, cybersec, mai, J-2, codename-haiti]
---

# 📨 Vocal Alec → Boris — 29 avril 2026 (~2 min)

> **Contexte** : Vocal d'Alec à Boris à J-2 de la prise de poste, formalisant directement le mandat audit IT + passation Mohamed sur tout le mois de mai. **Premier contact direct Alec → Boris sur ce sujet** (pas via Fabrice, pas via le call 1er mai).
>
> **Lecture politique** : Alec **acte le mandat en amont du 1er mai**. Donc le call de mardi n'a plus à valider — il a juste à confirmer/caler le calendrier. Alec consolide aussi sa **promotion implicite de Boris** comme owner cybersec/IT centralisé post-Mohamed.

## ⚡ Synthèse en 30 secondes

- 🎯 **Mandat acté** : audit IT (codename Alec = "Haïti") sur tout le mois de mai, Boris pilote en supervisant Mohamed
- 📅 **Calendrier précis** : du 1er au 31 mai. Fin de collaboration Mohamed = 31 mai. Pas S2-S4 comme estimé précédemment, c'est **tout le mois**
- 🔧 **Périmètre élargi** : SaaS (négociation/résiliation/mutualisation/internalisation) + cybersec pure (accès admin, MFA, comptes individuels) + rapatriement docs externes vers interne
- 💰 **Économie chiffrée** : ~2 000€/mois post-Mohamed (cohérent avec 24K€/an du replay 27/4)
- 🎖️ **Promotion implicite Boris** : *"tu centralises sous ton scope"* + *"j'ai 100% confiance en toi"* + *"t'es un banger"*
- ⚠️ **Position Alec sur Mohamed plus dure que Fabrice** : *"c'est un pirate"*, *"il est pas là dans l'intérêt de l'entreprise"*, *"j'ai pas 100% confiance"*. Divergence latente Alec/Fabrice à ne PAS relayer

## 📝 Contenu reconstitué du vocal

> *"Quand tu feras l'audit de sécurité Haïti [= IT] avec Mohamed, l'idée c'est que sur tout le mois de mai — je sais pas si t'as été informé mais je préfère te le dire — le but c'est que tu fasses l'audit de sécurité Haïti avec Mohamed sur tous les fichiers qui sont en externe, tous les abonnements qu'on paye dans le vide qu'on pourrait négocier ou qu'on devrait annuler, ou qu'on pourrait mutualiser, ou qu'on pourrait remplacer par une solution interne. Également revoir les accès admin, les docs, les machins à rapatrier en interne, s'assurer que Mohamed n'ait pas gardé des accès dérobés sur certains trucs ou autre, s'assurer que même nos outils soient carrés, mettre en place des MFA sur quasiment tous les outils critiques, s'assurer que des anciens collaborateurs n'y aient plus forcément accès, faire en sorte que les gens ne se partagent pas des accès et des comptes/Subs — à chaque fois attribuer individuellement. Le but c'est qu'on puisse le superviser, que toi tu puisses le superviser avec Mohamed Haïti durant tout le mois de mai, et qu'ensuite on arrête la collaboration. Comme ça boom on économise 2 000 balles par mois et que toi tu centralises sous ton scope. T'as les compétences, t'es un banger ? Et j'ai 100% confiance en toi, alors que Mohamed bah je sais pas si les compétences je pense que oui — c'est un pirate — mais il est pas là dans l'intérêt de l'entreprise, il a son intérêt, et j'ai pas 100% confiance en lui. C'est pas que j'ai pas confiance en lui, mais j'ai pas 100% confiance en lui. Donc je sais pas si j'avais demandé à Fabrice de te le partager, au cas où."*

## 🧩 Décodage du jargon Alec

- **"Haïti"** = **IT** (codename Alec — convention interne. À ajouter au glossaire jargon Alec dans sa fiche People)
- **"Mohamed Haïti"** = Mohamed dans sa fonction d'IT externe (pas d'info géographique sur Mohamed)
- **"Subs"** = abonnements / subscriptions (ex : Adobe, HubSpot, Zendesk, etc.)
- **"Pirate"** dans la bouche d'Alec à propos de Mohamed = compétent techniquement (positif sur les skills) mais **non aligné sur l'intérêt de l'entreprise** (négatif sur l'alignement). Pas une accusation de hacking au sens littéral.

## 🎯 6 éléments structurants

### 1. Calendrier précis : tout le mois de mai

Boris travaille **AVEC** Mohamed du 1er au 31 mai en supervision active, pas en audit post-départ. Fin de collaboration = 31 mai. Implication : **plan d'audit à étaler sur 4 semaines de co-travail**, pas en burst final.

→ **Reformulation du calendrier** dans `40_People/Mohamed.md` :
- S1 (1-5 mai) : prise de contact + cartographie initiale
- S2 (5-12 mai) : audit accès / inventaire SaaS / docs externes
- S3 (12-19 mai) : Marrakech (pause sur le terrain — supervision à distance)
- S4 (19-26 mai) : exécution rapatriements + rotation credentials
- S5 (26-31 mai) : finalisation + bascule complète sous scope Boris

### 2. Périmètre élargi (consolidation IT + audit SaaS)

Le mandat consolide en un seul chantier piloté par Boris ce qui était auparavant **deux mandats séparés** :
- **Audit SaaS** (replay Alec/Fabrice 27/4 — cible 70-100K€/an)
- **Passation cybersec Mohamed** (call Boris/Fabrice 28/4)

Le périmètre couvre maintenant :
1. **SaaS** : négociation / résiliation / mutualisation / remplacement par solution interne
2. **Fichiers externes** : rapatriement docs vers infra interne (cohérent avec NAS 1K€ déjà acté)
3. **Accès admin** : audit + révocation des comptes Mohamed après son départ
4. **MFA** : déploiement sur tous les outils critiques
5. **Anciens collaborateurs** : audit des accès résiduels (Tang, Mélissa, Olivia, Nolwenn, Alexis sortant, Axel sortant juin, etc.)
6. **Comptes individuels** : fin du partage d'accès / d'abonnements, attribution individuelle systématique

### 3. Position Alec sur Mohamed (divergence latente avec Fabrice)

| Aspect | Fabrice (28/4) | Alec (29/4) |
|---|---|---|
| Compétence technique | Implicitement OK | *"C'est un pirate"* (= très compétent) |
| Loyauté | *"Ça c'est vos trucs, j'interviens pas"* (Mohamed à Fabrice pendant Tang) — rassurant | *"Pas là dans l'intérêt de l'entreprise, il a son intérêt"* — réservé |
| Confiance | Implicitement OK | *"Pas 100% confiance"* (formulé 2x) |
| Recommandation | Audit standard suffisant | Audit serré, surveillance "accès dérobés" |

→ **Posture Boris** : exécuter l'audit au **niveau de paranoïa Alec** (plus serré que ce que Fabrice estimerait nécessaire) **sans relayer la lecture Alec à Fabrice ni à Mohamed**. Ne PAS amener cette divergence au call 1er mai.

→ **Lecture stratégique** : Alec a probablement reçu un signal récent (peut-être l'épisode NAS/Shade où Alec a balancé "vous êtes des couillons" à Mohamed, ou une autre interaction). Sa réserve n'est pas tang-historique, c'est récent. À ne pas creuser frontalement.

### 4. Promotion implicite Boris

Alec acte plusieurs choses simultanément :
- **Validation compétence** : *"T'as les compétences, t'es un banger"*
- **Confiance maximale** : *"J'ai 100% confiance en toi"*
- **Centralisation IT sous Boris** : *"Tu centralises sous ton scope"*

→ **Implication structurelle** : l'IT/cybersec devient une **zone permanente de Boris**, pas juste un mandat ponctuel de transition. Cohérent avec posture Co-COO + rôle "general manager de fait" (cf. HO31). À acter dans la charte V2 Boris/Fabrice (zone IT/cybersec = Boris owner explicite).

### 5. Premier mandat direct Alec → Boris

C'est le **premier contact direct** d'Alec à Boris sur un mandat opérationnel pré-prise de poste (en dehors du cadrage du 23/4 et de la règle du revirement du 23/4 soir). Alec court-circuite légèrement Fabrice (*"je sais pas si j'avais demandé à Fabrice de te le partager"*) — ce qui :
- Confirme que l'urgence est réelle (Alec ne veut pas attendre le call 1er mai)
- Peut créer une fragilité avec Fabrice si le mandat n'est pas re-cadré au call trio (Boris doit vérifier que Fabrice est aligné)

→ **Action Boris** : confirmer avec Fabrice que le mandat lui a été partagé. Si non, Boris peut lui en parler de manière neutre ("Alec m'a envoyé un vocal, je voulais valider que tu es aligné sur le calendrier") avant le call 1er mai.

### 6. Économie 2 000€/mois (24K€/an)

Cohérent à l'euro près avec ce qu'Alec avait annoncé à Fabrice au replay 27/4. Confirme que l'économie n'est pas négociable — Mohamed sort au 31 mai. **Pas de scénario "et si on le gardait à temps partiel"**.

## 🎯 Implications stratégiques consolidées

### Ce qui change vs ce qu'on savait

| Élément | Avant ce vocal | Après ce vocal |
|---|---|---|
| **Calendrier passation** | S2-S4 avant fin mai | **Tout le mois de mai en supervision active** |
| **Périmètre** | Cybersec pure (accès, MFA, backups) | **+ Audit SaaS + rapatriement docs externes + comptes individuels** |
| **Position Alec sur Mohamed** | Inconnue / supposée alignée Fabrice | **Réserve nette : "pas 100% confiance"** |
| **Owner cybersec/IT post-mai** | Implicite | **Boris explicite — *"tu centralises sous ton scope"*** |
| **Mandat formalisé via** | Fabrice au call 28/4 | **Direct Alec au vocal 29/4** |
| **Économie chiffrée** | 24K€/an estimé | **2 000€/mois confirmés (24K€/an)** |

### Ce qui change dans le call Alec 1er mai

Le sujet F1 (passation cybersec Mohamed) du Prep Call Alec **bascule de "à valider" à "déjà acté — accuser réception + caler calendrier précis"**. Boris peut amener au call :

1. **Confirmation accusé** : *"J'ai bien reçu ton vocal sur l'audit IT avec Mohamed sur mai. Je prends. Je commence le 5 mai (S1) avec une cartographie initiale."*
2. **Calendrier précis** : valider le découpage S1-S5 ci-dessus (en intégrant Marrakech 20-25 mai)
3. **Budget audit cyber externe** : si nécessaire (CASES type, 5-10K€) — Alec valide ou pas ?
4. **Modalités com** : Alec, Fabrice et Boris s'alignent sur un message à Mohamed pour cadrer la fin de collab (Alec parle direct, Fabrice annonce ?)

### Ce qui ne doit PAS être amené au call 1er mai

- **Ne PAS relayer la divergence Alec/Fabrice sur Mohamed**. Boris exécute au niveau Alec.
- **Ne PAS challenger le calendrier** (mois entier vs S2-S4) — c'est l'instruction.
- **Ne PAS proposer de garder Mohamed plus longtemps** — la fin au 31 mai n'est pas négociable.

## 🔗 Notes liées

- [[Mohamed]] (mise à jour cascade : calendrier mai entier, mandat élargi, position Alec)
- [[Alec Henry]] (mise à jour cascade : "Lecture Alec sur Mohamed" + glossaire jargon)
- [[Fabrice Jaeger]] (vérifier l'alignement avant call 1er mai — pas de divergence à acter)
- [[Prep - Call Alec 1er mai - Cartographie noeuds operationnels]] (sujet F1 bascule à "acté")
- [[Ressource - Replay Alec Fabrice 27 avril 2026]] (mandat audit SaaS initial — cohérence avec ce vocal)
- [[Ressource - Replay Boris Fabrice 28 avril 2026]] (mandat passation cybersec initial via Fabrice)
- [[Charte de fonctionnement Boris ↔ Fabrice — V1 (à envoyer)]] (V2 doit acter zone IT/cybersec = Boris owner permanent)
- [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] (HO15 — épisode NAS/Shade pourrait être à l'origine de la réserve récente d'Alec sur Mohamed)
