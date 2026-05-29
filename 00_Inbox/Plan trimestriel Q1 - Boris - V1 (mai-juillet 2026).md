---
type: plan-trimestriel
quarter: Q1 Boris (mai-juillet 2026 — 13 semaines)
date-created: 2026-05-01 (J0 PM)
version: V1 — pour discussion en trio Alec+Fabrice+Boris
date-validation-cible: 2026-05-01 16h FR (call OKR trio)
for: "[[Boris Arduy]]"
status: v1-pour-discussion
source: entrepreneurs-com
sensitivity: confidential-max
tags: [plan-trimestriel, Q1, mai-juillet-2026, operating-partner, V1, post-J0, post-slack-tripartite, 4-variables-alec]
naming-note: "EN INTERNE = OKR. EN SÉANCE TRIO = 'Plan trimestriel Q1' ou 'Engagements Q1'. Mot OKR proscrit (HO31bis)."
related-resources: "[[Draft OKR Q1 Boris]] (historique avant J0), [[Prep - Call OKR trio 1er mai]], [[Ressource - Slack Alec - Cadrage call Ops IT Tech Data IA 5 mai]], [[Ressource - Nœuds opérationnels Alec 1er mai 2026]]"
---

# 🎯 Plan trimestriel Q1 Boris — Operating Partner Entrepreneurs.com

> **Période** : 1er mai 2026 (J1) → 31 juillet 2026 (J+90 = échéance dure verticale Data/IA/Tech/Ops fixée par Alec au 1er août)
>
> **Mandat** : Operating Partner — co-COO de fait avec Fabrice (annonce officielle 1er juin), posture spec/architecte (Fabrice spec, Boris architecte), allocation 4,5j/semaine ENT.
>
> **Posture de présentation** : ce document est **un point de départ pour discussion**, pas un document à valider tel quel. Restriction volontaire à 4 objectifs et 2-3 KR par objectif — préférer 4 objectifs livrés à 80% que 8 objectifs à 30%.

---

## 🟢 MAJ 2026-05-28 J+27 — Post-Marrakech : Sophia décline, Mohamed maintenu, Aikho remplace Mithril, statut chantiers

> Mise à jour de cadrage suite au retour Marrakech + 1-1 Alec 26/5. **4 mutations.**

### 🔴 MUTATION A — Sophia décline → Objectif 4 reformulé, KR4.2 supprimé

Sophia a **décliné la mission** (charge jugée trop lourde/complexe). Elle finalise son audit au team building 5-7 juin, sans engagement de suite. Cf. [[Sophia]].

→ La structure top management devient un **triptyque interne pur** (Boris / Fabrice / Anisse), sans jambe consulting externe. Cf. [[Diag - Nouvel Organigramme & Cordon Sanitaire 2026-05-27]].
→ **KR4.2 (scope Sophia signé en quatuor) est SUPPRIMÉ.** L'Objectif 4 se recentre sur passation Axel (KR4.1) + résilience marketing (KR4.3) + sécurisation du triptyque + annonce co-COO 1/6.
→ Récupérer le **livrable d'audit Sophia** post-team building comme input ponctuel (frameworks/templates).

### 🔴 MUTATION B — Mohamed maintenu → KR2.2 perd l'économie "fin Mohamed"

Mohamed **reste sur forfait + format actuels** vu la charge cybersécurité (sprint + remediation phishing + NAS). Cf. [[Mohamed]].

→ **KR2.2** : l'économie "fin Mohamed IT = 24K€/an" **disparaît** — à compenser par d'autres lignes pour tenir la cible 70-100K€.
→ **GDZ (société de Mohamed)** mandatée sur le plan phishing = extension de son mandat, pas un coût tiers nouveau.
→ **Blocage accès** Boris+Mohamed pour l'audit SaaS **toujours non résolu au 28/5** — priorité de déblocage.

### 🔴 MUTATION C — Aikho remplace Mithril comme stack recrutement ENT

**Mithril est mis en pause** (réflexion sur la vision produit). Son rôle de **stack de sourcing/recrutement ENT est repris par Aikho** (solution jugée très intéressante, discussions en cours avec eux). Cf. [[Aikho]] + [[Mithril/README]].

→ **KR3.3** : partout où il était écrit "sourcing via Mithril/Aiko", lire désormais **sourcing via Aikho** (remplaçant Nicolas, dévs offshore, PMO local, futur CTO Dubai). Mithril n'est plus le véhicule opérationnel ENT à ce stade.

### 🟢 MUTATION D — Statut chantiers au 28/5

- **5 process (KR1.2)** : en cours de déploiement. **Jordan intégré sur la partie RAF** (Responsable Admin & Financier).
- **HubSpot source unique (KR3.1)** : s'éclaircit, mais **grosse prise en main à venir côté Boris** avec le nouvel organigramme.
- **Audit SaaS (KR2.2)** : chiffrage en cours mais **bloqué sur les accès** (Boris + Mohamed).
- **Sales Bis** : question pivot **tranchée → système réplicable** (avec ajustements). SOP devient actif. Cf. [[Scope - Documentation système Sales bis - Lancement Kelly]].
- **Cybersec** : tableau de suivi des datas en place, **~15K fichiers publics retirés** (82K → ~67K), **test phishing : 29 identifiants récupérés** → plan d'action GDZ. Cf. [[Scope - Sprint Cybersec 48-72h - mai 2026]].
- **Sortie Nicolas** : volontairement **ralentie** (ne rien casser) — collecte process/accès + recherche remplaçant en cours. Cf. [[Nicolas Farolfi]].
- **Cartographie contrats** : Phase 1 (cartographie de toutes les équipes) **faite** → passage Phase 2 contrat par contrat avec Fabrice.
- **Axel** : départ **imminent** (quelques jours) — KR4.1 en phase critique.
- **Team building** confirmé **5 juin (soir) → 7 juin**, Boris présent.

---

## 🔴 MAJ 2026-05-19 J+18 — Crise cybersec + sortie Nicolas + mandat onboarding sales externes (post-replays 18-19/5)

