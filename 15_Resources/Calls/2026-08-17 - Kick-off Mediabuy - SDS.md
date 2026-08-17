---
type: call
date: 2026-08-17
source: sembly
participants: ["[[Adil]]", "[[Boris Arduy]]", "[[Cédric De Saint Jean]]", "[[Hubert Smolen]]", "stivel@consulting-sd.com"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-08-17
---

# Kick-off Mediabuy - SDS

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (17/08/2026 10:26).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 17/08/2026 10:53 — corrige librement hors des marqueurs.

**Résumé** — Kick-off opérationnel pour le lancement de la campagne média "Scalingue" avec un budget de 300k€ et un objectif CPL de 25€. L'équipe vise un lancement dès le 20 août malgré des éléments encore en cours de finalisation (vidéos, tracking, intégrations WAP/Customer.io).

**Décisions**
- Lancement des campagnes dès le 20 août même si certains créatifs et l'upsell ne sont pas finalisés
- Structure du tunnel : opt-in → upsell → VIP avec une seule page d'ordre pour limiter la friction
- Deux pages de remerciement distinctes : une standard et une pour le retargeting
- Utilisation du pixel et événements de confirmation pour construire les audiences VIP plutôt que uniquement la liste emails
- Thomas intervient comme consultant pour structurer la passation et le cadre de travail de l'équipe Boris
- Duplication du produit à 17€ dans WAP pour router vers les bonnes pages de remerciement

**Actions**
- [ ] **Cédric** : Partager le lien Whimsicle et les fichiers de référence de la page d'upsell de jeudi dans Slack (échéance 2026-08-17)
- [ ] **Cédric** : Remplir l'onglet Ads dupliqué dans Uber Sheet avec les premières annonces (échéance 2026-08-18)
- [ ] **Cédric** : Fournir les accès aux comptes d'hébergement vidéo (Vimeo/Vidalytics) (échéance 2026-08-18)
- [ ] **Cédric** : Partager la vidéo brute d'Alec pour l'upsell (échéance 2026-08-17)
- [ ] **Cédric** : Prévenir dans Slack quand les premiers liens sont chargés dans Google Sheets (échéance 2026-08-18)
- [ ] **Adil** : Assurer l'intégration Customer.io pour pousser les données acheteurs et activer les scénarios d'onboarding (échéance 2026-08-19)
- [ ] **Adil** : Dupliquer le produit à 17€ en deux produits WAP pointant vers les pages de remerciement standard et retargeting (échéance 2026-08-18)
- [ ] **Adil** : Session de partage d'écran avec Hubert pour générer le code d'intégration formulaire WAP (échéance 2026-08-18)
- [ ] **Adil** : Réaliser les tests finaux des intégrations et flux de commande (échéance 2026-08-17)
- [ ] **Adil** : Coordonner avec Cédric le flux de communication WhatsApp VIP pour éviter confusion dans le parcours post-achat (échéance 2026-08-19)
- [ ] **Adil** : Relancer Boris sur la correction du problème Looker (méthode Bootstrap) (échéance 2026-08-18)
- [ ] **Hubert** : Mettre en place le mécanisme de préremplissage email sur la page de paiement WAP (échéance 2026-08-19)
- [ ] **Hubert** : Reconstruire le formulaire de commande avec style mode sombre (échéance 2026-08-17)
- [ ] **Hubert** : Valider avec Boris la configuration du pipeline de données et Looker avant le lancement (échéance 2026-08-19)
- [ ] **Hubert** : Décider et implémenter la redirection post-Tali (page intermédiaire vs WhatsApp direct) (échéance 2026-08-19)
- [ ] **Hubert** : Confirmer la faisabilité des CTA vidéo pointant vers ancre de page (échéance 2026-08-18)
- [ ] **Hubert** : Router les utilisateurs vers la bonne page de remerciement selon URL/contexte (échéance 2026-08-19)
- [ ] **Boris** : Corriger le problème Looker pour que les métriques marketing remontent correctement (échéance 2026-08-20)
- [ ] **Boris** : Faire intervenir Thomas comme consultant pour cadrer le travail de l'équipe (échéance 2026-08-19)
- [ ] **Thomas** : Intervenir comme consultant pour structurer la passation et le cadre de travail (échéance 2026-08-19)

**Risques & vigilances**
- Le tracking serveur et la capture complète des événements de conversion ne seront peut-être pas opérationnels au lancement
- Les métriques marketing ne remontent pas dans Looker à cause d'un problème de méthode Bootstrap non mis à jour
- Risque de confusion dans le parcours utilisateur si le timing des messages WhatsApp VIP n'est pas bien calibré
- Volume très élevé de micro-campagnes (200+ annonces) nécessite une structuration rigoureuse pour éviter les erreurs
- La conservation des paramètres URL (prénom, email) à travers le tunnel WAP reste incertaine
- Délai serré pour finaliser vidéos, pages d'upsell et intégrations avant le lancement du 20 août
- Dépendance à la disponibilité de la vidéo d'Alec (attendue mercredi) pour finaliser la page d'upsell

Tags : #mediabuy #campagne-scalingue #tracking #upsell-vip #wap #customer-io
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 17/08/2026 10:26 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

La réunion a confirmé le plan de lancement de la semaine « Scalingue » / CTL avec un budget de 300 000 € et un objectif de CPL d’environ 25 €. L’équipe a validé un déploiement rapide, idéalement dès le lundi 20, même si certaines pages ou créatifs restent à finaliser, afin de profiter au maximum du volume de tests publicitaires (environ 2 000 annonces par personne) et d’un tunnel multi-étapes intégrant une upsell VIP. Les priorités opérationnelles portent sur la mise en place urgente du tracking, de l’intégration WAP, de Customer.io, des audiences VIP, des pages de remerciement distinctes, ainsi que sur la finalisation des vidéos, des pages d’upsell et des automatisations email/SMS/WhatsApp. Plusieurs responsabilités ont été réparties entre Cedric, Adil, Hubert, Boris et Thomas, avec l’objectif commun de sécuriser la mesure des conversions, la fluidité du parcours et le lancement des campagnes dès que possible.

📋 Outline

1. Aperçu du lancement et calendrier • 0:00:00

- La campagne concerne la semaine « Scalingue » avec un budget disponible de 300 000 € et un objectif de CPL d’environ 25 € ; la responsabilité globale est portée par Cedric Desaintjan.
- La charge opérationnelle visée est d’environ 2 000 annonces à gérer par personne afin de tester un volume important de créatifs ; l’équipe média, notamment Hubert et Stivel, est concernée.
- La date de lancement cible est le 20 ; la réunion du 17 devait servir à finaliser la configuration et à laisser le temps de charger les créatifs et les tunnels.
- Le lancement doit intervenir le plus tôt possible, même si toutes les pièces ne sont pas encore finalisées, afin de ne pas perdre de temps sur la montée en puissance.
- Les vidéos sont partiellement disponibles : environ la moitié des créatifs vidéo est déjà prête, le reste devant arriver au fil de la semaine.

2. Structure du tunnel, prix et logique d’upsell • 0:00:00

- Le tunnel prévu suit la logique : opt-in → upsell → VIP, avec plusieurs niveaux de prix mentionnés à 17 €, 27 €, 47 € et 67 € selon les offres.
- Des créatifs de retargeting sont prêts à la fois pour les inscrits généraux et pour convertir les acheteurs non-VIP en acheteurs VIP.
- L’upsell/VIP doit idéalement être capturé sur une seule page d’ordre afin de réduire la friction et simplifier le taux de conversion.
- Les données du formulaire après upsell serviront à comparer la qualité des acheteurs VIP et non-VIP ; le volume VIP sera plus faible, mais reste exploitable pour l’analyse.
- L’équipe souhaite que la page d’achat ressemble à une vraie landing page de conversion, avec suffisamment de détails et un parcours clair.

3. Audiences VIP, retargeting et coordination des campagnes • 0:00:00

- L’équipe de Boris doit faire intervenir Thomas comme consultant afin d’aider à la passation et d’apporter un cadre de travail plus clair.
- Une liste d’emails d’acheteurs a été demandée pour créer des audiences spécifiques dans Meta et Google pour le ciblage VIP, mais cette base restera limitée.
- L’approche privilégiée est basée sur le pixel et les événements de confirmation pour construire les audiences, plutôt que de dépendre uniquement de la liste d’emails.
- Les campagnes doivent être coordonnées afin d’éviter des exclusions involontaires entre audiences, par exemple entre les campagnes book et les campagnes 5D.
- L’équipe souhaite également disposer d’un fichier d’acheteurs pour alimenter les automatisations CRM et les relances ciblées.

4. Comportement WAP, préremplissage et conservation des paramètres • 0:00:00

- Un problème de doublon de saisie d’email existe, car WAP demande actuellement l’email à la fois à l’opt-in et au moment du paiement.
- Le besoin est de préremplir l’email sur la page de paiement afin de réduire la friction pour l’utilisateur.
- La conservation des paramètres d’URL comme le prénom et l’email à travers le tunnel reste incertaine et dépend de la persistance via local storage, cookie ou GTM.
- Si la conservation native n’est pas possible, un fallback technique doit permettre à un composant HTML embarqué de relire les informations stockées et de préremplir les champs.
- L’upsell étant embarqué dans le tunnel, il faut un mécanisme fiable pour capturer puis réutiliser les informations utilisateur sans casser le parcours.

5. Intégration email et données clients avec Customer.io • 0:00:00

- Les acheteurs reçoivent actuellement les emails de confirmation WAP, mais pas les emails d’onboarding du système de l’équipe, notamment les liens WhatsApp et les instructions VIP.
- Il est nécessaire de pousser les données des acheteurs dans Customer.io pour activer les rappels et les relances ciblées.
- Une alternative consisterait à centraliser toutes les informations d’accès dans WAP, mais l’équipe préfère également envoyer un email officiel depuis son propre système.
- Adil est chargé d’assurer cette intégration et de valider que les scénarios Customer.io fonctionnent correctement avant le lancement.
- Des tests en conditions réelles, y compris les emails de confirmation, doivent être réalisés avant d’activer définitivement l’automatisation.

6. Accès WhatsApp VIP et questions de timing • 0:00:00

- Les acheteurs VIP seront invités dans un groupe WhatsApp distinct, avec un onboarding différent de celui des acheteurs classiques.
- Le timing des messages doit éviter qu’un acheteur reçoive un accès VIP alors qu’il est encore en train de regarder la vidéo d’upsell.
- Les instructions d’intégration WhatsApp par SMS semblent déjà en place, mais le contenu et le moment d’envoi doivent rester alignés sur le tunnel.
- Adil et Cedric doivent coordonner le flux de communication pour éviter toute confusion dans le parcours post-achat.
- L’objectif est de garantir une transition fluide entre la confirmation d’achat, les accès et les messages d’accompagnement.

7. Vidéo d’Alec et finalisation de la landing page d’upsell • 0:00:00

- La vidéo d’Alec pour l’upsell est attendue d’ici mercredi, avec une version sous-titrée intermédiaire disponible si nécessaire.
- La page d’upsell doit reprendre le modèle partagé jeudi, avec un niveau de détail élevé et une présentation digne d’une vraie page d’achat.
- Le contenu pédagogique destiné aux VIP doit aller au-delà de l’accès WhatsApp afin de justifier la valeur de l’offre VIP.
- Hubert et Olivier ont demandé une copie ou un exemple de la page de jeudi pour assurer l’alignement et éviter toute confusion.
- Cedric doit partager les références de cette page pour permettre à l’équipe de reproduire correctement la structure et le design.

8. Tracking, événements serveur et préparation Ops • 0:00:00

- Il existe un risque sur le tracking serveur et la capture complète des événements de conversion au lancement.
- L’équipe Ops de Boris, avec Hubert, doit s’assurer que le pipeline de données et Looker sont correctement configurés avant le go-live.
- Une décision reste à prendre entre rediriger les utilisateurs vers une page intermédiaire après Tali pour conserver les paramètres, ou les envoyer directement vers WhatsApp.
- Ce choix a un impact direct sur le tracking et sur l’expérience utilisateur.
- La validation de l’attribution ads → revenu et de la performance de campagne dès le premier jour est jugée critique.

9. Problème Looker et responsabilité de la donnée • 0:00:00

- Les métriques de l’initiative marketing, comme les calls bookés et le chiffre d’affaires, ne remontent pas correctement dans Looker.
- Le problème semble lié au fait que la méthode Bootstrap n’a pas été mise à jour.
- Thomas avait précédemment mis en place un système personnalisé que l’équipe actuelle ne sait pas reproduire.
- Adil a déjà relancé plusieurs fois Boris au sujet du correctif et attend une résolution dans la semaine.
- L’équipe de Boris est responsable de la remise en état de ce sujet data.

10. Landing intermédiaire et test de redirection temporisée • 0:00:00

- L’équipe a proposé de tester une landing intermédiaire avec redirection automatique après quelques secondes, sur le modèle d’une approche déjà observée ailleurs.
- Des délais de 2 à 6 secondes ont été évoqués, avec un bouton de secours si la redirection automatique ne fonctionne pas.
- L’idée pourrait servir à charger certains tags ou à afficher brièvement une image de marque avant la redirection.
- Le besoin exact en tags reste à clarifier.
- Hubert doit envisager l’implémentation technique tandis que Stivel et Adil doivent confirmer le besoin fonctionnel.

11. Partage des créatifs et organisation des assets • 0:00:00

- Cedric a été invité à partager le lien Whimsicle dans le chat afin que l’équipe puisse consulter le créatif de référence.
- Hubert doit fournir une capture d’écran pour permettre une lecture rapide pendant la configuration.
- Cedric doit aussi partager les fichiers de travail nécessaires pour accélérer la mise en place.
- Le but est d’éviter les allers-retours pendant la préparation des pages et des annonces.

12. Organisation du fichier Ads et duplication des campagnes • 0:00:00

- Cedric a dupliqué l’onglet Ads dans le Uber Sheet et commencera à le remplir avec les premières annonces.
- Le volume de micro-campagnes est déjà très élevé : environ 200 annonces au niveau des villes, auxquelles s’ajoutent des campagnes par pays, profession et tranche d’âge.
- L’organisation en dossiers et la structuration des campagnes sont jugées essentielles pour éviter les erreurs lors des uploads et du suivi.
- Hubert a confirmé qu’une bonne structure de dossiers permet de gérer la complexité plus facilement.

13. Budget, approbations créatives et créatifs restreints • 0:00:00

- Le budget de base est défini et doit servir de référence pour le spend initial, avec ajustements selon les performances.
- Le créatif Chabal est en attente d’approbation en raison de son coût et ne doit pas être lancé sans validation.
- L’équipe prévoit un pilote agressif sur trois semaines pour dépenser le budget tout en gardant le CPL sous contrôle.
- Les leaders de campagne doivent suivre de près les performances pour arbitrer rapidement les variations de budget.

14. Format de l’événement, planning live et objectifs KPI • 0:00:00

- L’événement comprend trois lives par jour : une longue session le dimanche soir, des sessions de mise en œuvre d’1 à 1,5 heure à midi chaque jour, et une session Q&A VIP de 18 h à 19 h.
- Le volume total représente environ 35 heures de contenu live.
- Les créatifs de retargeting et de retargeting candidats sont déjà filmés et prêts à être mis en ligne.
- Les objectifs de campagne sont d’au moins 12 000 inscrits et environ 1 200 à 1 500 calls bookés, avec un CPL cible autour de 25 €.
- Cedric porte le suivi des KPI de croissance.

15. Connexion Customer.io et tests de validation • 0:00:00

- Adil a confirmé que les inscriptions remontent bien dans Customer.io et dans Uber, mais que le scénario d’automatisation n’est pas encore activé pour permettre des tests sécurisés.
- Le plan consiste à terminer les tests en direct, y compris les emails de confirmation, avant d’activer définitivement le scénario.
- Adil et le marketing ops doivent valider que l’ensemble fonctionne avant le lancement.
- Cette étape est considérée comme un prérequis pour éviter des erreurs d’onboarding au moment du go-live.

16. Pages de remerciement distinctes et configuration du paiement • 0:00:00

- Deux pages de fin de paiement distinctes sont nécessaires : une page de remerciement standard et une page dédiée au retargeting, sans reprise du formulaire initial.
- L’objectif est d’éviter toute duplication dans le tunnel et de garder une logique claire entre les différents parcours.
- Adil va dupliquer le produit dans le plan de paiement en deux produits à 17 € qui pointeront vers les pages de remerciement correspondantes.
- Hubert doit router les utilisateurs vers la bonne page selon l’URL ou le contexte.
- La page de remerciement retargeting doit afficher la confirmation et les prochaines étapes, sans reprendre le formulaire d’origine.

17. Intégration du formulaire WAP et aspects de style • 0:00:00

- Le formulaire de commande peut être embarqué directement depuis WAP avec un style et des couleurs personnalisables.
- Adil a proposé une session de partage d’écran pour générer le code d’intégration.
- Hubert mettra le mode sombre par défaut et ajustera la largeur ainsi que le style pour assurer une apparence cohérente.
- L’équipe a aussi discuté de l’hébergement des vidéos via Vimeo ou Vidaly tics, ou de la simplification par dépôt des capsules dans Google Drive puis intégration dans WAP.
- Cedric doit coordonner les accès nécessaires et Adil fournir les liens d’intégration.

18. Hébergement vidéo, CTA dans la vidéo et embeds • 0:00:00

- Vidaly tics/Vimeo permettent des CTA temporels dans les vidéos, mais dans ce tunnel le CTA doit probablement pointer vers l’ancre de la page plutôt que rediriger vers une autre page.
- Hubert doit confirmer la faisabilité technique de ce comportement.
- Cedric doit fournir les accès aux comptes d’hébergement vidéo afin de pouvoir téléverser les contenus et configurer les CTA.
- L’équipe doit décider si les CTA vidéo déclenchent des composants WOP embarqués ou un autre comportement.
- Hubert et Adil doivent valider ensemble le chemin exact du flux.

19. Chargement des liens, reconstruction du formulaire et séquencement du lancement • 0:00:00

- Cedric préviendra l’équipe dans Slack lorsqu’il aura chargé les premiers liens dans Google Sheets afin que l’équipe média puisse commencer les uploads.
- Hubert reconstruira le formulaire de commande aujourd’hui.
- L’équipe a accepté l’idée de lancer les annonces même sans upsell complet pour gagner du temps, puis d’envoyer un email de relance pour proposer l’upsell aux acheteurs initiaux.
- Si le retard persiste, une simple page de remerciement avec le ticket et le formulaire embarqué sera utilisée pour ne pas bloquer le warm-up des campagnes.
- L’objectif est d’éviter tout décalage inutile du lancement publicitaire.

20. Disponibilité vidéo finale, tests et horizon de lancement • 0:00:00

- Cedric a précisé que la vidéo brute sera disponible aujourd’hui, tandis que le stylage et les sous-titres seront terminés entre mercredi et jeudi.
- Adil fera les tests finaux ce soir pour valider les intégrations et les flux avant le lancement.
- L’équipe vise un lancement publicitaire dès demain si les pages et les flux de commande sont opérationnels.
- Une landing page minimalement stylée est jugée acceptable si elle permet de gagner deux jours sur l’atteinte des objectifs.
- La priorité reste de mettre les campagnes en ligne rapidement plutôt que d’attendre une finition parfaite.
%% notes:fin %%
