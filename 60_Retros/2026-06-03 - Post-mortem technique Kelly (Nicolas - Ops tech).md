---
type: retro
date: 2026-06-03
source: "Document écrit de Nicolas Farolfi — « Post Mortem - 3D Kelly, analyse Ops tech » (PDF, 14 p.)"
author: "[[Nicolas Farolfi]]"
audience: "Document interne Ops (reçu via Boris)"
participants: ["[[Nicolas Farolfi]]"]
related-launch: "[[_Index|Lancement Kelly]]"
complements: "[[2026-05-30 - Post-mortem Kelly & Aikho (call Alec)]]"
tags: [retro, post-mortem, kelly-launch, ops-tech, cybersec, twilio, make, api-quota, iclosed, onboarding, delivery, ownership, archi-2.0, entrepreneurs-com]
status: inbox
sensitivity: confidential
---

# Post-mortem technique 3D Kelly — analyse Ops tech (Nicolas Farolfi)

> **Nature du document.** Post-mortem *écrit* par [[Nicolas Farolfi]] (Ops automatisations, **sortie en cours contrôlée** — cf. fiche). À lire avec une double grille : (1) **knowledge transfer réel** — c'est exactement la doc qu'on cherchait à capturer dans son offboarding, et elle est dense ; (2) **document de positionnement** — rédigé par quelqu'un qui part, il oriente la cause racine vers « l'humain / le manque d'owner » plutôt que la dette technique, et se met en valeur sur la gestion de crise. Garder cette tension en tête mais ne rien jeter : le contenu opérationnel est exploitable tel quel.
>
> **Complémentaire** au [[2026-05-30 - Post-mortem Kelly & Aikho (call Alec)]] (vue stratégie sales / commissions / réorg). Ici = vue **infra & data**, donc directement dans le scope **Support Infra (Co-COO)**.

---

## 0 — Données de campagne

- Origine lead : **3D Challenge** — funnel « 3 Day - La Méthode BOSS mai 2026 (Kelly) ».
- **37 471 inscrits ClickFunnels** ; ~1 700 avant lancement marketing (fallback 5D Tapie).
- Scénario Make d'optin concerné : `eu2.make.com/.../scenarios/7974865`.
- Sources de vérité campagne : HubSpot (vue contacts 145681735) + segment CustomerIO (workspace 196656).

---

## 1 — Phase Marketing

### 1.a Cybersécurité — attaque SPAM sur le webhook (🔴 scope Boris)
- **Première attaque observée** : week-end du 1er mai. L'attaquant a trouvé l'**URL du webhook en direct** (sans passer par ClickFunnels) et a généré **+12 000 fausses inscriptions**.
- **Cause racine** : ClickFunnels 1.0 (outil des LP marketing) **ne gère pas les webhooks protégés par JWT**. Make le gère, mais le point d'entrée n'est pas protégé.
- **Conséquences** :
  - Surcharge → *quota exceeded* sur plusieurs APIs (cf. 1.b).
  - **Sur-facturation Twilio** sur SMS d'optin vers Afghanistan, Yémen, Timor, Liban. Facture avril ≈ **40 039 $** dont **~14 300 $ Afghanistan** à elle seule.
- **Correctifs court terme appliqués** : filtre Make sur emails jetables (mailinator/yopmail) ; nettoyage des spams CustomerIO ; durcissement Twilio Geographic Permissions ; **ticket Fraud Reimbursement Twilio** ouvert (contact support ljoyce@twilio.com, ticket 27177400).
- **Vision long terme (Nicolas)** : filtre par IP si ClickFunnels expose une plage fixe ; **changer la solution de LP** pour permettre l'auth JWT des webhooks ; revoir les Geographic Permissions Twilio par continent.