> Cf. [[Ressource - Replay Weekly Fabrice × Alec 18 mai 2026]] + [[Ressource - Replay COMEX hebdo 19 mai 2026]]. **3 mutations majeures du Plan Q1.**

### 🆕 MUTATION 1 — KR3.3 explose : audit IT devient "audit IT + cybersec"

L'audit Mohamed (avril-mai) a révélé **3 vecteurs d'exposition cybersec critiques** :
- **~82 000 fichiers publiquement accessibles** sur la plateforme
- **Redirections email entreprise → boîtes privées** (supprimées immédiatement)
- **Slug iClose modifiable** par 6-7 super-admins → vecteur d'incident démontré (crash Kelly, perte estimée Alec >1M€)

**Décisions Alec en weekly 18/5** :
- Verrouillage par défaut de toute la plateforme
- Plan d'action structuré sous 48-72h
- **Plan NAS owner + échéance** demandés explicitement avant son départ Dubai 25-30/5

→ **Nouveau scope** : [[Scope - Sprint Cybersec 48-72h - mai 2026]] cadre l'exécution.

→ **KR3.3 ré-articulé** : la verticale Ops/IT/Tech/Data/IA hérite désormais explicitement de la **gouvernance cybersec**. Reporting consolidé mensuel 1/6 inclura audit IT + cybersec.

→ **HO39 (crise data systémique) amplifiée** : 3 angles cybersec s'ajoutent aux 6 problèmes data déjà identifiés.

### 🆕 MUTATION 2 — Sortie Nicolas Farolfi immédiate (semaine du 18/5)

- **Licenciement immédiat** acté par Alec en weekly 18/5
- **Retrait accès jeudi 21 → vendredi 22 mai nuit**
- **Notification appel + email vendredi 22/5**
- **Paiement réglé le 10 du mois suivant**
- **Équipe Boris (Mithril) en relai marketing ops 2-3 semaines** le temps du recrutement
- 3 profils déjà shortlistés par Cédric via Aikho à activer

→ Accélère **KR3.3 (stack équipe verticale)** : sourcing remplaçant prioritaire S3-S4 mai.

