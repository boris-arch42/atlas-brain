---
type: scope
status: draft
date-created: 2026-05-10
last-updated: 2026-05-11
owner: "[[Boris Arduy]]"
co-owners-pressentis: "[[Aziz Sfaihi]] (Head of Sales) + driver équipes externes à identifier"
target-folder-when-mature: "10_SOPs/Sales"
related-sops:
  - "[[People-RH - Process recrutement Aikho v1]]"
  - "[[People-RH - Onboarding-Offboarding collaborateurs]]"
tags: [sales, sales-bis, lancement-kelly, equipes-externes, documentation, post-event, scope, replication]
source: entrepreneurs-com
sensitivity: confidential
---

# Scope — Documentation système Sales Bis (Lancement Kelly)

> **MAJ 2026-05-11** — suite au weekly Fabrice × Alec du 11/5 :
> - 🔤 **Orthographe confirmée par Boris** : "Sales Bis" (capitales S et B). Le fichier a été renommé en conséquence.
> - 📊 **Chiffres confirmés** : 40 closers externes (Boris) / 42 sales déployés (Alec) — même ordre de grandeur
> - 💰 **Enjeu financier** : 1-2 millions à aller chercher
> - ⏱️ **Deadline opération en cours** : priorité jusqu'à dimanche 17 mai (verbatim Boris en call)
> - ⚖️ **Tension doctrinale assumée** : *"qui va un peu à l'encontre de tout ce qu'on s'est dit depuis le départ, à savoir alléger la structure. Mais bon, s'il y a 1 ou 2 millions à aller chercher, bon, on s'assiera un peu sur la doctrine pendant une petite semaine ou deux."*
> - ❓ **Question pivot non tranchée par Alec** : *"Est-ce que ça va se répéter ? Est-ce qu'on va refaire appel à des sales teams externes ou est-ce que c'est juste vraiment un test pour l'instant ?"* → réponse à cette question = pivot du SOP cible (one-shot test vs système réplicable). À trancher post-event Kelly.
> - 🔗 **Validation Alec en séance** : Boris a utilisé le système Sales Bis comme exemple concret du besoin RH Dubai (accès, licences, offboarding 40 closers) — Alec a entendu sans contester.
>
> Cf. [[Ressource - Replay Weekly Fabrice × Alec 11 mai 2026]] pour le contexte complet.

> **Note d'origine (carnet 2026-05-10)** : *"Documenter tout le système Sales bis pour prochain lancement mais aussi pour l'améliorer suite à l'event."*
>
> **Précision Boris** : c'est le **système parallèle développé pour les équipes externes du lancement Kelly**. ~40-42 closers externes mobilisés, enjeu 1-2M€.

## Pourquoi ce chantier existe

Le lancement Kelly a fait émerger une **architecture Sales parallèle** dédiée à des équipes externes — distincte de la machine sales standard d'Entrepreneurs.com. Ce système a été conçu dans l'urgence du lancement, fonctionne, mais n'est **pas documenté**.

Trois conséquences à ne pas laisser durer :

1. **Risque de single point of failure** : la connaissance opérationnelle vit dans la tête des opérateurs du lancement. Si l'un d'eux part / change de scope / tombe malade, le système devient un trou noir.
2. **Impossible à répliquer pour le prochain lancement** : sans doc, chaque nouveau lancement réinvente la roue — surcoût énorme et qualité d'exécution erratique.
3. **Impossible à améliorer méthodiquement** : les apprentissages post-event Kelly doivent atterrir quelque part pour devenir des évolutions concrètes du système. Sans doc de référence, les retex disparaissent.

