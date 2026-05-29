---
type: scope
status: draft
date-created: 2026-05-10
owner: "[[Boris Arduy]]"
co-owner: "[[Fabrice Jaeger]]"
target-owner: "[[Jordan]]"
related-sops:
  - "[[People-RH - Onboarding-Offboarding collaborateurs]]"
related-frameworks:
  - "[[Cadre - Process IT-SaaS-Cybersec]]"
tags: [contrats, prestataires, cartographie, finance, gouvernance, scope, audit, cas-maj-confidentiel]
source: entrepreneurs-com
sensitivity: confidential-max
---

# Scope — Cartographie contrats prestataires Entrepreneurs.com

> **🟢 MAJ 2026-05-28 — Phase 1 (recensement) FAITE → passage Phase 2**
>
> Boris a **cartographié toutes les équipes de la boîte** (le point de base / recensement Phase 1 est acquis). On peut désormais **s'atteler avec Fabrice à chaque contrat individuellement** (Phase 2 : récupération + audit contrat par contrat).
>
> **Note** : le "cas prioritaire #1 Mohamed" (formaliser la bascule forfait post-4/7) n'est **plus urgent** — Mohamed est maintenu sur son format actuel (cf. [[Mohamed]]). Reste à formaliser proprement son contrat existant.

> **Note d'origine (carnet 2026-05-10)** : *"Localiser tous les contrats et avoir un process clair onboarding et offboarding"* — précision Boris : majoritairement les contrats des prestataires à vérifier et mettre à jour.

## Pourquoi ce chantier existe

Trois constats convergents au mois de mai 2026 :