→ **Investigation logs iClose** = responsabilité Boris (indépendante de la décision Nicolas — pas d'attribution sans preuve).

→ Cf. [[Nicolas Farolfi]] pour le plan détaillé.

### 🆕 MUTATION 3 — Nouveau mandat Boris : partage onboarding/parcours post-vente avec sales externes

Mandat explicite Alec en COMEX 19/5 :
- Partager onboarding + parcours post-vente avec **toutes les équipes commerciales externes**
- **Alignement préalable Aziz** (pas de court-circuit Head of Sales)
- Canaux : contenu **School** + message **WhatsApp dédié**
- Même flux partagé en interne pour cohérence

→ **Convergence avec [[Scope - Documentation système Sales bis - Lancement Kelly]]** : la matière onboarding/parcours post-vente est **la matière même** du SOP Sales Bis en cours de captation Phase 1.

→ **Quick win politique** : exécuter ce mandat **accélère la Phase 1 SOP Sales Bis** avec validation Alec garantie.

→ Impact KR1.2 (top 10 process avec head owner) : ce process structurel s'ajoute aux 10 candidats prioritaires.

### 🟢 Validation — Trustpilot résolu (sort du scope Boris)

Le sujet Trustpilot avis frauduleux est **résolu** via escalade officielle Sabrina + Océane + avocat (cf. COMEX 19/5). L'action levier perso Boris **désactivée**. Cf. [[Note - Guerre Trustpilot mai 2026]] (statut maintenance).

### 🟢 Validation — Aikho confirme valeur opérationnelle

Pipeline RH Dubai au 19/5 : **22 candidats interview IA + 4 terminés + 100 rejetés CV**. Aikho filtre efficacement en amont. Renforce le narratif partenariat Hugues Pringault × EC structuré au call 12/5 (cf. [[Ressource - Replay Call Aikho × Hugues Pringault 12 mai 2026]]).

→ **Nouvelle deadline calendaire** : finalisation détails partenariat Aikho **29 mai** (cohabite avec Welcome Session Kelly 29/5).

### 🟡 Signaux faibles structurels

- **HO41 (visibilité Alec)** devient critique cette semaine : Boris physiquement absent jeudi-dimanche Marrakech pendant que la crise cybersec est ouverte. **Rituel reporting cybersec quotidien** (1 message Slack/jour) à installer avant départ — décision la plus haut levier de la semaine.
- **Capital politique Boris** sur le mandat IT : a défendu Mohamed publiquement 2 fois en 2 jours (18/5 + 19/5). À continuer mais éviter sur-protection.
- **Onboarding V2 Quentin + matching coach-client** (présenté COMEX 19/5, IPIP 130 + algo matching) = **matière forte pour KR3.2** (automation cycle de vie lead). Quick win critique HO39.
- **Système IA lancement marketing Anisse** : Cédric va le voir cette semaine. **Thermomètre HO32 (départ Cédric Q2-Q3)** — si Cédric trouve l'outil convaincant, signal positif rétention.

---

## ⚠️ Note tactique pour la séance — vocabulaire

**🚫 Le mot "OKR" est proscrit en séance.** Cf. HO31bis dans [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] — Tang/Charles ont contaminé le mot, Alec a explicitement validé *"on n'a pas d'OKR, on déteste les OKR"*.

**✅ À utiliser** : *"plan trimestriel Q1"*, *"engagements trimestriels"*, *"objectifs et résultats clés"*.

**Ce qui reste** : la **structure** objectifs/résultats clés, mesurable, datée, revue régulière.
**Ce qui change** : le **vocabulaire** uniquement.

---

## 🟢 MAJ 2026-05-05 J4 SOIR — Call verticale Ops/IT/Tech/Data/IA : décisions actées + timeline RH consolidée

> Cf. [[Ressource - Replay Ops IT Tech Data IA 5 mai 2026]] pour le replay complet.
>
> **Le call du 5 mai a transformé plusieurs hypothèses Q1 en décisions actées**. L'objectif 3 (verticale Data/IA/Tech/Ops) bascule de "à cadrer" à "plan d'exécution avec décisions actées".

### 🟢 Décisions actées au call 5 mai

| Sujet | Décision | Owner | Échéance |
|---|---|---|---|
| **Mohamed IT** | 2 mois à 4K€ (audit + plan) puis forfait 1 500€/mois | Boris (supervision) | 4 juillet bascule forfait |
| **Quentin plateforme** | Transition vers offshore actée (3 mois max) | Boris + Fabrice (co-pilotage) | Juillet 2026 |
| **Nicolas ops auto** | Remplacement via Mithril — fiche de poste Cédric déjà transmise | Boris (sourcing Mithril) | Cette semaine (lancement) |
| **PMO local** | Validé en transitoire (1 200-1 500€/mois, francophone) | Anisse + Boris | Mai-juin (recrutement) |
| **CTO Dubai** | Salarié à Dubai sous Fabrice (futur GM Dubai) | Alec (sourcing) | Q3-Q4 2026 |
| **Wassim** | Non tranché — doute Alec exprimé publiquement | Anisse + Boris (silence stratégique) | Arbitrage 60-90j |
| **Thomas data** | Conservé conditionnellement — plan Fabrice attendu | Fabrice + Boris (filet) | Plan sous 7-14j |
| **Livrable 48-72h** | Message Slack 3 phases (45j/90j/4-5 mois) | Anisse + Boris (co-construction) + Fabrice (validation) | Mercredi 6 mai max |

> 🔄 **Note de badge ajoutée 2026-05-10** : le carnet Boris du 10/5 mentionne *"trouver un gars spécialiste en automatisation pour le niveau macro de la boîte, surement inde ou maroc"*. Après clarification : **même profil que "Nicolas ops auto / Ops auto Maroc" ci-dessus**, simplement rebadgé dans les notes terrain. Pas un 2e poste à créer. Cf. [[Nicolas Farolfi]] pour la fiche personne et le plan de passation. Le KR3.3 reste donc inchangé sur ce point.

### 🟡 Cible budgétaire précisée

- **Aujourd'hui** : 52K€/mois (verticale Ops/IT/Tech/Data/IA)
- **Cible Alec à J+90** : 30K€/mois (-40%)
- **Cible Anisse à J+90** : 10K€/mois (-80%, fourchette basse)
- **Cadrage Alec en clôture** : *"Faire plus avec moins, pas faire moins avec moins"* — réduction sans ralentissement de cadence

### 🔴 Timeline RH consolidée — 6-8 mouvements simultanés sur 45-90 jours

**Risque turnover synchrone identifié par Boris en séance 32:14** : la verticale va vivre plusieurs rotations en parallèle. À gérer pour limiter déstabilisation.

| Phase | Sortie | Entrée | Risque |
|---|---|---|---|
| **Mai (J+4 à J+30)** | — | Sourcing 2-3 dévs offshore Maroc + Ops auto Maroc + PMO local | Charge sourcing Boris |
| **Juin (J+30 à J+60)** | Mohamed (31 mai bascule forfait) | 1er dév offshore opérationnel + remplaçant Nicolas | Décalage transmission Mohamed → Boris |
| **Juillet (J+60 à J+90)** | Quentin (transition fin) | 2e + 3e dévs offshore + PMO local opérationnel | Risque coupe sèche si Quentin non-coopératif |
| **Août-Octobre** | Possiblement Wassim | CTO Dubai salarié | Stabilisation phase 3 IA |

**Cadre transverse** : verbatim Boris en séance 32:14 :
> *"Faut vraiment faire attention au turnover. [...] À chaque fois qu'on fait tourner quelqu'un, à ce qu'on limite la déstabilisation que ça peut entraîner."*

→ **À surveiller en revue J+30 et J+60** : cadence des rotations vs capacité d'absorption équipe.

### 🟢 Matérialisation publique de Mithril

Le call du 5 mai a matérialisé publiquement Mithril comme stack de recrutement de référence pour Entrepreneurs.com :

- **Verbatim Alec 31:24** : *"Cédric t'a envoyé la fiche de poste Boris pour Mithril pour déjà commencer à faire tourner ?"*
- **Premier projet client** : remplacement Nicolas (ops auto)
- **Projets futurs probables** : 2-3 dévs offshore plateforme + PMO local + possiblement substitut Wassim

→ **Cohérence avec mandat 29/4 PM** (cf. [[Alec Henry]] section MAJ 29/4 PM). Mithril devient l'outil de référence opérationnel.

### 🔴 Nouveau livrable critique : message Slack 3 phases (J+1 à J+3)

Alec demande sous 48-72h un message structuré dans le canal Slack partagé avec :
- **Phase 1 (45 jours = 5 mai → 20 juin)** : annonces + sourcing + premier dévs offshore + audit consolidé
- **Phase 2 (90 jours = 5 mai → 5 août)** : transition opérationnelle + 3 dévs offshore + PMO local + Mohamed forfait
- **Phase 3 (4-5 mois = septembre-octobre)** : stabilisation + CTO Dubai + 5 piliers IT-SaaS-Cybersec V1 + couche dynamique IA

Décomposition par pôle : **IT** / **Data** / **IA** / **Tech (Plateforme)** / **Ops (automations)**.

**Owners explicites** par pôle et par phase. **Objectifs chiffrés** : humains, recrutement, budget.

**Co-construction** : Anisse (qui a porté la structure en séance) + Boris (cadre owners/deadlines/budgets), validation Fabrice avant publication.

→ **Inclure dans le KR3.3** comme livrable déclenchant début de Phase 1.

### 🟢 Capital politique Boris consolidé en séance

- **2 fois Boris contredit le tandem Alec-Fabrice et gagne** (Mohamed cybersec + PMO local)
- **Mandat IT permanent officialisé publiquement** devant Fabrice + Anisse
- **Slot jeudi 17h Mohamed transféré Fabrice → Boris** (libère 30-60 min/sem à Fabrice)
- **Excuses Alec à Fabrice obtenues** — épreuve 1er juin passée pour cette séance

→ **À cadrer dans KR4.2** (3 leviers Fabrice → support stabilisation) + **KR1.1** (cordon sanitaire en cours de matérialisation).

### 🔴 Nouvelle hypothèse à intégrer dans tous les KR : HO41 (visibilité, pas travail)

Le vrai problème d'Alec est l'**absence de visibilité** sur ce qui est fait, pas la qualité du travail. Cf. [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] HO41.

**Implication transverse Q1** : **installer un rituel de reporting hebdo verticale** comme priorité structurelle d'ici J+7. C'est probablement le plus haut levier de création de valeur Boris.

**Format proposé** :
- 1 bullet par pôle (IT / Data / IA / Tech / Ops)
- Status (vert/orange/rouge)
- Livrables réalisés cette semaine
- Livrables prévus la semaine prochaine
- Risques et arbitrages requis
- Diffusion : Alec + Fabrice + Anisse + Boris

→ **À ajouter comme KR3.X** ou comme rituel transverse dans la cadence Q1.

---

## 🧭 Cadre de pilotage — 4 variables canoniques Alec

Cadre posé par Alec au call CRO du 30/4 (cf. [[Ressource - Slack Alec - Cadrage call Ops IT Tech Data IA 5 mai]]). **Tout KR doit s'aligner sur au moins une de ces 4 variables — sinon, il sort du périmètre Q1.**

| # | Variable canonique Alec | Application Q1 Boris |
|---|---|---|
| 1 | **Maximisation des résultats sur les ressources mobilisées** | Audit dépenses + 70-100K€/an SaaS + verticale 52K€/mois sans ROI à transformer |
| 2 | **Augmentation du panier moyen** | Qualité de vente + ICP recadré + posture sales/coachs |
| 3 | **Réduction du délai d'attribution** | Automation cycle de vie lead + matrice jurisprudence + cordon sanitaire HO29 |
| 4 | **Élévation du revenu par lead** | Refonte stack data + boucle data → feedback marketing + segmentation 3 niveaux deals perdus |

> ✅ **Tout le reste est secondaire.** (verbatim Alec)

---

## 🧱 Principes directeurs Q1

1. **4 objectifs maximum** — un Operating Partner en prise de poste ne peut pas porter 5+ chantiers structurels simultanément.
2. **2-3 Key Results par objectif** — concrets, mesurables, datés (J+30, J+45, J+60, J+90).
3. **Règle des boucles fermées** — pas de nouvelle initiative tant qu'une initiative en cours n'est pas fermée ou explicitement abandonnée. (verbatim Anisse 26/4)
4. **Pas de KR qui dépend exclusivement d'autres que Boris ou de l'arbitrage trio** — sinon Boris ne porte rien.
5. **Mesurabilité non-ambiguë à J+30, J+60, J+90** — soit binaire, soit chiffré, soit qualitatif documenté.
6. **Posture spec/architecte** — Fabrice spec, Boris architecte. Pas d'overlap. Co-construction systématique.
7. **Cadence revue intégrée** — weekly + J+30 + J+60 + J+90.

---

## 📅 Calendrier dur Q1 — événements externes contraignants

| Date | Événement | Impact KR |
|---|---|---|
| **1er mai (J0)** | Prise de poste + cordon sanitaire posé + dette de confiance | KR1.1 actif |
| **5 mai (J+4)** | Call Ops/IT/Tech/Data/IA + démarrage audit IT (Mohamed) + workshop spec data | KR3.1 actif |
| **5 mai SOIR (J+4)** | ✅ Call verticale tenu — décisions actées (Mohamed/Quentin/Nicolas/PMO/CTO), excuses Alec à Fabrice, mandat IT Boris officialisé | KR3.1 + KR3.3 + KR4.2 enclenchés |
| **6-7 mai (J+5/J+6)** | ⏰ **Livrable 48-72h** : message Slack 3 phases (45j/90j/4-5 mois) co-construit Anisse + Boris | KR3.3 critique |
| **7 mai jeudi 17h (J+6)** | Premier point hebdo Boris × Mohamed (slot transféré Fabrice → Boris) | KR3.1 |
| **6/7/8 mai** | Workshop COMEX Mithril (vitrine sourcing) | KR3.3 actif |
| **18 mai (J+17)** | Jordan reprend recouvrement | KR2.1 actif |
| **20-25 mai** | Marrakech (Sabrina + Boris + Aziz à confirmer + trio Alec/Anisse/Abdel cadré) | KR1.3 + KR2.2 |
| **23 mai (J+22)** | Deadline onboarding auto + immersion plateforme | KR1.2 |
| **31 mai (J+30)** | Fin Mohamed IT + livrable audit IT consolidé + revue mi-parcours | **Revue J+30** |
| **1er juin** | Meeting mensuel — annonce co-COO + roadmap Fabrice GM Dubai | KR4.1 + KR4.2 |
| **5-7 juin** | Team building global | Levier KR1.3 (cadre Alec ouvert au team building) |
| **30 juin (J+60)** | Revue intermédiaire + cadrage Sophia | **Revue J+60** |
| **1er août (J+90)** | **Nouveau modèle Data/IA/Tech/Ops effectif** (échéance dure Alec) | **KR3.3 = épreuve de vérité** |

---

## 🎯 Objectif 1 — Restaurer la cadence opérationnelle transverse

> **Pourquoi** : briser le cycle vicieux HO29 (rapports verbaux → impulsivité → friction → silos) + restaurer mode catamaran/paquebot (HO30 — mode opératoire S1 2025 détruit par Tang) + concrétiser le cordon sanitaire posé J0 + restaurer la dette de confiance projet par projet (cf. [[Cadre - Dette de confiance]]).
>
> **Cible J+90** : décisions arbitrées au niveau heads sans remontée systématique. Cadence transverse stable. Top 10 process avec head owner identifié + adoption mesurée.
>
> **Variable canonique Alec** : (3) réduction du délai d'attribution (les heads décident plus vite quand ils ont l'autorité réelle).

