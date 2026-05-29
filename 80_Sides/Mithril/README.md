---
type: hub-side
status: actif-cas-client-interne
date-creation: 2026-04-29
sensitivity: confidential
tags: [side, mithril, aiko, recrutement, cas-client-entrepreneurs-com, produit-boris]
---

# 🪶 Mithril — Hub de capitalisation produit

> **🔴 MAJ 2026-05-28 — MITHRIL EN PAUSE + rôle ENT repris par Aikho**
>
> Boris met **Mithril en pause** pour **mieux réfléchir à la vision du projet** (repositionnement produit).
>
> Conséquence ENT : le **rôle de stack de recrutement de référence chez Entrepreneurs.com — que Mithril portait — est repris par [[Aikho]]** (solution jugée très intéressante, **discussions en cours** avec eux). C'est Aikho qui porte désormais le sourcing remplaçant Nicolas, dévs offshore, PMO local, futur CTO Dubai.
>
> ⚠️ Tout le contenu ci-dessous ("matérialisation publique Mithril", "cas client interne ENT", backlog d'apprentissages) décrit la phase **avril-mai où Mithril était le véhicule ENT**. Il est conservé comme historique mais **n'est plus le plan actif** tant que Mithril est en pause.

> ⚠️ **Note de positionnement** : Mithril n'est pas un "side project" classique \— c'est l'**entreprise principale de Boris** (SaaS recrutement, cf. [[userMemories]]). Cette fiche est plac\u00e9e dans `80_Sides/` \u00e0 titre **op\u00e9rationnel** : capter les apprentissages produit issus du d\u00e9ploiement chez Entrepreneurs.com, sans m\u00e9langer le pilotage Mithril (qui se fait ailleurs, notamment sur Notion Mithril) avec le pilotage Operating Partner ENT.
>
> **Ce que ce hub fait** : capter feedback, frictions, features manquantes, insights produit issus du d\u00e9ploiement ENT.
> **Ce que ce hub ne fait pas** : g\u00e9rer la roadmap globale Mithril, le pilotage \u00e9quipe Mithril (Venu, Aman), les sprints Linear, le GTM Facebook, etc.

## ⚡ Statut au 5/5 — matérialisation publique en réunion verticale

> Cf. [[Ressource - Replay Ops IT Tech Data IA 5 mai 2026]] (call 11h33-12h19, Alec + Fabrice + Anisse + Boris).

- **🟢 1ère matérialisation publique de Mithril** comme outil de recrutement de référence ENT. Verbatim Alec 31:24 (devant Fabrice + Anisse) : *"Cédric t'a envoyé la fiche de poste Boris pour Mithril pour déjà commencer à faire tourner ?"*
- **🟢 Cas Nicolas = premier projet client documenté Mithril × ENT**. Cédric a transmis la fiche de poste DataOps marketing **avant** le call du 5/5 — 5 jours d'avance sur le calendrier 30/4.
- **🟢 Cible profil consolidée en séance** : automation maîtrisée (Twilio, Mailchimp, Zapier, lancements), accepter horaires nocturnes/weekend, offshore Maroc, cible coût ~50% Nicolas. Verbatim Anisse 27:47 *"On peut aller chercher comme ils recrutent, Hamid ou d'autres agences au Maroc qui font de l'automatisation."*
- **🟢 Mandat élargi confirmé** : Mithril sourcing pour la transition Quentin (1 lead + 2 dévs offshore plateforme), PMO local (1 200-1 500€/mois francophone), futur CTO Dubaï (horizon Q3-Q4). **3 à 4 mandats clients ENT en parallèle sur 90 jours**.
- **🟠 Risque capacité à anticiper** : si 3-4 sourcings ENT lancés simultanément, charge cumulée potentielle ~2-3 j/sem côté Boris si Mithril (Venu/Aman) n'absorbe pas la charge opérationnelle. À cadrer en bilatéral Mithril cette semaine.

## ⚡ Statut au 29/4

- **Bascule majeure 29/4** : Alec acte le d\u00e9ploiement Mithril/Aiko comme stack de **r\u00e9f\u00e9rence pour TOUS les recrutements** d'Entrepreneurs.com (coachs, sales, RH, partenaires annuaire, marketing). Cf. [[Ressource - Replay Recrutement Ops Marketing 29 avril 2026]].
- **Workshop COMEX 6/7/8 mai** : pr\u00e9sentation officielle 1h avec Aziz + Claire + Fabrice + Oc\u00e9ane + Sabrina(replay) \u2014 **vitrine massive Mithril** + cas client de r\u00e9f\u00e9rence interne.
- **Coh\u00e9rence audit IT mai 2026** : Aiko (200\u20ac/mois) remplace un talent acquisition manager (cf. [[Mohamed]]) \u2014 levier d'\u00e9conomies structurelles. Stack Mithril/Aiko devient un **outil mentionnable** dans le narratif audit SaaS.

## 🎯 Pourquoi capter ces apprentissages dans le vault Atlas-Brain

Le d\u00e9ploiement Mithril/Aiko chez Entrepreneurs.com est un **cas client de r\u00e9f\u00e9rence interne** unique :
- Volume r\u00e9el de recrutements (3 briques marketing en 30-45j + coachs + sales + partenaires + RH)
- Multi-utilisateurs (C\u00e9dric, Aziz, Claire, Anisse, Fabrice, Oc\u00e9ane)
- Cas vari\u00e9s (offshore Maroc/Madagascar + remote francophone + experts senior)
- Feedback structur\u00e9 possible apr\u00e8s 30-60j d'usage \u2014 \u00e0 chaud, en interne, sans biais commercial

\u2192 **Insights captur\u00e9s ici remontent ensuite dans Notion Mithril / Linear** pour la roadmap produit. Ce hub est un **pipe de capture**, pas un syst\u00e8me de gestion.

## 📋 Backlog d'apprentissages \u00e0 capter

### \u00c0 capter pendant le d\u00e9ploiement (S1-S4 mai)

| # | Sujet | Source | Statut |
|---|---|---|---|
| 1 | **Limite Aiko 600-800 candidats/mois sur licence 200\u20ac** \u2014 alerte volum\u00e9trique automatique manquante ? Possibilit\u00e9 d'optimisation ? | Boris au call 29/4 | \u00c0 observer |
| 2 | **Workflow Upwork \u2192 contrat ensuite** (logique Anisse) \u2014 \u00e0 cr\u00e9er nativement dans Mithril ? | Anisse au call 29/4 | Feature potentielle |
| 3 | **Connexion native vs lien manuel par job board** \u2014 inventaire des plateformes manquantes pour le march\u00e9 francophone (Join, Welcome to the Jungle, etc.) | Anisse au call 29/4 | \u00c0 cartographier |
| 4 | **Score CV vs questionnaire orient\u00e9** \u2014 question C\u00e9dric : *\"Le score CV t'inclut aussi le petit questionnaire pour postuler ?\"* \u2192 transparence du scoring \u00e0 am\u00e9liorer ? | C\u00e9dric au call 29/4 | UX produit |
| 5 | **Fraud score** : feedback usage r\u00e9el sur recrutements offshore Maroc/Madagascar \u2014 d\u00e9tecte-t-il bien les usages IA des candidats ? Faux positifs ? | \u00c0 mesurer S2-S4 | Validation produit |
| 6 | **Adaptive vs trame logique Aiko** \u2014 r\u00e9action des candidats au call IA adaptatif. Taux de compl\u00e9tion ? Drop-off ? | \u00c0 mesurer S2-S4 | Validation produit |
| 7 | **Email IA personnalis\u00e9 pour booking** \u2014 taux de booking effectif post-email ? | \u00c0 mesurer S2-S4 | Conversion |
| 8 | **Sync calendrier** \u2014 friction lors du 1er usage par C\u00e9dric/Aziz/Claire ? Calendriers Google vs Outlook ? | \u00c0 observer | UX produit |

### \u00c0 capter au workshop COMEX 6/7/8 mai

| # | Sujet | Comment capter |
|---|---|---|
| 9 | **R\u00e9ticences expr\u00e9s-cit\u00e9es** par les heads (Aziz, Claire, Fabrice, Oc\u00e9ane) | Noter en direct + d\u00e9brief post-workshop |
| 10 | **Questions r\u00e9currentes** pos\u00e9es par les heads (probable : adaptive, fraud, biais) | Noter en direct \u2014 indicateur des points \u00e0 clarifier dans onboarding utilisateur |
| 11 | **Friction d\u00e9couverte de l'interface** lors de la d\u00e9mo en direct | Observation Boris pendant la cr\u00e9ation de l'annonce |
| 12 | **Quick wins demand\u00e9s** \u2014 features que les heads voudraient imm\u00e9diatement | Liste \u00e0 ramener en backlog Linear Mithril |

### \u00c0 capter via t\u00e9moignage David Toba (call planifi\u00e9 dans les prochains jours)

David Toba = utilisateur Aiko exp\u00e9riment\u00e9. Boris a pr\u00e9vu un call pour b\u00e9n\u00e9ficier de son retour d'exp\u00e9rience. \u00c0 capter :
- Pi\u00e8ges identifi\u00e9s \u00e0 \u00e9viter
- Workflows qu'il a optimis\u00e9s
- Limites rencontr\u00e9es
- Features qu'il aimerait voir

## 🔄 Workflow de capture

```
Friction / insight observ\u00e9 sur le terrain ENT
  \u2193
Capture rapide dans ce hub (section Backlog)
  \u2193 (chaque vendredi)
Tri + qualification : bug / feature / UX / GTM
  \u2193
Remont\u00e9e structur\u00e9e dans Notion Mithril ou Linear Mithril
  \u2193
Discussion avec Venu / Aman pour priorisation roadmap
```

## ⚠️ Ce que le hub ne fait PAS

- \u274c Pilotage roadmap Mithril (\u2192 Notion Mithril)
- \u274c Gestion sprints Linear (\u2192 Linear Mithril)
- \u274c Comm\u00e9rcial / GTM Facebook (\u2192 sous-dossiers Mithril ailleurs)
- \u274c Pilotage \u00e9quipe Venu/Aman (\u2192 1-to-1 Mithril)
- \u274c Synchronisation avec MTS / Riven Agency (\u2192 hubs respectifs)

## 🚧 Risques de m\u00e9lange ENT \u2194 Mithril \u00e0 surveiller

### Risque 1 \u2014 Conflit d'int\u00e9r\u00eat per\u00e7u

ENT devient un client b\u00e9ta de Mithril. Si quelqu'un (Sophia entrante, futur investisseur Mithril, futur client Mithril) per\u00e7oit ce d\u00e9ploiement comme un avantage indu pour Mithril, friction politique possible.

**Mitigation** :
- D\u00e9ploiement \u00e0 prix march\u00e9 (Aiko 200\u20ac/mois \u00e9quivaut au tarif standard)
- Pas de fonctionnalit\u00e9s exclusives ENT non disponibles dans Mithril public
- Documentation transparente du d\u00e9ploiement \u2014 auditable

### Risque 2 \u2014 Capture excessive de bande passante Boris

Si le d\u00e9ploiement ENT capture >1j/sem de Boris sur des sujets purement produit Mithril, **conflit avec mandat Operating Partner**.

**Mitigation** :
- Le d\u00e9ploiement op\u00e9rationnel chez ENT = mandat Operating Partner (mais pas plus de 1j/sem)
- Les am\u00e9liorations produit issues du feedback ENT = capacit\u00e9 Mithril (Venu / Aman)
- Si une feature ENT-sp\u00e9cifique n\u00e9cessite >1j Boris : escalade \u00e0 Alec, ou r\u00e9solution alternative

### Risque 3 \u2014 Asym\u00e9trie de feedback

Les heads ENT donnent du feedback \u00e0 Boris (qui est leur Co-COO), pas neutre. Risque de feedback complaisant.

**Mitigation** :
- Forcer la capture de **frictions** au moins autant que de **wins** dans le hub
- Cross-checker avec David Toba (utilisateur externe non li\u00e9)
- Ne pas conclure \u00e0 la qualit\u00e9 produit sur le seul d\u00e9ploiement ENT

## 📅 Jalons cl\u00e9s

| Date | Jalon | Capture associ\u00e9e |
|---|---|---|
| 29/4 | Mandat Alec d\u00e9ploiement Mithril | Cf. [[Ressource - Replay Recrutement Ops Marketing 29 avril 2026]] |
| 30/4 | Lancement annonces (DataOps, Naïma, CM possible) | First-touch Mithril/Aiko by ENT |
| 4 mai | **Pr\u00e9sentation Mithril Core Meeting** (J+3) | Premi\u00e8re pr\u00e9sentation produit en interne ENT \u2014 noter r\u00e9actions COMEX |
| 5 mai | Sujet "Ops toute entreprise" \u00e9quipe Anisse \u00e0 cadrer | Cas d'usage suppl\u00e9mentaire potentiel Mithril |
| 6/7/8 mai | **Workshop COMEX 1h** \u2014 cr\u00e9ation recrutement en direct | \ud83d\udd34 Capture exhaustive r\u00e9actions/frictions \u2014 cf. backlog #9-12 |
| Avant 5 mai | Call David Toba | Capture retour exp\u00e9rience externe Aiko |
| 31 mai | Fin mois 1 d\u00e9ploiement \u2014 first review | Synth\u00e8se backlog \u2192 priorisation Mithril roadmap |

## 🔗 Notes li\u00e9es

- [[Ressource - Replay Recrutement Ops Marketing 29 avril 2026]] (mandat 29/4)
- [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]] (coh\u00e9rence audit IT)
- [[Ressource - Replay Alec Fabrice 27 avril 2026]] (premi\u00e8re mention Mithril Core 4 mai)
- [[Alec Henry]] (sponsor du d\u00e9ploiement)
- [[C\u00e9dric De Saint Jean]] (1er utilisateur intensif \u2014 3 briques recrutement)
- [[Anisse Rbibe]] (utilisateur engag\u00e9 \u2014 \u00e9quipe Na\u00efma + Ops "toute entreprise")
- [[Mohamed]] (audit IT mai \u2014 coh\u00e9rence \u00e9conomies SaaS)
- [[Prep - Call Alec 1er mai - Cartographie noeuds operationnels]] (sujets M1-M2-M3 du 29/4 PM)
- [[80_Sides/Index - Sides|Index Sides]]
- [[80_Sides/Conform\u00e9 TPE-PME/README|Conformit\u00e9 TPE-PME]] (autre side actif)