### 1.b Quota Exceeded APIs & Billing
- Le scénario d'optin appelle de nombreuses APIs. ~**60 % d'entre elles ont rencontré un blocage** pendant la phase marketing. Deux types de problèmes :
  - **Quota exceeded (429)** : Google Calendar, Airtable. Aggravé par le volume (5D Tapie + 3D Kelly, 40k+) + le spam.
  - **Billing** : 40k+ inscrits consomment en quelques jours les crédits négociés (Make, 0CodeKit, OpenAI). L'**auto-recharge coûte plus cher au coup par coup** que l'abonnement, et les CB ne sont pas fiables → beaucoup d'allers-retours Fabrice/Nicolas pour débloquer les comptes en pleine campagne.
- **Correctifs** : bases de config Airtable → **Make Data Stores** ; passage de **4 → 20 comptes Google Calendar** en fallback ; **suppression de 0CodeKit** (validation tel) pour réduire le bruit ; monitoring renforcé.
- Note infra : **OpenAI utilisé pour valider/corriger les emails mal formés** (`@gmail.col`, `@gmail.co`) — astucieux mais fragile/coûteux à ce volume.

### 1.c Make — incomplete executions (déjà tracké Archi 2.0)
- Sur une fenêtre marketing 3D/5D, **1 000 à 2 000 inscrits/jour** (plusieurs milliers sur un week-end). Quand un blocage 1.a/1.b survient, il faut **rejouer tous les inscrits**.
- Pour un blocage API/billing : rejeu auto, mais re-déclenche des quotas (1k-5k exécutions sur une petite fenêtre).
- Pour un blocage **logique** (ex. IDs closers mappés à la main dans un switch) : le rejeu reprend la **version d'origine** du scénario, pas la nouvelle → on exporte le delta ClickFunnels↔CustomerIO et on relance un webhook, ce qui crée des **problèmes d'idempotence** (double/triple inscription WebinarJam, invitations Google Calendar multiples).
- **Acquis depuis décembre** : plus aucune data mappée à la main (bases de config) ; monitoring quotidien du delta CF↔CustomerIO.
- **Cible** : projet **Archi 2.0** (gestion idempotence + incomplete executions à grande échelle).

---

## 2 — Phase Sales

### 2.a Fréquence d'envoi SMS Twilio (MPS)
- 2 SMS par soir de live (19h55 et 20h30), à envoyer à **tous les inscrits en < 15 min**.
- **MPS Twilio par défaut = 10**. Pour 40k participants → **~67 min** d'envoi (≈ 1h10) : hors fenêtre.
- Démarche en cours : faire passer le compte à **50 MPS** (échanges avec le support Twilio depuis le 5D Tapie). Fabrice a pris un **plan de support supérieur** juste avant Kelly. **Non confirmé** : « je relance encore en juin pour vérifier que le compte est bien à 50 MPS ».
- **Correctif tactique** : scénario Make de doublage d'envoi le 1er soir (`scenarios/8216915`) → sur-consommation.
- **Point critique** : difficile d'ajouter un numéro mobile FR sur Twilio (justif de domicile ARIES CONSULTING) → forte dépendance au numéro du **Sender ID Alec Henry** (`MGda14c83ac7a152e15d783ffce7eac491`).

### 2.b Prefill iClosed manquant → ~100 doublons HubSpot
- Les liens **iClosed ne prefillent pas** firstname / lastname / email → **~100 doublons en base HubSpot** (constaté avec Thomas B.).
- Effets de bord en cascade : tracking (candidature sans détail funnel, contact sans transaction) ; **onboarding** (transaction sans détail funnel → introuvable pour la passer en fermée/gagnée).
- **Pour le prochain 3D : prefill iClosed obligatoire.** ⚠️ Correctif à très fort ROI / faible effort.

---

## 3 — Phase Onboarding / Coaching / Facturation

