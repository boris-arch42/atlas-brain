---
type: call
date: 2026-08-25
source: sembly
participants: ["[[Boris Arduy]]", "[[Cédric De Saint Jean]]"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-08-25
---

# Cédric & Boris

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (25/08/2026 16:36).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 25/08/2026 16:43 — corrige librement hors des marqueurs.

**Résumé** — Résolution d'un bug d'ingestion Customer.io pour un utilisateur et cadrage des besoins pour le remplacement de Looker par un dashboard interne offrant une visibilité complète du tunnel ads → leads → revenus avec granularité UTM.

**Décisions**
- SLA SDR fixé à 60–90 secondes pour l'appel des nouveaux leads opt-in Evergreen
- Adoption du schéma UTM testé pendant la 'Week of Killing' comme standard pour toutes les campagnes futures
- Utilisation d'un identifiant HubSpot / numéro de réservation (et non l'email seul) pour suivre les prospects
- Refonte du questionnaire pour capturer le nom d'entreprise et alimenter HubSpot automatiquement
- Création d'un document de conventions de nommage UTM et campagnes partagé avec marketing, comms et ops

**Actions**
- [ ] **Boris** : Tester l'ingestion opt-in avec l'utilisateur concerné (navigation privée/normale, cache, VPN, téléphone) puis escalader à Adil si problème persiste
- [ ] **Boris** : Tester l'attribution UTM des opt-ins lead magnet via redirection ou tagging
- [ ] **Cédric** : Produire un document détaillant tous les champs data requis, granularité et fonctionnalités de navigation pour le nouveau dashboard
- [ ] **Boris** : Implémenter avec Raph/devs les métriques du tunnel complet (ads → leads → réservations → closes → appels → revenus) en incluant iClosed (échéance 2026-09-30)
- [ ] **Adil** : Produire une vidéo Loom ou document écrit des conventions UTM et nommage de campagne
- [ ] **Cédric** : Définir et diffuser les règles de nommage de campagne pour HubSpot auprès de marketing, comms et ops
- [ ] **Alexandre** : Créer des notifications urgentes dans le SDR Hub pour prioriser les nouveaux leads et garantir le SLA 60–90s
- [ ] **Lucas** : Piloter la refonte du questionnaire high-close/tally pour capturer le nom d'entreprise
- [ ] **Boris** : Évaluer l'activation de l'option iClosed de blocage des réservations en double

**Risques & vigilances**
- Blacklist IP ou exclusions géographiques non documentées (Dubaï) peuvent bloquer des opt-ins légitimes
- Doublons de fiches HubSpot persistants si les prospects changent d'email entre opt-in et réservation
- Incohérences de nommage de campagne cassent les rapports et dashboards si pas de standard appliqué
- Plaintes commerciales récurrentes sur données HubSpot : besoin de formation ou problème systémique non clarifié
- Délai serré (30 septembre) pour atteindre le niveau d'insight requis sur le nouveau dashboard

Tags : #customer-io #dashboard #tracking-utm #hubspot #sla-sdr
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 25/08/2026 16:36 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a traité deux axes principaux : 1) un problème immédiat d’ingestion de données où les opt-ins d’un utilisateur spécifique n’apparaissent pas dans Customer.io, avec un plan de tests pour isoler la cause (navigation normale vs navigation privée, cache, VPN, IP, validation téléphonique, éventuels réglages d’exclusion, et escalade vers Adil si nécessaire) ; 2) la définition des besoins pour construire un tableau de bord interne plus fin, destiné à remplacer Looker et à suivre le tunnel publicités → leads → réservations → closes → appels → revenus avec une granularité supérieure. En parallèle, l’équipe a clarifié les exigences de tracking UTM, d’attribution des lead magnets, d’identifiant HubSpot / numéro de réservation, de déduplication des bookings, de SLA SDR (60–90 secondes), de mise à jour des questionnaires, et de documentation des conventions de nommage et de suivi afin d’améliorer l’alignement entre marketing, opérations et ventes.

📋 Outline

1. Problème immédiat d’ingestion de données avec un utilisateur spécifique • 0:01:40

