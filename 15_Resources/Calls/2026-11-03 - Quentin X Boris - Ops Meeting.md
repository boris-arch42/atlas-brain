---
type: call
date: 2026-11-03
source: sembly
participants: ["boris@entrepreneurs.com", "42lab@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Quentin X Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (03/11/2026 15:49).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 03/11/2026 15:49 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a passé en revue plusieurs chantiers prioritaires liés à la monétisation, aux automatisations, à la rétention et aux audits payants. Quentin doit vérifier les API de Boris, contrôler les automatisations HubSpot/Make liées aux transactions, préparer les communications d’invitation pour les multi-licences, et finaliser l’appui produit autour des offres détectées par l’IA. Boris a insisté pour finaliser rapidement la maquette de l’audit payant ainsi que le brief rétention/renouvellement afin de pouvoir accélérer la commercialisation avant la mi-novembre. En parallèle, l’équipe a validé le déclenchement des invitations collaborateurs à partir des organigrammes détectés par IA, ainsi que l’envoi d’un email ou d’une notification pour promouvoir les licences multi-utilisateurs. D’autres sujets ont porté sur des écarts de tags/transcription, les accès sensibles, le programme Moonshot beta, et la nécessité de clarifier les rôles, la segmentation et les documents manquants.

📋 Outline

1. Demande de vérification des API • 0:00:09

- Boris a demandé à Quentin de vérifier les API afin de pouvoir finaliser ses saisies de données financières et de lieu choisi pour les tableaux de bord.
- Quentin a confirmé que le sujet est urgent et qu’il prendra en charge cette vérification.

2. Promotion multi-licences et invitations collaborateurs via organigramme détecté par IA • 0:00:48

- Quentin a indiqué qu’il n’existe pas encore de positionnement public fort pour les multi-licences sur la plateforme, et qu’il a réutilisé la page « associates » pour préparer les futurs lancements de contrats duo/trio.
- Il a également développé une fonctionnalité de licence collaborateur qui génère des préconisations à partir d’un organigramme détecté par IA lors des séances de coaching.
- La détection identifie environ 300 clients ayant des collaborateurs internes pouvant recevoir un accès collaborateur.
- L’équipe a validé l’envoi d’un email ou d’une notification push invitant ces collaborateurs détectés et affichant les prénoms identifiés, afin que les détenteurs du compte puissent leur accorder l’accès.
- Quentin doit publier le contenu de l’email de monétisation dans le board de monétisation, puis lancer l’envoi lorsque ce sera prêt.

3. Maquette d’audit payant et documents manquants • 0:03:35

- Quentin a indiqué ne pas avoir reçu l’ensemble des documents nécessaires pour finaliser la maquette de l’audit payant, et attendait des fichiers complémentaires de Sabrina.
- Il a examiné la première version du diagnostic et a noté qu’une grande partie recoupe le contenu de l’onboarding V2, tout en s’attendant à des ajouts possibles une fois les matériaux complets reçus.
- Boris a demandé que l’audit payant soit prêt d’ici la mi-novembre afin de pouvoir commercialiser fortement pendant les deux dernières semaines de novembre et alimenter la campagne de lancement 5 jours.

4. Calendrier du lancement 5 jours • 0:05:28

- Les dates du lancement 5 jours ont été précisées du 22 au 26 novembre.
- Boris a insisté sur la nécessité d’avoir les supports d’audit et d’acquisition prêts pour tirer parti de ce lancement.

5. Transactions HubSpot et automatisations pour les ventes de sièges • 0:06:07

- Quentin soupçonne que les automatisations Make issues de WAP créent des transactions dans HubSpot, et il doit vérifier que la création de pipeline/onglet et la génération des transactions fonctionnent correctement pour les achats de places/sièges.
- Jordan avait déjà demandé de s’assurer que les transactions sont bien créées après une première vente ; Quentin a donc classé ce contrôle comme prioritaire.

6. Problème des « clients manquants » et envoi d’emails • 0:07:10

- Le problème des « clients manquants », où des emails n’étaient pas envoyés, a été analysé : Léonard a documenté la cause et la manière de corriger le problème, et Claire a confirmé l’incident après vérification du TLA.
- La cause semble liée à la configuration de l’email d’envoi et à une proposition de modification admin visant à changer l’adresse de l’expéditeur pour que les messages partent correctement.
- Quentin a précisé que Léonard avait fourni des pistes d’amélioration et qu’il poursuivra le suivi à son retour, Léonard étant absent ce jour-là et de retour le lendemain.

7. Brief rétention/renouvellement et segmentation par tags • 0:08:47

- Boris a confirmé avoir sollicité à plusieurs reprises le brief d’Alexandre sur la rétention et les renouvellements, sans l’avoir encore reçu, ce qui bloque l’industrialisation du flux.
- La segmentation souhaitée repose sur le statut client : actif (avec moins ou égal à 3 mois restants), sortant (parti depuis moins d’un mois) et sorti (depuis plus d’un mois), avec l’usage de tags pour déclencher des relances ciblées.
- Quentin a indiqué que la plateforme dispose déjà de la plupart des fonctionnalités nécessaires : tags, signaux de score et score d’upsell fondé sur l’IA à partir des notes des coachs et des signaux de coaching récents.
- Une vue renouvellements est disponible sur platform.entrepreneurs.com/renewals pour l’exploitation opérationnelle.
- Quentin a décrit le processus d’upsell : combiner les scores des questionnaires et une analyse IA des 90 derniers jours de coaching pour prioriser les appels et traiter les objections, afin d’augmenter la conversion sur des clients satisfaits.
- Caroline et Léonard ont déjà itéré sur les parcours de renouvellement et l’interface, mais certains éléments UI sont actuellement cassés et doivent être corrigés avant un déploiement complet.

8. Écart de transcription/vidéo et problème de tags • 0:14:24

- Un clic verbatim depuis l’outil a ouvert la vidéo à un moment qui contredisait le statut enregistré, ce qui laisse penser à une surcharge ou à une incohérence de données.
- Quentin pense avoir peut-être écrasé par erreur la version envoyée et attend le retour d’Alexandre pour confirmer l’origine de l’anomalie.
- Des tags liés au fait que Caroline ait appelé ou non n’étaient pas pris en compte, et ces tags manquants doivent être vérifiés.

9. Stratégie de revenus de la plateforme : services pluridisciplinaires et audit • 0:15:40

- L’objectif principal est de financer la plateforme via des offres pluridisciplinaires et des audits, l’audit servant surtout à compenser les coûts d’acquisition plutôt qu’à financer directement la plateforme.
- L’équipe ne doit pas retarder le travail sur l’audit, car cela impacte la compensation des coûts d’acquisition et le plan financier global de la plateforme.

10. Accélération marketing et création d’une nouvelle ligne de revenus • 0:16:24

- L’équipe prévoit de lancer rapidement une campagne d’emailing et de communication afin de tester la réceptivité du marché, notamment la sensibilité au prix.
- Les canaux promotionnels envisagés incluent l’email, les notifications push, la mise en avant sur la page d’accueil et des encarts dans le dashboard ciblant les utilisateurs potentiellement éligibles.
- L’objectif est de créer une nouvelle ligne de revenus à partir de la vente de licences plateforme et de licences collaborateur.

11. Tarification des licences, réalité commerciale et mesure du ROI • 0:17:08

- Une licence plateforme sur 12 mois existe avec un prix actuel évoqué à 0,20, mais des incertitudes persistent sur la manière dont les ventes sont présentées et suivies.
- Les discussions avec Alec montrent des contraintes budgétaires et des demandes de baisse de prix ou de démonstration du ROI ; Quentin doit préparer un document récapitulant l’année écoulée et les options proposées.
- La contribution indirecte de la plateforme — écosystème, gain de temps, positionnement premium — rend difficile l’attribution des conversions uniquement à la plateforme, ce qui complique la quantification du ROI.
- Deux pistes d’atténuation ont été discutées : absorber les coûts collaborateurs en centralisant les services pour réduire les coûts globaux, ou générer du business via le staffing et les recommandations pour augmenter le flux de trésorerie.

12. Programme Moonshot beta et collecte de données • 0:22:09

- Moonshot est un agent côté client, sur Windows ou Mac, qui collecte des données d’usage étendues (fenêtres ouvertes, messages envoyés, patterns) et nécessite des bêta-testeurs internes avant un lancement public.
- L’équipe souhaite faire tester l’agent par de plus gros collaborateurs afin d’identifier des patterns sans exposer des données RH trop sensibles ; des tests initiaux ont déjà été réalisés sur les machines de l’équipe.
- Le programme implémentera plus tard du chiffrement de bout en bout et du Bring Your Own Keys, mais les versions actuelles restent en clair pour accélérer le débogage ; la sécurité sera renforcée avant un déploiement plus large.
- L’adoption des n-grams et de l’outil NotTaker est faible chez les Heads et les commerciaux, ce qui limite la collecte de données et la construction de la base de connaissances ; une promotion interne, voire un changement de nom de l’outil, a été proposée pour améliorer l’adoption.

13. Contrôle des accès, rôles et gestion des appels sensibles • 0:26:34

- L’accès aux appels enregistrés et aux notes est actuellement très restreint : seuls les coachs ont accès aux appels de coaching, et les appels très sensibles des Heads sont limités à Léonard et Quentin.
- L’équipe n’a pas encore mis en place une gestion complète des rôles dans le produit et reste prudente en raison d’incidents passés de routage ou de fuite.
- Il existe une attente commune selon laquelle les réunions sensibles doivent rester hors de la capture générale, sauf si elles sont explicitement assignées et que les rôles appropriés sont configurés.

14. Coûts de développement, valeur de l’équipe et ajustements possibles • 0:27:31

- Quentin a rappelé le coût réel du développement sur le marché français et a défendu la valeur de l’équipe actuelle ainsi que de son expertise, jugées plus rentables qu’un remplacement par des profils inexpérimentés.
- L’équipe reste ouverte à des changements de stratégie ou à des remplacements si les besoins business l’exigent, mais privilégie des solutions qui préservent la qualité et l’expertise.

15. Revue du document de Quentin et processus de décision • 0:28:31

- Boris a indiqué qu’il allait relire le document préparé par Quentin et a promis une évaluation honnête et impartiale pour parvenir à une décision logique, plutôt qu’à une décision dictée par l’émotion ou le ressentiment.
- Quentin a rappelé que le document contient des solutions concrètes et des propositions de coûts, et a demandé que soient pris en compte une rémunération équitable et des conditions de travail durables.

16. Conclusion et prochains pas • 0:28:53

- Quentin a conclu en précisant qu’il n’est pas guidé par son ego, qu’il recherche une rémunération soutenable et qu’il attend de l’équipe qu’elle travaille comme si le produit leur appartenait, tout en veillant à pouvoir être payée correctement.
- Les prochaines étapes convenues sont l’envoi de la communication marketing, la finalisation et l’envoi du document pour revue, le recrutement de bêta-testeurs Moonshot, et l’attente des retours d’Alexandre/Alec sur l’override et les budgets.
%% notes:fin %%
