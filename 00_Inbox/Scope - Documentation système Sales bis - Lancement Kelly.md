---
type: scope
status: draft
date-created: 2026-05-10
owner: "[[Boris Arduy]]"
co-owners-pressentis: "[[Aziz Sfaihi]] (Head of Sales) + driver \u00e9quipes externes \u00e0 identifier"
target-folder-when-mature: "10_SOPs/Sales"
related-sops:
  - "[[People-RH - Process recrutement Aikho v1]]"
  - "[[People-RH - Onboarding-Offboarding collaborateurs]]"
tags: [sales, sales-bis, lancement-kelly, equipes-externes, documentation, post-event, scope, replication]
source: entrepreneurs-com
sensitivity: confidential
---

# Scope \u2014 Documentation syst\u00e8me Sales bis (Lancement Kelly)

> **Note d'origine (carnet 2026-05-10)** : *\"Documenter tout le syst\u00e8me Sales bis pour prochain lancement mais aussi pour l'am\u00e9liorer suite \u00e0 l'event.\"*
>
> **Pr\u00e9cision Boris** : c'est le **syst\u00e8me parall\u00e8le d\u00e9velopp\u00e9 pour les \u00e9quipes externes du lancement Kelly**.

## Pourquoi ce chantier existe

Le lancement Kelly a fait \u00e9merger une **architecture Sales parall\u00e8le** d\u00e9di\u00e9e \u00e0 des \u00e9quipes externes \u2014 distincte de la machine sales standard d'Entrepreneurs.com. Ce syst\u00e8me a \u00e9t\u00e9 con\u00e7u dans l'urgence du lancement, fonctionne, mais n'est **pas document\u00e9**.

Trois cons\u00e9quences \u00e0 ne pas laisser durer :

1. **Risque de single point of failure** : la connaissance op\u00e9rationnelle vit dans la t\u00eate des op\u00e9rateurs du lancement. Si l'un d'eux part / change de scope / tombe malade, le syst\u00e8me devient un trou noir.
2. **Impossible \u00e0 r\u00e9pliquer pour le prochain lancement** : sans doc, chaque nouveau lancement r\u00e9invente la roue \u2014 surco\u00fbt \u00e9norme et qualit\u00e9 d'ex\u00e9cution erratique.
3. **Impossible \u00e0 am\u00e9liorer m\u00e9thodiquement** : les apprentissages post-event Kelly doivent atterrir quelque part pour devenir des \u00e9volutions concr\u00e8tes du syst\u00e8me. Sans doc de r\u00e9f\u00e9rence, les retex disparaissent.

