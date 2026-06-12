---
type: meeting
date: 2026-06-12
date_call: "≈ 2026-06-10 (estimée — « les sales vendent dans 13 jours » vs lancement 23/06)"
participants: [Boris Arduy, Fabrice Jaeger]
contexte: ENT — contrats, frictions commerciales, tech, data, RH
source: Export Sembly AI (PDF, archivé via Claude)
tags: [meeting, ent, contrats, tech, data, rh]
---

# Boris × Fabrice — Ops, contrats, tech & data

> [!note] Transcriptions Sembly normalisées : « Clap » → **Claap**, « Hotspot » → **HubSpot**.

## TL;DR
Validation des clauses contractuelles sensibles (garantie 90 j, sessions, invitation gratuite), répartition DocuSign/OneFlow, alerte sur les annulations (2-3/jour, onboarding + positionnement flou), et ouverture de gros chantiers tech : preneur de notes IA propriétaire, context packs MCP, remplacement progressif de Make, correction doublons iClosed/HubSpot/Zoho (~100 k€ d'écart), sécurisation accès/sauvegardes, dépendance Quentin/Leonard.

## Décisions
- **Répartition contrats** : Boris → mises à jour **DocuSign** ; **Nicolas** → OneFlow (contrats actifs — modifs à planifier hors séquences de closing, ex. fin de journée). Fabrice (auteur du doc) fournit **un PDF de chaque contrat** comme ressource closers.
- **Incubateur** : 2 sessions individuelles/mois sur toute la durée du programme ; reprogrammation exceptionnelle limitée ; ni remboursement ni report cumulé.
- **« Invitation gratuite »** remplace la formulation « événement » → évite un risque de requalification TVA.
- **Garantie commerciale** : limitée à **90 jours après la fin du programme** (vs 180 j avant), conditionnée à des objectifs validés conjointement. Garanties harmonisées « à la fin du programme » (cohérence 3/6/9/12 mois).
- **Scaling** : bénéfices/sessions limités à la durée de l'accompagnement (pas d'accès à vie) ; 2 sessions individuelles ; 2 immersions physiques de 2-3 jours.
- **Naming/rebranding Kelly** (lancements fin juin, juillet, septembre) : 6 noms de programmes actifs → confusion. Options Sabrina : FIRST, GENESIS, STARTER, PRIME, BUILDER, AGORA. Préférence Boris : **BUILDER**. Décision marketing à figer. Incertitude sur les variantes encore actives (Kelly Light/Boss/Energy) vs contrats Incubateur/Scaling → liste finale des offres à confirmer.

