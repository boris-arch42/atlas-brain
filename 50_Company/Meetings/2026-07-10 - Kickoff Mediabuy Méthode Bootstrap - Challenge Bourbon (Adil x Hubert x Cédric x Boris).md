---
type: meeting
date: 2026-07-10
date_call: "≈ 10/07/2026 (vendredi) — export Sembly « Kickoff Mediabuy Méthode Bootstrap » sans date ; « lancement demain matin » ⇒ lancement ≈ sam 11/07. À confirmer"
participants: ["Adil (coordination funnel/CRM)", "[[Hubert Smolen]] (media buying)", "[[Cédric De Saint Jean]] (créatifs/validation)", "[[Boris Arduy]] (accès, HubSpot, Twilio/WhatsApp, Slack ops)", "[[Thomas Baeumlin]] (data/BigQuery)", "Stivel (uploads/formats)", "Mentionnés : [[Nicolas Farolfi]], Mario, [[Fabrice Jaeger]] (finance), [[Alec Henry]] (budget), [[Mohamed]] (accès)"]
contexte: "ENT — Kickoff media buying du funnel « Méthode Bootstrap » pour la campagne Challenge Bourbon : propriétés HubSpot, Tally + redirection WhatsApp, variantes Framer A/B, pipeline data (Make, Customer.io, BigQuery), monitoring Bugsnag, UTM/Lead Origin, backup ClickFunnels, créatifs, budget 75-100 K€, comptes publicitaires de secours, crédits Twilio/WhatsApp. Lancement le lendemain matin."
source: "Export Sembly AI (PDF, archivé via Claude)"
sensitivity: confidential
tags: [meeting, ent, mediabuy, bourbon, methode-bootstrap, funnel, hubspot, tally, whatsapp, framer, customerio, bigquery, bugsnag, utm, lead-origin, clickfunnels, twilio, budgets, comptes-pub, lancement, q3-2026]
status: inbox
---

# Kickoff Mediabuy — Méthode Bootstrap / Challenge Bourbon (≈ 10/07/2026)

> [!warning] **Sensibilité élevée.** Contient budgets média (75-300 K€), pratiques de comptes publicitaires prêtés/agency (Astra, Orange Trail), seuils de paiement et accès outils. Cercle media buying / direction uniquement.

> [!note] Normalisations transcription : « Tali » → **Tally** · « TimeStore / Fortune Time » = variables de tracking telles que transcrites (probablement horodatage — à vérifier avec Adil) · « Emma » = agent/flow de messagerie automatisée · « Dialogue » = outil messagerie tel que transcrit · « Revenue » = compte/entité détentrice de Bugsnag · Lead Origin funnel = **« method bootstrap »**.

## TL;DR
Kickoff opérationnel à J-1 du **lancement média** du funnel **Méthode Bootstrap** (campagne **Challenge Bourbon**). Alignement complet du funnel : **propriétés HubSpot** (prénom, nom, e-mail, CA annuel + **source du lead** — Adil confirme les noms, **Boris vérifie la config**), **préremplissage Tally cassé en iframe** (Hubert investigue, fallback = retirer le champ), **redirection directe vers WhatsApp post-formulaire** avec **stratégie de liens courts** (1 lien court par touchpoint → 1 lien central), **4 variantes Framer A/B** validées à 15h par Cédric, pipeline **Make → Customer.io → BigQuery** (Thomas finalise sécurité + schéma), **Bugsnag bloqué** par l'accès au compte Revenue (**Boris débloque**), **logique Lead Origin** définie (lead existant → origine conservée ; sinon « method bootstrap »), **backup ClickFunnels** confié à Cédric. Budget : **75-100 K€**, réévaluation à J+5, **jusqu'à 300 K€** possible selon CPL (Alec). ⚠️ **Environnement comptes pub instable** (Astra + comptes 25/07 bloqués, vérifs Meta) → **compte USD préfinancé en backup principal** (capacité ~9 548 $/j), 2-3 comptes supplémentaires à sourcer (Orange Trail…) et warmer, spend réparti sur 4 comptes. **Boris vérifie crédits/limites Twilio & WhatsApp** (flows Emma + 1-to-1). Coordination **Slack** : canvas to-do (Boris), point EOD canal Media Buying, **lancement demain matin**.

