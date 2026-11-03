---
type: call
date: 2026-11-03
source: sembly
participants: ["boris@entrepreneurs.com", "sabrina.dahel@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Sabrina X Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (03/11/2026 14:49).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 03/11/2026 14:49 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe s’est alignée sur plusieurs chantiers opérationnels et CRM pour soutenir la montée en charge du VSL, des lancements et de l’activité SDR, tout en évitant les frictions liées au produit 5 jours et aux problèmes de qualité de leads. Les décisions principales portent sur le renforcement des seuils de qualification, la mise en place d’un nouveau flux lead/contact/deal dans le CRM, la correction du placement des formulaires et du routage, ainsi que la création de structures d’équipe dans iClosed et d’une organisation plus propre des calendriers et des pipelines. En parallèle, l’équipe a revu la disponibilité SDR, les objectifs de volume et de conversion, les écarts de performance observés sur les derniers mois, et a convenu de mener un post-mortem sur l’événement 3 jours et de nettoyer HubSpot.

📋 Outline

1. Seuil de qualification des leads et volume cible • 0:00:02

- L’équipe a convenu de cibler uniquement les leads au-dessus de 250 k€ (ou « plus de 250 ») afin de préserver un niveau de qualité élevé pour les efforts de montée en charge ; responsables : Sabrina et Alec.
- Raphaël a proposé d’augmenter les objectifs de 300–320 appels à 500 appels sur le mois, à condition que la qualification > 250 k€ soit bien respectée ; responsables : Raphaël et Alec.
- Sabrina a insisté sur le fait de refuser les leads sous le seuil, car ils ne correspondent pas au profil cible ; responsable : Sabrina.

2. Tableaux de bord et plan de montée en charge du VSL • 0:01:03

- Les tableaux de bord ont été mis à jour afin d’inclure une catégorisation des leads qui alimentera les décisions de scaling du VSL et les indicateurs de « high-close » ; responsables : Boris et les propriétaires analytics.
- La montée en charge du VSL s’appuiera sur les dashboards pour faire remonter automatiquement les leads à fort taux de closing et faciliter la prise de décision ; responsables : Boris et Rachid.

3. Risque de cannibalisation du programme 5 jours et préoccupations de staffing • 0:01:34

- Sabrina a signalé le risque que le programme 5 jours cannibalise la performance du VSL et surcharge les SDR, ce qui impose de vérifier les niveaux de staffing avant le lancement ; responsables : Sabrina et Rachid.
- L’équipe devra suivre les performances jour par jour après le lancement afin de détecter rapidement toute cannibalisation et d’ajuster l’allocation ; responsables : Sabrina et Rachid.
- Cédric a reçu un retour indiquant qu’il fallait corriger le rythme du contenu du 5 jours afin que les clients n’attendent pas une livraison complète en cinq jours et ne génèrent pas de friction après la vente ; responsables : Sabrina et Cédric.

4. Motivation des partenaires site et problèmes de qualité des leads B2B • 0:03:13

- Des retours indiquent que certains partenaires site, par exemple le pool de Kelly, ne souhaitent pas continuer en raison d’une qualité perçue comme trop faible ou de typologies de leads mal alignées ; responsables : Lucas et les opérations.
- Le ciblage actuel du quiz / des lancements semble générer davantage de leads B2C, ce qui réduit l’adéquation avec les partenaires site orientés B2B et complique les placements ; responsables : Boris et le marketing.
- L’équipe doit relever la qualité des leads pour retenir et recruter des partenaires site, faute de quoi le sourcing deviendra plus difficile ; responsables : Sabrina et Lucas.

5. Mise en place du nouveau flux CRM lead/contact/deal • 0:03:49

- Un nouvel objet intermédiaire « lead » a été ajouté entre le contact et le deal afin de capturer les opt-ins issus des funnels et de conserver des données SDA propres pour les SDR ; responsables : Boris et l’équipe CRM.
- Tous les funnels Evergreen et de lancement ont été branchés sur le nouveau flux, à l’exception du site web qui doit encore être finalisé ; responsable : Boris (finalisation du site web).
- Le nouveau flux créera un contact unique par personne, plusieurs cartes lead par interaction avec un funnel, et plusieurs transactions par appel réservé, tout en conservant le lien avec le même contact pour assurer la traçabilité ; responsable : équipe CRM.

6. Suivi iClosed et génération de liens basée sur le propriétaire • 0:05:22

- Lorsqu’un SDR s’attribue la propriété d’un lead, le système génère automatiquement un lien iClosed tracké incluant la source, le support et la campagne UTM ; responsables : SDR et équipe CRM.
- Le lien iClosed ouvre le formulaire de transaction, ce qui permet au SDR de saisir les détails de la vente et de voir toute transaction déjà associée ainsi que son stade ; responsable : SDR propriétaire du lead.
- Cette automatisation supprime le tag manuel et devrait améliorer la précision du tracking si les SDR définissent correctement la propriété ; responsables : SDR et Boris.

7. Champ société, source des données de facturation et création de transaction • 0:08:02

- Le champ société ne se remplit plus automatiquement car le funnel ne le demande plus, ce qui crée des lacunes dans les fiches CRM de société ; responsables : Boris et les propriétaires des formulaires.
- Les données d’adresse et les données légales liées à la facturation sont capturées dans le contrat (OneFlow) et ne sont pas nécessaires au moment de la création de la transaction dans le CRM ; responsable : équipe ventes et contrats.
- Sabrina a demandé d’ajouter au minimum le nom de la société automatiquement afin d’aider à automatiser la validation des transactions (« won/lost ») et de permettre aux commerciaux de clôturer sans intervention manuelle du support ; responsable : Boris à évaluer et à implémenter.

8. Structure du quiz, champs obligatoires et visibilité de la lead card VSL • 0:11:42

- Les champs finaux du quiz doivent être revus avec Raphaël afin de décider ce qui est obligatoire, puisque les réponses du quiz pilotent le routage et la qualification ; responsables : Sabrina et Raphaël.
- Les commerciaux ont besoin d’une lead card visible dans le CRM affichant directement les réponses du quiz, afin d’éviter des navigations supplémentaires et d’accélérer les décisions de qualification ; responsable : Boris pour l’ajout de la lead card et Sabrina pour la validation de la mise en page.
- Un point de confusion existe autour du texte auto-généré de « plan d’action » dans certaines fins de quiz, qui pourrait induire les prospects en erreur ; le wording et les sorties doivent être revus pour éviter de fausses attentes ; responsables : Sabrina et les propriétaires produit/contenu.

9. Placement du formulaire avant la réservation, erreurs de routage et routages manquants • 0:14:05

- Point critique : certains funnels placent le questionnaire après la réservation de l’appel, ce qui empêche de collecter les données nécessaires avant le routage et provoque de mauvaises conversions ; responsables : Boris et Raphaël pour corriger le placement du formulaire.
- Sabrina a identifié des règles de routage manquantes pour les leads en dessous de 250 k€ sur iClosed, ce qui a entraîné l’absence de routage sur certaines plages de leads ; responsables : Sabrina et le propriétaire CRM/routage pour corriger les correspondances.
- L’équipe doit s’assurer que les formulaires collectent toujours les données de qualification avant la réservation afin de permettre un routage correct et d’éviter de gaspiller le temps des SDR ; responsables : Raphaël, Alec et les propriétaires de funnels.

10. Multiplication des liens calendrier iClosed et demande de création d’équipes • 0:16:10

- Le système génère actuellement un grand nombre de liens calendrier iClosed, ce qui doit être limité et nettoyé afin de réduire le bruit ; responsables : Boris et les propriétaires calendrier/configuration.
- Sabrina a demandé une formation ou un guide sur la création d’équipes dans iClosed (par exemple Team A, Team B) afin que les propriétaires puissent être assignés par équipe plutôt que de sélectionner des individus un par un ; responsables : Boris pour la démonstration et l’admin CRM pour l’implémentation des équipes.
- La création d’équipes dans iClosed simplifiera l’assignation et le routage tout en réduisant les erreurs de sélection manuelle lors de l’allocation des leads ; responsables : admin CRM et management SDR.

11. Utilisation de la nouvelle fonctionnalité « Assign to Team » dans le routage • 0:16:36

- Une nouvelle option « assign to team » existe désormais dans le routage conditionnel, ce qui permet une affectation au niveau équipe plutôt qu’au niveau individuel ; responsable : Boris.
- Le menu User management > Teams est l’endroit où les équipes sont créées et modifiées dans la plateforme ; responsable : Boris.
- Sabrina a indiqué qu’elle n’aurait peut-être pas immédiatement les droits nécessaires pour créer des équipes et vérifiera ses accès dans les paramètres ; responsable : Sabrina.
- Boris a recommandé de supprimer les équipes inutilisées et de recréer des groupes propres Team A / Team B / Team C pour simplifier les affectations ; responsable : Boris.

12. Documentation et droits d’accès dans le Wiki • 0:18:19

- Sabrina créera un dossier dans le Wiki interne nommé « Teams » pour documenter la composition des équipes et les processus ; responsable : Sabrina.
- Sabrina donnera à Boris et Alec l’accès à ce dossier Wiki afin que l’équipe puisse répartir le travail sans devoir faire intervenir Boris à chaque fois ; responsable : Sabrina.

13. Calendriers, préparation technique et tâches restantes • 0:18:46

- Boris a insisté sur la nécessité de remplir tous les calendriers en priorité pour garantir la préparation opérationnelle ; responsable : Boris.
- Dans l’ensemble, la configuration technique des SDR est presque prête, avec encore la configuration DSL et des corrections du site web que Boris prendra en charge ; responsable : Boris.

14. Disponibilité SDR et capacité individuelle • 0:19:18

- Les membres de l’équipe ont communiqué leur disponibilité : Nathan 4–5 appels/jour, Jérôme à temps plein en novembre, Alexandre 2–3 heures, Diane indisponible ce mois-ci, Walid à temps plein, Lucas visant le recrutement de 10–15 commerciaux ; responsable : Sabrina.
- L’équipe prévoit de répartir les appels entre les SDR et comptera sur Rachid pour une part importante de la génération des appels du soir et post-live ; responsable : Sabrina.

15. Volume de leads, projections d’appels et objectifs de conversion • 0:19:57

- La cible de leads pour l’événement est d’environ 1 200 leads, avec un scénario optimiste à 1 500 leads ; responsable : Sabrina.
- Si le panier moyen visé est de 4 000 € et que la conversion est de 15 %, le chiffre d’affaires projeté atteint 900 k€ sur 1 500 leads ; des volumes d’appels plus faibles réduiront cette estimation ; responsable : Sabrina.
- Boris estime que le volume d’appels SDR élevé aidera à atteindre les objectifs maintenant que les systèmes sont stabilisés ; responsable : Boris.
- Sabrina et Boris se sont accordés sur un résultat plus conservateur : environ 1 000 appels et une conversion proche de 10 %, ce qui réduirait fortement la prévision de revenus ; responsables : Sabrina et Boris.

16. Tendances de données et baisse observée des performances • 0:22:30

- L’équipe a constaté une hausse des segments « no activity » et une baisse des poches de deals de milieu de gamme au cours des derniers mois ; responsable : Sabrina.
- Les taux historiques d’opt-in et de complétion après opt-in, qui pouvaient masquer ou déformer les impressions de conversion précédentes, étaient d’environ 25–30 % de complétion ; responsable : Sabrina.
- Boris a suggéré qu’une partie de la baisse perçue peut être due à un meilleur tracking centralisé qui révèle le vrai niveau de base ; responsable : Boris.
- Le taux de conversion par tranche de revenus a diminué ; un exemple donné montre un passage de 28 % en mars pour l’ICP 500 k€–3 M€ à 13 % en septembre ; responsable : Sabrina.

17. Récupération et standardisation des données historiques pour l’analyse • 0:25:27

- Sabrina a recommandé d’analyser une période cohérente, idéalement de janvier à octobre, afin de comparer la performance sur l’année et d’identifier les points d’inflexion ; responsable : Sabrina.
- Boris tentera de récupérer les données historiques, tout en avertissant que l’extraction d’anciennes données pourrait être difficile ; responsable : Boris.
- Alec avait précédemment noté un événement de passation en mars qui pourrait expliquer une anomalie détectée, il faut donc intégrer la date de handover dans l’analyse ; responsable : référence à Alec.

18. Impact du turnover et de l’événement Kelly sur les opérations • 0:26:12

- Les turbulences de mai liées à « Kelly » et le turnover qui a suivi ont perturbé de manière significative les flux de leads / résidus et la stabilité de l’équipe ; responsable : Sabrina.
- L’équipe a convenu que plusieurs facteurs — turnover, changements de délégation et dégradation du profil des leads — ont contribué à la baisse de motivation et de performance au closing ; responsables : Sabrina et Boris.

19. Moral des ventes, répartition de la qualité des leads et problèmes d’assignation • 0:29:13

- Les ventes ont subi une mauvaise répartition des leads lors des événements précédents, avec des exemples de gros volumes de leads faibles ayant créé de la frustration, par exemple Walid recevant des leads de faible valeur ; responsables : Boris et Sabrina.
- Sabrina a ajusté le pricing et les règles d’acceptation pour l’événement 3 jours afin de privilégier les leads à plus forte valeur et d’éviter d’attribuer aux commerciaux des leads de faible qualité ; responsable : Sabrina.
- Certains commerciaux ont signalé de mauvaises performances historiques sur Evergreen et sur les semaines de scaling à cause d’une mauvaise allocation des leads ; responsable : Boris.
- L’équipe a convenu de conserver Alec comme relecteur neutre pour collecter des retours non biaisés et décider d’actions correctives si ces retours concordent avec les observations internes ; responsable : Sabrina.

20. Suivi des statistiques précoces de l’événement et blocages de travail intensifs • 0:30:19

- Boris s’attend à voir les premières statistiques sur la qualité des leads et les performances d’ici la fin de la semaine et souhaite les examiner rapidement ; responsable : Boris.
- Il a proposé un bloc de travail ciblé, en fin de semaine ou au début de la semaine suivante, pour nettoyer et optimiser HubSpot ainsi que les processus opérationnels ; responsable : Boris.
- Boris planifiera une session de deux heures, similaire à celle faite avec Rachid, pour traiter plusieurs sujets et ajoutera la réunion au calendrier de Sabrina ; responsable : Boris.

21. Nettoyage du pipeline HubSpot et post-mortem de l’événement 3 jours • 0:31:38

- Le pipeline commercial dans HubSpot est globalement propre, mais il reste encore des appels à traiter ; responsable : Sabrina.
- Sabrina mènera un post-mortem de l’événement 3 jours avec l’équipe externe mardi et partagera les enseignements ainsi que le pipe de l’équipe externe ; responsable : Sabrina.
- Boris a demandé à Sabrina d’envoyer le post-mortem et les livrables du pipeline afin qu’il puisse conserver une trace et assurer le suivi ; responsables : Boris et Sabrina.
%% notes:fin %%
