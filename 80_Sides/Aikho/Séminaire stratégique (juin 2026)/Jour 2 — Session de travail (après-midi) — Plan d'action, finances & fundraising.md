---
type: rapport-de-séance
domaine: SIDE
projet: "[[Partenariat Aikho]]"
date: 2026-06-25
seance: "Jour 2 — session de travail (après-midi, 12:07 → 14:11)"
participants:
  - "[[Boris Arduy]] (systèmes / LP / scraping)"
  - "[[Alec Henry]] (marketing / réseau / entrepreneurs.com)"
  - "[[Hugues Pringault]] (commercial — CEO Aikho)"
  - "Julien (tech / produit — CTO Aikho)"
  - "Mentionnés : Joe (run V1), Jonathan (infra/prod), Armand, André"
source: "Enregistrement Sembly — 25 juin 2026, 12:07 (2 fichiers, 35 p. + 2 p.) — boris@entrepreneurs.com"
statut: rapport-de-séance
sensitivity: confidential
tags: [aikho, seminaire, jour2, apres-midi, plan-action, finances, fundraising, gtm, landing-page, sales]
---

# Aikho — Jour 2 · **Session de travail (après-midi, 25 juin 2026)**

> **Nature** : déroulé opérationnel complet de l'après-midi — revue des décisions Jour 1, validation de la cartographie des rôles, **deep-dive landing page + machine de scraping**, méthodologie sales, produit V2, et surtout l'**ouverture du chantier finances / apport entrepreneurs.com / equity / levée de fonds** (premier vrai échange dessus).
> **Réserve transcription** : Sembly attribue mal les locuteurs et déforme plusieurs termes. Synthèse organisée **par thème**. Termes corrigés : *AECO/AEKO/ICO/Aiko = Aikho* · *Echo = V1 (« Echo »)* · *« clics »/Limova/Imova = Le Déclic* · *« Whoop » = Whop (paiement)* · *« 400 000 $/mois » ≈ 4 000 $/mois (à confirmer)* · *« 6, 26 juillet » = premiers calls ~6 juil (à confirmer)*.

---

