---
type: call
date: 2026-10-27
source: sembly
participants: ["boris@entrepreneurs.com", "42lab@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Quentin X Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (27/10/2026 16:07).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 27/10/2026 16:07 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a abordé deux grands axes de travail. D’une part, elle a validé la mise en place d’un flux automatisé pour envoyer les ventes issues de Scale vers HubSpot afin de créer les transactions et générer les factures, tout en cadrant les responsabilités marketing pour le lancement public, la finalisation de la fonctionnalité multilicence, l’onboarding commercial et plusieurs évolutions produit (organigramme client, résiliation automatique). Un objectif de chiffre d’affaires de 10 k€ a été retenu comme seuil rendant le produit financièrement significatif.

D’autre part, l’équipe a constaté une dégradation critique du traitement des tickets Zendesk, avec un volume important de messages non traités lié à des problèmes d’effectif et de process, et a considéré ce sujet comme prioritaire. En parallèle, elle a discuté d’optimisations de coûts pour Shade via du cold storage, d’une proposition de fonctionnalité MCP dont le calendrier doit être repoussé et budgété avec Jordan, du cadrage budgétaire 2027, et de l’avancement du projet Moonshot, dont la bêta, la monétisation et le positionnement restent à préciser.

📋 Outline

1. Synchronisation des ventes Scale vers HubSpot et génération des factures • 0:00:00

- L’objectif est d’envoyer toutes les ventes issues de Scale dans HubSpot afin de créer automatiquement une transaction puis de générer les factures.
- Quentin et Boris doivent se coordonner sur les paramètres nécessaires à la création de la transaction.
- Le sujet de la synchronisation Wop/Wap vers Odoo reste à vérifier : les transactions générées côté Wap ne créent actuellement pas de facture dans Odoo car le lien n’est pas confirmé.
- Quentin peut envoyer la transaction et définir son statut (closed/won/paid) une fois les paramètres et les produits correctement définis, afin d’éviter les doubles saisies.

2. Migration de l’infrastructure vers Cloudflare R2 et Ngram • 0:02:25

- Tout le code coaching issu de Vercel/Blog a été migré vers Cloudflare R2 et consolidé dans l’infrastructure Ngram.
- La migration est considérée comme terminée pour les assets cloud, désormais hébergés sur une infra contrôlée par l’équipe, ce qui réduit la dépendance à des services externes.

3. Lancement public, responsabilités marketing et gestion des tickets/contrats • 0:02:56

- La prochaine échéance est l’ouverture publique des ventes ; le marketing doit finaliser les synchronisations de landing page, pixels, copywriting, séquences email et configuration des domaines/sous-domaines avant le lancement.
- Quentin créera les accès et enverra les emails de confirmation lorsqu’une vente survient sur le produit WAP, mais il ne prend pas en charge les séquences marketing pré- et post-achat.
- L’équipe a identifié un risque d’incidents de dernière minute et de désalignement sur les tickets/places inclus dans les contrats ; il faut éviter les modifications tardives et vérifier les inclusions contractuelles en amont.

4. État de la fonctionnalité multilicence et plan de livraison • 0:06:23

- Le travail sur la multilicence est presque terminé ; Quentin enverra un document avec captures d’écran couvrant environ 30 à 40 vues et états différents pour relecture.
- Le format retenu est un document détaillé orienté écrans plutôt qu’une grosse spécification textuelle, afin de faciliter la validation et les tests.
- Quentin prévoit de mettre la fonctionnalité en production au plus tard vendredi et demande un retour sur le document avant le déploiement.
- Il ajoute également un flux de désabonnement optimisé pour capturer les raisons de résiliation, en ligne avec les bonnes pratiques SaaS.

5. Attentes d’onboarding et motion commerciale du nouveau produit • 0:08:46

- La vente du produit se fera comme un upsell ; un produit UpSpot doit être créé dans les outils commerciaux pour faciliter l’achat.
- L’onboarding sera délivré une fois qu’un client aura payé un ticket compris entre 1 000 € et 2 000 €, afin qu’il reçoive toute la valeur attendue avant un éventuel arrêt automatique en cas de non-engagement.
- La plateforme permet déjà les achats, l’accès aux factures et l’annulation automatique lorsqu’aucun programme actif n’existe, ce qui réduit le travail manuel des opérations.

6. Nouvelle fonctionnalité technique : organigramme client et recommandations • 0:08:46

- Une fonctionnalité récente recompose les organigrammes clients à partir des transcriptions de coaching et suggère des associés internes et externes pour créer un organigramme structuré.
- Cet organigramme peut servir à recommander des sièges/licences à des rôles spécifiques, ce qui améliore le ciblage commercial et l’upsell.

7. Objectif de chiffre d’affaires et justification financière • 0:09:43

- L’objectif initial de chiffre d’affaires est de 10 k€ afin de faire du produit une ligne de revenus significative, capable de couvrir une partie des coûts de l’équipe et d’avancer vers le point mort.
- Atteindre cet objectif doit permettre de valider la valeur de la plateforme et de justifier la poursuite de l’investissement et du développement.
- L’équipe reconnaît sa dépendance à une réussite commerciale externe pour générer des revenus indirects (upsell et Copilot) et souhaite ajuster l’offre et le positionnement en conséquence.

8. Gabarit d’audit et usage commercial • 0:14:07

- L’équipe a besoin d’un gabarit d’audit structuré, avec sections et sous-sections claires, plutôt que d’un long PDF, pour standardiser le contenu attendu de l’audit et des livrables.
- Plusieurs options sont envisagées : fournir le template aux commerciaux pour la restitution après les sessions, l’héberger sur la plateforme ou automatiser une partie de la production.
- Le format de restitution doit rester concis, actionnable et exploitable par les commerciaux pour garantir une valeur d’onboarding/audit cohérente.

9. Étapes suivantes, coordination et suivi des tickets • 0:15:20

- Boris coordonnera les parties prenantes et publiera des mises à jour au groupe sur la monétisation de la plateforme et les sujets en suspens.
- L’équipe continuera à suivre les petits tickets et les relances Handesk ; les rappels de tickets ont été traités ce matin.
- Les actions immédiates incluent l’envoi du document multilicence par Quentin, la mise en production de la fonctionnalité, l’implémentation du flux HubSpot transaction/facture par Quentin, Boris et Jordan, ainsi que la vérification du domaine, des pixels et des CGV/CGU avant le lancement.

10. Backlog support Zendesk et défaillances de traitement • 0:15:49

- Environ 100 à 110 messages clients restent non lus sur les canaux concierge et support plateforme, et sont restés sans traitement pendant deux à trois semaines.
- Historiquement, les tickets Zendesk étaient synchronisés vers Slack pour réduire le délai de réponse de plusieurs heures à quelques heures ; ce flux ne fonctionne plus ou n’est plus suivi.
- Les réponses préparées par le produit ne sont pas copiées-collées puis envoyées aux clients, ce qui laisse les tickets plateforme à l’abandon.
- Les perturbations d’effectif, notamment les départs possibles de Tessie et Lorraine, ainsi que des recrutements infructueux, ont laissé le traitement des tickets sans ownership efficace.
- Le backlog support est prioritaire et nécessite immédiatement de réattribuer la responsabilité et de restaurer le workflow Zendesk-vers-Slack.

11. Impact du workflow interne et clarification des attentes • 0:17:21

- L’ancien processus reposait sur un passage rapide de relais : le produit qualifie les tickets et rédige les réponses dans Slack, puis le support les publie dans Zendesk ; ce fonctionnement avait fait de Léa la meilleure traiteuse Zendesk.
- Lorsque les équipes support n’étaient pas disponibles, les latences de traitement pouvaient aller de zéro à cinq heures, plus le temps de traitement, ce qui a motivé le contournement via la synchronisation Slack.
- Il existe une confusion sur les attentes de rôle, par exemple Caroline pensait ne devoir consacrer qu’environ 10 heures par semaine, et ce décalage a contribué à laisser des tickets sans réponse.
- Boris doit clarifier les responsabilités et les niveaux d’engagement attendus.

12. Coût de stockage Shade et optimisation via cold storage • 0:20:27

- Shade a communiqué un montant trimestriel d’environ 37 k$ pour 125 To de données, dont une grande partie pourrait être du stockage froid rarement consulté.
- Si 80 à 100 % des données sont froides et seulement parfois prévisualisées, un déplacement vers un cold storage moins cher pourrait générer plusieurs milliers à plusieurs dizaines de milliers de dollars d’économies par an.
- L’architecture Cloudflare R2 est déjà en place et pourrait permettre un écran de prévisualisation pour les fichiers froids avec une inférence légère, sans trop dégrader l’expérience utilisateur.
- La décision dépend de la répartition entre rushes réutilisés activement et contenus archivés ; une analyse complémentaire est nécessaire avant toute décision.
- Il faut aussi arbitrer avec l’avantage opérationnel de Shade, notamment la recherche et le face-match, qui accélèrent l’édition ; une migration doit donc peser économies et confort d’usage.

13. Proposition de fonctionnalité MCP et calendrier • 0:22:49

- Léonard a préparé une présentation importante sur le MCP pour Alec, avec une capacité MCP administrateur et un contrôle plateforme pour les accompagnements clients.
- Alec a demandé à Léonard de coordonner les détails budgétaires avec Boris ; le périmètre et le coût du développement doivent donc être clarifiés avant validation.
- L’équipe recommande de repousser le gros chantier MCP après la période chargée du roadmap, avec une cible possible en janvier-février.
- Quentin explore des moyens alternatifs de réduire le coût client, via du business development et des arbitrages, afin de rendre l’offre MCP plus abordable.

14. Processus budgétaire 2027 et implication de Jordan • 0:25:30

- La préparation budgétaire 2027 démarre et Jordan travaille déjà sur les chiffres ; il sera associé aux décisions financières importantes.
- Toute décision de financement de nouveaux développements, comme le MCP, devra s’inscrire dans le budget émergent et être revue avec Jordan pour vérifier le réalisme des chiffres.
- L’équipe n’engagera pas de nouveaux développements immédiatement sans disposer d’une vue d’ensemble et d’un contexte budgétaire global.

15. Projet Moonshot : état, bêta et options de monétisation • 0:27:00

- La R&D Moonshot est presque terminée ; l’équipe a construit une architecture légère et performante, avec des astuces utiles inspirées d’outils existants, et les principaux défis techniques ont été résolus.
- Les prochaines étapes sont de lancer des tests bêta internes, d’ouvrir à quelques clients sélectionnés, puis de publier une première version publique tout en définissant la stratégie de monétisation.
- Les pistes de monétisation incluent des intégrations de prise de notes, des notes illimitées dans un abonnement, des versions différenciées du produit (light vs avancée) et des offres packagées pour incubateurs ou scalers.
- L’équipe a discuté de plusieurs modèles go-to-market : fournir Moonshot à tous les clients, le proposer gratuitement à certains et payant à d’autres, ou créer une licence par paliers pour capter la valeur chez les clients en croissance.
- Le produit est censé apporter une valeur claire aux débutants comme aux entreprises en phase de scale, avec un ROI potentiellement fort à plus grande échelle, mais le pricing et le packaging doivent encore être validés par la donnée.
%% notes:fin %%