1. **Mohamed (IT externe)** — départ acté 31/5, transition vers forfait 1 500€/mois post-4 juillet. Contrat à formaliser proprement (ce qui n'existe pas aujourd'hui en mode "ami du CEO sans cadre").
2. **Audit SaaS en cours** (cible 70-100K€/an d'économies — KR2.2 Plan Q1) — révèle des **prélèvements orphelins** (ex. ScoreUp depuis 2024) qui survivent parce que personne ne suit les contrats prestataires SaaS.
3. **Verticale Ops/IT/Tech/Data/IA** mobilise 52K€/mois, dont une grande partie en prestations externes (Quentin plateforme, Thomas Baumelin data, Anisse, Naïma, etc.) sans cartographie centralisée des engagements et durées.

→ **Risque actuel** : on découvre des contrats au moment où ils créent un problème (facturation continue, clause de sortie défavorable, durée d'engagement piégée), pas en amont.

→ **Risque structurel** : sans cartographie maintenue, l'**étape 4 du SOP offboarding** (clôture contractuelle/matérielle) ne peut pas s'exécuter proprement → on reste dans la dette de gouvernance dénoncée par Mohamed.

## Périmètre

### IN SCOPE
- **Prestataires individuels actifs** (freelances, consultants, IT externe, coachs, etc.) — contrat / lettre de mission / devis-bon de commande
- **Prestataires offshore** (en cours de recrutement via Mithril : 2-3 dévs Maroc, Ops auto Maroc, PMO local)
- **Anciens prestataires sortis depuis < 24 mois** — vérifier que les clauses post-rupture (NDA, non-concurrence, propriété intellectuelle) sont actives + factures soldées
- **Conditions de fin** : durée, préavis, modalités de rupture, clauses post-mission

### OUT OF SCOPE (dans cette V1, à traiter séparément)
- Contrats salariés (couvert par dossier RH classique sous Fabrice → Jordan)
- Baux immobiliers (Lyon, Dubai)
- Assurances, IP/brevets, partenariats commerciaux
- Contrats SaaS purs (couverts par cartographie SaaS Mohamed — pilier 2 [[Cadre - Process IT-SaaS-Cybersec]])

## Format de la cartographie

Tableau maintenu (à choisir : Notion DB sous Atlas Ventures / madetoscale, ou fichier Excel partagé, à arbitrer avec Fabrice/Jordan) avec colonnes :

| Champ | Notes |
|---|---|
| Nom prestataire | Personne physique ou société |
| Type | Freelance / société / consultant offshore / coach / IT |
| Mission | Description courte 1 ligne |
| Date début | Format ISO |
| Date fin | Soit fixe, soit "tacite reconductible" (à éviter) |
| Préavis | Durée + modalités de rupture |
| Tarif | €/mois ou forfait + modalités de facturation |
| Owner relation | Qui pilote la relation côté Entrepreneurs.com |
| Doc contractuel | Lien vers le contrat / devis / lettre de mission archivé |
| Statut | Actif / en transition / à renouveler / sorti |
| Date dernière revue | Pour cycle de revue trimestriel |
| Clauses post-mission | NDA, non-concurrence, IP, autres |
| Notes | Particularités, risques, points d'attention |

→ **Si Notion** : créer la DB sous l'espace madetoscale ou un nouveau espace dédié Entrepreneurs.com. Si Excel : versionné dans Drive Entrepreneurs.com avec accès limité.

## Méthode d'exécution

### Phase 1 — Recensement (S2-S3 mai)
- **Owner** : Boris
- **Action** : extraction de la liste des prestataires actifs depuis la compta (Pennylane factures récurrentes), Slack (mentions de noms), discussions avec Fabrice + heads.
- **Output** : liste brute des prestataires identifiés, à confronter à la réalité.

### Phase 2 — Récupération des contrats (S3-S4 mai)
- **Owner** : Boris + Fabrice
- **Action** : pour chaque prestataire, récupérer le doc contractuel (mail, Drive, autre source). Si pas de contrat formel : flag rouge → action Phase 3.
- **Output** : dossier `15_Resources/Contrats-prestataires/` avec un sous-dossier par prestataire, doc(s) archivé(s).

### Phase 3 — Audit + mise à jour (juin)
- **Owner** : Boris + Fabrice (transitoire) → Jordan (cible)
- **Action** : revue contrat par contrat. Identifier :
  - Contrats absents → rédiger + faire signer
  - Contrats périmés → renouveler ou clôturer
  - Clauses problématiques (durée d'engagement piégée, préavis trop long, absence NDA)
  - Tarifs non alignés à la valeur livrée
- **Output** : plan d'action contractuel + contrats régularisés.

### Phase 4 — Maintenance (post-stabilisation)
- **Owner cible** : Jordan (pôle Finance/RH)
- **Cadence** : revue trimestrielle de la cartographie + déclenchement systématique d'une mise à jour à chaque entrée/sortie via SOP onboarding/offboarding.
- **Trigger automatique** : la date de fin contractuelle dans la cartographie déclenche un rappel J-30 pour décider renouvellement/clôture (cohérent avec étape offboarding du SOP RH).

## Cas prioritaires identifiés

1. **Mohamed** — transition contrat audit (5 mai → 4 juillet, 4K€/mois) puis forfait 1 500€/mois post-4 juillet. À formaliser **par écrit** avant la bascule. Ne pas reproduire le mode "ami du CEO sans cadre" historique.
2. **Quentin (plateforme)** — transition vers offshore actée (3 mois max). Conditions de sortie à clarifier avant juillet.
3. **Thomas Baumelin (data, 5K€/mois)** — décision conditionnelle ("avec ou sans"). Si maintien → contrat à clarifier. Si sortie → conditions à cadrer.
4. **Nicolas Farolfi** — départ en cours, contrat de remplacement à mettre en place via Mithril. Clauses sortie à vérifier (cf. [[Nicolas Farolfi]]).
5. **Anisse, Naïma, autres prestations IA** — état des contrats à confirmer.
6. **Prestataires recrutés via Mithril en mai-juin** : 2-3 dévs offshore, Ops auto Maroc, PMO local, RH Dubai → contrats neufs, à cadrer dès l'entrée dans le SOP onboarding.
7. **🔴 Maj (cabinet expertise-comptable Dubai)** — prestataire actuel d'EC. **Sortie probable post-arrivée Jordan Leroux** (Jordan est actuellement directeur comptable Maj, jusqu'au 15/5). Cf. [[Ressource - Replay 1-to-1 Boris × Jordan Leroux 11 mai 2026]], verbatim Jordan : *"vous êtes tous clients Maj pour le moment. Je pense que ça sautera si tout se passe comme moi je le veux."*
   - **⚠️ CONFIDENTIALITÉ MAX** : Maxime (CEO Maj) ne doit pas être informé du recrutement de Jordan chez EC. Toute discussion sur la relation Maj × EC entre le 11/5 et le 15/5 (date sortie Jordan) doit rester côté EC uniquement.
   - **Posture Boris arrêtée 11/5** : ne pas rouvrir le sujet "prestation Maj" auprès d'Alec cette semaine. **Attendre que Jordan le propose lui-même post-arrivée (18/5+)**.
   - **Cadre de mission Maj actuel** : panel de services aux expatriés français (compta + fiscalité + conformité). À cartographier proprement avant toute décision de sortie.

## Articulation avec les autres chantiers

- [[People-RH - Onboarding-Offboarding collaborateurs]] → la cartographie est alimentée par chaque entrée/sortie via les étapes du SOP RH
- [[Cadre - Process IT-SaaS-Cybersec]] pilier 2 (gouvernance SaaS) → la cartographie SaaS pure est portée par Mohamed/Boris, mais les **contrats SaaS** (engagement, durée, tarifs négociés) ont des recoupements
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] KR2.2 (audit dépenses 70-100K€/an d'économies) → la cartographie contrats prestataires complète l'audit SaaS pour donner une vision exhaustive des coûts récurrents externes
- Pôle Finance/RH (en construction sous Jordan post-stabilisation) → cible naturelle de l'ownership permanent de cette cartographie

## Questions ouvertes / à arbitrer

1. **Outil** : Notion DB ou Excel partagé ? Décision rapide à prendre pour ne pas créer de friction au démarrage.
2. **Owner permanent** : Jordan en cible (cohérent avec rôle finance/RH structuré post-mai) — confirmer avec lui à son retour.
3. **Périmètre V2** : à quel horizon étendre aux contrats salariés / baux / assurances ? Probablement Q2-Q3 2026.
4. **Doc contractuel "minimum viable"** pour les prestataires individuels : lettre de mission type à créer ? Avec NDA / IP / clauses standard à toujours présentes ?
5. **Anciens prestataires sortis** : combien remonter ? Limite proposée à 24 mois mais à arbitrer selon volume.

## Statut & prochaines étapes

- **2026-05-10** — Création du scope (Boris, draft)
- **À faire S2 mai** : décision outil + démarrage Phase 1 recensement
- **À faire S3-S4 mai** : Phase 2 récupération
- **À faire en juin** : Phase 3 audit + mise à jour
- **Cible Q3** : Phase 4 maintenance opérationnelle, ownership transféré à Jordan

## Notes liées

- [[People-RH - Onboarding-Offboarding collaborateurs]]
- [[Tech - Process création-transmission accès]]
- [[Cadre - Process IT-SaaS-Cybersec]]
- [[Mohamed]]
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]]
- [[Jordan Leroux]] — target owner permanent post-stabilisation pôle Finance/RH (arrivée 18/5)
- [[Ressource - Replay 1-to-1 Boris × Jordan Leroux 11 mai 2026]] — contexte cas Maj confidentiel
