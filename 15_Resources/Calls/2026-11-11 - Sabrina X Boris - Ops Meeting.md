---
type: call
date: 2026-11-11
source: sembly
participants: ["boris@entrepreneurs.com", "sabrina.dahel@entrepreneurs.com", "fabrice@entrepreneurs.com", "rachid.oubih@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Sabrina X Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (11/11/2026 16:12).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 11/11/2026 16:12 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

Les participants ont comparé les volumes de rendez-vous entre iClose et HubSpot et identifié plusieurs sources possibles d’écart, notamment le décalage horaire, les doublons et les propriétés ou automatisations HubSpot. Ils ont discuté de la normalisation des UTM et Boris a indiqué qu’il allait fusionner les données et vérifier les rendez-vous du site web individuellement. Les participants ont convenu de prioriser le nettoyage du pipeline HubSpot et de ses motifs et catégories, avec un travail sur le pipe prévu le lendemain et un nettoyage global visé vendredi. Ils ont aussi discuté de la fiabilité des données entre iClosed, HubSpot et les outils financiers, ainsi que de l’évolution des workflows, des licences et du pipe de fidélisation.

📋 Outline

1. Rapprochement des rendez-vous iClose et HubSpot • 0:01:24

- Pour le tunnel VSL, iClose et le tableau de vente indiquaient tous deux 51 appels réservés du 1er au 11 novembre, correspondant à 50 personnes distinctes et à un doublon.
- Les participants ont relevé que des leads ayant déjà une transaction ouverte pouvaient générer une seconde transaction, plutôt que mettre à jour la première.
- Un écart d’un rendez-vous peut s’expliquer par le changement d’heure : un rendez-vous réservé près de minuit en heure française a pu être comptabilisé dans le mois précédent par iClose, dont le système fonctionne selon l’heure américaine.
- Les participants ont souligné qu’il fallait distinguer le nombre total d’appels réservés des doublons, des tests et des leads déjà associés à une transaction ouverte.
- Pour le site web, les chiffres comparés n’étaient pas cohérents : 19 appels apparaissaient sur iClose pour Sabrina, 20 pour Boris, et moins de rendez-vous ressortaient dans HubSpot selon les filtres appliqués.
- Boris a indiqué qu’il vérifierait un par un les 20 rendez-vous associés à la page d’accueil pour contrôler leurs UTM et comprendre ceux qui ne ressortaient pas dans HubSpot.

2. Qualité des données et automatisations HubSpot • 0:10:39

- Les participants ont évoqué des suppressions de transactions par des membres de l’équipe et ont rappelé qu’un doublon devait être fermé comme 'perdu, doublon' plutôt que supprimé, afin de conserver une trace dans l’historique.
- Boris a estimé que les données extraites directement d’iClose étaient la référence pour les rendez-vous et que les écarts pouvaient provenir du transfert vers HubSpot ou de traitements effectués dans HubSpot.
- HubSpot compte environ 200 à 300 anciens workflows susceptibles de modifier des transactions ou des propriétés UTM, ce qui complique l’identification de la source des écarts.
- La suppression de tous les workflows a été évoquée comme une option, mais Rachid a préconisé d’examiner leurs connexions et usages avant toute intervention.
- Sabrina a proposé de tracer quelques transactions concrètes pour déterminer pourquoi elles ne ressortent pas dans les recherches filtrées.

3. Normalisation des UTM et méthodes de filtrage • 0:14:13

- HubSpot comporte une ancienne et une nouvelle propriété UTM campagne, cette dernière étant signalée par une icône de flamme.
- La nouvelle propriété ayant été mise en place récemment, les premiers leads du mois ne sont pas nécessairement renseignés dans ce champ, ce qui peut expliquer certains écarts de filtrage.
- Des variantes d’écriture d’une même campagne, comme 'quiz funnel' et 'quiz-funnel', peuvent séparer les résultats et empêcher une recherche de remonter tous les deals concernés.
- Une liste déroulante a été proposée pour limiter les erreurs de saisie, mais les participants ont relevé qu’elle demanderait une mise à jour à chaque création d’UTM et pourrait être difficile à gérer compte tenu du volume.
- Rachid a proposé une structure avec une catégorie principale sélectionnable et une sous-catégorie en texte libre, afin de mieux repérer les champs vides ou mal renseignés.
- Sabrina a aussi proposé de publier chaque mois dans Works la liste des deals à utiliser pour permettre un copier-coller sans variations d’orthographe.
- Le document partagé recensait 427 valeurs UTM campagne, tandis que les participants ont noté que l’historique et les pratiques antérieures contribuaient à ce volume.
- Boris a indiqué qu’il allait fusionner les données.

4. Réorganisation des workflows et des étapes de transaction • 0:20:39

- Rachid a relevé des workflows qui se chevauchent ou se contredisent, notamment des automatisations qui recréent des transactions après certains changements de statut.
- Sabrina a rappelé que l’équipe ne dispose que d’une semaine et a proposé de traiter les éléments par ordre de priorité.
- Rachid a proposé d’ajouter des étapes permettant de distinguer les contrats envoyés, signés et achetés, mais ne veut pas modifier seul des éléments utilisés par les équipes.
- Sabrina et Rachid ont convenu de se bloquer une heure le lendemain à midi pour préciser les changements du pipeline.
- La colonne 'Tentative de contact' doit être archivée afin qu’elle ne soit plus visible et n’encombre pas le pipeline.

5. Rapprochement des données commerciales et financières • 0:23:24

- Fabrice a recommandé de rapprocher régulièrement les chiffres des rapports avec les données de HubSpot, iClosed, de la finance et de la base client.
- Un contrôle mensuel par échantillonnage de chiffres permettrait de repérer les écarts et de vérifier la cohérence des données.
- Sabrina a expliqué qu’iClosed indique les rendez-vous, mais ne permet pas à lui seul de connaître le devenir des leads ni les résultats financiers des transactions.
- Sabrina a indiqué qu’un rapprochement avec Odoo serait nécessaire pour consulter les encaissements liés aux ventes.
- Rachid a précisé que le travail sur HubSpot doit être finalisé avant que Wacim se rapproche de Boris pour la connexion avec Odoo.

6. Suivi des rendez-vous et qualité des données dans HubSpot • 0:25:18

- Rachid a ajouté au tableau de bord une vue des transactions dont le rendez-vous a eu lieu sans que l’étape soit mise à jour, afin d’identifier les dossiers à relancer auprès des closers.
- Certains commerciaux déplacent le rendez-vous R1 pour enregistrer un R2 au lieu de créer une nouvelle invitation, ce qui fausse le décompte des rendez-vous.
- Sabrina a expliqué que les rendez-vous R1 et R2 doivent être enregistrés séparément pour obtenir des données fiables.
- La connexion des agendas des commerciaux à HubSpot pourrait permettre de savoir si un rendez-vous a eu lieu ou a été annulé, mais cette connexion avait été arrêtée en raison de problèmes de routage avec Calendly.
- Rachid a proposé de créer un tableau de bord à partir des données de rendez-vous disponibles et de clarifier si les agendas doivent être reconnectés.

7. Numéros CloudTalk pour les équipes • 0:29:07

- Rachid a indiqué avoir obtenu des numéros belges et suisses pour CloudTalk, notamment un numéro associé à la région de Lausanne.
- Il a créé des comptes CloudTalk pour Alexandre et Caroline et leur a communiqué un numéro mobile français.
- Il a proposé de fournir un numéro suisse, éventuellement mutualisé, si les équipes en ont besoin pour appeler des clients suisses.
- CloudTalk étant connecté à HubSpot, les appels devraient être détectés et associés aux données correspondantes.

8. Accès et licences HubSpot • 0:29:30

- Sabrina a signalé que le nombre de licences disponibles pourrait être insuffisant pour les besoins des commerciaux et que les comptes Google posaient également une contrainte.
- Rachid a indiqué avoir demandé la conversion de sept à huit licences Entreprise en licences Core, ce qui porterait le total à seize licences.
- Il a précisé que les sièges n’ont pas tous besoin d’une licence Entreprise et qu’il est possible de revoir les accès des utilisateurs externes.
- Rachid a demandé à Sabrina de l’aider à déterminer quels utilisateurs conserver ou retirer lors de la revue des accès.

9. Nettoyage des pipelines et échéances • 0:31:08

- Sabrina a demandé une échéance pour fiabiliser les données du pipeline, notamment les motifs de fermeture et les catégories supplémentaires.
- Le nettoyage de la partie pipeline a été prévu pour le lendemain, tandis que Boris a estimé que le nettoyage global et des données UTM pourrait être fait vendredi.
- Les participants ont également évoqué la nécessité de clarifier les événements et canaux d’acquisition ouverts, dont le nombre élevé complique le maintien de données propres.
- Boris a expliqué que la multiplicité des canaux et des funnels entraîne la création de nombreux événements pour suivre correctement les sources d’acquisition.

10. Organisation du pipe de fidélisation • 0:34:22

- Les recommandations d’ambassadeurs ne remontent pas automatiquement dans HubSpot et pourraient être saisies manuellement au départ.
- Sabrina a proposé de supprimer les étapes M0, M3, M6 et M9 du pipe de fidélisation, car le suivi correspondant est désormais géré sur la plateforme.
- Elle a proposé de faire remonter les clients dans une étape dédiée à J-60 de la fin de leur contrat, afin que Caro les prenne ensuite en charge.
- Aujourd’hui, une transaction gagnée crée automatiquement une nouvelle fiche client à M0 dans le pipe de fidélisation.
- Sabrina a souligné le risque de doublons et de suivis inadaptés si les clients résiliés ou rétractés restent aussi dans le pipe de fidélisation.
- Rachid a estimé que conserver les données dans HubSpot pourrait rester utile pour de futures campagnes de nurturing, mais a indiqué que ce sujet n’était pas urgent.

11. Éligibilité des participants aux immersions et aux boards • 0:38:20

- Rachid a demandé si une personne extérieure n’ayant jamais été cliente pouvait payer pour participer à une immersion board.
- Sabrina a indiqué que la participation à un board suppose un niveau d’expérience et des problématiques de gouvernance adaptées, afin d’éviter de mélanger des débutants avec les clients.
- Pour les événements de scaling, Sabrina a indiqué que l’accès est plus ouvert et qu’une personne extérieure peut être accueillie.
%% notes:fin %%