- Les opt-ins d’un utilisateur précis ne sont pas enregistrés dans Customer.io, alors que d’autres utilisateurs et les propres tests de Boris apparaissent correctement dans le système. (Responsable : Boris).
- L’utilisateur concerné peut s’inscrire en navigation privée/incognito, mais pas en navigation normale, ce qui suggère un problème côté client : cache, blocage d’IP ou état du navigateur. (Responsables : Boris et Cedric).
- Le champ numéro de téléphone est obligatoire, mais un numéro incorrect ne bloque pas l’inscription à lui seul, car des tests avec de faux numéros ont tout de même généré des opt-ins. (Responsable : Cedric).
- Il existe une suspicion de blacklist IP ou d’exclusions basées sur la localisation ; des utilisateurs basés à Dubaï pourraient être affectés, même si Dubaï ne devrait pas être exclu selon les réglages actuels. (Responsable : Cedric pour vérification, Boris pour test avec Adil).
- Action : tester depuis le téléphone et l’ordinateur de l’utilisateur, avec et sans VPN, vider le cache, puis escalader à Adil pour vérifier d’éventuels réglages backend/exclusion ou règles de validation des numéros de téléphone. (Responsables : Boris et Cedric ; escalade vers Adil).

2. Plan de troubleshooting et tests immédiats pour isoler le problème • 0:03:17

- Boris partagera un lien de test unique afin que tout le monde exécute le même test et puisse confirmer si le problème est lié au lien ou à l’environnement. (Responsable : Boris).
- Cedric a proposé d’essayer manuellement plusieurs combinaisons arbitraires email/téléphone afin de confirmer le comportement de l’opt-in selon les environnements. (Responsable : Cedric).
- Si l’inscription fonctionne en navigation privée mais échoue en navigation normale, l’équipe investiguera en priorité le cache client, les extensions de navigateur ou un éventuel blocage IP. (Responsables : Boris et Cedric).
- Si le problème persiste, escalade vers Adil pour inspecter l’intégration / le système amont gérant les opt-ins ainsi que les exclusions de localisation ou de numéro de téléphone. (Responsable : Boris).

3. Tracking des lead magnets et défis d’attribution • 0:06:04

- Océ souhaite que les personnes qui opt-in pour un lead magnet soient automatiquement enregistrées pour l’événement et que Customer.io reçoive ces inscriptions via webhook ; cette partie fonctionne. (Responsables : Boris et Océ).
- Le point non résolu est le tracking et l’attribution de ces opt-ins de lead magnet à l’UTM de la publicité ou à la source d’origine, afin d’identifier quelles campagnes génèrent les conversions. (Responsable : Boris pour test).
- Les solutions proposées incluent l’ajout de paramètres UTM au lien du lead magnet, une redirection vers une URL taguée UTM avant l’ingestion dans Customer.io, ou le tagging de ces leads dans Customer.io pour une automatisation manuelle ou ultérieure. (Responsables : Boris pour tester UTM/redirection ; Cedric a proposé le tagging).
- Action : Boris réalisera des expériences avec des tags UTM et des redirections pour vérifier si les opt-ins du lead magnet conservent la source tout au long du flux ; si cela échoue, collaboration avec Adil pour une solution technique. (Responsable : Boris ; escalade vers Adil si besoin).

4. Avancement des dashboards et stratégie de remplacement de Looker • 0:08:32

- Boris a signalé des progrès sur les nouveaux dashboards 2.0 (main-to-scale) et a confirmé que la capture actuelle des opt-ins fonctionne, avec les champs UTM source / medium / campaign / content présents dans les tests. (Responsable : Boris).
- L’objectif est de remplacer Looker par un dashboard interne entièrement flexible, offrant davantage de granularité et de contrôle que Looker ne le permettait. (Responsable : Boris, avec les devs).
- L’équipe veut non seulement le volume d’opt-ins, mais une visibilité de bout en bout sur le tunnel : pubs → leads → réservations → closers → appels → revenus, y compris les conversions et les métriques de délai jusqu’à conversion par closer. (Responsables : Boris et Cedric pour le cadrage).
- Les dashboards doivent permettre des segmentations telles que nouveaux leads vs leads récurrents, opt-ins VIP, et les découpages par média/campagne déjà présents dans les tests actuels (segmentation au niveau UTM). (Responsable : Boris pour l’implémentation).
- Boris a insisté sur la nécessité de capturer à la fois des métriques de qualité au niveau lead et des données de booking/closing, notamment en intégrant iClosed ou les réponses de réservation pour mesurer l’impact bas de funnel. (Responsable : Boris pour l’intégration iClosed).

