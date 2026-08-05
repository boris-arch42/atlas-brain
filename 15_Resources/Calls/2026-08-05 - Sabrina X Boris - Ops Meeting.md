---
type: call
date: 2026-08-05
source: sembly
participants: ["boris@entrepreneurs.com", "sabrina.dahel@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Sabrina X Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (05/08/2026 11:33).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 05/08/2026 11:33 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a constaté que la plateforme ne couvre pas encore les besoins essentiels de suivi, de tableaux de bord et de simplicité d’usage, ce qui génère beaucoup de travail manuel pour les opérations, des calculs de coûts inexacts et une perte de clients en début de parcours. Il a été décidé de structurer précisément les besoins en données étape par étape, puis de les intégrer à la roadmap produit afin que Quentin et l’équipe engineering puissent les implémenter dans la plateforme. En parallèle, la réunion a abordé la gestion du churn, l’usage du Hops Cockpit comme source unique de pilotage des projets, la clarification des responsabilités, et quelques urgences clients et facturation. Actions clés : Boris doit consolider les données à capturer, Sabrina fournir des exemples et contournements existants, Quentin/devs estimer et implémenter, et Christelle/sales suivre les métriques de churn.

📋 Outline

1. Confusion dans la passation et documentation existante du projet • 0:00:00

- Sabrina a confirmé que les supports projet et les échanges précédents existent déjà et ont été transmis à l’équipe ; elle n’a pas pour rôle de contrôler à qui les transferts sont envoyés. (Responsable : Sabrina).
- Elle a indiqué avoir transmis rapidement les documents demandés à Alice, car tout avait été préparé depuis six mois. (Responsable : Sabrina).
- Sabrina a aussi signalé que le processus de passation a créé des doublons de travail, les documents ayant été envoyés à plusieurs personnes, ce qui a généré des frictions. (Responsable : Sabrina).

2. Absence de tableaux de bord et consolidation manuelle des données • 0:00:32

- Sabrina passe environ deux heures par semaine à consolider des sources de données disparates pour produire les reportings de fin de semaine, faute d’outil centralisé de reporting sur la plateforme. (Responsable : Sabrina).
- La plateforme ne stocke pas et n’affiche pas des métriques opérationnelles clés, comme le coût de livraison par session, ce qui oblige à faire des calculs manuels client par client. (Responsable : Plateforme / Engineering).
- Sabrina doit vérifier les dossiers client par client ainsi que les taux de rémunération des coachs selon les pays, car les chiffres de la plateforme sont erronés ou incohérents, ce qui fausse le coût réel de livraison. (Responsable : Sabrina ; à escalader à Quentin / Engineering).

3. Données de rémunération des coachs incorrectes et impact sur le reporting de coût • 0:01:07

- La plateforme affiche des tarifs génériques de coachs, par exemple 80 €, alors que les tarifs réels varient fortement (exemples : Nicolas 70 €, Mathieu 160 €), ce qui rend les coûts reportés trompeurs. (Responsable : Sabrina ; à vérifier avec Payroll / Finance).
- Comme les structures de paiement diffèrent (par session, par paliers, forfait), l’absence de métadonnées de rémunération fiables empêche de calculer le vrai coût de livraison et provoque des pertes pour certains coachs rémunérés au forfait. (Responsable : Sabrina ; Product / Engineering).
- Sabrina a construit un outil HTML externe pour calculer la rémunération mensuelle des coachs comme solution temporaire, mais cela crée un outil isolé supplémentaire et n’est pas soutenable. (Responsable : Sabrina).

4. Propriété de la plateforme et contraintes de roadmap (capacité développeur) • 0:02:56

- Quentin est le développeur qui travaille sur ces corrections de plateforme, mais il n’a actuellement pas le temps d’implémenter des changements complets ; il priorise pour l’instant le suivi basé sur les sessions. (Responsable : Quentin / Engineering).
- Sabrina a reconnu que Quentin fait de son mieux, mais que les changements nécessaires prennent du temps et devront être intégrés comme priorités dans la roadmap produit. (Responsable : Sabrina ; Product).
- Boris a insisté sur le fait que ces problèmes doivent être résolus dans la plateforme elle-même, et non via des outils ad hoc ou des tableaux de bord séparés. (Responsable : Boris / Product).

5. Processus de décision interne et problèmes de cadrage du périmètre • 0:03:12

- Sabrina a signalé un problème récurrent : les membres de l’équipe peuvent dire non à certaines demandes, mais Alec contredit parfois ces refus et pousse malgré tout le travail, même lorsque les conséquences sont déjà visibles. (Responsable : Alec ; observé par Sabrina).
- Cette dynamique a conduit à surcharger certains contributeurs, par exemple la responsable communauté, et à ne plus avoir la bande passante nécessaire pour accepter de nouvelles tâches. (Responsable : Team leads / People Ops).
- Le manque de limites claires et de priorisation contribue à une mise en œuvre inconstante du Customer Journey initial. (Responsable : Product ; Alec).

6. Customer journey dégradé et communications marketing trop bruyantes • 0:03:12

- Le blueprint initial du Customer Journey n’est pas respecté, et les clients sont fortement “chauffés” par les ventes puis laissés sans étapes claires, ce qui crée de l’insatisfaction. (Responsable : Product ; Sales).
- Les clients continuent de recevoir un grand volume d’e-mails marketing sans lien avec leur parcours, car leurs adresses ne sont pas correctement retirées des listes après l’onboarding, ce qui génère de la frustration. (Responsable : Marketing ; CRM Owner).
- Le manque d’orchestration entre ventes, onboarding et communications de la plateforme provoque des attentes mal alignées et une baisse de satisfaction client. (Responsable : Sales ; Onboarding).

7. UX de la plateforme trop complexe pour les utilisateurs types • 0:05:52

- Sabrina a indiqué que la plateforme est jugée trop complexe par de nombreux utilisateurs, en prenant l’exemple de la persona “Robert, 57 ans, plombier”, et que cette complexité réduit l’utilisabilité et le NPS. (Responsable : Product / UX).
- Les fonctionnalités actuelles sont trop compliquées et comprennent des classifications financières confuses ainsi que des éléments bogués qui entravent l’usage de base. (Responsable : Product / Engineering).
- Les concurrents et certains outils IA simples réussissent parce qu’ils privilégient une interaction directe et des livrables clairs, ce qui suggère que la plateforme doit évoluer vers une UX plus simple et orientée tâches. (Responsable : Product / UX).

8. Problèmes d’adoption interne chez les équipes • 0:06:46

- Sabrina a indiqué que les utilisateurs internes, notamment les coachs et les commerciaux, ont eux aussi du mal à utiliser correctement la plateforme et ne trouvent pas certains éléments clés, ce qui montre un problème de formation et d’ergonomie. (Responsable : People Ops ; Product).
- L’équipe a observé que si les collaborateurs internes ne savent pas naviguer avec assurance dans la plateforme, les clients rencontreront des difficultés encore plus importantes et poseront davantage de questions au support. (Responsable : Team leads).

9. Besoin d’un onboarding étape par étape et de son suivi • 0:07:32

- Sabrina a proposé un onboarding progressif, “porte par porte”, avec des jalons obligatoires comme une session de bienvenue suivie et un questionnaire requis avant l’affectation d’un coach. (Responsable : Product ; Onboarding).
- Elle a expliqué qu’en pratique, seule une petite partie des clients, environ 3 à 4 sur 20, participe à la session de bienvenue sans mécanisme d’obligation ; rendre les étapes d’onboarding obligatoires augmenterait les taux de complétion. (Responsable : Onboarding ; Sabrina).
- L’équipe a convenu qu’il fallait suivre les dates de complétion de l’onboarding et la présence afin de mesurer la différence entre “client inscrit” et “client réellement terminé l’onboarding”. (Responsable : Product ; Engineering).

10. Exigences précises de données et de tracking par étape • 0:08:40

- Boris a insisté sur la nécessité de lister les points de données exacts à capturer à chaque étape, par exemple : présence à l’appel de découverte, inscription à l’onboarding, présence à l’onboarding, complétion de l’onboarding, afin de fixer des objectifs mesurables. (Responsable : Boris ; Product).
- Le suivi présence versus inscription est crucial, car une inscription sans présence doit être considérée comme un échec à améliorer. (Responsable : Product ; Analytics).
- Sabrina a indiqué que Quentin dispose déjà d’une grande partie des éléments de données sous-jacents, mais que les sessions de bienvenue sur Zoom n’ont pas de liens de suivi et nécessitent aujourd’hui un suivi manuel dans les e-mails. (Responsable : Quentin / Engineering).

11. Métriques nécessaires pour améliorer le processus de manière itérative • 0:09:28

- Boris souhaite passer d’un simple volume d’entrées à une logique de conversion à travers des “portes” d’onboarding définies, afin d’améliorer progressivement les taux, par exemple faire passer le taux de présence de 70 % à 75 % puis au-delà. (Responsable : Boris ; Product ; Analytics).
- Le groupe a convenu que mesurer le passage de chaque porte permettra de relier les étapes de process aux métriques de succès client et d’identifier les jalons qui améliorent les résultats. (Responsable : Product ; Analytics).
- La mise en œuvre nécessite de décider quels KPI capturer puis d’instrumenter la plateforme pour les enregistrer automatiquement. (Responsable : Product ; Engineering).

12. Churn élevé en phase initiale et échec à l’entrée • 0:11:57

- L’analyse de Christelle, partagée par Sabrina, montre que le churn avant la première session est supérieur à 20 % et peut atteindre 25 à 27 %, ce qui indique un sérieux problème d’entrée dans le parcours. (Responsable : Christelle ; Analytics).
- Ce churn précoce suggère un éventuel sur-promesse commerciale ou un décalage entre les promesses de vente et l’expérience réellement délivrée. (Responsable : Sales ; Product).
- Si les données confirment que l’entrée constitue un point de rupture majeur, il faudra lancer des chantiers séparés sur le message commercial et sur les processus d’onboarding pour réduire le churn. (Responsable : Sales ; Product).

13. Suivi du churn et raisons d’annulation • 0:12:38

- Depuis avril, Angèle suit les raisons d’annulation qui n’étaient auparavant pas monitorées, et elle dispose d’un tableau avec toutes les données nécessaires pour analyser le churn. (Responsable : Angèle).
- Sabrina a mis à jour Zendesk en juin afin de capturer des motifs d’annulation plus précis et attend une meilleure fiabilité de cette source. (Responsable : Sabrina).
- Les données montrent déjà un churn notable qui doit être traité par des améliorations produit et process. (Responsable : Product & Ops leads).

14. Fonction concierge et spécialisation des rôles • 0:13:08

- Quentin travaille actuellement sur le service concierge et recommande d’avoir une personne dédiée exclusivement à cette activité pour gagner en efficacité. (Responsable : Quentin).
- Sabrina propose d’embaucher Aïda au même niveau de rémunération pour travailler uniquement sur le concierge, afin d’éviter la dispersion des tâches et d’améliorer la concentration. (Responsable : Sabrina / RH).
- L’équipe a convenu qu’attribuer une responsabilité par projet plutôt que de répartir une multitude de petites tâches améliorera l’accountability et les résultats. (Responsable : Project owners / Managers).

15. Propriété de projet et KPI de présence aux onboarding calls • 0:13:29

- Boris a proposé de traiter les améliorations comme des projets avec un objectif de propriété, par exemple faire passer la présence aux appels d’onboarding d’un niveau de base (par exemple 50 %) à 85 % en trois mois. (Responsable : un propriétaire de projet à désigner).
- La première étape de ces projets consiste à mesurer le KPI de référence — le nombre de personnes présentes aux appels d’onboarding — afin de définir des objectifs et suivre les progrès. (Responsable : Data / Analytics et propriétaire du projet).

16. Customer journey et simplification de l’interface de la plateforme • 0:14:11

- Sabrina fournira les données nécessaires pour repenser le customer journey en réordonnant les étapes du flux actuel afin de simplifier l’expérience. (Responsable : Sabrina).
- Quentin doit fournir une vue de données pour soutenir cette refonte, et le travail UI de la plateforme doit simplifier les interactions plutôt qu’ajouter de la complexité. (Responsable : Quentin / Product).
- Le produit doit tenir compte des habitudes des utilisateurs façonnées par des applications grand public simples et viser une expérience guidée, orientée tâches, sans supprimer les fonctionnalités cœur. (Responsable : Product / UX).

17. Hops Cockpit et tableau de suivi des problèmes pour clarifier les projets • 0:15:43

- Boris a insisté pour utiliser le Hops Cockpit comme source unique de vérité pour les projets, les alertes, l’avancement et les blocages afin de réduire les interruptions ad hoc. (Responsable : toute l’équipe / Project owners).
- Le cockpit doit déclencher des notifications à Boris lorsqu’un projet remonte un blocage, ce qui permet une escalade et une résolution plus rapides. (Responsable : Project owners pour consigner les blocages).
- Chaque projet doit avoir une prochaine étape claire et une prochaine action afin d’éviter d’être considéré comme bloqué ; les responsables doivent assigner la personne qui exécutera l’action suivante. (Responsable : Project owners).
- Le tableau de problèmes actuel sera à terme consolidé dans le Hops Cockpit pour un suivi plus clair des blocages de projets. (Responsable : Boris / Operations).

18. États des tickets et définitions de workflow (triage, analyse, action, résolution) • 0:17:02

- Le “triage” consiste à attribuer la propriété d’un ticket à la bonne personne de l’équipe. (Responsable : lead de triage / Ops).
- L’“action” signifie qu’un plan est défini et que le responsable assigné doit l’exécuter. (Responsable : responsable assigné).
- La “résolution” signifie que le problème est corrigé et qu’aucun suivi supplémentaire n’est nécessaire. (Responsable : responsable assigné et propriétaire du projet pour validation).

19. Invitation des membres de l’équipe et attribution des tâches dans le cockpit • 0:19:30

- Sabrina ne peut pas assigner de tâches aux membres de l’équipe qui ne sont pas encore invités dans le Hops Cockpit ; des invitations doivent donc être envoyées pour permettre l’attribution complète. (Responsable : Boris / Ops pour inviter les utilisateurs).
- Boris enverra le lien du cockpit et demandera aux membres de l’équipe de se connecter avec leurs adresses e-mail entrepreneur afin d’apparaître dans le système. (Responsable : Boris).
- Sabrina a précisé qu’elle doit attribuer Océane et Quentin à des templates et à des projets une fois qu’ils seront visibles dans le cockpit. (Responsable : Sabrina / Boris après invitation).

20. Planification de l’événement « Immersion » et risque de voyage pour les participants à Dubaï • 0:21:45

- L’équipe prévoit de décider de la date de l’Immersion le 10, mais Boris anticipe un possible report et Sabrina craint que le 10 soit trop tard pour confirmer. (Responsable : organisateur de l’événement / Sabrina pour confirmation).
- Il y a 4 à 5 clients qui ont acheté des billets pour Dubaï, avec un risque si les vols sont annulés ou si les conditions tarifaires empêchent le remboursement ; certains billets peuvent être non remboursables selon la classe tarifaire. (Responsable : Customer Success / Finance).
- Pour les clients impactés, Sabrina a proposé de supprimer les frais d’annulation à titre commercial si nécessaire, et a indiqué que certains clients avaient déjà resigné avec l’entreprise. (Responsable : Sabrina / Finance).

21. Client à risque et facture impayée (Mickael Joyeux) • 0:23:42

- Mickael Joyeux, client important et ambassadeur, envisage d’arrêter le service et semble partir vers Era Hub, ce qui inquiète l’équipe s’il pousse activement à la résiliation. (Responsable : Customer Success / Boris pour investigation).
- Alice n’a pas émis les factures depuis janvier, ce qui a entraîné des impayés ; Jordan prendra en charge l’émission de la facture en attente pour récupérer les montants dus. (Responsable : Jordan pour la facturation ; Customer Success pour le suivi du paiement).
- Sabrina essaiera de contacter Mickael et escaladera s’il évite la communication ; l’équipe a convenu qu’il faut sécuriser le recouvrement des paiements même si le client arrête le service. (Responsable : Sabrina / Jordan / Finance).
%% notes:fin %%
