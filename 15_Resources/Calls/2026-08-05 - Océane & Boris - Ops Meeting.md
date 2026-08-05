---
type: call
date: 2026-08-05
source: sembly
participants: ["[[Océane De Queiros]]", "[[Boris Arduy]]"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-08-05
---

# Océane & Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (05/08/2026 12:03).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 05/08/2026 15:50 — corrige librement hors des marqueurs.

**Résumé** — Point ops sur les défaillances du tracking marketing (UTM cassés par les raccourcisseurs, données incohérentes) et les problèmes d'attribution SDR vs web. Décision de centraliser le suivi UTM et de construire d'abord un dashboard communication comme pilote avant généralisation.

**Décisions**
- Centraliser le tracking UTM dans un système unique géré par Boris
- Construire d'abord un dashboard dédié au pôle communication comme pilote avant de généraliser aux autres pôles
- Intégrer les UTM sur toutes les pages et liens calendrier pour permettre l'attribution par source/medium/campagne
- Abandonner la plateforme COMEX pour le tracking partagé (non fiable)
- Utiliser Entrepreneurs Work comme système global de gestion de projet

**Actions**
- [ ] **Boris** : Corriger l'intégration iClosed et les règles UTM pour assurer le tracking multi-funnel
- [ ] **Boris** : Construire le dashboard dédié communication connecté au hub SDR
- [ ] **Boris** : Déboguer les automatisations WhatsApp (déconnexions via Make)
- [ ] **Boris** : Fournir la spécification des métriques et flux de données pour le dashboard
- [ ] **Océane** : Rédiger le cahier des charges des métriques et flux nécessaires pour l'analyse CRO
- [ ] **Océane** : Se connecter au système UTM de Boris et à Entrepreneurs Work avec l'adresse @entrepreneurs.com
- [ ] **Sabrina** : Attribuer les tâches Trustpilot à Océane dans Entrepreneurs Work une fois l'accès configuré
- [ ] **Boris** : Vérifier les résultats financiers internes d'Alchimie (échéance 2026-08-05)

**Risques & vigilances**
- Attribution SDR artificiellement gonflée par des leads web non tracés correctement
- Impossibilité d'optimiser les campagnes sans métriques intermédiaires (vues uniques/page viewers)
- Raccourcisseurs de liens (short.io) qui suppriment ou modifient les UTM et cassent le tracking
- Automatisations WhatsApp instables bloquant les flux d'opt-in
- Risque de silos entre marketing et communication si la coordination UTM n'est pas cadrée
- Baisse du CA après fin juillet malgré volumes d'appels SDR constants (probable dépendance aux leads web)

**Projets liés** : [[Automatiser Trustpilot collecte]] · [[Plateforme Partenaires Dubaï — tracking & dashboards]]

Tags : #tracking #attribution #utm #dashboard #marketing-ops
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 05/08/2026 12:03 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a examiné plusieurs points opérationnels et de pilotage. La mise sur le marché de Bourbon génère une forte charge de travail et du stress, tandis que les automatisations WhatsApp ne fonctionnent pas de manière fiable. En parallèle, les données de tracking sont jugées incohérentes, avec des écarts importants entre impressions, vues uniques et inscriptions, ce qui empêche le marketing d’être autonome dans l’analyse de la performance. Un autre sujet majeur concerne l’attribution des leads, avec le risque que les indicateurs SDR soient artificiellement gonflés par des leads web non correctement tracés. La décision commune est de centraliser le suivi UTM, de fiabiliser l’embedding iClosed et de construire d’abord un dashboard de communication / lancement comme pilote, avant de généraliser. Boris prendra en charge l’intégration du tracking dans un système unique, l’ajustement des règles UTM et des embeds, ainsi que la construction de dashboards dédiés. Océane se connectera à cette base UTM et rédigera un cahier des charges précisant les métriques et flux de données attendus. Sabrina et Charlotte devront ensuite recevoir les accès et les tâches dans le nouvel outil de gestion de projet.

📋 Outline

1. Charge de travail liée au lancement Bourbon et état général • 0:00:00

- Boris a indiqué que le lancement de Bourbon crée une forte charge de travail et beaucoup de stress, car plusieurs problèmes doivent être traités simultanément entre différentes équipes.
- Boris a précisé que les finances d’Alchimie ne vont « pas si mal », mais qu’il doit encore vérifier les résultats internes et prévoit d’autres retours dans l’après-midi.

2. Format de réunion mensuelle et retours • 0:00:00

- La réunion mensuelle a duré environ 1 h 20 et s’est déroulée sans problème technique.
- Les retours des participants ont été globalement positifs, avec une note moyenne autour de 0,9 au sondage interne.
- Océane a mentionné des préparatifs de dernière minute et travaille avec Céline pour automatiser les demandes d’informations en vue des prochaines réunions.

3. Automatisations WhatsApp défaillantes • 0:00:00

- Boris a réalisé deux tests via Make pour les messages et les opt-ins et a constaté que les connexions WhatsApp se déconnectent immédiatement et se ferment automatiquement.
- Cette défaillance bloque des flux de communication fiables et nécessite un débogage afin de rétablir un envoi d’opt-in stable.

4. Anomalies de tracking et préoccupations sur les données marketing • 0:00:00

- Océane a signalé des anomalies majeures dans le suivi des campagnes, en citant l’exemple de 757 000 impressions LinkedIn pour seulement 47 inscriptions, ce qui est incohérent et doit être analysé.
- Le métrique intermédiaire manquant est celui des vues uniques (page viewers), qui permettrait de savoir si le problème vient du faible taux de clic ou d’une mauvaise conversion de la landing page.
- Océane n’a pas aujourd’hui l’autonomie nécessaire pour accéder aux vues uniques et à d’autres métriques de tracking, ce qui limite sa capacité à commenter la performance avec confiance.
- Cédric a fait passer les liens par des raccourcisseurs (short.io) et Boris soupçonne que short.io a supprimé ou modifié les UTM, ce qui a cassé le tracking.
- HubSpot dispose de plusieurs connexions permettant de relier les leads tagués par UTM au revenu ; l’attribution des ventes aux inscriptions devrait donc être possible une fois les UTM corrigés.

5. Décision de centraliser les UTM et de construire d’abord un dashboard communication • 0:00:00

- Boris a proposé de conserver les outils tiers pour des usages spécifiques, tout en centralisant le tracking dans un seul système et en intégrant l’ensemble dans un flux de suivi unifié.
- L’approche retenue consiste à piloter d’abord une solution data/dashboard pour le pôle communication, à la valider et l’optimiser, puis à répliquer ce modèle dans les autres pôles.
- Boris a expliqué pourquoi une tentative directe de mise en place d’un modèle de données d’entreprise final n’a pas fonctionné et pourquoi un déploiement pôle par pôle est plus réaliste.
- Océane a demandé à se connecter à l’outil UTM déjà existant de Boris et a exprimé sa crainte de créer des processus en silos ; elle veut une bonne coordination pour que marketing et communication utilisent un tracking compatible.
- La plateforme COMEX n’est pas considérée comme suffisamment fiable ni digne de confiance pour un tracking partagé à ce stade ; elle devra être refondue ou remplacée pour cet usage.

6. Attribution SDR, leads web non tracés et besoin de segmentation • 0:00:00

- Boris a constaté que les SDR indiquent beaucoup d’appels, mais que le chiffre d’affaires a baissé après fin juillet malgré des volumes d’appels similaires, ce qui suggère que les leads générateurs de revenus proviennent davantage du site web que de l’outbound SDR.
- Le mélange actuel entre données SDR et sources web / marketing fait courir un risque de mauvaise attribution de la performance aux mauvais canaux.
- Cette mauvaise attribution empêche toute optimisation pertinente, car l’équipe ne peut pas distinguer quel canal — SDR, site web, YouTube, etc. — génère réellement les conversions.

7. Mise en place du tracking UTM et conventions de nommage • 0:00:00

- Océane a insisté sur le fait qu’il est impossible d’optimiser les lancements et les funnels sans savoir si les leads viennent de YouTube, Instagram, du site web ou d’autres canaux.
- Boris a proposé d’utiliser des paramètres UTM simples, au minimum utm_source, sur les liens des plateformes et des calendriers afin de capturer la source, le medium et la campagne pour chaque lead.
- Une bonne utilisation des UTM permettra de segmenter un iClosed embarqué sur plusieurs funnels en enregistrant source, medium et campagne dans la fiche du lead.
- Boris a expliqué qu’il existe des UTM sur le calendrier, pour savoir quel agenda a été utilisé, et des UTM sur les pages, pour connaître la source du lead ; les deux sont nécessaires pour une attribution complète.
- Le widget iClosed peut être intégré sur plusieurs pages, mais doit être associé à des UTM afin qu’un seul iClosed puisse servir de nombreux funnels tout en conservant les données de source.
- Boris ajustera le système pour permettre le choix des conventions de nommage et s’assurer que les UTM sont correctement appliqués sur les pages et les liens de calendrier.

8. Spécifications du dashboard et reporting dédié aux lancements • 0:00:00

- Océane va mettre en place un processus et accepte d’utiliser l’outil de tracking de Boris pour suivre les lancements au niveau des inscriptions et des sources.
- Boris construira un dashboard dédié, connecté au hub SDR, qui montrera combien de leads ont été contactés, combien ont pris rendez-vous et via quelle source, sans mélanger les métriques générales.
- Océane rédigera un cahier des charges listant les champs de données et les métriques précises nécessaires pour l’analyse CRO et les lancements.
- Océane a demandé à Boris de fournir une spécification claire des métriques et flux de données requis pour le dashboard de communication afin qu’elle puisse le construire rapidement.
- L’objectif attendu est qu’Océane se connecte au système UTM de Boris et mette en œuvre le dashboard pour suivre les impressions, les vues uniques, les inscriptions, les taux de conversion et le revenu par canal.
- Boris confirmera quels outils doivent être conservés, lesquels doivent être abandonnés, et comment les UTM doivent être générés et maintenus pour éviter de futures pertes liées aux raccourcisseurs.

9. Système de gestion de projet, accès et répartition des tâches • 0:00:00

- Boris déploie une couche globale de gestion de projet (Entrepreneurs Work) et a demandé à Océane de se connecter avec l’adresse Entrepreneurs afin que Sabrina puisse attribuer les tâches Trustpilot et les sujets de responsabilité.
- Le nouveau système inclura des alertes en temps réel, les enregistrements d’appels, les transcriptions et une visibilité sur la charge de tâches individuelle afin de mieux gérer les affectations et les blocages.
- Océane a confirmé qu’elle aura accès au système et qu’elle sera assignée au projet concerné afin que Sabrina puisse lui déléguer des tâches.
- Sabrina attribuera les tâches dans le système une fois qu’Océane aura rattaché son accès au compte Entrepreneurs, et Charlotte recevra l’accès lorsque le processus sera validé.
%% notes:fin %%
