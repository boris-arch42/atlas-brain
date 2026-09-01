---
type: call
date: 2026-09-01
source: sembly
participants: ["boris@entrepreneurs.com", "aman.verma@entrepreneurs.com", "venugopal.venkatesan@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Weekly Catch Up with Boris

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (01/09/2026 10:43).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 01/09/2026 10:43 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe va prioriser la construction d’un Data Dashboard centralisé et détaillé en mettant en place un processus documenté pour ingérer les données de Thomas dans la base de données de l’entreprise, puis en ajoutant le suivi, des filtres et le lien avec HubSpot pour tous les funnels. Les priorités immédiates sont le suivi des visiteurs et des UTM, ainsi que l’extraction des leads de calendrier afin de les recouper avec les données Closed-Won de HubSpot. Les décisions clés incluent la création d’un groupe WhatsApp avec Thomas, la vérification ou création d’une organisation cloud pour l’accès aux données, et une échéance de fin septembre pour finaliser le dashboard à l’échelle de l’entreprise.

📋 Outline

1. Préoccupation concernant les preneurs de notes automatiques et la confidentialité des données • 0:00:02

- Boris a soulevé une préoccupation de sécurité et de confidentialité au sujet des preneurs de notes automatiques pouvant être reliés aux événements du calendrier et partager le contenu des réunions sans consentement.
- Boris a demandé à Aman de confirmer si de tels outils étaient présents et de les exclure s’ils n’étaient pas autorisés.
- Responsables : Boris pour vérifier, Aman pour confirmer la présence éventuelle de preneurs de notes.

2. Créer un processus documenté pour stocker les données de Thomas dans la base de données • 0:01:05

- La tâche principale de la semaine consiste à créer, à partir des documents de Thomas, un processus permettant de stocker tous les flux de données dans la base de données de l’entreprise.
- Le processus doit couvrir le Data Storage, BigQuery, Looker Studio, les couches de requêtes et de staging, ainsi que les outils utilisés par l’équipe.
- Boris créera un groupe de communication WhatsApp incluant Thomas, Aman et les membres concernés de l’équipe pour coordonner les questions et clarifier les points ouverts.
- Responsables : Aman pour implémenter le processus documenté à partir des feuilles de Thomas ; Boris pour créer le groupe et soutenir l’avancement ; Thomas pour fournir des documents complémentaires.

3. Compte cloud et organisation pour le travail sur la donnée • 0:03:28

- Boris vérifiera avec l’équipe IA la visibilité actuelle du compte cloud et si un accès peut être accordé à l’équipe data.
- Si l’accès cloud existant n’est pas adapté, Boris créera une organisation ou un compte cloud séparé pour le projet de l’entreprise afin d’éviter d’interférer avec la configuration de l’équipe IA.
- La configuration proposée pourrait inclure des abonnements séparés pour les individus sous une nouvelle organisation, afin d’assurer une séparation des coûts et des գործընթացs.
- Responsables : Boris pour vérifier et créer l’organisation cloud si nécessaire ; l’équipe IA pour confirmer l’accès existant.

4. Tâches immédiates du dashboard — suivi des visiteurs et des leads UTM sur les pages de funnel • 0:05:44

- Deux tâches doivent être terminées avant la fin de la journée : 1) compter les visiteurs des pages du book funnel, 2) mettre en place le suivi des leads UTM par funnel/fenêtre pour la Week of Scale.
- Boris partagera l’accès à l’outil de funnel et aux pages afin que l’équipe puisse extraire les données de vues et de clics à intégrer dans le dashboard.
- L’objectif est de mesurer les conversions entre les vues de page, les leads et les clics sur chaque page de funnel spécifique.
- Responsables : Venugopal pour fournir aujourd’hui les données et l’accès requis ; Aman et Boris pour intégrer les comptages dans le dashboard.

5. Accès et identification des pages spécifiques du “book funnel” • 0:08:04

- Le book funnel dans l’outil est nommé “unlimited clients” ou “unlimited customers”, et l’accès aux pages sera fourni.
- Aman a confirmé avoir reçu la feuille de livraison des données qui liste les champs pertinents et servira de référence.
- Responsables : Venugopal pour envoyer l’accès aux pages ; Aman pour vérifier et utiliser la feuille de données.

6. Recouper les réservations de calendrier avec les deals Closed-Won de HubSpot • 0:09:20

- L’équipe doit extraire toutes les réservations de calendrier (callbooks) et les comparer aux enregistrements Closed-Won de HubSpot afin d’identifier les écarts dans les chiffres de ventes.
- Boris souhaite obtenir l’extraction du nombre d’appels réservés, des emails utilisés, du nombre de ventes conclues et du nombre de produits vendus à partir de ces événements de calendrier.
- L’objectif est de vérifier si les ventes générées par le funnel via les événements calendrier correspondent aux données de pipeline rapportées par Raphael et l’équipe Evergreen.
- Responsables : Venugopal pour vérifier la visibilité et extraire les données calendrier ; Boris pour recevoir et examiner la comparaison avec HubSpot.

7. Utiliser l’ID de deal HubSpot, des filtres par date et des pop-ups détaillés dans les dashboards • 0:12:07

- Le dashboard doit inclure des filtres de dates basés sur des plages calendaires précises, et pas seulement des fenêtres prédéfinies comme 7/30/90/12 mois, afin de permettre une analyse sur des périodes exactes.
- Chaque entrée Closed-Won dans les vues de funnel doit ouvrir une pop-up affichant les détails du deal : nom, email, téléphone, produit et revenus.
- L’identifiant le plus important à stocker et à relier est l’ID de deal HubSpot, afin de faire correspondre de manière fiable appels, opt-ins, leads et ventes, même lorsque les emails changent.
- Responsables : les développeurs du dashboard (Venugopal/Aman) pour implémenter les filtres et les pop-ups ; Boris pour s’assurer que l’ID HubSpot est inclus dans le modèle de données.

8. Échéance et périmètre du dashboard de données de l’entreprise • 0:15:54

- Boris a fixé une échéance à l’échelle de l’entreprise pour finaliser le Data Dashboard complet d’ici la fin septembre.
- Le périmètre du dashboard inclut les funnels Evergreen, les événements de communication/marketing comme la Week of Scale, ainsi que les données de livraison et d’opérations.
- Boris a insisté sur le respect strict des délais et a indiqué qu’il gérerait les autres automatisations afin que l’équipe puisse se concentrer sur le travail du dashboard.
- Responsables : Venugopal et Aman pour prioriser les tâches liées au dashboard ; Boris pour gérer les automatisations plus larges et superviser l’avancement.

9. Semaine de construction et plan de duplication du template • 0:19:41

- Cette semaine est une semaine de “build” concentrée sur la création d’un template de dashboard validé pour les funnels book et quiz.
- Une fois le template du funnel validé, le plan est de le dupliquer sur les autres funnels afin d’accélérer les futurs développements du dashboard.
- Boris reste le point de contact principal pour la vision du dashboard et sera disponible pour répondre aux questions tout au long de la semaine.
- Responsables : Aman et Venugopal pour construire et valider les templates ; Boris pour fournir l’orientation et répondre aux questions.
%% notes:fin %%