\u2192 **Cible** : un SOP d\u00e9pos\u00e9 dans `10_SOPs/Sales/` (dossier vide aujourd'hui \u2014 ce serait le **premier SOP Sales** du vault) qui (a) capte le syst\u00e8me actuel tel qu'il a tourn\u00e9 sur Kelly, (b) int\u00e8gre les am\u00e9liorations post-event, (c) sert de base au prochain lancement.

## P\u00e9rim\u00e8tre

### IN SCOPE
- **Architecture du syst\u00e8me Sales bis** : qui fait quoi, quels outils, quels flux entre \u00e9quipes externes et machine interne EC
- **Onboarding des \u00e9quipes externes** : kit d'arriv\u00e9e, formation produit/script/objections, acc\u00e8s outils (cf. articulation [[Tech - Process cr\u00e9ation-transmission acc\u00e8s]])
- **Pilotage op\u00e9rationnel pendant un lancement** : cadence de meetings, KPIs suivis, escalades, rituels
- **Outillage** : HubSpot, Aircall, scripts, dashboards, automatismes
- **R\u00e9mun\u00e9ration / contractualisation \u00e9quipes externes** : structure de commission, modalit\u00e9s de paiement, contrat-type
- **Offboarding post-lancement** : cl\u00f4ture des acc\u00e8s, capitalisation des apprentissages, traitement des leads non finalis\u00e9s
- **Retex Kelly** : ce qui a march\u00e9, ce qui a frott\u00e9, ce qui doit changer

### OUT OF SCOPE (pour cette V1)
- La machine sales standard EC (interne, sans \u00e9quipes externes) \u2014 SOP \u00e0 part si besoin
- La strat\u00e9gie produit/marketing du lancement Kelly lui-m\u00eame
- L'analyse financi\u00e8re du lancement (CA, marge, ROI) \u2014 sujet finance s\u00e9par\u00e9

## Format de la doc cible

SOP au format standard Entrepreneurs.com (cf. `_Templates/SOP.md`) avec sections sp\u00e9cifiques :

1. **Pourquoi le syst\u00e8me Sales bis existe** \u2014 distinction avec la machine standard
2. **Architecture g\u00e9n\u00e9rale** \u2014 sch\u00e9ma des flux, r\u00f4les, responsabilit\u00e9s, outils
3. **Cycle de vie d'un lancement** : phases pr\u00e9-event / event / post-event avec livrables \u00e0 chaque \u00e9tape
4. **Onboarding des \u00e9quipes externes** \u2014 articul\u00e9 avec [[People-RH - Onboarding-Offboarding collaborateurs]] mais sp\u00e9cifique aux \u00e9quipes externes lancement
5. **Pilotage op\u00e9rationnel** \u2014 rituels, KPIs, escalades, dashboards
6. **Contractualisation et r\u00e9mun\u00e9ration** \u2014 structure, contrat-type, modalit\u00e9s
7. **Offboarding post-lancement** \u2014 articul\u00e9 avec SOP RH
8. **Pi\u00e8ges connus / retex** \u2014 section vivante mise \u00e0 jour apr\u00e8s chaque lancement
9. **Roadmap d'am\u00e9lioration** \u2014 bond accumulateur des chantiers identifi\u00e9s pour les prochains lancements

## M\u00e9thode d'ex\u00e9cution

### Phase 1 \u2014 Captation \u00e0 chaud du syst\u00e8me Kelly (S2-S3 mai)
- **Owner** : Boris (cadrage) + driver op\u00e9rationnel du lancement Kelly (\u00e0 identifier en S2)
- **Action** : entretien(s) structur\u00e9(s) avec les op\u00e9rateurs cl\u00e9s du lancement Kelly (interne + repr\u00e9sentant \u00e9quipe externe). Captation par Loom + transcription vers brouillon SOP.
- **Output** : brouillon V0 du SOP \u2014 inventaire factuel de \"comment \u00e7a a tourn\u00e9 sur Kelly\".

### Phase 2 \u2014 Retex post-event (S3-S4 mai)
- **Owner** : Boris + Aziz (Head of Sales) + driver \u00e9quipe externe
- **Action** : atelier retex 60-90 min en format start/stop/continue. \u00c0 caler tant que les apprentissages sont frais. Captation des frictions sp\u00e9cifiques \u00e9quipes externes vs internes.
- **Output** : liste priorit\u00e9 d'am\u00e9liorations \u00e0 int\u00e9grer dans la V1 + sujets \u00e0 traiter au prochain lancement uniquement.

### Phase 3 \u2014 R\u00e9daction V1 (juin)
- **Owner** : Boris (orchestration) + Aziz (validation contenu sales)
- **Action** : r\u00e9daction du SOP V1 sur la base brouillon V0 + retex Phase 2. Application du format SOP standard. Cross-r\u00e9f\u00e9rences avec SOP RH onboarding/offboarding et SOP Tech acc\u00e8s.
- **Output** : SOP V1 d\u00e9pos\u00e9 dans `10_SOPs/Sales/Sales - Syst\u00e8me Sales bis - Lancement \u00e9quipes externes.md` (statut active).

### Phase 4 \u2014 Test sur le prochain lancement
- **Owner** : driver du prochain lancement + Boris (sponsor) + Aziz (validation)
- **Action** : ex\u00e9cuter le SOP V1 tel quel sur le prochain lancement. Logger en temps r\u00e9el les \u00e9carts entre la doc et la r\u00e9alit\u00e9. Atelier retex \u00e0 chaud post-event.
- **Output** : SOP V2 enrichi des apprentissages + roadmap d'am\u00e9lioration consolid\u00e9e.

## Questions ouvertes / \u00e0 arbitrer

> Ces questions sont \u00e0 r\u00e9soudre avant de d\u00e9marrer la Phase 1. Boris \u00e0 cadrer avec Aziz et le driver op\u00e9rationnel Kelly.

1. **Driver op\u00e9rationnel Kelly** \u2014 qui est la r\u00e9f\u00e9rence interne \u00e0 d\u00e9briefer en priorit\u00e9 ? Aziz directement, ou y a-t-il un sales ops sp\u00e9cifique au lancement ?
2. **Repr\u00e9sentant \u00e9quipes externes** \u2014 qui c\u00f4t\u00e9 externe est le mieux plac\u00e9 pour donner le retex ? Un manager d'\u00e9quipe externe, un closer top performer ?
3. **Date de l'event Kelly** \u2014 quand exactement, pour situer la fra\u00eecheur des apprentissages et urgence de captation ?
4. **Date du prochain lancement pr\u00e9vu** \u2014 d\u00e9termine la deadline dure du SOP V1 (au plus tard J-30 du prochain lancement)
5. **Sensibilit\u00e9 contractuelle des \u00e9quipes externes** \u2014 le contrat-type doit-il rester confidentiel ou \u00eatre publi\u00e9 dans le SOP ?
6. **Articulation avec SOP recrutement Aikho** \u2014 les \u00e9quipes externes sont-elles recrut\u00e9es via Aikho ou via un autre canal (recrutement collectif, partenariat) ?
7. **Volet acc\u00e8s outils** \u2014 les \u00e9quipes externes ont-elles des acc\u00e8s @entrepreneurs.com ou un environnement isol\u00e9 ? Cohabitation avec [[Tech - Process cr\u00e9ation-transmission acc\u00e8s]] \u00e0 cadrer.

## Articulation avec les autres chantiers

- [[People-RH - Onboarding-Offboarding collaborateurs]] \u2014 le volet onboarding/offboarding des \u00e9quipes externes peut s'inspirer du SOP RH g\u00e9n\u00e9ral, avec adaptations sp\u00e9cifiques (dur\u00e9e courte, p\u00e9rim\u00e8tre acc\u00e8s restreint, contrat de mission)
- [[Tech - Process cr\u00e9ation-transmission acc\u00e8s]] \u2014 cas particulier \u00e0 prendre en compte (acc\u00e8s temporaires \u00e0 dur\u00e9e d\u00e9termin\u00e9e par lancement)
- [[People-RH - Process recrutement Aikho v1]] \u2014 si les \u00e9quipes externes sont recrut\u00e9es via Aikho, articulation \u00e0 documenter ; sinon, distinction \u00e0 expliciter
- [[Scope - Cartographie contrats prestataires Entrepreneurs.com]] \u2014 les contrats des \u00e9quipes externes alimentent la cartographie
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] \u2014 KR1.2 (top 10 process avec head owner identifi\u00e9, 5 d\u00e9ploy\u00e9s) : ce SOP est candidat naturel pour rejoindre le top 10
- [[Aziz Sfaihi]] \u2014 head owner cible

## Statut & prochaines \u00e9tapes

- **2026-05-10** \u2014 Cr\u00e9ation du scope (Boris, draft)
- **\u00c0 faire S2 mai** : r\u00e9pondre aux 7 questions ouvertes + identifier les bons interlocuteurs Phase 1
- **\u00c0 faire S2-S3 mai** : Phase 1 captation \u00e0 chaud
- **\u00c0 faire S3-S4 mai** : Phase 2 retex
- **\u00c0 faire en juin** : Phase 3 r\u00e9daction V1, basculement en `10_SOPs/Sales/`
- **Cible** : SOP V1 op\u00e9rationnel J-30 du prochain lancement, V2 enrichie post-prochain lancement

## Notes li\u00e9es

- [[Aziz Sfaihi]]
- [[People-RH - Onboarding-Offboarding collaborateurs]]
- [[Tech - Process cr\u00e9ation-transmission acc\u00e8s]]
- [[People-RH - Process recrutement Aikho v1]]
- [[Scope - Cartographie contrats prestataires Entrepreneurs.com]]
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]]