## Alertes & risques
- **Annulations 2-3/jour** : cause principale = onboarding insuffisant + positionnement flou (coaching vendu vs formation délivrée). 2 voies (Fabrice) : assumer un positionnement formation, ou upgrader vers un vrai coaching. Les sales vendent dans **13 jours** → message produit + formation + supports = urgents.
- **Dépendance owner-key Quentin + Leonard** (code, hébergement, migrations). Actions : documenter les emplacements données/code, rapatrier le code sur des serveurs contrôlés ENT, onboarder un dev moins coûteux pour relire/documenter la base de Quentin. Sauvegardes + tests sécurité + inventaire données = **priorités urgentes**.
- **Compte Thomas Rodier** réactivé par intermittence (récupération d'automatisations/code) → risque Cloudflare/contrôle de domaine. Fabrice + Mohamed vérifient, suppriment les accès résiduels, retirent l'ancien compte de Cloudflare. → Audit des accès + centralisation des identifiants.
- **Charlotte** : incidents pouvant justifier une faute grave ; tolérance pour l'instant ; **dossier synthétique** à constituer (RH ou Boris/Fabrice) en cas de procédure.
- **Nicolas** : conservé jusqu'à fin juin max, pas de salaire en juillet → risque URSSAF / requalification freelance → négociation prudente. Départ en vacances imminent → sécuriser urgences + handover ; Fabrice envoie immédiatement les contrats à jour à Nicolas et à l'équipe.

## Data & intégrations
- **Bug iClosed / HubSpot / Zoho** : réservations répétées → HubSpot crée plusieurs enregistrements là où Zoho met à jour le contact (1 seul deal) → **écart de reporting ≈ 100 k€**. Effet amplificateur : un « Closed Won » Zoho marque gagnées toutes les transactions HubSpot du même email. **Actions** : dédupliquer l'automatisation de réservation sur l'email + réconcilier les doublons historiques. Boris + Nicolas coordonnent le debug avec Thomas — plan testé **avant le prochain lancement**.
- **Data marketing** : données de lancement avec 4-5 j de retard + indicateurs erronés ; cause non identifiée (hypothèse migration CRM vs systèmes purement marketing). Owner clair requis ; Fabrice + Boris escaladent ; Cédric assure le suivi ; Thomas relais technique.
- **CRM** : migration vers Zoho non justifiée à court terme (features manquantes) → négocier avec HubSpot des **licences plus souples** (sièges annuels activables). Compartimenter les accès CRM des équipes externes.
- **BigQuery / Chatia V2** : migration des données financières (Udo + Jordan) — chantier majeur. Chatia V2 = interrogeable depuis interfaces cloud/GPT (insights live, au-delà des dashboards statiques). Audit des accès BigQuery + cloisonnement minimal entre départements. Tagging par pays (ex. Portugal) conçu pour activer de nouveaux marchés sans casser les schémas.
- **MCP / context packs** : Thomas + Naïma + Wassim — nettoyage des bases client/ventes/marketing, glossaires & définitions standardisées (ex. « client actif »), dédoublonnage. Tests fermés en cercle restreint pour la V1 du chat IA.

## Produit & tech
- **Preneur de notes IA propriétaire** (remplace le preneur de notes partagé Claap) → « cerveau collectif » des notes de coaching. Roadmap T3-T4 : sortie de Circle, LMS interne, comms internes, recommandations de coaching en temps réel, **connecteur MCP** pour le suivi quotidien des entrepreneurs. Prochaines étapes : task forces avec les coachs (méthodologie) + livraison du context pack de test.
- **Dashboard d'usage client** demandé (adoption des features, clients actifs, fonctions inutilisées).
- **App mobile** : validation App Store ≥ 14 j (dépendance critique, plus en cas de souci) ; Android/Google Play plus simple → à intégrer au plan de release.
- **Pôle tech transversal unique** + remplacement progressif de **Make** par un système code-based maintenable. Roadmap créée. Migration des automatisations critiques (**projet Ravel**) ≈ **16 jours-homme**. Gros lancement sur la nouvelle archi = quelques jours de config + monitoring renforcé au premier run ; **dispo pour juin/juillet non garantie**. Flou budgétaire : lead type CTO + 2 devs, potentiellement offshore.
- **Coûts ingénierie** : ~240 k€ évoqués comme cohérents ; alternative : 1 senior type Quentin + 2-3 devs ≈ 15-20 k€/mois. Risque qualité offshore (Dubaï/Inde/Russie) → lead technique interne indispensable. Optimisation : remplacer un prestataire à 4 100 €/mois par une ressource ≈ 800 $/mois avec supervision maintenue ; modèle cible = lead central + juniors dédiés marketing/lancements.

## Pipeline Quentin & dossiers
- Pipeline T3/T4 présenté à Alec (appel organisé par Fabrice). Négociation client : 20 k€ → cible 17-18 k€. Projets clients externes = « **crédits de développement** » pour financer le dev interne. Nouvelle stack testée et livrable **fin juin**, montée en charge équipe en juillet.
- **Dossier Claap** : ownership du deal incertain (Axel initialement sur les contacts) ; Quentin vérifie, Fabrice contacte Axel si besoin. Vérifier les **clauses de sortie** (résiliation, réduction de licences possible ?) → revue juridique Quentin + Fabrice + conseils.

## RH & personnes
- **Recrutements imminents** : profil front-end (reprise tâches Nicolas, via Cédric — arrivée **lundi**) + profil anglophone très expérimenté back-office/marketing/CRM (via Boris — ~10 jours).
- **Yoann** : output visible limité après l'onboarding/test ; facture 3 k€ + bonus de performance négocié 2,5 k€ (essai 3 mois) ; paiement + clarté contractuelle à résoudre. Réunion à 3 avec Cédric pour cadrer périmètre/livrables. → **Boris prend le lead du suivi Yoann** ; Fabrice collecte les infos auprès de Cédric (PPR, contexte onboarding).
- **Johan** : nouvelle architecture + automatisations livrées, attend leur déploiement sur les prochains lancements ; manque de supervision et de clarté de rôle ; **facture d'avril impayée** malgré relances à Cédric ; demande un échange de 30 min avant la fin de sa période d'essai.

## Divers
- Board Clone (Fabrice) avec tâches attribuées par membre ; rendre accessible dans Slack.
- Workflow **listes Slack par lancement** (viewers limités, échéances par responsable) ; export/import CSV si l'automatisation via Claude ne génère pas la liste directement.

## Actions
| Action | Owner | Échéance |
|---|---|---|
| Mises à jour contrats dans DocuSign | Boris | ASAP |
| PDF de chaque contrat (ressource closers) | Fabrice | Immédiat |
| Modifs OneFlow synchronisées avec les closings | Nicolas | Fenêtre sécurisée |
| Figer le nom du programme (BUILDER ?) | Marketing / Sabrina | Avant lancement |
| Formation + supports sales (message produit) | Fabrice + équipes | J-13 → ASAP |
| Dossier incidents Charlotte | RH ou Boris/Fabrice | À attribuer |
| Debug doublons iClosed/HubSpot/Zoho + déduplication email | Boris + Nicolas + Thomas | Avant prochain lancement |
| Escalade data marketing (retards 4-5 j) | Fabrice + Boris (suivi Cédric, relais Thomas) | Semaine en cours |
| Documenter hébergement code/données + sauvegardes + onboarding dev relecture | Tech (Quentin/Leonard) | Urgent |
| Vérifier et couper accès résiduels Thomas Rodier / Cloudflare | Fabrice + Mohamed | Urgent |
| Vérifier ownership + clauses de sortie Claap | Quentin (+ Fabrice → Axel) | Cette semaine |
| Suivi Yoann (périmètre, livrables, paiement) | **Boris** | En cours |
| Échange 30 min Johan + facture avril | Fabrice/Cédric | Avant fin essai |
