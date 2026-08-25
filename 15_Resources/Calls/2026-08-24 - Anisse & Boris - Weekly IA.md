---
type: call
date: 2026-08-24
source: sembly
participants: ["[[Anisse Rbibe]]", "[[Boris Arduy]]"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-08-24
---

# Anisse & Boris - Weekly IA

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (24/08/2026 11:46).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 24/08/2026 11:47 — corrige librement hors des marqueurs.

**Résumé** — Point hebdomadaire IA couvrant le recrutement RH/événements, l'automatisation du reporting hebdomadaire de l'équipe IA, la refonte de la plateforme, le suivi de consommation des tokens par projet, et le déploiement de l'assistant de formation commerciale Blueprint via GPT et Slack.

**Décisions**
- Séparer les rôles RH/admin et événements plutôt que recruter une personne multifonctionnelle
- Déployer Blueprint (formation commerciale) d'abord via GPT puis intégration Slack pour centraliser les ressources
- Mettre en place le reporting de fin de semaine et fin de mois selon les consignes envoyées par Boris

**Actions**
- [ ] **Anisse** : Partager avec Boris le dispositif de rapport hebdomadaire IA et le flux des transcriptions
- [ ] **Anisse** : Vérifier en production l'usage de DeepSeek et l'exactitude du tableau de bord de consommation
- [ ] **Anisse** : Mettre en place une vue tableau de bord montrant les schémas d'usage par équipe et temps passé avec les agents
- [ ] **Boris** : Débloquer les données nécessaires pour que Naïma puisse avancer sur Superbowl (échéance 2026-08-26)
- [ ] **Mariam** : Développer l'application Événement pour le marketing
- [ ] **Anisse** : Ajuster les modules Blueprint selon les retours de Lucas et Alec, puis développer les modules écrits
- [ ] **Anisse** : Préparer et animer deux sessions Bootcamp Sales orientées Mindset (échéance 2026-08-29)
- [ ] **Anisse** : Contacter Aziz pour médiation avec Alec
- [ ] **Naïma** : Implémenter le reporting de fin de semaine et fin de mois avec Wassim

**Risques & vigilances**
- La faible consommation de tokens peut refléter une utilisation limitée plutôt qu'une optimisation réelle
- Le déploiement de Super Bob est bloqué par l'attente des données de coaching de l'équipe data de Quentin
- Le recrutement externe RH/admin n'aboutit pas depuis deux mois

Tags : #ia #reporting #recrutement #blueprint #formation-commerciale
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 24/08/2026 11:46 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

La réunion a couvert trois grands axes : les besoins de recrutement et la définition des rôles RH/bureau/événements, les avancées de l’équipe IA sur le reporting hebdomadaire, la refonte de la plateforme et le suivi de l’usage des modèles, ainsi qu’un point plus large sur les métriques d’activité, les agents, les dépendances data et le déploiement d’un assistant de formation commerciale « Blueprint » via GPT et Slack. Les décisions clés ont été de séparer les fonctions RH/admin et événements, de poursuivre l’automatisation des transcriptions de réunions vers les rapports hebdomadaires, de renforcer le suivi de la consommation de tokens par projet via des clés API et un tableau de bord, d’unblocker les données nécessaires, et de prioriser la construction de Blueprint avec une intégration Slack/GPT. Des actions ont également été assignées pour les rapports de fin de semaine/mois, les sessions Bootcamp Sales et le développement de l’application Événement.

📋 Outline

1. Arrivée et bref échange informel • 0:02:00

- Les participants ont échangé des salutations informelles et ont expliqué un léger retard au démarrage de la réunion. (Participants : Boris Arduy, Anisse R'bibe).
- Le ton était décontracté et a posé le cadre d’une réunion courte et opérationnelle centrée sur les sujets en cours. (Participants : Boris Arduy, Anisse R'bibe).

2. Discussion recrutement — poste RH/admin versus événements • 0:03:45

- L’entreprise tente de faire venir un candidat externe depuis environ deux mois sans aboutir, et les parties prenantes réévaluent désormais l’option d’un recrutement en interne. (Responsables : Anisse R'bibe, Boris Arduy).
- Une proposition consistait à recruter une seule personne couvrant les fonctions de responsable RH, office manager et événements, mais cela soulève la crainte de mélanger trop de compétences distinctes. (Responsable : Boris Arduy).
- Boris a recommandé de séparer les rôles, car le recrutement/l’administration et l’organisation d’événements requièrent des compétences différentes et des processus dédiés. (Responsable : Boris Arduy).
- Anisse a expliqué que la stratégie initiale visait un recrutement multifonctionnel pour réduire les coûts fixes, tout en reconnaissant qu’une seule personne pourrait rencontrer des difficultés face à des responsabilités trop hétérogènes. (Responsable : Anisse R'bibe).
- Action implicite : finaliser les entretiens pour un rôle RH/admin orienté recrutement et envisager un recrutement séparé ou un contrat dédié pour les événements. (Responsables : Anisse R'bibe, suivi RH).

3. Aménagement du bureau et amélioration du fond vidéo • 0:07:19

- Boris a noté un nouveau fond vidéo et une meilleure organisation du bureau, ce qui améliore la présentation à l’écran. (Responsable : Boris Arduy).
- Anisse a confirmé avoir réorienté le bureau pour éviter un reflet direct de la baie vitrée en façade et améliorer ainsi l’éclairage. (Responsable : Anisse R'bibe).
- Ce changement opérationnel mineur a amélioré la présentation en réunion à distance et l’ergonomie. (Responsable : Anisse R'bibe).

4. Automatisation du reporting hebdomadaire à partir des daily standups IA • 0:07:41

- Anisse a décrit l’automatisation des transcriptions des réunions quotidiennes de l’équipe IA vers un rapport de fin de semaine que Michael compile, afin de réduire les demandes manuelles de statut. (Responsables : Anisse R'bibe, Michael).
- L’automatisation permet de gagner du temps entre fuseaux horaires, car les membres de l’équipe à distance au Maroc et à Dubaï terminent plus tôt par rapport à Paris, ce qui limite les relances du week-end. (Responsable : Anisse R'bibe).
- Boris utilise un setup personnel de type Jarvis pour agréger des données dans des synthèses de début de journée et de fin de semaine, et a առաջարկé de partager ses outils et méthodes. (Responsable : Boris Arduy).
- Action : Anisse partagera avec Boris le dispositif de rapport hebdomadaire et le flux des transcriptions. (Responsable : Anisse R'bibe -> Boris Arduy).

5. Refonte de la plateforme et choix visuels • 0:09:13

- Anisse a expliqué que la plateforme a été refondue à partir d’inspirations de designers et d’outils de référence (Apple, Linear, Stripe) et qu’un designer IA (Claude) a choisi les couleurs, les polices et les règles CSS. (Responsable : Anisse R'bibe).
- La refonte a produit une interface proche de la plateforme Entrepreneurs et a introduit un schéma de sidebar qui disparaît / double sidebar pour mieux gérer l’espace à l’écran. (Responsable : Anisse R'bibe).
- Boris a validé le comportement de la sidebar et l’amélioration globale de l’esthétique pour l’ergonomie. (Responsable : Boris Arduy).

6. Détails du rapport hebdomadaire IA et mises à jour produit • 0:09:57

- Le rapport hebdomadaire IA (du 16 au 21 août) détaille les contributions par personne et des livrables précis, comme l’ajout par Naima d’un bouton de suppression pour les fichiers importés dans le Wiki. (Responsable : Naima, rapporté par Anisse R'bibe).
- Naima a implémenté la charte de marque demandée, ajouté une page de tableau de bord d’usage IA pour suivre la consommation des API et modifié le tableau de bord global Host World. (Responsable : Naima).
- L’ajout du tableau de bord vise à suivre les coûts et les taux de consommation des API, afin de mieux surveiller les dépenses sur des outils comme DeepSeek et OpenAI. (Responsable : Anisse R'bibe).
- Action : Anisse vérifiera en production l’usage de DeepSeek et l’exactitude globale du tableau de bord. (Responsable : Anisse R'bibe).

7. Consommation actuelle de tokens IA et discussion sur l’optimisation • 0:10:55

- Boris a noté que les dépenses actuelles en tokens sont modestes (exemple cité : 136 $ sur 30 jours) et a demandé si cela s’explique par l’optimisation ou par une utilisation limitée de l’équipe. (Responsable : Boris Arduy).
- Anisse a indiqué disposer d’une ventilation par projet montrant une consommation très faible pour certains bots (par exemple SDRBot avec un usage minimal) et a rappelé que les coûts sont moyennés sur 30 jours. (Responsable : Anisse R'bibe).
- L’équipe utilise plusieurs modèles et sélectionne le modèle adapté à la tâche plutôt que de recourir systématiquement aux modèles les plus coûteux. (Responsable : Anisse R'bibe).
- Action : surveiller la consommation de tokens au fil du temps à mesure que l’usage IA augmente, et déterminer si la faible dépense provient surtout de l’optimisation ou d’une utilisation contrainte. (Responsables : Anisse R'bibe, Boris Arduy).

8. Vectorisation et stratégie d’embeddings pour réduire les coûts • 0:13:33

- L’équipe a vectorisé 100 % de la base de données afin que les recherches s’appuient sur des embeddings plutôt que de rescanner systématiquement les textes complets, ce qui réduit la consommation de tokens. (Responsable : Anisse R'bibe).
- L’embedding est utilisé pour les transcriptions, le contenu du Wiki et Rosetta, ce qui permet une récupération rapide et un coût API plus faible par requête. (Responsable : Anisse R'bibe).
- Le système utilise actuellement GPT 5.4 mini-WAS et d’autres modèles optimisés pour l’embedding et la récupération. (Responsable : Anisse R'bibe).
- Cette approche permet d’éviter la plupart des appels lourds en production, maintenant ainsi des coûts IA faibles tout en conservant des capacités analytiques efficaces. (Responsable : Anisse R'bibe).

9. Demande d’un suivi plus granulaire de l’usage et des logs • 0:15:03

- Boris a demandé s’il existe un tableau de bord d’usage montrant comment les équipes utilisent les agents IA et combien de temps elles passent avec eux, au-delà des seuls volumes de tokens. (Responsable : Boris Arduy).
- Anisse a confirmé que des logs existent et qu’il est possible de filtrer par utilisateur pour obtenir des données d’usage plus granulaires. (Responsable : Anisse R'bibe).
- Action : mettre en place ou exposer une vue de tableau de bord qui mette en évidence les schémas d’usage par équipe et le temps passé avec les agents, au-delà de la simple consommation de tokens. (Responsables : Anisse R'bibe, suivi équipe IA/engineering).

10. Besoins en métriques d’activité et d’usage au niveau utilisateur • 0:15:42

- Les parties prenantes souhaitent des métriques d’usage par utilisateur, comme le nombre de requêtes, les accès à des agents spécifiques et l’activité temporelle, afin de mieux comprendre les usages des outils. (Responsable : Produit/Analytics).
- Le système actuel montre uniquement la première connexion et le fait que la session reste ouverte, sans détail sur le temps passé sur la page ou l’usage par fonctionnalité. (Responsable : Engineering/Product).
- Une demande a été formulée pour étendre les logs afin d’inclure des actions telles que les authentifications, les invitations et les événements utilisateurs, afin d’améliorer l’observabilité. (Responsable : Engineering).

11. Corrections d’agents, boucles de feedback et état de la feuille de route • 0:16:33

- Un bug sur l’agent « Michael » a été identifié et corrigé par l’équipe qui suit les problèmes liés à N8N et aux logs. (Responsables : Ops/Engineering).
- Super Joe a reçu des améliorations à la suite de l’analyse de Fabrice et de retours sur des analyses et calculs incorrects. (Responsables : Engineering/Product).
- De nouvelles demandes de fonctionnalités de Léa et des demandes liées au coaching pour Super Bob sont en cours et intégrées à la feuille de route initiale avec Sabrina. (Responsables : Product/Engineering).
- Le déploiement est actuellement en phase de configuration avec les premiers workflows en cours de création ; l’équipe a insisté sur un suivi hebdomadaire des changements et des commentaires pour centraliser l’avancement. (Responsables : Product/Ops).
- La publication d’une réponse a été retardée dans l’attente de la préparation des données de coaching par l’équipe data de Quentin, ce qui bloque certaines livraisons. (Responsable : Data Team - Quentin).

12. Déblocage des données et objectifs hebdomadaires • 0:18:31

- Boris s’est engagé à débloquer les données nécessaires lundi afin que Naïma puisse avancer sur le travail Superbowl. (Décision/Responsable : Boris).
- La génération de rapports et le suivi d’historique (qui a créé/modifié les éléments) sont jugés utiles pour les résumés hebdomadaires et la transparence inter-départements. (Responsable : Product/Ops).
- Mariam est chargée de développer l’application Événement pour le marketing comme objectif hebdomadaire. (Responsable : Mariam).

13. Développement et déploiement de la formation commerciale Blueprint (version 1) • 0:19:42

- Le plan de formation Blueprint (14 à 15 modules) a été validé après revue et nécessite désormais des ajustements en fonction des retours de Lucas et Alec. (Responsable : Anisse pour l’ajustement du contenu).
- Anisse développera les modules écrits et standardisera la base de formation commerciale pour les équipes sales. (Responsable : Anisse).
- Le plan consiste à exposer la formation d’abord via un GPT, et non via Slack, afin que les closer externes sans accès Slack puissent interroger le contenu. (Responsable : Anisse/Product).
- Boris a recommandé de collecter les questions des utilisateurs pour identifier les sujets les plus fréquents, les trous dans le processus et guider les futures versions de Blueprint (V1 vers V2 puis V3). (Responsable : Product/Data).

14. Options d’intégration de l’assistant de formation : GPT, Super Joe ou Slack • 0:22:05

- Une option a été discutée : intégrer le GPT dans Super Joe afin que les utilisateurs voient à la fois des indicateurs de performance et puissent poser des questions de formation au même endroit. (Responsable : Product/Engineering).
- Une autre option consiste à fournir aux closer externes un accès via une adresse entrepreneurs.com et éventuellement leur donner un accès Works ou Slack pour interroger les agents. (Responsable : IT/Product).
- Boris privilégie l’intégration Slack car elle centralise les ressources, conserve l’historique, réduit l’usage de WhatsApp et permet de mettre à jour facilement les ressources ; il a précisé que le coût des licences Slack est acceptable au regard de la valeur apportée. (Responsable : Product/IT).
- L’équipe a convenu d’intégrer l’assistant aux canaux Slack pour les équipes internes et d’envisager un accès contrôlé pour les externes si nécessaire. (Décision/Responsables : Anisse, Boris, Product).
- La collecte et l’analyse des questions posées au GPT/aux agents permettront de catégoriser les demandes et de prioriser les améliorations de formation. (Responsable : Product/Data).

15. Sessions Bootcamp Sales et médiation interne • 0:25:51

- Anisse doit préparer et animer deux sessions Bootcamp Sales orientées Mindset d’ici la fin de la semaine. (Responsable : Anisse).
- Anisse tentera également de jouer un rôle de médiation entre Aziz et Alec dans le cadre de ses livrables et contactera Aziz pour coordonner cela. (Responsable : Anisse).
- Les organisateurs fourniront, si besoin, l’équipement ou le support nécessaire pour ces sessions. (Soutien implicite de Boris / Operations).

16. Mise en place du reporting de fin de semaine et de fin de mois • 0:26:24

- Boris a envoyé ce matin des consignes détaillées pour mettre en place les rapports de fin de semaine et de fin de mois, de sorte qu’aucune spécification lourde ne soit nécessaire. (Décision/Responsable : Boris).
- Naïma et Wassim devraient se relayer pour prendre en charge l’implémentation rapidement. (Responsables : Naïma et Wassim).
- L’objectif est d’obtenir une configuration légère qui soutienne les synthèses hebdomadaires et centralise les données opérationnelles. (Responsables : Product/Ops/Data).

17. Démonstration d’un laboratoire personnel et pratiques d’automatisation • 0:27:33

- Anisse a décrit un laboratoire personnel installé sur un ancien iMac avec Docker pour auto-héberger des services comme la synchronisation de photos, une instance locale de Hermes et Obsidian pour organiser les enregistrements d’appels et les tâches à faire. (Information : Anisse).
- Ce laboratoire personnel intègre un agent via Telegram capable d’écrire dans ses outils locaux, de planifier des blocs d’agenda et de préparer des briefs nocturnes pour le lendemain. (Information : Anisse).
- Cette automatisation personnelle illustre une exécution pilotée par agent et pourrait inspirer les outils internes ou les futures capacités des agents. (Enseignement pour Product/Engineering).
%% notes:fin %%
