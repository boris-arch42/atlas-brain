---
type: call
date: 2026-08-26
source: sembly
participants: ["[[Boris Arduy]]", "lea@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-08-26
---

# Résolutions problèmes Sales

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (26/08/2026 15:58).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 26/08/2026 16:06 — corrige librement hors des marqueurs.

**Résumé** — Call opérationnel couvrant les problèmes d'accès Slack et Aiko, l'alignement des données entre HubSpot/iClose/Hotspot/Looker, et la refonte des dashboards Sales. Décision de maintenir Hotspot comme CRM principal et de traiter les upsells comme transactions séparées.

**Décisions**
- Maintenir Hotspot comme CRM principal jusqu'à nouvel ordre, Boris étudie en parallèle un CRM custom
- Traiter les upsells comme des transactions séparées plutôt que de remplacer le contrat existant
- Créer des one-pagers PDF par funnel avec promesse, landing page, parcours et campagnes
- Rebuild complet des dashboards Looker avec deadline au 30 septembre 2026
- Workflow fiches de poste Aiko : Léa prépare, Boris valide et publie
- Ajouter le champ historique entreprise à tous les questionnaires iClose

**Actions**
- [ ] **Boris** : Renvoyer invitations Slack à Nathan et Walid après confirmation déblocage support
- [ ] **Léa** : Confirmer résolution graylist Slack côté support
- [ ] **Boris** : Ajuster permissions Aiko pour Léa et investiguer erreurs création mandates
- [ ] **Boris** : Fermer mandates terminés dans Aiko pour libérer emplacements
- [ ] **Boris** : Documenter règles de routage iClose par événement
- [ ] **Boris** : Demander à Raph production one-pagers funnel (promesse, landing, parcours, campagnes)
- [ ] **Boris** : Corriger mappings propriétés HubSpot/iClose (UTM, funnel, Bookfunnel, Quizfunnel) (échéance 2026-09-30)
- [ ] **Boris** : Rebuild dashboards Looker avec granularité closer et conventions nommage alignées (échéance 2026-09-30)
- [ ] **Boris** : Préparer documentation processus et visualisation flux Marketing/Sales/Ops (Miro) (échéance 2026-09-30)
- [ ] **Boris** : Implémenter champ historique entreprise dans questionnaires iClose
- [ ] **Boris** : Contrôler disponibilités calendriers iClose (Fatima, Chamzingui)
- [ ] **Léa** : Coordonner avec Aziz évaluation alertes calendriers vides iClose
- [ ] **Boris** : Auditer licences Hotspot inactives et récupérer si possible
- [ ] **Boris** : Formaliser process upsells avec Léa (transactions séparées)
- [ ] **Boris** : Standardiser workflows et noms campagnes/événements avec Marketing et Data
- [ ] **Boris** : Ajouter recherche par téléphone et e-mail dans SDR Hub
- [ ] **Léa** : Investiguer push données vers Aircall pour affichage noms appelants
- [ ] **Léa** : Vérifier avec Marketing et Wassim travail déjà fait sur outils suivi commercial

**Risques & vigilances**
- Période d'instabilité data d'un mois prévue liée au départ en Asie de Boris
- Manque de licences Hotspot bloque l'onboarding de nouveaux closers
- Incohérences de nommage campagnes/événements entre Marketing et Sales créent confusion reporting
- Process upsells non formalisé alors que volume attendu en augmentation
- Pas d'alerte configurée pour calendriers iClose vides longue période

Tags : #sales-ops #crm-data #dashboards #iclose #hubspot #looker
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 26/08/2026 15:58 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

La réunion a couvert plusieurs chantiers opérationnels et data. D’abord, des problèmes d’invitation Slack pour deux utilisateurs ont été identifiés et une relance côté support Slack puis côté Boris a été actée. Ensuite, l’accès et les permissions dans Aiko ont été revus afin que Léa puisse créer, valider et suivre les fiches de poste et mandates, avec un workflow clarifié entre Léa et Boris. La discussion a aussi porté sur iClose, sa logique de routage par événement, la visibilité des équipes, les questionnaires, les calendriers et les alertes de disponibilité. Un autre bloc important a concerné l’alignement des données et du tracking entre HubSpot, iClose, Hotspot/Hotspot, Looker, SDR Hub, Aircall et OS/wiki : besoin d’une normalisation des UTM et des noms de campagnes, d’un rebuild des dashboards, d’une documentation des process, et d’une meilleure visibilité des funnels pour les équipes Sales et Marketing. Enfin, des décisions ont été prises sur la gestion des upsells comme transactions séparées, le maintien de Hotspot comme CRM principal pour l’instant, ainsi que sur la capacité de licences, la recherche dans SDR Hub et l’intégration Aircall.

📋 Outline

1. Invitations Slack pour Nathan et Walid • 0:00:00

- Deux comptes utilisateurs, Nathan et Walid, avaient été supprimés puis réintégrés, mais n’ont pas reçu les invitations Slack car Slack les a placés sur une graylist.
- Léa a déjà contacté le support Slack pour débloquer la situation.
- Léa a partagé les adresses e-mail des deux utilisateurs dans la conversation, avec l’attente qu’une nouvelle invitation envoyée par Boris atteindra bien ces boîtes mail.
- Responsabilités : Léa confirme la résolution côté Slack ; Boris renvoie les invitations et vérifie leur bonne réception.

2. Permissions Aiko et création de mandates • 0:01:30

- Léa a signalé ne pas pouvoir créer de nouvelles annonces ni accéder correctement aux flux candidats dans Aiko, ce qui indique un manque de permissions.
- Boris a ajouté Léa à deux annonces, dont une annonce Refresh, et a montré comment créer un New Mandate puis le partager pour permettre l’édition et la validation de la fiche de poste.
- Le workflow retenu est le suivant : Léa prépare la fiche de poste, peut soit la créer dans Aiko pour validation par Boris, soit l’envoyer à Boris pour qu’il la crée et la partage ensuite.
- Une fois la fiche validée, Boris publie l’annonce, notamment sur la page vitrine LinkedIn.
- Un blocage temporaire a également été observé lors de la création de mandates supplémentaires, possiblement lié à une limite d’annonces actives ; l’équipe devra fermer les mandates terminés pour libérer des emplacements.
- Responsabilités : Boris ajuste les permissions, investigue les erreurs de création et publie ; Léa valide les fiches de poste et signale les besoins d’accès.

3. Routage iClose et visibilité des équipes • 0:08:00

- IClose fonctionne avec une logique de visibilité par événement et de routage conditionnel, plutôt qu’avec des objets d’équipe explicites.
- Les règles sont définies par événement, par exemple via des tranches de revenu qui attribuent certains leads à des personnes précises.
- Léa souhaitait voir une visibilité de type Team A/B/C dans iClose ; Boris a expliqué que l’assignation se fait surtout par règles de routage et sélection manuelle des membres concernés.
- Boris a montré comment ajouter des membres spécifiques pour traiter des événements au-dessus de certains seuils de revenu.
- Pour les événements sans champ de question, le routage conditionnel basé sur des propriétés comme le revenu n’est pas possible ; il faut donc utiliser des événements qui incluent des questions ou adapter leur structure.
- Responsabilités : Boris documente les règles de routage existantes et ajuste les événements si nécessaire ; Léa vérifie les affectations d’équipe.

4. Besoin de contexte funnel pour les équipes Sales • 0:10:26

- Les SDR et les closers ont besoin de contexte sur chaque funnel : promesse de la page, contenu vu par le lead, logique de campagne et parcours suivi.
- Boris a proposé de créer des one-pagers par funnel, au format PDF, présentant la promesse initiale, la landing page, les achats possibles, la logique de résultat, les outils et ressources, ainsi que les campagnes e-mail reçues.
- Léa a demandé s’il serait possible de centraliser des liens cliquables vers les sources de contenu dans iClose ou Azure Hub ; Boris a indiqué que les limites d’iClose rendent cela difficile.
- L’option recommandée est donc de stocker les documents détaillés et les processus dans Works/OS, puis de les utiliser comme référence pour les équipes.
- Responsabilités : Boris demande la production de ces documents à Raph ; Marketing produit les one-pagers ; Sales et Léa s’y réfèrent.

5. Écarts de données entre HubSpot, iClose, Hotspot et Looker • 0:12:58

- Léa a constaté des incohérences de funnel et d’UTM entre HubSpot, iClose et Looker, avec certains leads UTM-tagged mais sans affichage de funnel/UTM dans iClose.
- Boris a indiqué que certaines propriétés sont actuellement cachées ou mal mappées et qu’il doit corriger les mappings.
- Il reconstruit également les dashboards Looker de zéro afin de refléter correctement la performance par closer et de corriger les champs manquants.
- La phase de transition explique une partie du désordre temporaire et des données incomplètes.
- Le funnel est censé être porté par le champ de campagne UTM, et les correctifs récents doivent enrichir iClose avec des identifiants tels que Bookfunnel ou Quizfunnel.
- Responsabilités : Boris poursuit les corrections et le rebuild Looker ; l’équipe Data assiste ; Sales vérifie les nouveaux leads.

6. Cartographie de process et alignement des dashboards • 0:18:53

- Léa a demandé une représentation visuelle du flux de bout en bout, par exemple sous forme de Miro, pour relier Marketing, Sales (SDR et closers) et Ops.
- L’objectif est de visualiser comment s’articulent les événements, les UTMs, iClose, SDR Hub et Hotspot.
- Boris s’est engagé à préparer une documentation des processus et des règles UTM, ainsi qu’un rebuild des dashboards par funnel avec des conventions de nommage et des métriques cohérentes.
- Les conventions actuelles diffèrent entre Marketing et Sales, ce qui crée des écarts de lecture et de suivi.
- Le résultat attendu est un ensemble de dashboards réconciliés et des one-pagers funnel permettant aux SDRs/Closers de s’auto-servir en contexte et d’escalader vers Marketing lorsque nécessaire.
- Responsabilités : Boris produit la documentation et la visualisation ; Marketing et Sales alignent la nomenclature.

7. Échéance de mise à jour data et dashboards • 0:20:29

- Les dashboards présentés par Boris doivent progressivement remplacer Looker car ils seront plus précis.
- L’objectif annoncé est d’avoir toutes les données à jour au 30 septembre.
- Une période d’instabilité d’environ un mois est attendue, liée au départ en Asie.
- Responsabilités : Boris pilote la mise à jour et la transition ; les équipes doivent anticiper une phase de fluctuation.

8. Ajouter l’historique d’entreprise dans les questionnaires iClose • 0:20:56

- Le champ d’historique de l’entreprise doit être ajouté à tous les questionnaires iClose, conformément à la demande du marketing.
- Marketing a déjà été informé de réintégrer ce champ lorsque c’est nécessaire.
- Responsabilités : Boris implémente le champ ; Marketing s’assure de sa présence dans les questionnaires concernés.

9. Calendriers iClose, priorités et alertes • 0:21:45

- IClose permet de définir des priorités par closer et par événement, avec une segmentation qui s’applique avant l’ordre des priorités.
- Certains closers, comme Fatima et Chamzingui, n’ont pas de disponibilité renseignée dans iClose, ce qui les empêche d’être bookés.
- La donnée de disponibilité doit donc être vérifiée et complétée.
- Aucune alerte n’est actuellement configurée pour prévenir lorsqu’un calendrier reste vide trop longtemps ; le besoin d’un tel mécanisme a été soulevé.
- La logique actuelle affiche les jours ouverts, mais pas les longues périodes sans créneaux, par exemple un mois et demi sans slot visible.
- Responsabilités : Boris contrôle les disponibilités ; Léa coordonne avec Aziz et l’équipe technique pour évaluer les alertes et la stratégie de priorisation.

10. Manque de licences Hotspot • 0:24:10

- L’équipe n’a plus de licences Hotspot disponibles ; une seule a été récupérée depuis Sabrina.
- Il n’est donc pas possible d’ajouter de nouveaux closers sans acheter des licences supplémentaires ou récupérer des licences inactives.
- Une pression similaire existe sur d’autres outils, comme Clap ou Oasis, et l’équipe Sales a atteint ses limites d’allocation actuelles.
- Responsabilités : Boris audite les utilisateurs et récupère les licences inactives si possible ; Léa signale l’impact commercial.

11. Gestion des upsells, transactions et outils comptables • 0:25:24

- Le fonctionnement actuel consiste à remplacer le contrat sur la même transaction lors d’un upsell, mais Penny Lane ne lit que le premier contrat et ne capte pas correctement les détails de l’upsell.
- La tendance discutée est de traiter les upsells comme des transactions séparées afin de ne pas perdre la date d’origine et de refléter les montants correctement.
- En attendant, un contournement manuel consiste à générer un contrat/PDF dans Onflow et à l’envoyer à la comptabilité, via Penny Lane, lorsque les upsells deviennent fréquents.
- L’équipe ne dispose pas encore d’un process opérationnel formalisé pour les upsells, alors que ceux-ci devraient augmenter avec la montée en gamme des programmes d’entrée de gamme vers des offres plus élevées.
- Responsabilités : Boris formalise le process avec Léa ; Boris fournit les informations manuelles à Angèle si nécessaire.

12. Exactitude de Looker et conventions de nommage • 0:29:42

- Looker reste utilisé pour vérifier les transactions bloquées, mais ses chiffres et sa granularité funnel ne sont pas totalement à jour.
- Des incohérences de nommage existent entre campagnes et événements, par exemple entre « bootstrap » et « method ».
- Un exemple a été cité où Anthony Bourbon apparaît sous juillet 2025 au lieu de 2026 à cause de conventions de méthode/nommage.
- La mise en place d’un workflow standardisé pour les noms de campagnes et d’événements permettrait de réduire la confusion dans le reporting.
- Responsabilités : Boris standardise les workflows et les noms ; Marketing et Data s’alignent sur la convention commune.

13. Fonctionnalités de recherche dans SDR Hub et visibilité de l’historique client • 0:31:43

- Le SDR Hub prend actuellement en charge la recherche par e-mail et, prochainement, par téléphone.
- Léa a observé que seule la recherche par nom semblait fonctionner pour elle ; Boris a confirmé qu’il allait ajouter les recherches par téléphone et e-mail.
- Des clients déjà existants étaient exclus de la liste SDR ; un changement récent a réactivé la détection par e-mail pour filtrer les clients récurrents.
- L’identification dans le SDR Hub repose sur le matching d’e-mail et doit servir à éviter de recontacter des clients existants.
- Responsabilités : Boris complète les fonctionnalités de recherche ; l’équipe SDR utilise le matching e-mail pour éviter la sur-sollicitation.

14. Intégration Aircall et identification de l’appelant • 0:33:29

- Aircall est connecté au SDR Hub et peut être utilisé pour appeler depuis le hub.
- Un problème a été relevé : lorsqu’un SDR appelle un prospect sans réponse, puis que le prospect rappelle, le numéro affiché ne montre pas toujours le nom du prospect dans Aircall.
- Un push de données vers Aircall pourrait être nécessaire pour afficher automatiquement les noms.
- L’ajout du numéro de téléphone dans les enregistrements permettra au moins une recherche rapide par les SDRs.
- Responsabilités : Léa investigue l’envoi de données vers Aircall ; Boris apporte son support technique.

15. Stratégie CRM — conserver Hotspot pour l’instant • 0:34:45

- La décision prise est de continuer à utiliser Hotspot comme CRM principal jusqu’à nouvel ordre.
- Boris étudie en parallèle les options pour construire un CRM sur mesure.
- Sales utilisera ponctuellement iClose pour le suivi des no-shows et la prise de rendez-vous, mais le travail CRM principal reste dans Hotspot.
- Responsabilités : Boris évalue l’option CRM custom ; Sales continue d’opérer dans Hotspot.

16. Coordination marketing, OS/wiki et suivi des demandes • 0:35:26

- Le marketing et la communication ont accès à l’OS/wiki de l’entreprise ; il faut donc vérifier les outils et processus déjà existants avant de dupliquer les efforts.
- Léa construit un outil spécifique de suivi commercial avec Wassim et doit confirmer si Marketing a déjà commencé un travail similaire afin d’éviter les redondances.
- Pour les problèmes et demandes de reporting, Léa continuera à envoyer les éléments de manière informelle pour le moment, avec la possibilité de basculer vers des tickets sur un board si Boris préfère ce mode de fonctionnement.
- Responsabilités : Léa vérifie avec Marketing et Wassim ; Boris confirme le canal de suivi à privilégier.
%% notes:fin %%