5. Bénéfices attendus d’un meilleur suivi publicités → revenus • 0:10:46

- Cedric a expliqué qu’un tracking complet des publicités jusqu’au revenu permettra d’identifier quelles créations publicitaires et quelles campagnes génèrent des rendez-vous, des no-shows ou des deals conclus, et de quantifier le revenu attribuable à chaque publicité. (Responsable : Cedric).
- Ces données permettront de reproduire les campagnes gagnantes et d’optimiser en privilégiant les publicités qui produisent des résultats à plus forte valeur, même si leur CPL est plus élevé. (Responsables : Cedric et l’équipe media).
- Le système doit conserver au minimum le même niveau de métriques historiques que Looker, voire davantage, et inclure un ratio opt-ins / questionnaires complétés / réservations pour mesurer la qualité des leads. (Responsable : Boris pour assurer la parité et les améliorations).

6. Collecte des besoins data et prochaines étapes • 0:13:44

- Boris a demandé un message ou document court et clair listant tous les points de données nécessaires, afin que l’équipe dev puisse implémenter les métriques sur l’ensemble des tunnels sans échanges prolongés. (Responsable : Boris).
- Cedric a accepté de produire un document détaillant tous les champs requis, le niveau de granularité attendu et les fonctionnalités de navigation souhaitées (par exemple, relier une ligne d’annonce à la création visuelle dans Meta). (Responsable : Cedric).
- Cedric a noté qu’une fonctionnalité secondaire idéale serait un lien cliquable depuis les lignes campagne / annonce du dashboard vers la vue de la création Meta, pour accélérer l’analyse, même si ce n’est pas prioritaire. (Responsable : Cedric ; Boris doit en évaluer le périmètre).
- Action : Cedric créera et transmettra le document de besoins data ; Boris et Raph / l’équipe dev implémenteront puis itéreront par funnel, en ajoutant des métriques supplémentaires entre les lancements si nécessaire. (Responsables : Cedric pour le document ; Boris et Raph / devs pour l’implémentation).

7. Dashboard centralisé et visibilité de bout en bout sur le tunnel • 0:14:25

- L’objectif est de disposer d’un espace unique pour visualiser la performance du tunnel, du marketing jusqu’à la livraison, afin de voir les conversions et les patterns de remboursement ; responsables : Boris et Cedric. .
- Le dashboard ne remplacera pas les analyses approfondies dans les outils sources, mais agrégera les indicateurs clés pour signaler les problèmes et déclencher des investigations complémentaires ; responsable : Boris. .
- Un objectif majeur est de relier les actions marketing aux résultats aval comme les clients complétés, les comptes impayés et les remboursements, même si la causalité directe peut être complexe ; responsable : Boris. .
- Des revues hebdomadaires du dashboard et des améliorations itératives de sa conception sont nécessaires pour atteindre le niveau d’insight requis avant l’échéance du 30 septembre ; responsables : Boris et Alec. .

8. Refonte du questionnaire et capture du nom de l’entreprise • 0:15:54

- Les questionnaires seront revus, en partie sous la conduite de Lucas, afin de capturer les champs manquants comme le nom de l’entreprise pour faire remonter cette donnée dans HubSpot ; responsables : Lucas et Cedric. .
- L’ajout du nom de l’entreprise dans le flux high-close / tally permettra d’alimenter les fiches HubSpot avec le nom de la société et de réduire les saisies manuelles côté ventes ; responsable : Cedric pour l’implémentation. .

9. Plaintes de l’équipe commerciale et besoin de suivi plus granulaire • 0:16:11