### KR 1.1 — Cordon sanitaire HO29 effectif et tracé

**Mesure** : sur les 13 semaines de Q1, **au moins 80% des revirements/scuds Alec → N-2/N-3 sont tracés et passent par Boris d'abord**. Journal des revirements observés mis à jour hebdo.

**Cible J+30** : règle effective et reformulée par Alec dans une situation réelle (✅ déjà acquis 30/4 avec cas Léa).
**Cible J+60** : décompte des bypass dans le mois — cible <2.
**Cible J+90** : tendance baissière confirmée + auto-régulation Alec sans rappel Boris.

### KR 1.2 — Top 10 process cartographiés avec head owner + 5 process déployés avec adoption mesurée

**Co-construction Boris+Fabrice** (posture spec/architecte). Le Miro Fabrice + observations Boris S1 = base.

**Cible J+10 (10 mai)** : cartographie écrite des nœuds opérationnels validée Alec+Fabrice+Boris (déjà à 70% via Miro Fabrice).
**Cible J+30** : 10 process top identifiés avec **un head owner nommé pour chacun** (pas de "à voir avec X", un nom unique).
**Cible J+45** : **5 process déployés avec adoption mesurée via logs d'utilisation** (méthode Anisse). Inclut au minimum :
- Onboarding RH (mandat actuel sortant Alexis)
- Centralisation lettres de résiliation client
- Architecture support tech sales (agent IA + escalade — cas test bug Mike paiement)
- Nurturing leads non qualifiés (avec Cédric + Anisse)
- Process de recouvrement (post-reprise Jordan 18 mai)