→ **Cible** : un SOP déposé dans `10_SOPs/Sales/` (dossier vide aujourd'hui — ce serait le **premier SOP Sales** du vault) qui (a) capte le système actuel tel qu'il a tourné sur Kelly, (b) intègre les améliorations post-event, (c) sert de base au prochain lancement.

→ **Stratégie de pivot** : si la réponse à la question d'Alec (réitération vs test) penche vers "test ponctuel", le SOP devient une **note retex documentaire** (capitalisation des apprentissages sans cadre opérationnel à maintenir). Si la réponse penche vers "réplication", le SOP devient un **SOP actif** déclenché à chaque lancement, intégré au cycle de vie EC.

## Périmètre

### IN SCOPE
- **Architecture du système Sales Bis** : qui fait quoi, quels outils, quels flux entre équipes externes et machine interne EC
- **Onboarding des équipes externes** : kit d'arrivée, formation produit/script/objections, accès outils (cf. articulation [[Tech - Process création-transmission accès]])
- **Pilotage opérationnel pendant un lancement** : cadence de meetings, KPIs suivis, escalades, rituels
- **Outillage** : HubSpot, Aircall, scripts, dashboards, automatismes
- **Rémunération / contractualisation équipes externes** : structure de commission, modalités de paiement, contrat-type
- **Offboarding post-lancement** : clôture des accès, capitalisation des apprentissages, traitement des leads non finalisés
- **Retex Kelly** : ce qui a marché, ce qui a frotté, ce qui doit changer

### OUT OF SCOPE (pour cette V1)
- La machine sales standard EC (interne, sans équipes externes) — SOP à part si besoin
- La stratégie produit/marketing du lancement Kelly lui-même
- L'analyse financière du lancement (CA, marge, ROI) — sujet finance séparé

## Format de la doc cible

SOP au format standard Entrepreneurs.com (cf. `_Templates/SOP.md`) avec sections spécifiques :

1. **Pourquoi le système Sales Bis existe** — distinction avec la machine standard
2. **Architecture générale** — schéma des flux, rôles, responsabilités, outils
3. **Cycle de vie d'un lancement** : phases pré-event / event / post-event avec livrables à chaque étape
4. **Onboarding des équipes externes** — articulé avec [[People-RH - Onboarding-Offboarding collaborateurs]] mais spécifique aux équipes externes lancement
5. **Pilotage opérationnel** — rituels, KPIs, escalades, dashboards
6. **Contractualisation et rémunération** — structure, contrat-type, modalités
7. **Offboarding post-lancement** — articulé avec SOP RH
8. **Pièges connus / retex** — section vivante mise à jour après chaque lancement
9. **Roadmap d'amélioration** — accumulateur des chantiers identifiés pour les prochains lancements

## Méthode d'exécution

### Phase 1 — Captation à chaud du système Kelly (S2-S3 mai)
- **Owner** : Boris (cadrage) + driver opérationnel du lancement Kelly (à identifier en S2)
- **Action** : entretien(s) structuré(s) avec les opérateurs clés du lancement Kelly (interne + représentant équipe externe). Captation par Loom + transcription vers brouillon SOP.
- **Output** : brouillon V0 du SOP — inventaire factuel de "comment ça a tourné sur Kelly".
- **Deadline cible** : avant Marrakech 20-25/5 si possible, sinon glissement à fin mai.

### Phase 2 — Retex post-event (S3-S4 mai)
- **Owner** : Boris + Aziz (Head of Sales) + driver équipe externe
- **Action** : atelier retex 60-90 min en format start/stop/continue. À caler tant que les apprentissages sont frais. Captation des frictions spécifiques équipes externes vs internes.
- **Output** : liste priorité d'améliorations à intégrer dans la V1 + sujets à traiter au prochain lancement uniquement.

### Phase 3 — Rédaction V1 (juin)
- **Owner** : Boris (orchestration) + Aziz (validation contenu sales)
- **Action** : rédaction du SOP V1 sur la base brouillon V0 + retex Phase 2. Application du format SOP standard. Cross-références avec SOP RH onboarding/offboarding et SOP Tech accès.
- **Output** : SOP V1 déposé dans `10_SOPs/Sales/Sales - Système Sales Bis - Lancement équipes externes.md` (statut active) **OU** note retex documentaire selon la décision Alec sur la réitération.

### Phase 4 — Test sur le prochain lancement (si réitération validée)
- **Owner** : driver du prochain lancement + Boris (sponsor) + Aziz (validation)
- **Action** : exécuter le SOP V1 tel quel sur le prochain lancement. Logger en temps réel les écarts entre la doc et la réalité. Atelier retex à chaud post-event.
- **Output** : SOP V2 enrichi des apprentissages + roadmap d'amélioration consolidée.

## Questions ouvertes / à arbitrer

> Ces questions sont à résoudre avant de démarrer la Phase 1.

1. **Driver opérationnel Kelly** — qui est la référence interne à débriefer en priorité ? Aziz directement, ou y a-t-il un sales ops spécifique au lancement ? À trancher au call Aziz mardi.
2. **Représentant équipes externes** — qui côté externe est le mieux placé pour donner le retex ? Un manager d'équipe externe, un closer top performer ? À demander à Aziz.
3. **Date de l'event Kelly** — quand exactement, pour situer la fraîcheur des apprentissages et urgence de captation ? Priorité jusqu'à dimanche 17/5 = event en cours ou imminent.
4. **Date du prochain lancement prévu** — détermine la deadline dure du SOP V1 (au plus tard J-30 du prochain lancement). À demander à Alec/Aziz.
5. **Sensibilité contractuelle des équipes externes** — le contrat-type doit-il rester confidentiel ou être publié dans le SOP ?
6. **Articulation avec SOP recrutement Aikho** — les équipes externes sont-elles recrutées via Aikho ou via un autre canal (recrutement collectif, partenariat) ?
7. **Volet accès outils** — les équipes externes ont-elles des accès @entrepreneurs.com ou un environnement isolé ? Cohabitation avec [[Tech - Process création-transmission accès]] à cadrer.
8. **🆕 Question pivot Alec — réitération vs test ponctuel** — détermine si le SOP est actif ou documentaire. À trancher post-event avec Alec, probablement post-Marrakech.

## Articulation avec les autres chantiers

- [[People-RH - Onboarding-Offboarding collaborateurs]] — le volet onboarding/offboarding des équipes externes peut s'inspirer du SOP RH général, avec adaptations spécifiques (durée courte, périmètre accès restreint, contrat de mission)
- [[Tech - Process création-transmission accès]] — cas particulier à prendre en compte (accès temporaires à durée déterminée par lancement)
- [[People-RH - Process recrutement Aikho v1]] — si les équipes externes sont recrutées via Aikho, articulation à documenter ; sinon, distinction à expliciter
- [[Scope - Cartographie contrats prestataires Entrepreneurs.com]] — les contrats des équipes externes alimentent la cartographie
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] — KR1.2 (top 10 process avec head owner identifié, 5 déployés) : ce SOP est candidat naturel pour rejoindre le top 10
- [[Aziz Sfaihi]] — head owner cible
- [[Ressource - Replay Weekly Fabrice × Alec 11 mai 2026]] — cadrage et chiffres validés en weekly