---

## 1 — Propriétés HubSpot
- Liste précise des **propriétés à renseigner à la création de contact** : prénom, nom, e-mail, **CA annuel / chiffre d'affaires** + une propriété **source du lead** (traçage de l'origine).
- **Adil confirme les noms de propriétés** ; **Boris vérifie la configuration HubSpot**.

## 2 — Tally : préremplissage & iframe
- Le préremplissage du prénom fonctionne via l'**URL non embarquée** mais **échoue dans l'iframe** → investigation **Hubert** (contexte config : Cédric + [[Nicolas Farolfi]]).
- La **redirection post-Tally** doit être définie **à l'appel du composant** (ne fonctionne pas sans URL explicite à l'embed).
- **Fallback UX** : retirer le champ de préremplissage du titre Tally si non résolu rapidement (Hubert + validation produit). Hubert évalue aussi si la variable prénom vaut la complexité (retrait par Cédric si ça ralentit la page).

## 3 — Redirection WhatsApp & liens courts
- **1 lien court par point de contact → 1 lien court central** : changer la destination des groupes WhatsApp **en un seul endroit** (mise en place Adil, convention de nommage Cédric).
- **Redirection directe vers WhatsApp après le formulaire** (limiter la perte) : la redirection Tally est **contrôlée par le marketing** et ne doit pas être écrasée par le composant embarqué (URL : Adil ; garde-fou embed : Hubert).
- Message post-opt-in **concis** + nomenclature cohérente (ex. « Redirection post-formulaire opt-in challenge ») pour simplifier le tracking (Cédric + Adil).

## 4 — Variantes Framer & tests A/B
- Funnel **en ligne avec 4 variantes A/B** prêtes ; Hubert partage les liens de test + duplique les variantes en pages Framer.
- **Validation des 4 variantes : deadline ferme 15h00** (revue + approbation Cédric ; implémentation Hubert).
- Pages de remerciement/redirection maintenues **ouvertes pour les tests** mais pas destination finale si le funnel redirige vers WhatsApp.

## 5 — Pipeline data (Make · Customer.io · BigQuery)
- **Make opérationnel** : infos leads transitent, **invitations calendrier envoyées** correctement ; **Customer.io OK** pour les confirmations d'opt-in (config/validation Adil + Thomas).
- Routage des données de campagne validées vers **BigQuery** une fois les **contrôles de sécurité + schéma** finalisés (**[[Thomas Baeumlin]]** confirme l'ingestion ; **Adil** briefe le CTO).
- **Brief e-mail de campagne encore à envoyer au CTO** (config e-mail + capture data aval) — Adil.

## 6 — Monitoring Bugsnag & accès Revenue ⚠️ blocage
- Intégration **Bugsnag** nécessaire pour suivre les erreurs du funnel ; le **snippet doit être récupéré depuis le compte Bugsnag rattaché à « Revenue »**.
- **Hubert n'a pas accès à Revenue** → blocage tant que l'accès/le code n'est pas fourni. **Boris vérifie l'accès Revenue et débloque.**

## 7 — UTM & logique Lead Origin
- Tests : champs **UTM incohérents** (campaign, source, medium, term partiellement renseignés) → **Hubert garantit les paramètres UTM**, **Adil vérifie le tracking**.
- **Lead Origin ≠ auto-rempli depuis les UTM** ; il représente le **premier point de contact** : si le lead **existe déjà dans Customer.io → conserver l'origine initiale** ; sinon → origine = funnel (**« method bootstrap »**). Logique : **Adil + Boris + Cédric**.
- **Tests bout-en-bout en conditions réelles** (e-mails + numéros de test) : nom complet, e-mail, téléphone, pays, UTM, origine → **Customer.io + HubSpot** (exécution Hubert, confirmation Adil).
- 🔗 Même philosophie que le **tag d'origine immuable** de la communauté (cohérence conventions Lead Origin à l'échelle ENT).

## 8 — Variables de tracking Customer.io
- Champs requis : **UTM, TimeStore, Fortune Time, Gclid, FBclid** + un champ **channel** mappé au **type d'opt-in** (Adil vérifie des exemples).
- L'origine du lead est lue depuis Customer.io et doit inclure UTM + click IDs (mapping Hubert + Adil).