### KR 1.3 — Cadence transverse refondue (3 rituels installés)

**Cible J+14 (14 mai)** : 3 rituels installés et tenus sans interruption :
- **Weekly hebdo Boris↔Fabrice** (jeudi 30 min) — revue d'exécution + arbitrages opérationnels
- **COMEX hebdo refondu** (lundi format dense — fini les "pendant qu'un parle, les autres s'en branlent") — décisions documentées par défaut
- **Rituel hebdo data structuré** (1h/semaine, 5 personnes minimum : Boris + Fabrice + Anisse + Aziz + Cédric — coordination horizontale tech-data-marketing-sales sans toucher aux organigrammes)

**Cible J+90** : 12+ rituels weekly tenus sur 13 semaines (>92% taux de tenue).

---

## 🎯 Objectif 2 — Redresser la trésorerie et professionnaliser la finance

> **Pourquoi** : trésorerie en fonte 50-200K€/mois + 2-3M€ d'impayés non recouvrés + dépenses discrétionnaires 2025 non auditées + chaque ticket finance traité ad hoc par Fabrice (HO38 — proxy parfait HO8) + sortie Mohamed IT 31 mai = économies SaaS à acter.
>
> **Cible J+90** : 70-100K€/an d'économies SaaS actées + matrice jurisprudence financière déployée et opérationnelle pour Sabrina/CFO + recouvrement opérationnel post-Jordan + bascule prélèvement automatique 350K€.
>
> **Variable canonique Alec** : (1) maximisation des résultats sur les ressources mobilisées + (3) réduction du délai d'attribution (matrice jurisprudence = délégation).

### KR 2.1 — Recouvrement opérationnel post-Jordan + bascule prélèvement automatique

**Cible J+17 (18 mai)** : Jordan opérationnel sur le recouvrement (reprise officielle après son retour). Cadrage rituel hebdo Boris↔Jordan installé.

**Cible J+45** : **30% des 2-3M€ d'impayés en cours de récupération active** (pipeline structuré, par cohorte, par produit Scaling/Accélérateur/Incubateur, suivi BigQuery).

**Cible J+60** : **bascule prélèvement automatique 350K€ effective** (cf. mandat Sabrina 28/4 — sortie de la dépendance manuelle).

**Cible J+90** : tendance d'encaissement Q1 vs Q4 2025 + ratio impayés/CA stable ou en baisse.

### KR 2.2 — Audit dépenses SaaS/IT — 70-100K€/an d'économies actées

**Cohérent avec mandat Alec vocal 29/4 + Slack 1er mai (IT pas besoin Manager dédié = pilotage Boris)**.

**Composantes chiffrées** (cible cumulée 70-100K€/an) :
- HubSpot, Zendesk, Aircall : négociation → 30K€/an min
- ~~Fin Mohamed IT au 31 mai : 24K€/an (2K€/mois)~~ → **CADUC (MAJ 28/5)** : Mohamed maintenu (charge cybersec). Économie à compenser ailleurs.
- NAS physique 1K€ → économie Google ~20K€/an
- Suppression Klap (à câbler avec Quentin) : montant à confirmer
- Petites licences (Typeform, Monday) : ~5K€/an cumulé

**Cible J+30 (31 mai)** : audit complet réalisé + 3 plus gros tickets négociés + décision Mohamed IT + NAS physique déployé. **Reporting consolidé pour annonce au meeting mensuel 1er juin** (cohabite avec annonce co-COO).

**Cible J+45** : économies effectivement actées (factures réduites visibles).

**Cible J+90** : audit dépenses 2025 ≥ 50K€ étendu (van 120K€, bureaux Dubai 250-400K€, Tang/Scale, etc.) + plan d'action proposé à Alec/Fabrice.

### KR 2.3 — Matrice jurisprudence financière déployée et opérationnelle

**Cohérent HO38 — proxy parfait HO8 (décision distribuée)**. Aujourd'hui chaque ticket finance (remboursement, sortie anticipée, échéancier, mise en demeure) remonte à Fabrice. Cible : que Sabrina/CFO puissent traiter en autonomie.

**Cible J+21 (21 mai)** : premier point d'avancement avec Fabrice. Si non-démarré → Boris propose co-construction (cf. [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] HO38).