### 3.a Le vrai angle mort : ownership Delivery (point central de Nicolas)
- Problème **humain plus que technique** : pas d'**Ops owner garant de la donnée HubSpot** pour le Delivery (onboarding plateforme, signature contrat, facturation).
- Ce rôle était tenu par **[[Wassim]]**, parti rejoindre l'équipe d'[[Anisse Rbibe]] quelques semaines avant Kelly. L'onboarding a été repris à 100 % côté plateforme, mais le **scope Ops/Data Delivery est resté orphelin**.
- L'email d'onboarding (géré par Wassim sur Make) a été repris **début juin par [[Quentin]]** sur la plateforme.
- Scénarios Make rattachés aux webhooks **OneFlow** (`[Revenue]`, `[Delivery]`, `[Finance & Admin]`) : **non scalables, non documentés**, intégrés uniquement à **OneFlow / HubSpot / Airtable** — **pas d'intégration Zoho/DocuSign**, pas modulaires. **Personne n'en est garant.**
- Sur Kelly : aucun incident sur le Delivery « classique » (OneFlow/HubSpot a tenu), mais **angle mort confirmé**.
- **Alerte Nicolas** : positionner un **Owner OPS DELIVERY avant le prochain 3D Rentabilité**, sinon on reproduit le schéma.

### 3.b Archi « pansement » montée en urgence pour l'onboarding Kelly
Chaîne mise en place dans l'urgence (recoupe directement [[Architecture - Funnel parallèle closers externes]] et [[Scenario A2 - iClosed vers Zoho]] / [[Scenario A4 - DocuSign Zoho]]) :
- **#0 — [Revenue] Bridge iClosed → HubSpot** (création Nicolas) : crée la transaction HubSpot en « Appel Réservé » depuis iClosed/Zoho. Souci = doublons liés au prefill (cf 2.b).
- **#1 — Zoho → Sheets, Ventes fermées** (**création Boris**, MAJ Nicolas) : capte les transactions fermées/gagnées Zoho (pré-requis : contrat signé + paiement effectué).
- **#2 — ZohoCRM callback fermé** (Nicolas) : reçoit le webhook de #1, retrouve la transaction de #0 (filtre détail funnel + email — **beaucoup de casse si doublon**), associe Produit↔Transaction (line item), met à jour la transaction selon conditions plateforme (`dealstage=Fermé gagné`, `contract_status=Signé`, `payment_status=Payé`, product_code/sku/format/dates non nuls…).
- **#3 — Scénarios « Debug » data Kelly** (debug line item, détail funnel vide, onboarding boss energy, update amount/deal product).
- **#4 — Channel Slack** `#zoho-won-monitoring-plateforme` (monitoring manuel des transactions à vérifier).

### 3.c Problèmes data qui bloquent l'onboarding (liste Nicolas)
- **#0** Pas de doc officielle de la data plateforme, pas d'expertise Ops documentée.
- **#1** Propriétés `product_code` / `sku` manquantes sur le DEAL (le line item sert à la facturation, pas à l'onboarding — il faut les propriétés Deal HubSpot).
- **#2/#4** Prefill iClosed manquant → détail funnel ou email d'inscription absent → transaction non reconnue.
- **#3** Changement d'email signataire Zoho ≠ email d'inscription HubSpot → transaction non reconnue.
- **#5** **SKU incohérents** entre Zoho / HubSpot Deal / Line Item / plateforme (`INCUBATEUR ≠ INCUB ≠ INCUBATOR ≠ INCUB-ENTRE-SOLO-x1 ≠ Incub - Solo`). Formatage ajouté dans le fix.
- **#6/#7** Dates de démarrage / de fin manquantes → à synchroniser avec OneFlow dans les autos.
- **#8** Erreurs sales Zoho : transactions repassant de fermé/gagné à « Engagé » (contrat non signé/non réglé), données entreprise manquantes.

---

## 4 — Recommandation centrale de Nicolas
> « La recommandation prioritaire n'est pas technique, elle est humaine. » Avant le prochain 3D Rentabilité, le Head of Ops doit faire valider collectivement, par phase (Marketing / Sales / Onboarding / Coaching / Facturation / Tracking) : le **scope**, l'**owner désigné**, les **interfaces** (qui passe le relais à qui, sur quelle donnée), et les **critères go/no-go** pour éviter qu'un problème amont ne cascade silencieusement.

