---
type: draft
domaine: Clover
date: 2026-06-12
version: v0
statut: à relire (Boris) → envoi Alexandre → revue avocat/EC
sensitivity: confidential
tags: [clover, pacte-associes, juridique, draft]
---

# Pacte d'associés — Draft v0 (term sheet)

> [!warning] Document de travail
> Term sheet de négociation entre fondateurs, **pas un acte juridique**. À faire transformer/valider par avocat + expert-comptable avant signature (comme convenu au call du 12/06). Les [●] sont des variables à fixer.

> [!important] 🔴 À trancher avant envoi à Alexandre
> 1. **Montant de l'apport cash d'Alexandre** [●] € — fixe mécaniquement la valorisation miroir de l'IP (hypothèse runway : ~20 k USD / 6 mois)
> 2. **Vesting** : durée 36 ou 48 mois — recommandé de l'annoncer d'emblée, sur les deux fondateurs
> 3. **Présidence de la SAS** : Alexandre (cohérent avec le rôle de directeur opérationnel) ou Boris/Atlas Ventures ?
> 4. **Mécanisme final de deadlock** : buy-sell (offre alternée) oui/non — attention à l'asymétrie de moyens financiers
> 5. **Périmètre de l'IP apportée** : code/architecture seuls, ou aussi le déploiement Clover Guyane existant (~34 biens) comme premier client de la société ? Sort du contrat actuel à clarifier.

---

## 1. Parties
- **Associé A** : Atlas Ventures (holding de Boris Arduy)
- **Associé B** : Alexandre [nom complet], en nom propre (faculté d'apport ultérieur à une holding, sous réserve d'adhésion de la holding au pacte)

## 2. Société
- Forme : **SAS de droit français** ; siège : domiciliation **Paris** (~30 €/mois)
- Dénomination sociale : simple et distincte du nom produit [●]
- Objet : édition et commercialisation d'une plateforme SaaS de gestion locative et conciergerie (PMS), et verticales connexes (véhicules, bateaux)
- Constitution lancée en parallèle du go-to-market (délai 4-6 semaines) ; expert-comptable : [contact Boris]

## 3. Capital & apports — 50/50
- **Apport B (numéraire)** : [●] € — calibré sur le besoin de la fenêtre de validation 6 mois (réf. budget : ~1 700 USD/mois équipe + ~800 USD/mois outils + 5 000 USD réserve constitution ≈ 20 000 USD)
- **Apport A (nature)** : propriété intellectuelle de la plateforme Clover existante — code, architecture, schémas Supabase, workflows n8n, intégrations (Beds24, RemoteLock, WhatsApp), documentation — valorisée **[●] € en miroir de l'apport en numéraire** → 50/50
- Principe de valorisation : **simple, symétrique, non gonflée**. Rappel de cadrage : les 4 500 € historiques = prix de build facturé, **pas** une valorisation d'actif.
- Commissaire aux apports : vérifier avec l'EC la dispense (conditions de seuils en SAS) — à confirmer juridiquement
- **Condition suspensive** : le transfert effectif de l'IP à la société n'intervient **qu'à la signature du présent pacte + immatriculation**. Licence d'usage transitoire consentie par A si nécessaire d'ici là.

## 4. Engagements des fondateurs
- **Rôles** : A = produit, tech, opérations internes · B = **directeur opérationnel** — marketing, vente, terrain, relation client
- **Temps** : B = temps majoritaire (rôle opérationnel principal) · A = ≥ 2 jours/semaine flexibles, davantage si nécessaire
- **Clause de revoyure M+6** : si l'engagement réel de l'un diverge significativement de l'engagement déclaré → ajustement (vesting, rééquilibrage) discuté de bonne foi
- **Exclusivité / non-concurrence** : aucune activité concurrente (PMS / conciergerie courte durée) pendant la détention + [12-24] mois après sortie ; non-sollicitation clients & équipe
- Reporting interne : point hebdo + tableau de bord (MRR, churn, cash, pipeline)