## 1. Rappel des décisions Jour 1 (re-validées en ouverture)
Go big or go home · promesse figée « AI hiring assessment » (on évalue & on s'adapte au process, **on vend un système, jamais des agents**) · **V2 = socle** au plus vite, V1 (« Echo ») maintenue par un collaborateur et migration V1→V2 d'ici **sept-oct** · **B2B-first**, kill de la proposition de valeur sourcing (feature gardée, non marketée) · GTM = **GCC/grands comptes (EN + AR)** + **TPE-PME francophone** (canal entrepreneurs.com) · **pricing annuel** up-front (~200 candidats managés/mois max), **1 400 → 6 000** ou **12 000 → 15 000 $/an** · chaque client passe par un **call Sales/OBM**, closing externalisé (Alchimie) · **test payant 7 %** · closing visio sauf profils > 15 000 $/an (Hugues se déplace).

---

## 2. Cartographie des rôles (confirmée)
| Owner | Périmètre |
|---|---|
| **Hugues** | Commercial : workflow lead, leads rappelés, équipes formées, data/dashboards sales à jour ; collabore avec Alchimie |
| **Julien** | Tech/produit : développement V2 + appui d'un tiers sur la V1 |
| **Boris** | Systèmes : landing page, site web, scraping, lead gen, sollicitations au jour le jour |
| **Alec** | Marketing, copywriting, direct-response global, mise en relation réseau (Dubaï, France, entrepreneurs.com) |

---

## 3. 💰 Finances, apport entrepreneurs.com & equity *(nouveau chantier majeur)*
**Trésorerie Aikho serrée** — c'est le point bloquant pour cadrer l'exécution (les ressources dépendent du cash).
- **Coûts fixes ≈ 4 000 $/mois** *(transcription ambiguë « 400 000 » — à confirmer)* : infra, API, abonnements, ~5-7 providers LLM. **Marge ≈ 70-80 %** une fois les coûts LLM déduits ; optimisation permanente (ex. −60 % sur un poste, bascule dès qu'un modèle meilleur/moins cher sort).
- **Cash restant ≈ 20-30 k$** + ~20 k$ de crédits AWS à récupérer (déjà ~30 k$ de crédits cramés). → si on ne fait pas rentrer de clients, le runway se réduit vite.
- **Apport entrepreneurs.com** : surtout **en nature ≈ 300 000 €** (épisode Le Déclic + base mail + clients + séminaire). Un **bundle partenariat** de ce type se vend ~**120-150 k€**. Le réseau / les équipes mobilisées ne seront pas co-facturés (accord).
- **Ressources à payer par Aikho** (pas par Boris/Alec) : équipe Inde (SEO/contenu), licence Apollo (~70 $/mois), tools, **OBM** (~500-800 $/mois full-time à terme), 2-3 SDR Maroc.
- **Posture Boris/Alec** : pas de cash injecté obligatoire, apport en ressources = valeur équivalente ; rémunération via **equity / stock-options**. Les fondateurs Aikho comptent se prendre un salaire sur la boîte.

### ⚖️ Clarification juridique à anticiper (avant levée)
- entrepreneurs.com **en tant qu'entité légale** mobilise des ressources → il faut **documenter proprement** qui apporte quoi (Alec apporte X, entrepreneurs.com apporte Y, et **ce qu'entrepreneurs.com en retire**). Donner des charges/parts « gratos » est problématique, surtout au moment de la levée.
- **Situation Boris** : 100 % entrepreneurs mais **fiscalement perso en France** → structurer prudemment (cf. [[Atlas Ventures]]) ; aligner aussi avec **Armand** et sa contribution.

### 🚀 Levée de fonds
- **Cible initiale 2-3 M$** (avant de rencontrer Boris) → susceptible d'évoluer selon la traction. Speaker réseau évoque pouvoir aller chercher **« jusqu'à 20 M »** sur des boîtes comparables.
- **Fenêtre de marché ouverte MAINTENANT** (valos IA très hautes, parfois 1 Md$ sans produit) mais **va se refermer** (5 jours / 3 semaines / mois / an) → **locker les fonds le plus vite possible** ; la **traction** deviendra le critère n°1.
- Pistes : un investisseur prometteur via le réseau (figure connue de la tech FR, a investi dans des ATS, « a vu le produit, est chaud ») ; **David Gurley** (ex-bras droit de Bill Gates, 2 licornes, board Rothschild, mentor levées IA) — intro possible. **SPV** envisagé pour faire entrer plusieurs personnes d'un coup ; éviter l'argent famille (pression inutile).
- **Le Déclic** = levier double : selon les résultats de sept., tourner l'épisode soit « vente Echo » seule, soit « vente + on lève auprès d'institutionnels + SPV avec X slots / lien Apply ». Potentiel **0,5 M$** facile via la communauté.

---

## 4. 🛬 Landing page Aikho (construite sur Claude par Boris)
- **Copy orienté bénéfices / direct-response**, **pas le mot « agents »** écrit nulle part. Promesse immédiate : *« tu rencontres les meilleurs candidats, real-world interview dans leur langue, scoring équitable, shortlist en 48 h »* + CTA *book a demo* / vidéo 90 s.
- **Ciblée GCC** (Hospitality / Retail / F&B — transversales d'acquisition Apollo), version dédiée par marché/ICP. Design **orange & noir**, plus tech/friendly que le design system « Médecine Pro » dont il s'inspire ; sliders auto, FAQ en copywriting, social proof.
- **Placeholders à remplacer par du réel** : logos (Jumeirah, Paris Society, Unlock — en gris, anticipés), testimonials, chiffres (ex. « 87 % fit ») → mettre **vrais logos + vrais témoignages + vrais chiffres**.
- **Vidéo motion design** (A→Z, EN/AR, ~1 semaine de prod via une équipe dédiée) branchée en home.
- **iClosed embed** (widget bas-droite + page dédiée) : capteur de données — **récupère nom/prénom/email même si la personne ne book pas** ; SDR relance par mail. Démos de 30 min connectées à l'agenda des sales.
- **Transfert** : la LP (sur Claude) doit être **mise en ligne sur les systèmes Aikho** → passer par **Jonathan** (contrôle infra/prod ; Boris ne touche pas la prod). Le site actuel **devient la LP** (pas de double) ; pas de lien sign-in/sign-up exposé (le site fait partie de l'app via cookie Echo → friction à éviter). ~10 clients actuels (→9) prévenus par **WhatsApp** du nouveau process.

---

## 5. 🏴 Machine marketing « pirate » (deadline vendredi 3 juillet)
- **Apollo** : coût ≈ licence **70 $/mois**, le reste = scraping mail de base. Visibilité délivrabilité temps réel + **warm-up ~100 jours**.
- **Process** : la machine scrape en continu (10→500+ contacts), injecte dans des **séquences mail**, **A/B test par batchs de 100-200**, on vire la version perdante, on itère (subjects/CTA différents), on garde le **winner** pour scaler le flux. **Cartographie du décideur** : séquence Owner → si KO, **HR** → autres portes (« par la fenêtre »).
- **Cibler d'abord les petites boîtes**, monter progressivement pour ne pas se cramer. Volume potentiel énorme rien que sur Dubaï. Base-mails directs des boîtes (FR + EN). Possibilité de scraper aussi les **téléphones** (API ouvertes, peu cher) — à A/B tester selon flux/qualité/taux de close.
- **Timeline** : tout setup (séquences + Agenda + Alchimie) **effectif le ven. 3 juil**, **premiers calls ~6 juil**, **premier closing encaissé ~7 juil**. 2-3 **SDR marocains** bombardent les calls (boostés IA, supervisés) ; **Hugues** se concentre sur grands comptes / GCC.
- **Brancher la base candidats existante** (~11 000) : campagne mailing 2-3 mails → sign-in sur Echo (cohérence : on acquiert des **entreprises**, pas des candidats — donc secondaire).

---

## 6. 🎯 Méthodologie sales
- **100 % des calls enregistrés** (AirCall ou équivalent) = mine d'or data → **cerveau centralisé (Obsidian)** des objections/contres ; le script évolue ~tous les 10 jours (test & learn).
- **« Des acteurs, pas des vendeurs »** : script qui défile sous la caméra + **IA qui mentore/coache en direct** ; référence d'un proche passé de **20 % → 35 % de close** sur panier ~18 k€. On **vend la transformation (point A → Z)**, pas la feature ; les profils ne sont pas techniques.
- **Closing** : R1 direct, **carte au téléphone / CNA dans le call**, ils ne raccrochent pas sans payer. Pas d'obligation de **refund aux Émirats** (vs France) — mais churn annuel = surtout des demandes de **refund** → réactivité indispensable (un lead non rappelé J+1 perd ~50 % de sa valeur de close).
- **Réf. closing entrepreneurs.com** : ~30 000 calls de closing/an sur cet avatar → data + séquences réutilisables.

---

## 7. 🧑‍💼 OBM, onboarding & anti-churn
- Recruter un **OBM** (~500-800 $/mois) dès qu'il y a du cash : prend les RDV, **active les comptes**, **prépare la démo** (pré-remplir un template aux couleurs du prospect avant le call → effet « waouh »).
- **Cas particuliers** (limites de candidats, négociation SDR) : **pas d'accès back-end** aux SDR (tout ou rien) → **système de tickets** (Slack/WhatsApp) vers une personne qui gère.
- **Onboarding V1 (« Echo ») peu intuitif** : prévoir un kickstart guidé (créer le 1er mandat avec le client), voire **pomper les offres LinkedIn** du client pour préremplir. Chantier **simplification V1 avec Jonathan** (masquer la complexité sans tout casser).
- **Anti-churn** : mesurer l'activité, **rappel proactif** ; à scale, prévoir un process support/success (CSM).

---

## 8. 🛠️ Produit / V2 (précisions)
- **V1 maintenue** : Joe dessus ; **Julien forme Joe à partir du 10 juil** (process Claude). V1 **containerisée & scalable** (testée jusqu'à ~40 instances simultanées, pas de blocage volume → 1-2k clients OK).
- **V2 = socle** : **definition of done avant le 18 juil (idéal 15 juil)** — avant l'**absence de Julien (~3 sem US)** ; pendant l'absence : **Joe sur V1, Julien remote sur V2** (surface de risque = bugs beta-testeurs, faible).
- **UX V2** : bonne base ; jouer sur **templates/skins (simple/pro)** sans changer le back-end → tester ce qui plaît. **Exposition sélective de la complexité** (on choisit ce qu'on expose).
- **Tracking « Hire »** : pas de solution propre trouvée (les clients ont déjà un ATS) → passer plutôt par la **raison de clôture de pipeline** (recruté / plus de besoin) + limiter le nombre de pipelines ouverts (double bénéfice : data + relance).
- **Plugin Claude (MCP)** : page d'intégration → bouton → plugin dans Claude (auth gérée) ; sert surtout aux **comptes spécifiques** (activation single/multi-tenant). Julien **sceptique** sur un plugin MCP « code » — à instruire.
- **Plateforme agnostique / compliance** : construire une **matrice** (pays → contraintes → déploiement, data residency, AI privacy) exploitable pour entraîner l'IA.
- **Billing** : Stripe (ou in-app) ; refacturation/limites gérables en back-end.

---

## 9. 🔗 Affiliation / apport d'affaires
- **Automatisé** : « devenir partenaire » → **lien d'affilié (UTM)** → la personne référée book un call, paie via **Stripe** (lien tracké) → **commissions** remontent sur un **dashboard**. Landing dédiée par affilié + tracking propre.
- **Gamification** (à terme) : classement, cadeaux, challenges entre affiliés (« easy money »).
- **Nuance** : recommander un outil de recrutement quand on **cherche un job** n'est pas naturel → l'affiliation cible surtout **clients/partenaires**, pas les candidats. Brief affiliation à co-créer (Alec + Hugues + Boris) puis transmettre à **Julien** pour la V2.

---

## 10. 📈 Objectifs & projection
- Projection chiffrée difficile (evergreen Apollo + pics de com) → on pose des **objectifs**.
- **Cible Alec : ≥ 500 k$ encaissés d'ici octobre** (global), jusqu'à **1 M$** évoqué ; **ARR** comme boussole. Actuel ~**100 k**. ~80 clients à ~6 k$/an pour 500 k. Podcasts (4-5) sortis en décalé = capture étalée sur la fin d'année. Le Déclic seul ≈ 0,5 M potentiel.
- Croissance = répliquer le système (FR TPE-PME → restos GCC → par pays) ; **vitesse de pénétration** = la raison de lever.

---

## 11. 🤝 Opportunités & réseau
- **Samuel Duhal / Groupe Actual** (RDV juillet) : groupe ~2 Md€, **family office** investissant en HR-tech, **31 000 clients entreprises** → gros client **et** investisseur potentiel ; réfléchir au meilleur cas d'usage Aikho.
- **Gouvernement Abu Dhabi** : data de satisfaction citoyenne via **WhatsApp/Echo** (2 min interactives) au lieu des formulaires « bonhomme jaune ».
- **iClosed** : **licence à vie gratuite** dans toutes les boîtes où Alec est au capital (ami du fondateur — français, basé US) → à activer pour Aikho.
- **Whop** (paiement) : alternative Stripe moins chère + apporteur d'affaires potentiel (réseau du partnership manager).
- **Infra** : envisager migration **AWS → cloud type David Gurley** (3-20× moins cher) ; AWS gardé comme « tampon » de crédibilité pour la levée. **Claude responsable du check-in / revue de code** sur une infra qui va se complexifier (instances partout) ; Jonathan = structure / CI-CD.

---

## 12. ⚠️ Risques & cadence
- **Risques** : désalignement/désaccord équipe ; ressources ; **cash runout** ; **daily conversion / closing** des leads ; **complaisance** si le cash rentre (→ déléguer vite l'opérationnel pour se concentrer sur la levée). Garder les opérations fluides, **non-corpo** (« un sujet → quelqu'un le prend → on l'éclate »).
- **Cadence** : créer un **Slack** (canal externe) + WhatsApp (canal « AECO 2 DA MOON ») ; **meetings hebdo avec tâches + KPI** ; écran KPI partagé (réf. Revolut) ; rythme remote. **ADN 24-7** assumé et attendu de tous (« des entrepreneurs, pas des salariés »).

---

## ▶️ Décisions / next concrets de la séance
1. **Machine pirate en place d'ici ven. 3 juil** (Apollo + séquences + Alchimie + Agenda) → calls ~6 juil, closing ~7 juil. → Boris (systèmes) + Alec (copy/Alchimie) + Hugues (close grands comptes)
2. **LP transférée** de Claude vers les systèmes Aikho via **Jonathan** + iClosed embed → ASAP. → Boris
3. **Chiffrage budgets** (prestataires, tools, Inde, OBM, SDR Maroc) à mettre en face de l'**état des finances Aikho** → rendre l'apport « palpable ». → Hugues (finances) + Boris/Alec (chiffrage ressources)
4. **Cadre juridique apport entrepreneurs.com / equity / situation Boris** à instruire avant la paperasse de levée. → Alec + Hugues (+ Armand)
5. **DoD V2 avant 18 juil** (idéal 15) + relais d'absence (Joe V1 / Julien remote V2) ; Julien forme Joe dès le 10 juil. → Julien
6. **Brief affiliation** (% / mécanique / spec V2) à co-créer puis transmettre à Julien. → Alec + Hugues + Boris
7. **Stratégie de levée** : viser à locker vite ; activer réseau (dont David Gurley) ; option SPV via Le Déclic. → Alec
8. **Moment equity + échéances signature** à caler en clôture. → tous

---

## 🔗 Notes liées
- [[Jour 2 — Point Boris × Alec (matin) — Cartographie rôles & plan d'attaque]] · [[Jour 1 — Rapport consolidé]] · [[Jour 1 — Plan d'action & owners (après-midi)]]
- [[Partenariat Aikho]] · [[Aikho]] · [[Alec Henry]] · [[Hugues Pringault]] · [[Atlas Ventures]]
- [[🗼 Tour de contrôle - Projets en cours]]