**Cible J+45 (15 juin)** : matrice opérationnelle déployée pour Sabrina + CFO (entrée 18 mai). Au moins 5 cas types traités sans remontée Fabrice.

**Cible J+90** : 80% des cas finance traités au niveau opérationnel (Sabrina/CFO) sans remontée Fabrice.

---

## 🎯 Objectif 3 — Refondre la verticale Data/IA/Tech/Ops avec ROI mesurable (échéance dure 1er août)

> **Pourquoi** : mandat Alec officialisé Slack 1er mai SOIR (cf. [[Ressource - Slack Alec - Cadrage call Ops IT Tech Data IA 5 mai]]). 52K€/mois mobilisés sans ROI proportionnel. 6 problèmes data structurels identifiés (chiffres faux, sources non synchronisées, pas de granularité deals perdus, pas d'automation cycle de vie lead, Data Studio Marketing mal conçu, Atelier Dubaï à l'aveugle). Crise data systémique HO39 nouvelle hypothèse.
>
> **Cible J+90 (1er août — ÉCHÉANCE DURE Alec)** : nouveau modèle Data/IA/Tech/Ops effectif. Source unique de vérité (HubSpot) avec dashboards fiables. Automation cycle de vie lead opérationnelle. Stack équipe verticale refondue.
>
> **Mandat tripartite officialisé** : Fabrice responsable verticale + Anisse consolidation ressources + Boris challenge / regard neuf / exigence sur les choix structurants.
>
> **Variables canoniques Alec** : (1) maximisation résultats/ressources + (3) délai d'attribution + (4) revenu par lead. **Touche les 3 sur 4**.

### KR 3.1 — Source unique de vérité HubSpot + dashboards fiables (priorité 1 du Slack 1er mai)

**Workshop spec data 5-6 mai** (Boris+Fabrice+Anisse+Aziz) — cartographie sources actuelles + identification source de vérité par KPI.

**Cible J+10 (10 mai)** : cartographie sources existantes (HubSpot, Looker, Data Studio, COMEX, Aircall) + plan d'action priorisé.

**Cible J+30 (31 mai)** : source unique de vérité (HubSpot) déclarée + dashboards Looker/Data Studio reconstitués sur cette source + chiffres exacts au jour près au COMEX.