- Les responsables commerciaux ont indiqué que la donnée leur paraît peu fiable ou peu claire, avec des plaintes récurrentes sur des champs manquants ou difficiles à trouver dans HubSpot ; responsables : Cedric pour collecter le feedback et Boris pour traiter les problèmes systémiques. .
- Certains utilisateurs commerciaux ne maîtrisent pas des filtres simples (par ex. marquer les no-shows dans HubSpot), ce qui crée des écarts d’interprétation et des escalades inutiles ; responsables : managers sales et Cedric pour la formation et la documentation. .
- Cedric demande davantage de variables granulaires (par ex. le nom de l’entreprise) affichées automatiquement afin de vérifier si l’équipe commerciale utilise réellement les outils existants ou ne fait que prétendre les utiliser ; responsables : Cedric et product / ops. .

10. Standardisation UTM, tests et résultats de la campagne récente • 0:20:00

- Adil a mis en place le tagging UTM et des tests pendant la “week of killing”, et ce tagging a fourni une granularité meilleure que prévu, y compris une attribution au niveau du contenu. (Responsables : Adil et Boris).
- Le schéma UTM utilisé pendant cette campagne doit devenir la référence standard (par exemple : “Semaine du Scale”) pour tous les futurs liens afin d’assurer une cohérence des champs source / medium / campaign / content. (Responsables : Boris et l’équipe marketing).
- Des points de contrôle hebdomadaires sur la performance des UTM et l’intégration au dashboard sont nécessaires pour maintenir la qualité du tracking et guider les changements en aval. (Responsables : Boris, Cedric, Adil).

11. Stratégie d’identifiant HubSpot et numéro de réservation • 0:21:14

- Plutôt que de s’appuyer uniquement sur les adresses email, l’équipe attribuera un identifiant HubSpot / numéro d’ordre de réservation au moment de la prise de rendez-vous afin de suivre un prospect au fil des opérations et de la finance. (Responsables : Boris et opérations).
- Limitation actuelle : si un opt-in utilise une adresse email et que l’appel réservé en utilise une autre, deux fiches HubSpot peuvent être créées ; l’identifiant au niveau réservation est donc actuellement le lien le plus fiable. (Responsable : Boris).
- Le matching par numéro de téléphone peut aider à dédupliquer, mais produira toujours un certain taux d’erreur ; l’identifiant de réservation et les changements de process sont donc prioritaires. (Responsables : Boris et l’équipe data).

12. Prévention des réservations en double et paramètres de booking • 0:22:57

- IClosed propose une option pour empêcher les réservations en double pour le même événement lorsqu’un prospect a déjà un appel planifié, et l’équipe évalue l’activation de cette option. (Responsable : Boris pour décision).
- L’équipe a discuté des cas limites où des prospects re-réservent légitimement (par ex. conflit d’agenda), et l’impact UX de l’option de blocage des doublons doit être évalué. (Responsables : Cedric et Boris).

13. SLA de rappel SDR, mesure du time-to-lead et notifications • 0:23:48

- La nouvelle décision est d’exiger qu’un SDR appelle un lead ayant opt-in dans le flux Evergreen sous 60 à 90 secondes, et le time-to-lead doit être suivi comme KPI. (Responsables : Alexandre pour l’implémentation du tracking et managers SDR pour l’application).
- Alexandre a été prié de créer des notifications urgentes dans le SDR Hub afin de prioriser les nouveaux leads et garantir le respect du SLA. (Responsables : Alexandre et Raph pour l’implémentation).
- Cedric et Boris suivront l’efficacité SDR via le nouveau métrique time-to-lead et ajusteront l’effectif / les processus en conséquence. (Responsables : Cedric et Boris).

14. Documentation, conventions de nommage et processus partagés • 0:24:31

- Adil a un processus de tracking / nommage “en tête” et l’équipe a convenu de produire une vidéo Loom ou un document écrit pour que marketing, communication et opérations appliquent les mêmes conventions UTM et de nommage de campagne. (Responsables : Adil et Cedric pour la documentation).
- Les incohérences de nommage des campagnes dans HubSpot (par exemple des orthographes différentes pour le même événement) ont déjà cassé les rapports et les dashboards Looker ; une norme formelle de nommage et un propriétaire du process sont donc nécessaires. (Responsable : Cedric pour définir et faire appliquer les règles).
- Les membres de l’équipe comms (par ex. Océane, Charlotte) et Raph doivent avoir accès à la même documentation pour que chaque lien publié inclue source, medium, campaign et, idéalement, le champ content UTM. (Responsables : Cedric et Adil pour diffuser et former).
%% notes:fin %%
