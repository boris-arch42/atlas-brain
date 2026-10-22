---
type: call
date: 2026-10-22
source: sembly
participants: ["boris@entrepreneurs.com", "pierrenauts@gmail.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Pierre x Boris (Entrepreneurs.com) 🚀

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (22/10/2026 16:53).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 22/10/2026 16:53 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

Aligner les correspondances entre événements et modèles, ainsi que les déclencheurs calendrier, afin que les messages automatisés (confirmations de réservation, rappels et relances d’épisode) s’envoient correctement. Corriger également les connecteurs Instagram et YouTube pour récupérer les prospects manqués. Les responsabilités sont clarifiées pour les mises à jour Zapier/webhook et pour la mise en place d’une campagne de récupération. Prochaines étapes : Boris doit vérifier les connexions Zapier/webhook et calendrier, Sun doit créer de nouvelles landing pages par épisode, et Pierre doit lancer les campagnes de récupération dès que Boris fournit les listes de contacts exportées.

📋 Outline

1. Objectifs de la réunion et problèmes urgents de connecteurs • 0:00:00

- L’objectif de la réunion était de s’assurer que les connexions e-mail et messagerie déclenchent les bonnes automatisations en aval, et d’identifier les lacunes sur les intégrations YouTube et Instagram.
- Instagram est actuellement déconnecté de ClosedMap et doit être reconnecté en urgence ; il n’était pas clair si Anne ou Boris prendrait en charge cette reconnexion.
- Une configuration manquante sur l’épisode 2 de YouTube a laissé passer des prospects ; le flux YouTube doit donc être revu et corrigé.

2. Correspondance modèles-événements et confusion sur les noms • 0:01:38

- Les modèles envoient des messages de confirmation différents selon qu’un prospect a déjà échangé sur WhatsApp ; ces modèles sont déclenchés par des événements calendrier qui doivent être correctement associés.
- Certains noms d’événements sont dupliqués ou trop proches, ce qui crée un risque de confusion et de déclenchement incorrect des modèles ; la cartographie doit être clarifiée et standardisée.
- Pierre a revu quels pictogrammes d’événements correspondent aux sources (téléphone, loupe, ordinateur) et a demandé à Boris de confirmer les correspondances source → événement.

3. Événements spécifiques par source, notamment YouTube • 0:02:51

- Les prospects provenant de YouTube doivent disposer d’un lien de réservation dédié et d’un événement calendrier spécifique afin de recevoir le bon modèle ; Boris a confirmé qu’un lien de réservation spécifique YouTube existe بالفعل.
- Certains événements, par exemple la réactivation d’anciens prospects, sont déjà correctement cartographiés, mais Pierre supprimera les associations incorrectes lorsqu’une source n’a pas réellement échangé avec l’équipe.

4. Relaunch / relance de réservation et tags de suivi • 0:06:37

- Les prospects qui commencent mais ne finalisent pas la réservation sur le site doivent être capturés via un événement/calendrier de type « relance site web » et recevoir des messages de relance spécifiques.
- Pierre a constaté peu ou pas de trafic sur un calendrier de relance et a effectué un test en direct pour vérifier l’envoi des messages ; le test a montré que le flux fonctionne désormais.
- Deux tags servent de points de contrôle pour ces flux : book_site_web et recup_site_web ; ils doivent être appliqués de manière cohérente pour déclencher les messages de récupération.

5. Flux de réservation du site web et cohérence des CTA • 0:09:58

- Le CTA du site (« réserver votre session » / « obtenir un plan d’action personnalisé ») pointe vers le même calendrier ; les deux CTA doivent donc mener au même événement de réservation afin d’éviter la fragmentation.
- Si les prospects remplissent le formulaire de réservation, tout est correct ; sinon, ils doivent être dirigés vers le flux de relance pour suivi.
- Pierre a réalisé un test de bout en bout du parcours de réservation afin de vérifier les modèles et le comportement de réservation, et a confirmé que les modèles attendus sont bien reçus.

6. Modèles de rappel et délivrabilité attendue • 0:11:28

- Un rappel pré-appel à 3 heures est configuré et envoie un court message de confirmation avec l’heure du rendez-vous ; ce message a été vérifié lors des tests.
- Les modèles de relance et de rappel utilisent les mêmes icônes de source (ordinateur, loupe, téléphone) et ont été contrôlés pour garantir la couverture de toutes les sources.
- Pierre s’attend à une amélioration du taux de présence grâce à la cartographie corrigée et à la configuration des rappels.

7. Workflow des épisodes YouTube et configuration Zapier/webhook • 0:13:11

- Pour les flux déclenchés par épisode, un webhook sur la landing page envoie les données vers Zapier, qui ajoute un tag spécifique YouTube (par exemple youtube_secret_1) et déclenche la séquence de suivi ; c’est ainsi que l’épisode 1 a été géré.
- La landing page ou le webhook de l’épisode 2 n’était pas connecté à temps, ce qui a entraîné une perte de prospects ; chaque épisode nécessite soit une nouvelle landing page, soit une mise à jour du déclencheur webhook vers le bon tag d’épisode.
- Le Zap doit être dupliqué ou mis à jour pour chaque épisode, et le tag (youtube_secret_2, youtube_secret_3, etc.) doit être correctement défini dans Zapier pour envoyer le bon message / replay.

8. Récupération des prospects manqués et lancement d’une campagne • 0:18:42

- Boris a confirmé qu’un export Excel des prospects peut être fourni et qu’au minimum le fichier doit contenir le prénom et le numéro de téléphone pour les relances.
- Pierre lancera une campagne de récupération dès qu’il recevra la liste de contacts et les consignes sur le message d’ouverture souhaité ainsi que le rythme d’envoi pour éviter la saturation.
- Boris vérifiera et fournira les contacts exportés, et précisera le premier message à envoyer ainsi que le résultat attendu (par exemple, reprogrammer un appel).

9. Responsabilités et validation des prochaines étapes • 0:19:58

- Boris vérifiera les connexions Zapier/webhook et calendrier, dupliquera ou mettra à jour les Zaps pour les nouveaux épisodes YouTube, et fournira le fichier exporté des prospects pour la reprise.
- Sun doit créer une nouvelle landing page par épisode afin que le déclencheur webhook fonctionne correctement pour chaque diffusion.
- Pierre mènera la campagne de récupération à partir du fichier exporté et sera informé du message initial à envoyer ainsi que de la logique de réservation attendue ; Pierre et Boris coordonneront les corrections supplémentaires si nécessaire.
%% notes:fin %%