Tableau de priorités de Nicolas (owners restés flous) :
- 🔴 **Positionner un Ops Owner Delivery / Facturation / Contrat / Coaching** → owner = **« ??? »** (le trou central).
- 🔴 Onboarding Ops Owner Delivery → Wassim / Nicolas (support Quentin, Sabrina, Jordan).
- 🔴 Documenter & fiabiliser les scénarios Make OneFlow/Zoho/HubSpot → « Ops Delivery désigné ».
- 🔴 **Prefill iClosed** (firstname/lastname/email) → « externalisé actuellement ? ».
- 🔴 Recruter un(e) assistant(e) Sales Delivery (FAQ contrats/produits/Zendesk/onboarding) — vu avec Aziz.
- 🟠 Confirmer 50 MPS Twilio + hotline support < 24h → Nicolas/Twilio.
- 🟠 Standardiser les SKUs produit (Zoho/HubSpot/Line Item/plateforme).
- 🟡 Archi 2.0 (idempotence & incomplete executions) → Yohan/Nicolas.
- 🟡 Protection webhook JWT / remplacement ClickFunnels 1.0 → Tech/Marketing.

---

## 5 — Pièges connus (consolidé, réutilisable hors Kelly)
1. **Point d'entrée webhook non authentifié** (ClickFunnels 1.0 sans JWT) = vecteur de spam/fraude direct, contournant la LP.
2. **Geographic Permissions Twilio ouvertes** = sur-facturation immédiate sur pays à coût SMS élevé en cas de spam.
3. **MPS Twilio à 10 par défaut** insuffisant pour une fenêtre de 15 min à 40k+ → exiger 50 MPS + plan support prioritaire **avant** le live, pas pendant.
4. **Auto-recharge SaaS** (Make/OpenAI/0CodeKit) plus chère que l'abonnement et CB non fiables → provisionner les crédits en amont d'un gros lancement.
5. **Rejeu d'incomplete executions Make = bombe à idempotence** (reprend l'ancienne version du scénario, double les effets de bord WebinarJam/Calendar).
6. **Prefill manquant sur lien de booking (iClosed)** = doublons CRM en cascade → casse tracking + onboarding. Toujours prefill email/nom/prénom.
7. **SKU non standardisés** entre outils = transaction non reconnue à l'onboarding. Une seule nomenclature SKU, partout.
8. **Email signataire ≠ email d'inscription** → clé de matching cassée. Matcher sur identifiant stable, pas sur l'email saisi par le closer.
9. **Scénario orphelin non documenté** (les Make OneFlow post-départ Wassim) = single point of failure invisible jusqu'à la casse.

---

