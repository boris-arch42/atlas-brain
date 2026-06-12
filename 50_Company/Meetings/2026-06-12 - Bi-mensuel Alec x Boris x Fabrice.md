---
type: meeting
date: 2026-06-12
date_call: "Semaine du 8 juin 2026 (réunion bimensuelle 40 min, organisée par Alec Henry)"
participants: [Alec Henry, Boris Arduy, Fabrice Jaeger]
contexte: ENT — point bi-mensuel ops (data, lancement juin, CRM, SaaS, recrutement, cyber)
source: Export Sembly AI (PDF, archivé via Claude)
tags: [meeting, ent, bimensuel, data, lancement-juin, crm, saas, cyber]
---

# Point bi-mensuel — Alec × Boris × Fabrice

> [!note] Transcriptions Sembly normalisées : « Hotspot » → **HubSpot**, « Data Looker » → **Looker Studio**, « Echo/ICO » → **Aikho**. « Point de suivi scolaire » = probablement **Skool** (à confirmer).

## TL;DR
Trois irritants récurrents : incohérences data, communication inter-équipes, manque d'ownership. Décisions : preuves obligatoires (captures + horodatage) sur les incidents data, revue data hebdo, correctif prioritaire des doublons Zoho↔HubSpot, pôle ops/tech unique, Fabrice dans les appels CRO avec plan d'implémentation concret. Jalons lancement juin figés (16/06 revue technique, 22/06 freeze, 23/06+ monitoring). Avancées cyber fortes (fichiers publics 82k → <20k, MFA enforced).

## Décisions & cadrage
- **Toute remontée data** doit inclure **captures d'écran + horodatage** (chronologie détection/correction).
- **Revue data hebdomadaire courte** (proposition Boris), synchrone ou asynchrone, en amont des réunions — sortir du mode pompier.
- **Looker Studio = source consolidée de référence** une fois le correctif doublons appliqué. Sinon : arrêter d'y investir. Gouvernance à définir : décideur unique + plan de remédiation + formation continue ; chaque équipe s'engage à l'utiliser et à remonter du feedback.
- **Centralisation ops + tech sous un pôle unique** (réunions transverses régulières, ownership partagé des automatisations/connecteurs) — décision à porter par la direction.
- **Fabrice** : attendu sur des solutions concrètes et déployables + plan d'implémentation (process, cadences, responsables, échéances) ; rejoint les **appels CRO** ; Alec réintégré aux appels CRO (visibilité directe). Réduire les 1:1 annulés.
- **Post-mortem précis** exigé de Cédric + Thomas, **Boris présent** — pas d'édulcoration, apprentissages tangibles et mesurables.
- **Réunion « 6 heroes »** : pilotée par Fabrice à partir du **17/06** (1ʳᵉ : 1h30, suivantes 1h15). Slides + métriques + structure d'animation + extrait de transcript + actions avec owners. **Océane** : slides + registre d'actions consolidé (marketing/ventes/CRO).
- **Format bimensuel resserré sur 5 sujets** (proposition Boris) : lancement juin · audits & coupes SaaS · décommissionnement · recrutements · point « Skool » (?). → Boris diffuse deck + agenda.

## Lancement juin
- **Jalons** : **16/06** revue technique + tests bugs · **22/06** freeze complet · **23/06+** tests finaux + monitoring live. Objectif du freeze : éviter les régressions CRM/liens du lancement précédent.
- **Offre** : Starter vs Builder — **Sabrina finalise**, Alec donne un retour fondé sur la logique marché ; contenu validé sur le besoin marché, pas seulement sur les ressources dispo.
- **Leads** : répartition Alchimie / CGM — coûts par lead closé **14 % vs 10 %**, taux de closing similaires → **split 50/50 pour juin**, retester puis renégocier (Alec + Boris). *(Note Atlas : à réconcilier avec les taux contractuels connus — CGM 13 %, Tip Talent 10 %.)*
- **Volumes** : objectif **~400 appels réservés** ; conversion attendue **7-8 %** ; attention aux prospects inactifs → ne pas surdimensionner les salles externes ; marketing confirme les estimations de génération.
- **Delivery** : 30-35 onboardings jugés gérables (Program Lead confirme la capacité). **Boris garantit ressources + formation closers à J-10** du challenge.
- **Coachs** : recrutement en ~10 j possible mais risqué (onboardings réduits à 3-4 j observés → qualité, churn, remboursements). People Ops + Program Leads : évaluer le pipeline + plan d'onboarding atténué. Référents temps partiel → temps plein à étudier (rôle + rémunération).

## Data
- **Écart constaté** : HubSpot **577 k€** vs Looker **477 k€** → **100 k€** de doublons (1 client = 3 appels Zoho → 3 transactions HubSpot). Observé par Aziz, investigué par Fabrice ; l'agrégation Looker a permis de révéler/corriger — le dashboard consolidé donnait le bon montant.
- **Correctif duplication Zoho → HubSpot** : Nicolas + équipe intégration ; tester pour éviter toute récurrence d'inflation des revenus.

