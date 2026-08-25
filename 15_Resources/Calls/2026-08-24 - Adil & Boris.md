---
type: call
date: 2026-08-24
source: sembly
participants: ["[[Adil]]", "[[Boris Arduy]]"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-08-24
---

# Adil & Boris

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (24/08/2026 17:17).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 24/08/2026 17:21 — corrige librement hors des marqueurs.

**Résumé** — Call de déblocage urgente sur l'effondrement des conversions (62% à 8% Tally, 60% à 17% WhatsApp) suite à un changement d'ordre du tunnel VIP. Revue complète du tracking, de l'attribution UTM et des intégrations Tally/Customer.io/HubSpot pour fiabiliser les données avant la semaine de scaling.

**Décisions**
- Rétablir l'accès SDR Hub pour Adil afin qu'il supervise le flux leads et la nouvelle structure SDR
- Ajouter des UTM aux liens de calendrier pour attribuer correctement les rendez-vous à la campagne de scaling
- Créer un lien/embed dédié pour l'atelier du mardi avec UTM et copie spécifique (rencontre expert)
- Ajouter une propriété HubSpot 'Atelier mardi : participé' avec date pour tracer la présence aux ateliers
- Synchroniser les champs Tally (CA, ARR, etc.) vers Customer.io comme propriétés personnalisées pour permettre la segmentation automatique
- Vérifier et restreindre l'accès API de Smart Funnel (Mathis) pour limiter l'exposition des données de rendez-vous et volumes

**Actions**
- [ ] **Boris** : Donner accès SDR Hub à Adil (échéance 2026-08-25)
- [ ] **Adil** : Alerter Alex et l'équipe SDR pour contacter les 31 leads prioritaires non traités (échéance 2026-08-25)
- [ ] **Boris** : Vérifier le mapping VIP vs 500K (opt-in, sources, volumes) dans les dashboards (échéance 2026-08-26)
- [ ] **Boris** : Créer les liens calendrier avec UTM (standard + funnel) pour les SDR (échéance 2026-08-26)
- [ ] **Boris** : Créer le lien/embed atelier du mardi avec UTM et ajuster la copie (échéance 2026-08-26)
- [ ] **Adil** : Relire et valider la copie de l'atelier avant mise en ligne (échéance 2026-08-26)
- [ ] **Adil** : Envoyer le brief des champs personnalisés Tally à mapper dans Customer.io/HubSpot (noms exacts, valeurs attendues) (échéance 2026-08-25)
- [ ] **Boris** : Implémenter les champs personnalisés Tally dans Customer.io et mettre à jour les automatisations (échéance 2026-08-28)
- [ ] **Adil** : Créer la propriété HubSpot pour les ateliers du mardi (ou coordonner avec Léa) (échéance 2026-08-26)
- [ ] **Boris** : Auditer la clé API Smart Funnel/CTO et restreindre le webhook au strict nécessaire (échéance 2026-08-27)

**Risques & vigilances**
- Effondrement de conversion (62% à 8% Tally) bloque le ROI de la semaine de scaling tant que le tunnel n'est pas corrigé
- 31 leads prioritaires VIP 500K non contactés risquent de refroidir
- Exposition potentielle de données sensibles (volumes RDV, leads) via l'API Smart Funnel (Mathis)
- Processus manuel d'export/import Tally empêche la segmentation en temps réel et ralentit les campagnes
- Attribution incomplète sans UTM sur les liens calendrier rend impossible la mesure du ROI acquisition
- Incohérence des liens iClosed (lien d'Aziz, mauvais templates) génère des trous de données et des corrections manuelles

Tags : #conversion-funnel #tracking-utm #integration-tally #sdr-hub #attribution-acquisition
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 24/08/2026 17:17 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a examiné plusieurs problèmes majeurs de tunnel, de suivi et d’intégration qui provoquent des chutes importantes de conversion et des lacunes d’attribution. Les principaux points convenus sont : rétablir l’accès à SDR Hub pour Adil, clarifier le mapping des sources et des tunnels (notamment VIP vs 500K), ajouter des UTM aux liens de calendrier, créer un lien/embeddage dédié pour l’atelier du mardi, fiabiliser le suivi des participants dans HubSpot, synchroniser correctement les réponses Tally vers Customer.io/HubSpot, et vérifier les risques d’exposition de données liés à Smart Funnel / API. Les actions immédiates concernent Boris (accès, mapping, liens UTM, audit technique, intégrations) et Adil (brief champs, coordination SDR/sales, validation des copies et des liens).

📋 Outline

1. Changement d’ordre du tunnel et effondrement des conversions • 0:00:00

- L’ordre du tunnel a été modifié : les personnes s’inscrivent désormais en VIP avant de remplir Tally, et ce changement semble avoir provoqué une forte baisse des conversions.
- Adil a indiqué que le taux de complétion Tally est passé de 62 % à 8 %, et que les inscriptions WhatsApp sont tombées de 60 % à 17 %.
- Cette chute de conversion rend inefficaces, à ce stade, les dépenses d’acquisition liées à la « semaine de scaling » tant que le tracking et l’ordre du funnel ne sont pas corrigés.

2. Accès à SDR Hub et visibilité sur les leads • 0:00:53

- Boris a accepté de donner à Adil l’accès à SDR Hub afin qu’il puisse inspecter le flux des leads et la nouvelle structure SDR.
- Les leads au-dessus de 500K sont automatiquement envoyés dans SDR Hub ; l’équipe doit confirmer quels champs sont bien mappés (source, nom du funnel, revenu).
- Adil a demandé s’il fallait désactiver l’automatisation qui envoie aussi les leads vers Slack si elle est redondante ; la décision sera prise après vérification du mapping dans SDR Hub.

3. Leads prioritaires non contactés et relance SDR • 0:03:31

- Boris a signalé 31 leads prioritaires marqués « new » dans SDR Hub, ayant rempli le Tally VIP 500K, mais qui n’ont pas encore été contactés ni mis à jour dans le système.
- Boris a demandé à Adil d’avertir Alex et l’équipe SDR afin qu’ils contactent ces 31 leads en urgence et mettent à jour leur statut.
- Aircall est connecté, ce qui permet aux SDR de cliquer pour appeler directement depuis la fiche lead, et les numéros de téléphone sont bien présents dans les enregistrements.

4. Distinction et mapping entre les leads VIP et 500K • 0:05:12

- Les leads VIP et les leads 500K correspondent à deux événements distincts.
- Adil gère une liste VIP d’environ 75 à 77 personnes et peut créer des listes dans HubSpot ou Customer.io si nécessaire.
- Boris vérifiera comment l’opt-in VIP est capturé (mapping page/formulaire) et confirmera le volume ainsi que la répartition des sources dans les dashboards.
- Les nouveaux dashboards de données (remplaçant Looker) affichent la source, le medium et la campagne, et aideront à clarifier les conversions par étape du funnel une fois le mapping corrigé.

5. Suivi et attribution via UTM et liens de calendrier • 0:07:28

- Pour attribuer correctement les rendez-vous pris grâce aux dépenses d’acquisition de la « semaine de scaling », l’équipe ajoutera des UTMs aux liens de réservation du calendrier afin que les appels réservés remontent vers la bonne campagne et les bonnes entrées iClosed.
- Les SDR gèrent actuellement plusieurs liens de calendrier, ce qui complexifie le processus ; Boris propose de leur fournir deux liens — un standard et un spécifique au funnel — pour garantir un suivi propre, et il demande à Alex de gérer ce surcroît de liens.
- La convention UTM retenue inclura les champs source, medium et campaign, alignés avec la nomenclature iClosed afin d’assurer une attribution cohérente.

6. Liens iClosed, codage couleur des dashboards et règles d’embed • 0:10:03

- Boris a expliqué que les liens iClosed existent en plusieurs variantes et que les dashboards codent les sources de trafic par couleur : rouge pour challenges/webinars, vert pour les funnels evergreen, jaune pour l’organique/communications, et bleu pour les modèles de calendrier.
- Certains événements utilisent actuellement de mauvais liens iClosed ou des liens incohérents (par exemple le lien d’Aziz), ce qui a obligé à corriger manuellement des emails ; Boris créera les bons liens avec UTMs pour éviter de nouveaux trous de données.
- Boris mappera les funnels et les règles d’embed afin que l’équipe puisse réutiliser les templates et conserver une nomenclature UTM/funnel cohérente entre les flux live et evergreen.

7. Lien, copie et diffusion de l’atelier du mardi • 0:11:36

- Adil a demandé un lien/embed dédié pour l’atelier du mardi, présenté comme une « rencontre avec un expert », afin qu’il soit suivi proprement ; Boris a accepté de dupliquer un template de calendrier existant, d’ajuster le texte et d’ajouter les UTMs.
- Boris produira le lien webinar/atelier tagué en UTM et l’enverra à Adil via WhatsApp et Slack ; Adil relira la copie avant la mise en ligne.
- L’équipe créera à la fois un lien simple et un lien avec UTM pour cet atelier afin de concilier facilité d’usage et précision du tracking.

8. Suivi des participants à l’atelier dans HubSpot • 0:14:43

- L’équipe a besoin d’un moyen clair d’enregistrer les personnes qui assistent aux ateliers du mardi, même si elles ont déjà un appel programmé, afin que la présence soit traçable.
- La solution proposée consiste à ajouter une propriété HubSpot personnalisée, par exemple « Atelier mardi : participé » avec une date, pour marquer la participation.
- Les ventes doivent être informées lorsque des participants sont marqués, afin que les SDR — notamment Léa — puissent effectuer un suivi et continuer à « réchauffer » ces leads.

9. Données Tally non synchronisées complètement vers Customer.io • 0:16:10

- Actuellement, les réponses des formulaires Tally (par exemple les champs de chiffre d’affaires) n’apparaissent pas automatiquement comme propriétés dans Customer.io, ce qui oblige l’équipe à faire des exportations/importations manuelles.
- Ce processus manuel empêche des segmentations fines, comme envoyer un email uniquement aux leads à 1 M€ d’ARR, sans exporter les données à chaque fois.
- L’objectif est de pousser les champs Tally vers Customer.io sous forme de propriétés personnalisées afin que les équipes puissent filtrer et lancer des campagnes sans étapes manuelles.

10. Exigences et calendrier de mise en place des champs • 0:17:35

- Boris peut créer les champs dans Customer.io, mais préfère qu’Adil fournisse les noms exacts des champs et les valeurs attendues afin de garantir un paramétrage correct.
- Si Adil envoie le brief le jour même ou au plus tard le lendemain matin, Boris estime pouvoir résoudre le sujet entre mercredi et jeudi, sous réserve de la charge de travail de l’équipe.
- Il existe déjà un flux d’automatisation entre Tally et le système, mentionné comme « Mario », et les mises à jour devraient s’appuyer dessus autant que possible.

11. Architecture d’URL et redirections pour les liens de lancement • 0:19:41

- Adil a expliqué une structure d’URL parent/enfant : des liens courts enfants redirigent vers des liens parents, ce qui permet d’attribuer les canaux tout en conservant la possibilité de modifier globalement la destination en changeant une seule redirection parent.
- Ce système fournit une attribution par canal (par exemple WhatsApp vs général) afin que l’équipe puisse voir quels canaux génèrent les présences en direct et ajuster la stratégie d’acquisition en conséquence.
- Les liens courts utilisés dans les newsletters et communications sont tagués avec des UTM et suivis dans la feuille de calcul ; Adil peut créer de nouveaux liens courts si nécessaire.

12. Suivi de l’origine des données, dashboards et granularité des A/B tests • 0:22:29

- Le dashboard Looker et le Data Studio d’Adil sont tous deux disponibles ; le dashboard d’Adil se rafraîchit plus vite et servira à obtenir une attribution plus granulaire, jusqu’à savoir quelle publicité a conduit à une vente.
- La proportion de leads à origine non définie est faible, environ 2 % sur le dernier lancement, ce qui est acceptable, mais l’équipe continuera à améliorer l’attribution.
- L’objectif est d’atteindre une granularité suffisante pour permettre des A/B tests au niveau publicité-vers-vente lors des prochains lancements.

13. Smart Funnel / clé API CTO et sécurité des données • 0:24:08

- Smart Funnel (Mathis) dispose actuellement d’une clé API qui pourrait exposer des données de rendez-vous et des volumes de leads ; Adil a exprimé une inquiétude concernant le partage de données granulaires avec un prestataire externe.
- Boris vérifiera l’intégration pour voir quelles données sont envoyées (tous les rendez-vous réservés ou seulement les leads pertinents) et si le webhook peut être filtré afin de limiter l’exposition.
- Parmi les alternatives discutées : utiliser un webhook Customer.io avec filtres ou ajuster le webhook pour que Smart Funnel ne reçoive que le sous-ensemble de leads voulu.
- L’équipe a convenu d’être prudente, car l’accès actuel pourrait permettre au fournisseur de voir les volumes de rendez-vous ou d’autres métriques sensibles.

14. Décisions finales et prochaines étapes immédiates • 0:27:23

- Adil enverra dès que possible un brief listant les champs personnalisés exacts et les conventions de nommage souhaités dans Customer.io/HubSpot, idéalement ce soir ou demain matin.
- Boris implémentera les champs et mettra à jour les automatisations entre Tally et Customer.io, avec un objectif de livraison entre mercredi et jeudi selon la charge.
- Adil créera la propriété HubSpot pour les ateliers du mardi, ou coordonnera cette création avec Léa, afin que les ventes aient une visibilité sur la participation.
- Boris audira la clé API Smart Funnel / CTO et la configuration du webhook afin de restreindre le partage de données au strict nécessaire.
- Adil continuera à gérer le tableau des liens et la stratégie UTM, et l’équipe utilisera Looker/Data Studio pour l’attribution détaillée et les tests A/B.
%% notes:fin %%