## 9 — Backup ClickFunnels
- **Cédric construit un funnel de secours ClickFunnels** au cas où Framer/embeds échouent au lancement.
- **Adil renvoie le dossier** déjà partagé (assets, UTM, éléments de design) pour la config alternative.

## 10 — Créatifs & plan média
- **Cédric partage les liens créatifs existants** + le **2e tournage en montage** (≈ **+30-40 créatifs vidéo**).
- **Hubert crée/maintient la feuille de plan média** (Drive) agrégeant liens, assets, statiques.
- **Stivel** reposte les liens et **teste les formats** (certains créatifs possiblement non conformes Google — tentera quand même).

## 11 — Budget & plan de scaling
- **Spend prévu : 75-100 K€** (montée à 100 K€ si CPL favorable) — décision finale **Cédric + Alec**.
- **Réévaluation à J+5** ; **Alec pourrait recommander jusqu'à 300 K€** selon performances.
- **Sensibilité CPL forte** → réactivité immédiate aux variations (Hubert).

## 12 — Comptes publicitaires : risques & plan de secours ⚠️
- **Astra + plusieurs comptes fournisseurs bloqués** (vérifications sécurité Meta) ; les comptes prévus pour le lancement (**25, 07…**) sont **indisponibles**.
- Partir du principe d'un **environnement instable** (les fournisseurs ne disent pas s'ils sont « dans le viseur »).
- ✅ **Compte publicitaire USD préfinancé = backup principal** (éviter les échecs de paiement) — mise en place Hubert, financement Finance.
- **Sourcer 2-3 comptes supplémentaires** (débloquer Astra, contacter **Orange Trail** et autres) + **warming petits budgets** (Hubert, Mario).
- Plan de répartition : **petit budget sur 4 comptes** au départ → bascule du spend si un compte saute.
- **Capacité compte USD** : ~**9 548 $/jour** (940 $ dépensés la veille en retargeting) ; **seuil Amex ~405 $** → **recharge Amex** pour continuité (Finance / [[Fabrice Jaeger]]).

## 13 — Crédits Twilio & WhatsApp
- **Adil a besoin de confirmation des crédits/tokens Twilio + WhatsApp Business** pour les messages automatisés (**Emma**) et les parcours WhatsApp 1-to-1.
- **Boris vérifie** : limites des comptes, **restrictions MPS passées**, accès de « Dialogue » + intégration automatique de carte.
- Accès : Adil peut demander les mots de passe à [[Mohamed]] ; **Boris tente de récupérer les identifiants déjà publiés**.

## 14 — Coordination & lancement
- **Synchronisation Slack** : **canvas / to-do dans le groupe** pour lister et attribuer 4-5 tâches clés (mise en place **Boris**) ; **canal Media Buying** pour les points de fin de journée.
- **Point complet EOD** pour confirmer l'achèvement des tâches **avant le lancement de demain matin** ; Cédric envoie les dossiers créatifs pour uploads anticipés.
- **Énergie de l'équipe** en baisse chez certains → pragmatisme sur la charge + async pour couvrir les shifts nuit/jour ; **Stivel préserve son énergie pour les uploads** (attentes réalistes sur les délais de retour).

---

## Actions consolidées

