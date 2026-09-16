---
type: call
date: 2026-09-16
source: sembly
participants: ["boris@entrepreneurs.com", "42lab@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Quentin X Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (16/09/2026 17:28).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 16/09/2026 17:28 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a fait le point sur l’avancement de la version V2, les correctifs de sécurité restants, la migration de Clap vers Ngram et la synchronisation HubSpot, ainsi que sur plusieurs déploiements : Success Core, exports NPS, gestion des paiements, module concierge et versions mobiles. Décisions principales : pousser les correctifs de sécurité au plus tard vendredi, déployer Success Core ce soir, viser la bascule Clap sous 4 à 10 jours et publier les mises à jour Android / Apple dans les 1 à 2 jours. Lors de la seconde partie de l’échange, l’équipe a aussi validé le lancement rapide des mises à jour App Store / Play Store et a commencé à structurer les flux de billetterie pour Scale 2027, tout en poursuivant les POC Moonshot et en clarifiant les options de monétisation de la plateforme.

📋 Outline

1. Correctifs de sécurité en attente après la sortie V2 • 0:01:28

- La version V2 est en ligne et quatre vulnérabilités de sécurité majeures ont été identifiées comme prioritaires à corriger.
- Quentin a déjà implémenté plusieurs correctifs, mais doit encore tester deux ou trois éléments et nettoyer du code d’intégration pour Calendly et cal.com avant de pousser.
- Quentin prévoit de valider et pousser les derniers correctifs au plus tard vendredi.
- Boris a rappelé l’échéance de vendredi et a indiqué qu’une fois les quatre points majeurs clos, le niveau de sécurité sera acceptable à court terme.

2. Migration de Clap vers Ngram et synchronisation HubSpot • 0:03:16

- La migration de Clap vers Ngram est en cours, avec un objectif ferme de basculer sous 4 à 10 jours afin d’éviter des problèmes opérationnels.
- Quentin a mené un audit de ce que Clap écrit dans HubSpot et de ce qui remonte dans l’autre sens, car une intégration HubSpot critique impacte Clap et entreprenance.works.
- La finalisation de l’intégration HubSpot reste le dernier blocage avant d’ouvrir Ngram plus largement.
- Boris a insisté sur l’urgence et a fixé l’attente d’une sortie rapide de Clap pour éviter les incidents.

3. État du module Success Core et plan de déploiement • 0:04:33

- Le module Success Core est développé, testé dans les parcours UX et peaufiné pour les cas limites liés au suivi de progression.
- Quentin prévoit de pousser les changements Success Core ce soir.
- Le module évite d’obliger les utilisateurs à ressaisir les jalons déjà passés lorsqu’ils rejoignent en cours de programme et gère la logique conditionnelle de re-questionnement des jalons.
- Boris a demandé une revue demain après le push et a proposé d’annoncer la sortie du module sur le prochain Wiki interne.

4. Captation des données d’usage et métriques pour Success Core • 0:05:39

- Boris souhaite pouvoir extraire des métriques d’usage, notamment le nombre de revues complétées par un client et la proportion de clients qui ont été sollicités puis ont effectivement terminé les revues.
- Quentin a confirmé qu’il peut ajouter ces métriques dans l’admin, sur le modèle des mécanismes d’export NPS.
- Boris prévoit d’exploiter ces données sur plusieurs mois après le lancement, typiquement 3 à 6 mois, pour éclairer les initiatives futures.

5. Exports NPS et alimentation des tableaux de bord • 0:06:51

- Les données NPS sont exportables en CSV avec un niveau de granularité par question et par utilisateur, et Quentin a déjà implémenté un mécanisme similaire pour d’autres exports.
- Boris a besoin de deux flux de données : un NPS historique pour l’accompagnement et un NPS pour la plateforme ; il transmettra l’export historique à son analyste.
- Quentin peut ajouter un accès direct / un flux vers ces métriques dans le dashboard ou l’admin via API, avec sécurité par jeton.
- L’admin inclut déjà des contrôles et un suivi des sollicitations (nombre de sauts, dernière date de report) ainsi que le décompte des réponses en attente, ce qui facilitera l’analyse des taux de complétion.

6. Gestion des impayés et éventuel flux Apple Pay • 0:10:44

- La pratique actuelle consiste à envoyer les clients vers le portail InPay, où la facture et la gestion du paiement sont traitées.
- Un contournement direct via Apple Pay est techniquement possible en générant un checkout Stripe lié à l’adresse e-mail du client et en traitant des webhooks pour mettre à jour Jordan / InPay.
- Quentin recommande de valider d’abord l’approche avec Jordan, notamment pour des raisons de traçabilité et de rapprochement comptable.
- Si Jordan approuve, l’équipe pourra mettre en place des liens de paiement à la demande avec Apple Pay et déclencher des webhooks de réconciliation dans le flux InPay.

7. Module concierge en production et comptes de messagerie • 0:12:32

- Le module concierge est en production et les comptes de messagerie ont été activés pour concierge, entreprendre, s’agir et support.
- Des échanges utilisateurs ont déjà eu lieu et des réponses ont été traitées, y compris des réponses de Sabrina.
- Tessie est informée et a peut-être pris en charge une partie des relances conversationnelles.

8. Plan de publication mobile sur Play Store et App Store • 0:13:29

- L’équipe a discuté de la possibilité de scinder la communauté en deux applications ou de conserver une seule application, et a décidé d’attendre avant de pousser Android afin de finaliser l’approche.
- Quentin a indiqué qu’après une session récente de réflexion, la publication Android a été mise en attente pour éviter de publier plusieurs versions.
- Android devrait être publié sous 1 à 2 jours, et une nouvelle version App Store (v1.01) intégrant la fonctionnalité communauté sera soumise.
- Boris a confirmé l’intention de publier sur Google Play et sur l’App Store Apple dès que les builds seront prêts.

9. Mise à jour App Store / Play Store • 0:14:31

- L’équipe enverra la mise à jour sur le Play Store et sur Apple dès que possible afin de débloquer les sorties applicatives et de synchroniser la mise à jour sur les deux stores.

10. Stratégie de billetterie pour Scale 2027 • 0:14:42

- Scale 2027 est prévu en avril et l’équipe estime devoir vendre environ 1 000 billets.
- La stratégie proposée repose sur des pop-ups bloquants ou non bloquants pour distinguer les personnes ayant déjà réservé, celles qui confirment leur présence et les nouveaux acheteurs.
- L’objectif est de capter les confirmations pour construire une liste de participants et permettre l’achat direct pour les autres.

11. Réutilisation du module immersif existant et du flux de paiement • 0:15:36

- Le module immersif actuel prend déjà en charge un flux similaire et la majorité des intégrations de paiement avec WAP sont déjà en place, ce qui réduit l’effort de développement.
- Le webhook de WAP confirme les paiements et débloque automatiquement l’accès à Scale sur la plateforme.
- Des ajustements UX sont nécessaires pour transformer la bannière / l’interface immersive en pop-up plus impactante pour Scale.

12. Travail préliminaire Moonshot et POC • 0:17:11

- L’équipe est en phase de brainstorming sur Moonshot et prépare plusieurs petits POC pour valider les approches techniques et les coûts avant de s’engager.
- Léonard teste des alternatives, notamment Little Bird et des solutions open source, afin de comprendre les mécanismes et d’optimiser les coûts en tokens.
- L’objectif est d’éviter des solutions prohibitivement coûteuses, avec un coût par client trop élevé.
- Un plan plus concret et une feuille de route sont attendus dans environ deux à trois semaines, après les POC en cours.

13. Assistant de coaching en direct et priorité de monétisation • 0:18:22

- L’assistant de coaching en direct est en phase de finalisation et constitue une fonctionnalité prioritaire à lancer avant des initiatives Moonshot plus larges.
- L’équipe doit décider comment rendre la plateforme génératrice de revenus sans cannibaliser les offres existantes.
- Un appel dédié à la monétisation / upsell sera organisé afin de structurer les options et d’alimenter les priorités produit d’octobre.

14. Options de monétisation et workflow d’upsell • 0:19:29

- Les idées de monétisation sont nombreuses et l’équipe doit veiller à ce que de nouveaux paywalls n’éloignent pas les diplômés récents des programmes.
- Le flux d’upsell proposé repose sur un processus alimenté par les ventes, avec un appel d’un CES pour présenter la poursuite des programmes plutôt qu’un paywall immédiat.
- Il n’existe actuellement aucune visibilité sur les métriques de conversion à l’upsell, et Quentin va examiner combien de clients ont plusieurs programmes afin d’estimer l’opportunité.

15. Freemium et propositions tarifaires Moonshot • 0:20:46

- Une offre freemium pourrait proposer une expérience d’onboarding légère et quelques fonctionnalités à forte valeur ajoutée sans coûts importants en IA / tokens.
- Moonshot pourrait être packagé avec un nombre réduit de sièges et proposé en option pour des collaborateurs supplémentaires, à environ 30 à 50 EUR par mois et par siège supplémentaire.
- L’offre Moonshot pourrait remplacer plusieurs preneurs de notes tiers et mettre en avant la sécurité des données françaises comme argument commercial.

16. Partenariats, revenus d’affiliation et monétisation des leads • 0:22:28

- La création d’intégrations partenaires et d’un annuaire de conseillers / fournisseurs pourrait générer des revenus d’affiliation ou de recommandation, par exemple avec des outils comptables comme Conto ou Pennylane.
- Des liens d’affiliation simples vers les outils recommandés pourraient fournir un revenu à faible effort pour financer la plateforme.
- La plateforme capte des leads de haute qualité via l’onboarding, ce qui peut être monétisé comme opportunités commerciales qualifiées pour les équipes internes ou les partenaires.

17. Revenue intelligence et fidélisation post-programme • 0:24:04

- La plateforme dispose déjà d’une fonctionnalité de revenue intelligence qui détecte les clients proches de la fin de leurs programmes de coaching afin de déclencher des actions de rétention ciblées.
- Une action de relance directe est suggérée pour convertir ces clients vers des programmes prolongés, par exemple un autre programme de scaling ou un incubateur.
- Quentin va analyser les données pour quantifier les clients ayant plusieurs programmes afin de prioriser le revenu de rétention.

18. Planification de l’appel monétisation / upsell avec Sabrina • 0:26:33

- Boris organisera un appel avec Sabrina pour discuter des flux d’upsell alimentés par les ventes et de la monétisation, afin que Sabrina mène l’échange commercial.
- Les participants sont tombés d’accord pour éviter les réunions conflictuelles et maintenir une discussion professionnelle et constructive.
- Le groupe a retenu le mercredi à 15h00 comme créneau alternatif disponible.

19. Vérifications finales, revue de la page coach et préparation au lancement • 0:27:51

- Boris enverra un message récapitulatif de la semaine précédente pour que Quentin le valide avant le lancement.
- Quentin a revu et amélioré la page destinée aux coachs, qui explique la nouvelle fonctionnalité afin de faciliter son adoption.
- Une fois tous les systèmes lancés, l’équipe confirmera sur le canal 42Lab puis procédera au déploiement.
%% notes:fin %%