## 5. Vesting fondateurs (les deux)
- 100 % des titres soumis à vesting : **[36-48] mois, cliff 12 mois**, linéaire ensuite
- **Good leaver** : conserve les titres vestés ; titres non vestés rachetés à la valeur nominale
- **Bad leaver** (faute grave, violation du pacte ou de la non-concurrence) : rachat de tout ou partie à valeur nominale/décotée
- Finalité : protéger chaque associé contre le désengagement de l'autre — symétrique par construction

## 6. Gouvernance & décisions
- Président : [●] (cf. décision ouverte n°3)
- **Décision finale par domaine** (anti-paralysie du 50/50) :
  - A : produit, tech, infrastructure, roadmap technique
  - B : marketing, commercial, terrain, relation client
- **Décisions réservées à l'unanimité** : budget annuel et dépassement > [10] % ; dépense unitaire > [●] € ; embauche/rupture d'un poste clé ; endettement ; émission de titres / dilution ; cession d'actifs essentiels (dont IP) ; modification des statuts ; rémunération des fondateurs ; lancement d'une verticale majeure ; entrée d'un investisseur

## 7. Anti-blocage (deadlock)
1. Notification écrite du désaccord + délai de résolution [15] jours
2. **Médiation par un expert/conseiller externe sectoriel** (avis [consultatif / décisif sur les sujets opérationnels — à trancher])
3. Blocage persistant > [60-90] jours sur une décision réservée : mécanisme de sortie — [option buy-sell à offre alternée, avec garde-fous de valorisation — à valider avec l'avocat]

## 8. Transferts de titres
- **Inaliénabilité** : [2-3] ans, sauf accord mutuel écrit
- **Préemption réciproque** prioritaire avant toute cession à un tiers
- **Agrément** pour toute entrée d'un tiers au capital
- **Tag-along intégral** (100 %) en cas de cession de contrôle
- **Drag-along** : seuil > [60-66] % avec prix plancher [ou unanimité fondateurs pendant les [3] premières années]
- Anti-blocage minoritaire : les droits de veto sont limités à la liste des décisions réservées — aucun veto général sur les opérations stratégiques

## 9. Incapacité, décès, succession
- **Décès** : promesse croisée de cession — **droit de rachat prioritaire automatique** du coassocié survivant sur les titres, valorisation par expert indépendant [ou formule pré-agréée]. Les héritiers perçoivent la **valeur économique** (prix de rachat et/ou dividendes courus) mais **aucun droit de gouvernance**.
- **Incapacité prolongée > [6] mois** : option de rachat partiel ou total au profit du coassocié, mêmes modalités
- **Assurance croisée associés** (« homme-clé ») à étudier pour financer le rachat

## 10. Investisseurs futurs
- Entrée soumise à l'**unanimité des fondateurs**
- Dilution **proportionnelle et pari passu** entre A et B
- **Adhésion obligatoire** de tout nouvel entrant au présent pacte

## 11. Propriété intellectuelle future
- Tout développement, contenu, marque, base de données ou savoir-faire créé dans le cadre du projet = **propriété exclusive de la société** (cession automatique, fondateurs et prestataires)
- Marques et noms de domaine déposés **au nom de la société**

## 12. Rémunération & distributions
- **Pas de salaire fondateurs** pendant la fenêtre de validation (6 mois) ; remboursement de frais sur justificatifs
- Politique : **réinvestissement prioritaire du CA** (réf. modèle : ~6 500 €/mois réinvestissables à 10 k€ MRR) ; revue à M+6 selon traction

## 13. Durée, confidentialité, droit applicable
- Durée : [10] ans renouvelable, ou tant que la société compte au moins deux associés
- Confidentialité réciproque sur les termes du pacte et les affaires de la société
- Droit français — compétence : [tribunal des activités économiques de Paris]

---
*v0 — 2026-06-12 — rédigé pour itération avec Alexandre, puis transformation par avocat/EC. Liens : [[Clover/README]] · [[2026-06-12 - Alexandre x Boris - Pacte & structuration SAS]]*