## CRM
- Double CRM (Zoho + HubSpot) intenable → **analyse comparative** + faisabilité d'un **CRM léger custom pour les ventes externes** (capture leads → export CSV/API vers HubSpot pour réaffectation interne). Vrai défi : pipelines API in/out robustes + réconciliation historique emails/appels (le front est rapide à faire). **Anis** estime l'effort ; Sales/Ops définissent champs & workflows.
- Licences HubSpot internes chères et annuelles → négocier **mensuel / sièges activables**.
- Idée : plateforme légère de lancement type **launch.entrepreneurs.com** (ressources de vente externe + CRM) → **Boris évalue** intégration + économies de licences ; Finance modélise coût/bénéfice.

## SaaS & outils
- **Accès outils bloqués depuis le 28/05** (Mohamed détient/coordonne les transferts) → **Alec rédige un message ferme mais respectueux, Boris l'envoie** + segment « demandes d'accès » en réunion Core. Gains : économies de licences + posture cyber.
- **Notion** : coupure glissée du 15/06 à **~20/06** (temps de transfert des ressources) ; arrêter de payer des licences inutilisées. Audit plus large des licences SaaS redondantes en cours.
- **Aircall** : paiements suspendus fin juin **sans couper l'accès** (levier de négo lié à la date de l'événement Scale). Possibles : licences gratuites + statut partenaire + billets. Blocage numéros FR (docs FR à jour requis ; pas de support UAE pour docs émiratis). Négociation multi-fournisseurs **Aircall / Ringover / OnOff** ; modèles partenaire/affilié = 20-30 % de commission récurrente.
- **Join → Aikho** : bascule faite la veille ; informer Aziz (anciens workflows encore actifs). Compte Join **non fermé** (factures impayées sur plusieurs mois → risque à négocier) ; licences réduites en attendant.
- **Zendesk** : avancées significatives Sabrina + Mohamed **sans payer les 4 000 €** annoncés.
- **Riot** : négocier le partage des coûts ENT/prestataires + statut partenaire/annuaire → cible **coût net ~0** (au pire ~3,50 €/licence côté prestataires). **Boris conduit l'appel de négo lundi**.

## Recrutement & orga
- **5 mandats Aikho ouverts** ; capacité passée de 1 à 5, objectif **10-20 slots** (discussion le lendemain).
- **RH Dubaï** très difficile — sourcing via Romane, Ous, Roco.
- **Sales Senior** : opérateur commercial senior orienté performance (responsabilités proches Head of Sales, intitulé différent pour éviter les frictions). Candidats à **92 / 90 / 88 %**, surtout sourcés France.
- **Aziz** : préfère la vente pure + leadership d'équipe (coaching, conversion) ; pas les missions transverses. Restructuration : une personne au-dessus pour la stratégie commerciale transverse (CRM, marketing, relais de croissance). **Package de rémunération à revoir**.
- **Jordan (finance)** : onboarding rapide et positif → pleinement opérationnel + reprise des sujets historiques **avant fin juin**.

## Cybersécurité
- **Fichiers publics** : ~82 000 → **<20 000** ; objectif **<10 000** fin de semaine.
- **MFA** : obligatoire en cours sur les comptes Google, la plupart sécurisés ; comptes critiques restants à confirmer ; relances automatisées. À partir de **vendredi prochain** : MFA obligatoire pour les nouveaux comptes + restriction d'accès Google pour les non-conformes (Mohamed, suivi avec Alec).
- **Audit sécurité plateforme client (Quentin)** : améliorations identifiées, moyens donnés à Mohamed. Suivi Mohamed + Boris.

## Actions
| Action | Owner | Échéance |
|---|---|---|
| Plan d'implémentation ops (process, cadences, owners) | Fabrice | Court terme |
| Correctif doublons Zoho→HubSpot + tests | Nicolas + intégration | Prioritaire |
| Mise en place revue data hebdo | Ops + analytics | Semaine prochaine |
| « 6 heroes » : préparation + animation / slides + actions | Fabrice / Océane | 17/06 |
| Post-mortem (Boris présent) | Cédric + Thomas | À planifier |
| Deck + agenda bimensuel 5 sujets | Boris | Prochaine session |
| Évaluation launch.entrepreneurs.com + économies licences | Boris (+ Finance) | À cadrer |
| Message accès outils (rédaction / envoi) | Alec / Boris | Immédiat |
| Ressources + formation closers | Boris | J-10 (≈13/06) |
| Split leads 50/50 + stratégie renégo post-lancement | Alec + Boris | Juin |
| Appel négociation Riot | Boris | Lundi 15/06 |
| Comptes MFA restants + enforcement | Mohamed | Vendredi prochain |
| Fichiers publics <10 000 | Mohamed + Boris | Fin de semaine |
| Consolidation des actions du call | Alec | Continu |