**Cible J+45** : Data Studio Marketing repensé avec vraie logique pilotage marketing (CPL, CPA, ROAS, panier moyen, délai d'attribution, revenu par lead par funnel).

**Cible J+60** : segmentation 3 niveaux deals perdus (rouge/jaune/vert) opérationnelle avec analyse réactivation + identification top performers.

### KR 3.2 — Automation cycle de vie lead opérationnelle (problème #4 Slack)

**Cas applicatif concret** : aujourd'hui un membre de l'équipe fait les réaffectations clients à la main tous les jours, week-ends et vacances inclus. **Quick win Anisse** = casser ce pattern.

**Cible J+14 (14 mai)** : automation réaffectations clients prototypée par Anisse + déployée. Cas applicatif HO39 résolu.

**Cible J+30** : verdict de faisabilité d'Anisse sur l'automation pipeline complet HubSpot (détection fin de call → bascule auto R1/R2/disqualifié sans saisie commerciale).

**Cible J+60** : automation pipeline déployée (si verdict positif) + blocage Aircall ↔ HubSpot débloqué + boucle data → feedback marketing fonctionnelle (cas Atelier Dubaï résolu).

**Cible J+90** : taux de RDV requalifiés automatiquement vs manuellement > 70%.

### KR 3.3 — Stack équipe verticale refondue avant 1er août

> 🔴 **MAJ 28/5** : le sourcing/recrutement ENT passe désormais par **Aikho** (et non Mithril, mis en pause). Lire "Aikho" partout où figure "Mithril/Aiko" ci-dessous. Cf. MUTATION C en tête.

**Cohérent mandat Mithril/Aiko 29/4 PM + workshop COMEX 6/7/8 mai vitrine**.

**Composantes** :
- **2 Ops** distincts à terme — 1 Ops Marketing (recrutement immédiat sous Cédric, déjà cadré 29/4) + 1 Ops Entreprise (offshore via Mithril/Aiko, intégré équipe Automation IA Anisse)
- **1-2 profils IA type Naïma** (sourcés via Mithril/Aiko)
- **1 PM IA** (Anisse mandaté, priorité haute)
- **Audit IT consolidé** (Boris owner permanent post-31 mai, fin Mohamed)
- **Transition CTO/Plateforme** : CTO salarié Dubaï (30K AED ≈ 7-8K€) + équipe dev (≈12K€) — actuel 20K€/mois à internaliser
- **Décision Thomas Baumelin** (Data, 5K€/mois — *"avec Thomas ou sans"* — à creuser)

**Cible J+30** : audit IT consolidé livré (31 mai) + Boris owner permanent IT/cybersec + sourcing Mithril/Aiko démarré + workshop COMEX réalisé (6/7/8 mai).

**Cible J+60 (30 juin)** : 2 Ops + 1 PM IA + 1-2 profils IA recrutés. Décision Thomas Baumelin actée. CTO Dubaï identifié, démarrage transition.

**Cible J+90 (1er août — ÉCHÉANCE DURE)** : nouveau modèle Data/IA/Tech/Ops effectif. **52K€/mois ramené à un coût justifié + ROI mesurable sur les 4 variables canoniques Alec.**

---

## 🎯 Objectif 4 — Sécuriser la transition top management (Axel sortant + Sophia entrante + co-COO 1er juin)

> **Pourquoi** : 5e+ mouvement top en 22 mois (HO26) + Axel part début juin + Sophia arrive juillet + annonce co-COO Boris/Fabrice 1er juin + transition Fabrice GM Dubai à préparer + risque résilience marketing si turnover S2 (formulé sans nommer pour préserver la confidentialité absolue).
>
> **Cible J+90** : aucune discontinuité client/opérationnelle majeure post-Axel. Scope Sophia/Boris/Fabrice clarifié. Top management resserré + dette de confiance en résorption mesurable.
>
> **Variable canonique Alec** : (1) maximisation résultats sur les ressources mobilisées (top management = ressource humaine la plus chère).

### KR 4.1 — Plan de passation Axel + 0 deal >20K€ perdu pour cause de passation

**Cible J+14 (14 mai)** : plan de passation Axel formalisé par écrit. Transmissions prévues vers Aziz (commercial), Sabrina (produit), Cédric (marketing), Océane (BRO). Validé par Axel + Fabrice + Boris.

**Cible J+45 (15 juin, 15 jours après départ Axel)** : aucun deal client actif > 20K€ perdu spécifiquement pour cause de passation mal gérée. Mesure : suivi pipeline par Aziz.

**Cible J+90** : pipeline post-Axel stable, équipe sales sans rupture de capacité.

### KR 4.2 — ~~Scope écrit Sophia ↔ Boris ↔ Fabrice clarifié et signé avant arrivée~~ — 🔴 SUPPRIMÉ (MAJ 28/5)

> **KR caduc** : Sophia a décliné la mission (cf. [[Sophia]] + MUTATION A en tête). Plus de scope quatuor à signer. Contenu conservé ci-dessous pour historique uniquement.

**Cible J+30 (31 mai)** : premier brief Boris↔Sophia (en amont de son arrivée) + cadrage scope préliminaire avec Alec.

**Cible J+60 (30 juin, avant signature définitive)** : **scope écrit Sophia ↔ Boris ↔ Fabrice signé en quatuor** (Alec + Sophia + Boris + Fabrice). Document inclut : périmètre Sophia, articulation avec Boris, articulation avec Fabrice (post-annonce 1er juin), zones d'overlap explicitement adressées.

**Cible J+90** : Sophia onboardée sans friction Boris/Fabrice. Scope tient.

### KR 4.3 — Résilience marketing Q2-Q3 cadrée (formulé générique — ne pas nommer en séance)

**⚠️ Note de discrétion** : ce KR adresse **HO32 (départ Cédric Q2-Q3 — confidentiel)** sans verbaliser le risque. Formulation cadre comme "résilience marketing générique" — peut servir même si Cédric reste.

**Cible J+30 (31 mai)** : cartographie de la résilience marketing validée Alec + Boris :
- Qui intérime sur les 6 chantiers clés du marketing en cas de turnover ?
- Délai réaliste de recrutement remplacement si nécessaire
- Plan de continuité des 3 recrutements en cours (DataOps + responsable webinaire + intégrateur, via Mithril)
- Cadrage du retour Amine Achour si confirmé (% temps, durée, scope)

**Cible J+45** : **checklist + contrôle qualité co-portée Boris + Anisse** sur les top 5 risques marketing déployée (cf. proposition Anisse 26/4 — *"on met 400K€ pour Tapie et il y a eu des choses qui auraient pu être évitées juste avec une checklist"*). Bonus : si turnover marketing S2-S3, ces checklists deviennent garantie de continuité minimum.

**Cible J+90** : équipe marketing élargie (3 recrutements) + checklists actives + résilience opérationnelle confirmée.

---

## 📊 Cadence de revue

| Date | Format | Participants | Durée | Output |
|---|---|---|---|---|
| **Weekly (jeudi)** | Stand-up ops | Boris + Fabrice | 30 min | État des KR en cours, arbitrages opérationnels |
| **J+30 (31 mai)** | Revue mi-parcours | Alec + Fabrice + Boris | 60 min | Statut chaque KR + ajustements + reporting audit IT |
| **J+60 (30 juin)** | Revue intermédiaire + cadrage Sophia | Alec + Fabrice + Boris (+ Sophia si arrivée) | 90 min | Go/no-go Q2, intégration Sophia, scope signé |
| **J+90 (31 juillet)** | Bilan Q1 + définition Q2 | Alec + Fabrice + Boris | 120 min | Plan trimestriel Q2 + revue DR Operating Partner |

---

## ⚖️ Questions à poser explicitement en séance

1. **"Est-ce que ces 4 objectifs couvrent bien les priorités que vous voyez pour moi sur ce trimestre ?"** — Alec et Fabrice peuvent me dire qu'il manque quelque chose d'essentiel.
2. **"Y a-t-il un objectif que vous voudriez enlever ou remplacer ?"** — je ne m'accroche à aucun des 4.
3. **"Sur l'Objectif 3 (verticale Data/IA/Tech/Ops), est-ce que la formulation correspond bien à ce qu'on a posé hier dans le Slack ?"** — articulation avec mandat Fabrice + Anisse à valider.
4. **"Les 4 variables canoniques d'Alec sont-elles bien le bon cadre de mesure transverse ?"** — cohérence narrative.
5. **"Sur la cadence de revue (weekly + J+30/J+60/J+90), Alec es-tu OK avec le format ?"** — dépendance Alec.
6. **"Qui est sponsor sur quoi ?"** — Boris pilote tout, mais Fabrice sponsor sur O1 + O3 (verticale = sa responsabilité), Alec sponsor sur O2 + O4.
7. **"La règle des boucles fermées — vous êtes OK pour qu'on s'engage là-dessus collectivement ?"** — c'est probablement le plus important du trimestre.

---

## 🚫 Pièges à éviter en séance

| Piège | Antidote |
|---|---|
| ❌ Dire "OKR" en séance | Vocabulaire : "plan trimestriel", "engagements", "objectifs et résultats clés" |
| ❌ Arriver en mode "voilà mes OKR validez" | Cadrage explicite : *"C'est un draft, rien n'est figé, optimisons ensemble"* |
| ❌ Laisser Alec improviser 5 objectifs de plus | Rappeler le principe des 4 objectifs max + règle boucles fermées |
| ❌ Faire émerger frontalement le sujet co-COO 1er juin | Sujet hors-périmètre de la séance — annonce du 1er juin |
| ❌ Mentionner les verbatims Cédric (replay 30/4) | Confidentialité absolue — KR4.3 formulé "résilience marketing" générique |
| ❌ Mentionner les verbatims Alec sur Fabrice (J0 matin) | Confidentialité absolue — Fabrice ne sait pas |
| ❌ Mentionner l'augmentation chiffrée Abdel (8K€) | Confidentialité — sujet entre Alec et Fabrice |
| ❌ Tirer la couverture sur les 3 leviers Fabrice | Présenter en co-construction (top 10 process + audit IT + matrice jurisprudence) |
| ❌ Sur-promettre sur les KR pour faire plaisir à Alec | Tenir l'ambition réaliste — Boris porte la délivrabilité |
| ❌ Oublier d'aligner sur les 4 variables canoniques | Le cadre de pilotage doit apparaître explicitement en ouverture |
| ❌ Sortir sans accountability claire | Finir par synthèse écrite partagée dans 24h + créneaux J+30/J+60/J+90 bloqués |

---

## 📝 Post-call (dans les 24h)

1. **Écrire la version finale V2** du plan trimestriel avec modifications actées en séance
2. **Partager en trio** pour confirmation écrite (mail court + lien doc partagé)
3. **Archiver dans le vault** — fichier de suivi hebdo créé
4. **Bloquer les créneaux** J+30 (31 mai), J+60 (30 juin), J+90 (31 juillet) dans les calendriers Alec + Fabrice + Boris
5. **Communiquer aux heads concernés** chacun sur leur scope respectif (Aziz / Sabrina / Cédric / Anisse / Océane / Fabrice) — pas le document complet, des extraits ciblés

---

## 🔗 Cohérence narrative — articulation avec les mandats déjà actés

| Mandat antérieur | Date | Intégré dans |
|---|---|---|
| **Charte Boris↔Fabrice spec/architecte** | Replay 28/4 | Posture transverse — explicite en intro |
| **Cordon sanitaire HO29** | Call J0 matin | KR 1.1 |
| **Top 10 process / décharge Fabrice** | Replays 27/4 + 28/4 + Boris↔Fabrice | KR 1.2 |
| **Cadence transverse + COMEX refondu** | Replay 28/4 + retours middle | KR 1.3 |
| **Recouvrement Jordan post-18 mai** | Replays 27/4 + 28/4 | KR 2.1 |
| **Audit dépenses SaaS 70-100K€/an** | Replay Alec↔Fabrice 27/4 + vocal Alec 29/4 | KR 2.2 |
| **Matrice jurisprudence financière (HO38)** | Replay Sabrina 28/4 + Boris↔Fabrice 28/4 | KR 2.3 |
| **Mandat verticale Data/IA/Tech/Ops** | Slack tripartite 1er mai SOIR | **Objectif 3 entier** |
| **Source unique HubSpot + dashboards fiables** | Slack 1er mai (problèmes #1-#2) | KR 3.1 |
| **Automation cycle de vie lead** | Slack 1er mai (problème #4) + replay 28/4 (Aziz) + replay Abdel 30/4 (cas réaffectations) | KR 3.2 |
| **2 Ops + Mithril/Aiko vitrine** | Call Recrutement Ops 29/4 PM + Slack 1er mai | KR 3.3 |
| **Audit IT mai 2026 (Boris owner permanent post-31 mai)** | Vocal Alec 29/4 + Slack 1er mai | KR 3.3 |
| **CTO Dubaï + équipe dev** | Vocal 25/4 + Slack 1er mai | KR 3.3 |
| **Extension équipe Automation IA Anisse** | Call 29/4 PM + Slack 1er mai | KR 3.3 |
| **Plan passation Axel (départ juin)** | Replays 23/4 + 24/4 (Axel) | KR 4.1 |
| **Scope Sophia clarifié** | Cadrage 23/4 (Alec) | KR 4.2 |
| **Plan rétention/délestage Cédric (10-15h/sem) — confidentiel** | Replay 1-to-1 Cédric 30/4 PM | Absorbé silencieusement par KR 4.3 + KR 3.3 (3 recrutements via Mithril) |
| **HO34 Abdel actionnable (Dubaï + augmentation + scope ETI) — confidentiel** | Call J0 matin + replay Alec×Abdel 30/4 | Absorbé silencieusement par KR 3.2 (automation réaffectations) + KR 3.3 (cadre management Anisse manager officiel à acter) |

→ **Tous les mandats convergent**. Le plan trimestriel n'invente rien — il **structure et coordonne** ce qui a déjà été décidé sur les 8 derniers jours.

---

## 🔗 Notes liées

- [[Draft OKR Q1 Boris]] — version historique pré-J0 (gardée comme référence évolutive)
- [[Prep - Call OKR trio 1er mai]] — préparation tactique du call 16h FR
- [[Ressource - Slack Alec - Cadrage call Ops IT Tech Data IA 5 mai]] — origine mandat verticale + 4 variables canoniques
- [[Ressource - Nœuds opérationnels Alec 1er mai 2026]] — call J0 matin (cordon sanitaire + dette de confiance)
- [[Ressource - Replay Alec × Abdel 30 avril 2026]] — cas réaffectations + 4 dimensions HO34
- [[Ressource - Replay 1-to-1 Cédric 30 avril 2026]] — plan délestage 10-15h/sem (confidentiel)
- [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]] — Boris owner permanent IT post-mai
- [[Ressource - Replay Recrutement Ops Marketing 29 avril 2026]] — Mithril/Aiko + workshop COMEX 6/7/8 mai
- [[Ressource - Replay Boris Fabrice 28 avril 2026]] — posture spec/architecte
- [[Ressource - Replay Alec Fabrice 27 avril 2026]] — co-COO acté en privé
- [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] — toutes les HO référencées
- [[Cadre - Dette de confiance]] — grammaire commune Alec/Boris
- [[Charte de fonctionnement Boris ↔ Fabrice — V1 (à envoyer)]] — base posture spec/architecte
- [[2026-04-30 - Operating Partner chez Entrepreneurs.com]] — DR mère
- [[Règles d'engagement — Operating Partner Entrepreneurs.com]] — allocation 4,5j