| # | Action | Owner | Échéance |
|---|---|---|---|
| 1 | Confirmer les **noms de propriétés HubSpot** (dont source du lead) | Adil | Avant lancement |
| 2 | **Vérifier la config HubSpot** | **[[Boris Arduy]]** | Avant lancement |
| 3 | Résoudre le **préremplissage Tally en iframe** (ou fallback) | [[Hubert Smolen]] | Avant lancement |
| 4 | Poser les **URLs de redirection Tally → WhatsApp** (contrôle marketing) | Adil (+ garde-fou Hubert) | Avant lancement |
| 5 | Mettre en place les **liens courts** (1/touchpoint → central) + nomenclature | Adil + Cédric | Avant lancement |
| 6 | **Valider les 4 variantes A/B** | [[Cédric De Saint Jean]] | **15h00 (ferme)** |
| 7 | Confirmer l'**ingestion BigQuery** (sécurité + schéma) | [[Thomas Baeumlin]] | Court terme |
| 8 | Envoyer le **brief e-mail de campagne au CTO** | Adil | Immédiat |
| 9 | **Débloquer l'accès Bugsnag** (compte Revenue) → snippet à Hubert | **Boris** | Immédiat |
| 10 | Garantir les **paramètres UTM** + implémenter la **logique Lead Origin** | Hubert + Adil + Boris + Cédric | Avant lancement |
| 11 | **Tests bout-en-bout réels** (Customer.io + HubSpot) | Hubert (exéc.) + Adil (confirm.) | Avant lancement |
| 12 | Construire le **backup ClickFunnels** (dossier assets renvoyé par Adil) | Cédric | En parallèle |
| 13 | Partager **créatifs** + 2e tournage (+30-40 vidéos) | Cédric | Immédiat |
| 14 | Créer/maintenir la **feuille de plan média** | Hubert | Continu |
| 15 | Tester les **formats** (dont conformité Google) | Stivel | Lancement |
| 16 | **Préfinancer le compte USD** + recharge Amex | Hubert + Finance/[[Fabrice Jaeger]] | Immédiat |
| 17 | **Sourcer 2-3 comptes pub de secours** (Astra, Orange Trail…) + warming | Hubert + Mario | Immédiat |
| 18 | **Vérifier crédits/limites Twilio & WhatsApp** (Emma, 1-to-1, MPS, Dialogue) | **Boris** (accès via Mohamed si besoin) | Avant lancement |
| 19 | Mettre en place le **canvas to-do Slack** + point EOD canal Media Buying | **Boris** + équipe | Aujourd'hui |
| 20 | **Lancement matinal** selon état de la tech | Équipe | Demain matin (≈ 11/07) |

## Décisions clés
- **Redirection directe WhatsApp post-formulaire**, contrôlée par le marketing (jamais écrasée par l'embed).
- **Stratégie de liens courts centralisée** + nomenclature standard.
- **Tests A/B en conditions réelles** avec contrôles HubSpot/UTM ; validation variantes à 15h.
- **Lead Origin** : origine initiale conservée si lead existant, sinon **« method bootstrap »**.
- **Backup ClickFunnels** préparé en parallèle (Cédric).
- **Compte USD préfinancé = backup principal** ; spend réparti sur 4 comptes.
- Budget **75-100 K€**, réévaluation **J+5**, plafond potentiel **300 K€** (Alec).

## Points de vigilance
- **Comptes publicitaires = risque n°1 du lancement** (blocages Meta en cascade) — le plan 4 comptes + USD doit être opérationnel **avant** le premier euro dépensé.
- **Bugsnag non branché = lancement en aveugle** sur les erreurs funnel → dépendance à l'accès Revenue (Boris).
- **UTM/Lead Origin** : toute incohérence à J1 pollue définitivement l'attribution (et le CPL reporté) — tests bout-en-bout non négociables.
- **Seuils de paiement** (Amex ~405 $) : risque de coupure silencieuse du spend.
- **Fatigue de l'équipe** à J-1 : arbitrer la charge, tout n'est pas critique pour le lancement.
- 🔗 L'arbitrage **CGM vs Alkimiy** sur la prise d'appels Bourbon (cf. Point hebdo 10/07) conditionne la valeur de ce trafic : caler le dimensionnement call center sur les volumes réels du funnel.

## Liens
- [[Hubert Smolen]] · [[Cédric De Saint Jean]] · [[Boris Arduy]] · [[Thomas Baeumlin]] · [[Adil]] · [[Nicolas Farolfi]] · [[Mohamed]] · [[Fabrice Jaeger]] · [[Alec Henry]]
- Réunions sœurs (bloc 09-10/07) : [[2026-07-10 - Point hebdo 1-1 (Boris x Alec)]] (arbitrage Bourbon CGM/Alkimiy) · [[2026-07-10 - Gouvernance Ops, Conformité & Support Client (Alec x Boris x Sabrina)]]
- Infra & précédents : [[Kelly Launch — infra commerciale & Sales Bis]] · [[Lucas (CGM)]] · [[2026-07-08 - CRO Cash & Growth (Alec x Boris x Aziz x Cédric x Océane x Fabrice)]] · [[🗼 Tour de contrôle - Projets en cours]]