## 6 — Lecture Boris / enjeux Support Infra
- **Le « ??? » du tableau de Nicolas tombe en partie dans mon scope.** Dans le triptyque, la couche **DataOps / intégrations / scénarios Make-Zoho-HubSpot** = Support Infra (moi). Mais **Facturation = finance = Fabrice**, et **Coaching/Delivery = Sabrina**. L'« Ops Owner Delivery » que Nicolas réclame **chevauche la frontière Boris/Fabrice/Sabrina** : il ne peut pas être une seule personne sans découper proprement scope data (moi) vs scope finance (Fabrice) vs scope delivery métier (Sabrina). C'est une **question d'org à trancher en comité**, pas une embauche unique.
- **Deux stacks commerciales parallèles co-existent** et divergent : le Delivery « classique » (OneFlow/HubSpot/Airtable, scénarios Nicolas non documentés) et le funnel Kelly que j'ai construit (Zoho/DocuSign/Sheets/Vercel). Nicolas note lui-même que ses scénarios **n'intègrent ni Zoho ni DocuSign**. Risque de **fragmentation durable** → à fusionner/rationaliser dans Archi 2.0, sinon on maintient deux dettes.
- **La cybersec (webhook JWT) est désormais explicitement mon mandat** (sécurité). Le tableau l'assigne à « Tech/Marketing » ; post-1er juillet c'est à moi de le porter, en lien Mohamed.
- **Dépendance départ Nicolas confirmée** : ce doc *est* une partie de la passation. Le matcher avec le transfert ciblé Nicolas → [[Thomas Baeumlin]] (orchestration campagne A→Z, conventions detail_funnel) déjà flaggé dans sa fiche. Les scénarios Make orphelins (#0, #2, #3) doivent être **cartographiés et ré-ownés avant retrait d'accès**.
- **Prefill iClosed** : c'est un réglage de quelques minutes sur le lien de booking, pas un chantier « externalisé ». À fermer immédiatement avant le 3D Rentabilité (calendrier Alec : **23-25 juin**).

---

## 7 — Décisions à instruire (vers Decision Records)
- [ ] **DR — Découpage de l'ownership Ops Delivery** (data / facturation / coaching) sur le modèle triptyque. À porter en comité avant le 23 juin.
- [ ] **DR — Rationalisation des deux stacks commerciales** (OneFlow classique vs funnel Kelly Zoho) dans Archi 2.0.
- [ ] **DR — Remplacement ClickFunnels 1.0 / protection webhook JWT** (sécurité + marketing).

## 8 — Actions

| Qui | Quoi | Quand |
|---|---|---|
| Boris | Fermer le **prefill iClosed** (firstname/lastname/email) sur tous les events | Avant 23 juin |
| Boris | Cartographier + ré-owner les scénarios Make orphelins (#0, #2, #3) avant retrait accès Nicolas | Fenêtre passation |
| Boris | Porter en comité le découpage Ops Owner Delivery (data/facture/coaching) | Avant 23 juin |
| Boris / Mohamed | Action plan webhook JWT + Geographic Permissions Twilio par continent | Archi 2.0 / sprint cybersec |
| Nicolas / Twilio | Confirmer le passage effectif à **50 MPS** + hotline < 24h | Juin (à vérifier) |
| Ops Delivery désigné | Standardiser les SKUs produit (Zoho/HubSpot Deal/Line Item/plateforme) | Avant 3D Rentabilité |
| Boris / Thomas | Transfert Nicolas → Thomas (orchestration campagne, detail_funnel frontend) | Avant notification départ |
| Yohan / Nicolas | Archi 2.0 : idempotence & incomplete executions à grande échelle | Moyen terme |

## 9 — Points de vigilance
- **Twilio 50 MPS = non confirmé** : à valider avant le live du 23 juin, sinon SMS hors fenêtre sur 40k+.
- **Provisioning crédits SaaS** (Make/OpenAI) à anticiper avant chaque gros lancement — pas d'auto-recharge en pleine campagne.
- **Numéro Sender ID = celui d'Alec** : dépendance personnelle critique sur un asset opérationnel. Sécuriser un numéro entité.
- **Scénarios Make orphelins** : ne pas couper l'accès Google de Nicolas tant que #0/#2/#3 ne sont pas ré-ownés et documentés.
- **Document de positionnement** : utile mais à recouper ; ne pas prendre « la cause est 100 % humaine » pour argent comptant — la dette technique (idempotence, empilement d'outils, webhook non authentifié) est bien réelle et reste dans mon scope.

## 10 — Liens
- Hub : [[_Index|Lancement Kelly]]
- Archi funnel : [[Architecture - Funnel parallèle closers externes]] · [[Scenario A2 - iClosed vers Zoho]] · [[Scenario A4 - DocuSign Zoho]]
- Post-mortem stratégique : [[2026-05-30 - Post-mortem Kelly & Aikho (call Alec)]]
- Personnes : [[Nicolas Farolfi]] · [[Wassim]] · [[Quentin]] · [[Thomas Baeumlin]] · [[Sabrina Dahel]] · [[Jordan Leroux]]
- Source : PDF « Post Mortem - 3D Kelly, analyse Ops tech » (14 p.) — reçu de Nicolas, juin 2026.