## Statut & prochaines étapes

- **2026-05-10** — Création du scope (Boris, draft)
- **2026-05-11** — MAJ post-weekly Fabrice × Alec : orthographe "Sales Bis" confirmée, chiffres validés, enjeu 1-2M€ confirmé, question pivot réitération vs test ajoutée
- **À faire S2 mai** : répondre aux 8 questions ouvertes + identifier les bons interlocuteurs Phase 1 (call Aziz mardi)
- **À faire S2-S3 mai** : Phase 1 captation à chaud (Loom driver Kelly mercredi, représentant équipe externe jeudi/vendredi)
- **À faire S3-S4 mai** : Phase 2 retex (avant Marrakech si possible)
- **À faire en juin** : Phase 3 rédaction V1, basculement en `10_SOPs/Sales/` ou en note documentaire selon décision Alec
- **Cible** : SOP V1 opérationnel J-30 du prochain lancement (si réitération validée), V2 enrichie post-prochain lancement

## Notes liées

- [[Aziz Sfaihi]]
- [[People-RH - Onboarding-Offboarding collaborateurs]]
- [[Tech - Process création-transmission accès]]
- [[People-RH - Process recrutement Aikho v1]]
- [[Scope - Cartographie contrats prestataires Entrepreneurs.com]]
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]]
- [[Ressource - Replay Weekly Fabrice × Alec 11 mai 2026]]
