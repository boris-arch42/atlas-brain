---
type: call
date: 2026-09-16
source: sembly
participants: ["achilleaime.fouman@entrepreneurs.com", "alexandre.gauthier@entrepreneurs.com", "boris@entrepreneurs.com", "claude-marc.nogha@entrepreneurs.com", "lysaaicha.danpoulobaba@entrepreneurs.com", "raphael.wautier@entrepreneurs.com", "roman.tebenikhinbonamy@entrepreneurs.com", "valentin.lhoste@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Réunion SDR x Boris

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (16/09/2026 09:57).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 16/09/2026 09:57 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a passé en revue plusieurs problèmes fonctionnels dans le FDR Hub : vues d’alertes incohérentes selon les utilisateurs, droits d’accès, historique des leads peu fiable, recherche absente ou limitée, comportements de scorecard instables, ainsi que des difficultés d’envoi du récapitulatif aux closers. Il a été convenu de corriger à la fois le backend et le frontend afin que les utilisateurs puissent accéder, rechercher, rouvrir et transmettre de manière fiable des données de lead complètes. Boris coordonnera les correctifs, suivra le processus de handoff avec les closers, et les utilisateurs partageront des liens et des exemples pour reproduire les bugs. Par ailleurs, le groupe a aussi discuté des alertes sonores, du système de relance/tâches, des doublons d’appels, des désinscriptions, de la fiabilité de l’historique selon les sources d’import, de l’identification des clients déjà signés, et de la création d’un canal Slack dédié aux mises à jour SDR.

📋 Outline

1. Objectif de la réunion et cadrage • 0:00:02

- Objectif de l’appel : passer en revue le FDR Hub, identifier les écarts entre les écrans des différents utilisateurs et proposer des modifications pour simplifier et améliorer l’usage. (Organisateur : alexandre.gauthier@entrepreneurs.com ; facilitateur : Boris).
- L’équipe a prévu de comparer les écrans, partager les URL et reproduire les problèmes en direct afin d’en identifier la cause. (Facilitateur : Boris).

2. Vues d’alertes différentes selon les utilisateurs • 0:01:07

- Plusieurs utilisateurs ont signalé voir des noms d’alertes/leads différents sur la même URL du FDR Hub, ce qui indique des vues incohérentes entre comptes. (Signalé par : Boris ; observé par : Claude-Marc, Lisa, Achille).
- Boris a demandé à chaque participant de partager l’URL exacte utilisée afin de comparer les environnements et reproduire l’écart. (Action : tous les utilisateurs doivent coller leurs URL dans le chat).

3. Partage d’écran et premières comparaisons • 0:02:01

- Claude-Marc a partagé son écran ; celui-ci correspondait à la vue admin attendue et confirmait les bons noms d’alertes pour ses leads. (Observé par : Boris).
- Lisa et Achille ont partagé leurs écrans et ont montré d’autres noms de leads (par exemple « Jackie »), confirmant une donnée incohérente selon les utilisateurs. (Signalé par : Lisa, Achille).

4. Bug sur le comportement des alertes et des affectations • 0:04:26

- Un bug a été identifié : les alertes et callbacks (par exemple une demande de rappel lundi de 17h à 18h) ne s’affichaient pas de manière cohérente pour tous les utilisateurs. (Observé par : Boris, Lisa).
- Boris a reconnu le bug et s’est engagé à le corriger dans le système central. (Action : Boris).

5. Même URL, plusieurs vues : cause suspectée • 0:05:14

- Les utilisateurs ont confirmé utiliser la même URL tout en voyant trois vues différentes, ce qui suggère que le problème vient probablement des droits d’accès backend ou de l’attribution des rôles. (Observé par : Boris, tous les participants).
- Boris va investiguer pourquoi un lien identique produit des écrans différents et ajuster la logique d’accès en conséquence. (Action : Boris).

6. Besoin de navigation arrière dans le scorecard • 0:06:25

- Les utilisateurs ne peuvent pas revenir à une étape précédente du scorecard sans perdre les données saisies, ce qui interrompt les appels et la saisie. (Signalé par : Boris comme douleur produit).
- L’amélioration demandée consiste à permettre la navigation en arrière dans le scorecard sans réinitialiser tous les champs. (Action : Produit/Ingénierie — Boris doit l’implémenter).

7. Historique de lead peu fiable et comportement de disqualification • 0:06:36

- L’historique du lead affiche souvent « numéro jamais appelé » même lorsque plusieurs appels ont bien eu lieu, ce qui complique le suivi des interactions. (Signalé par : Lysa).
- Les leads disqualifiés réapparaissent pour certains utilisateurs et pas pour d’autres, provoquant des doublons de prospection et de la confusion. (Signalé par : Lysa).
- Le problème semble lié à une visibilité des leads et à des droits d’accès incohérents entre utilisateurs. (À investiguer : Boris).

8. Recherche limitée et manipulation des leads / scorecards • 0:08:37

- Les utilisateurs n’ont pas de barre de recherche efficace pour trouver les leads par nom, email ou téléphone et doivent faire défiler manuellement de longues listes. (Signalé par : Lysa et Achille).
- Même lorsqu’un lead est trouvé dans l’onglet leads, les utilisateurs ne peuvent souvent pas agir dessus, car leur vue n’inclut pas tous les leads. (Signalé par : Achille).
- Les fonctionnalités demandées sont une recherche globale sur les leads et la possibilité de manipuler les leads directement depuis les résultats de recherche. (Action : Produit/Ingénierie — Boris doit ajouter la recherche et élargir l’accès).

9. Erreur « lead not found » au clic sur un lead visible • 0:11:06

- Certains utilisateurs voient un lead dans la liste mais reçoivent un message « lead not found » lorsqu’ils l’ouvrent, ce qui bloque le suivi. (Signalé par : Achille).
- Boris soupçonne un problème d’assignation de lead et de droits d’accès : un lead attribué à un autre utilisateur pourrait disparaître pour les autres. (Investigation : Boris).
- Le plan immédiat consiste à ouvrir l’accès backend afin que les utilisateurs puissent voir et traiter les leads de manière cohérente. (Action : Boris mettra à jour les permissions backend).

10. Rouvrir un scorecard après un non-réponse • 0:12:28

- Lorsqu’un lead est marqué « not answered » et passe dans le scorecard, les utilisateurs ne peuvent pas rouvrir ou réutiliser le même scorecard plus tard si le lead rappelle. (Signalé par : Valentin).
- L’équipe a convenu d’ajouter une fonction simple de « rouvrir le scorecard » afin qu’un lead ne génère pas plusieurs scorecards et que les utilisateurs puissent reprendre la saisie des informations. (Action : Produit/Ingénierie — Boris doit ajouter un bouton de réouverture).

11. Contenu final du récapitulatif manquant sur la page de rendez-vous • 0:13:52

- La page finale de rendez-vous/booking ne contient que le champ déclencheur initial, mais n’inclut pas les objectifs, enjeux ou notes d’écart saisis pendant l’appel. (Signalé par : Roman).
- L’équipe a demandé que la page de résumé se remplisse automatiquement avec les champs clés saisis pendant l’appel, afin d’aider à pitcher et confirmer les éléments avec les prospects. (Action : Produit/Ingénierie — Boris doit ajouter les champs de récapitulatif).

12. Échec de l’envoi du résumé d’appel aux closers et processus de handoff • 0:15:18

- Les utilisateurs rencontrent une erreur lors de l’envoi du résumé d’appel aux closers, car le champ email du closer est obligatoire et le processus échoue. (Signalé par : Achille).
- Boris a proposé de pousser automatiquement les scorecards validés vers HubSpot (CRM) plutôt que de s’appuyer sur l’email, afin de garantir que les closers reçoivent l’information. (Action : Boris doit mettre en place l’intégration CRM et définir le workflow de handoff avec les closers).

13. Absence de notifications audio et disponibilité tardive des leads • 0:16:30

- Certains utilisateurs ne reçoivent pas de notification sonore lors de l’arrivée de nouveaux leads, ce qui entraîne des retards dans la prise en charge en temps réel. (Signalé par : Lysa).
- Plusieurs utilisateurs ont indiqué que les nouveaux leads n’étaient souvent visibles que plusieurs heures après le passage de Claude-Marc, ce qui révèle un problème de distribution ou de timing. (Signalé par : Lysa ; impactés : Achille, Valentin, Roman).
- L’équipe doit garantir une distribution des leads en temps voulu ainsi que des notifications fonctionnelles afin que les agents disponibles puissent agir immédiatement. (Action : Produit/Ingénierie — Boris doit investiguer le timing de distribution et les paramètres de notification).

14. Bug des alertes sonores et perception de favoritisme • 0:17:02

- Les utilisateurs subissent des alertes sonores incohérentes ou absentes lorsqu’ils contactent des leads, et le problème semble toucher l’ensemble de l’équipe. (Signalé par : Boris, Valentin).
- Une perception a émergé selon laquelle certains utilisateurs seraient « favorisés » ; Boris a précisé qu’il n’y a aucun favoritisme intentionnel et que le problème est technique. (Responsable : Boris).
- Boris s’est engagé à corriger le bug des alertes sonores. (Action : Boris).

15. Besoin d’un système de relance / tâches de rappel • 0:17:30

- L’équipe SDR suit actuellement les rappels et les disqualifications dans un tableau externe, ce qui crée de la friction et un risque d’oubli. (Signalé par : Lysa).
- L’équipe demande une fonctionnalité de création de tâches dans l’application, liée à un lead, avec nom, lead associé et date/heure planifiée. (Demandé par : Boris/Lysa).
- L’équipe demande également une vue calendrier ou une liste quotidienne de tâches regroupant les relances dues chaque jour. (Demandé par : Boris).
- Cette fonctionnalité réduirait l’usage manuel des tableaux et améliorerait la fiabilité du suivi des relances. (Bénéfice).

16. Prévention des doublons d’appels et visibilité de l’historique partagé • 0:18:33

- Les SDR appellent parfois le même prospect plusieurs fois, car l’état des prises de contact et des rappels n’est pas visible de façon fiable pour les autres agents. (Signalé par : Achille).
- Plusieurs prospects se plaignent d’être recontactés par plusieurs membres de l’équipe, ce qui nuit à l’expérience lead et à la conversion. (Signalé par : Achille, Lysa, Valentin).
- L’équipe demande qu’un rappel actif, une tâche ou un drapeau « ne pas contacter » soit visible dans la fiche lead pour empêcher d’autres utilisateurs d’appeler. (Demandé par : Achille/Lysa).
- Boris ajoutera des filtres ou une logique anti-spam pour réduire les relances répétées et étudiera une meilleure visibilité des rappels. (Action : Boris).

17. Échecs du disqualify / « do not contact » et des désinscriptions • 0:19:30

- Les SDR marquent certains leads comme disqualifiés ou « do not contact », mais ces marquages ne les retirent pas systématiquement des listes d’appels ni n’empêchent les recontactations. (Signalé par : Valentin/Roman).
- Certains SDR renseignent comme motif « souhaite être retiré de la base », mais l’automatisation backend n’applique pas toujours ce drapeau. (Signalé par : Valentin).
- Boris prévoit de rendre l’action de disqualification plus robuste afin que les leads marqués ne réapparaissent plus, sauf si le prospect se réinscrit via un nouveau funnel. (Action : Boris).
- Le marketing doit recevoir une liste nocturne ou périodique des emails à retirer des campagnes lorsque des prospects demandent une désinscription. (Action : SDRs collectent, Marketing traite).
- Il faut aussi étudier une automatisation entre le champ de disqualification et les listes de suppression marketing afin d’éviter les transferts manuels. (Action : Boris + Marketing).

18. Fiabilité de l’historique de contact et diversité des sources d’import • 0:24:07

- Les informations historiques de contact sont peu fiables, car certaines listes (par exemple les imports de webinaires) proviennent de CSV non reliés à l’automatisation et n’ont donc pas de traçabilité automatique. (Expliqué par : Boris).
- Dans certaines interfaces, des leads apparaissent comme « jamais contactés » malgré des appels antérieurs, à cause de la séparation entre funnels automatisés et imports CSV manuels. (Signalé par : Valentin).
- Boris va investiguer l’optimisation de la synchronisation de l’historique et améliorer la traçabilité entre les sources d’import pour garantir un statut de contact cohérent. (Action : Boris).

19. Différencier les clients déjà signés des leads • 0:26:27

- Les SDR contactent parfois des clients déjà signés parce que le système ne les identifie pas clairement comme clients. (Signalé par : Roman).
- Contacter des clients déjà signés fait perdre du temps aux SDR et crée un risque de confusion chez des clients déjà onboardés. (Risque).
- L’équipe demande un indicateur ou un drapeau client clair sur les fiches afin que les SDR puissent ignorer ou traiter ces contacts correctement. (Demande ; responsable : Boris).

20. Canal de communication et workflow de mise à jour • 0:28:26

- Boris créera un canal Slack dédié (nom suggéré : update-SDR) pour centraliser les bugs, les demandes de fonctionnalités et les mises à jour opérationnelles. (Action : Boris).
- Boris fournira des mises à jour vidéo Loom lorsque des correctifs ou fonctionnalités seront déployés, et les publiera dans le nouveau canal Slack. (Action : Boris).
- Ce nouveau canal deviendra l’espace principal pour que les SDR publient les problèmes urgents et pour que Boris annonce les corrections et les priorités. (Changement de processus).

21. Priorisation et amélioration itérative • 0:30:15

- Boris a insisté sur la priorité à donner aux améliorations fonctionnelles ayant un impact direct sur la productivité des SDR, plutôt qu’aux changements esthétiques comme les thèmes de couleur. (Orientation : Boris).
- L’équipe a convenu d’une approche itérative : traiter d’abord les principaux problèmes, puis affiner en fonction des retours terrain supplémentaires. (Accord).
- Si les discussions ou les problèmes deviennent trop complexes, l’équipe planifiera des appels de suivi de 30 à 45 minutes pour se réaligner. (Contingence).
%% notes:fin %%
