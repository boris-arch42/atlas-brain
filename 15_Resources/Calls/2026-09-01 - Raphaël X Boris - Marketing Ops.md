---
type: call
date: 2026-09-01
source: sembly
participants: ["boris@entrepreneurs.com", "raphael.dalleau@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Raphaël X Boris - Marketing Ops

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (01/09/2026 11:13).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 01/09/2026 11:13 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a examiné les écarts entre les conversions remontées et les dépenses publicitaires dans plusieurs outils. Elle a convenu d’unifier les filtres de date et de créer un événement de conversion dédié (« Quiz Final ») avec des UTMs afin de nettoyer l’attribution. La réunion a également couvert les améliorations du SDR Hub V2, ainsi que les prochaines étapes pour suivre les no-shows et partager des liens d’implémentation directs plutôt que des captures d’écran. Les actions clés portent sur la création de l’événement dédié et de l’UTM, l’alignement des filtres de date d’ici demain, l’investigation des écarts de conversion restants avec Uber/WOP, et l’échange de liens directs.

📋 Outline

1. Écart signalé entre conversions et dépenses publicitaires • 0:00:00

- Raphaël a indiqué que les conversions sur les 7 derniers jours ne concordent pas entre les outils, avec des totaux différents (par exemple 12, 32 et 39), ce qui crée une incertitude sur la performance réelle. (Raphaël doit revérifier sa vue.).
- Boris a noté que l’écart peut venir de plages de dates 7 jours différentes utilisées par chaque outil et a proposé d’aligner les filtres de date comme première correction. (Boris doit ajuster les filtres.).
- Les deux ont convenu que l’écart n’est pas énorme mais suffisamment important pour nécessiter une investigation afin d’éviter de mauvaises décisions. (Les deux doivent surveiller.).

2. Réconciliation du spend total et alignement des devises • 0:02:47

- Raphaël a présenté des chiffres cumulés de dépenses publicitaires totalisant 14 168 $ sur l’ensemble des campagnes.
- Boris a reconverti ce montant à environ 12 100 € et a confirmé que cela correspond à la vérification récente d’Uber.
- Conclusion de Boris : les dépenses globales s’alignent, ce qui indique que le problème concerne surtout le comptage des conversions plutôt que le reporting des dépenses. (Boris doit poursuivre les vérifications.).

3. Événements manquants et incohérences de comptage (iClosed / scheduler) • 0:03:42

- Raphaël a relevé des différences entre les chiffres du tableau de bord et ceux du scheduler, par exemple 17 appels réservés dans une vue contre seulement 6 événements scheduler pour BookFunnels, ce qui brouille la lecture des appels réellement réservés. (Raphaël doit revérifier les requêtes concernées.).
- Boris a expliqué qu’une partie des écarts provient de sources de données différentes (produit WOP versus autres intégrations) et de noms d’événements réutilisés qui polluent les comptes. (Boris doit cartographier les sources.).

4. Nécessité de créer un événement dédié pour le Quiz Final • 0:07:59

- Boris a recommandé de créer un événement unique et dédié pour le funnel du quiz final afin d’éviter la contamination croisée liée à la réutilisation d’événements et d’obtenir des comptes propres. (Boris doit créer l’événement ; Raphaël doit l’implémenter dans son funnel.).
- Raphaël a estimé que les chiffres changeraient fortement une fois l’événement dédié mis en place, avec un exemple à 18 dans le SDR Hub qui serait différent ensuite. (Raphaël doit confirmer après modification.).
- Ils ont discuté du nom de l’événement, avec une suggestion comme « Meeting with an expert », et de l’ajout d’un emoji distinct pour le rendre facilement identifiable. (Les deux doivent valider le nom final.).

5. Lacunes d’attribution et UTMs manquants (Google vs Meta) • 0:09:51

- Raphaël a indiqué que l’attribution actuelle ne montre que les données Meta et que l’attribution Google n’a pas encore été intégrée, ce qui rend l’attribution incomplète. (Boris doit activer l’intégration de l’attribution Google.).
- Boris a dit qu’il ajoutera un UTM au nouvel événement (score-up) afin qu’il puisse être réutilisé sur plusieurs funnels avec un suivi cohérent de la source, du medium et de la campagne. (Boris est responsable de l’ajout des UTMs ; Raphaël doit les appliquer sur les funnels.).
- Ils ont identifié des liens de quiz embarqués et certaines sources de leads inconnues sans UTMs (leads « mystère ») ; Raphaël a suggéré de désactiver les aimants à leads dont l’origine ne peut pas être retrouvée. (Raphaël doit envisager de désactiver ; Boris doit tracer l’intégration embed.).

6. Démo du SDR Hub V2 et améliorations du workflow • 0:13:26

- Boris a présenté les nouvelles fonctionnalités du SDR Hub, notamment les alertes en temps réel, le rafraîchissement automatique, les notifications sonores pour les nouveaux leads, ainsi qu’un affichage clair de la priorité et de la source du lead. (Boris est responsable du déploiement.).
- Le Hub inclut désormais des mémos de leads enrichis, les liens des landing pages, les réponses aux formulaires et un scorecard guidé que le SDR remplit pendant l’appel pour vérifier l’identité et les critères de qualification. (L’équipe SDR doit suivre ce nouveau processus de scorecard.).
- Une fois qualifié, le Hub ouvre le bon calendrier (Book Funnel, Quiz Funnel) et préremplit l’UTM, le prénom, le nom, l’e-mail et le téléphone, puis génère un résumé pour le closer. (Boris doit s’assurer du bon fonctionnement du préremplissage ; les SDR doivent l’utiliser.).
- L’outil de données V2 propose des visuels améliorés et un centre de commande global affichant les dépenses, les leads, les appels réservés, les revenus hebdomadaires et les métriques par funnel ; deux points de données restent à connecter : les appels SDR et l’EROS collecté. (Boris doit finaliser ces connexions.).

7. Suivi des no-shows et besoin de définir un processus • 0:17:57

- Boris a expliqué que le reporting des no-shows n’est actuellement pas fiable car il dépend d’un signalement manuel par les commerciaux, ce qui fait que les no-shows sont souvent non enregistrés et que les données restent incomplètes. (Boris et Lucas doivent définir un processus.).
- Ils ont convenu de concevoir un processus clair pour capturer les no-shows avant d’ajouter un suivi automatisé dans le Hub, car l’outil doit refléter le flux opérationnel convenu. (Boris doit proposer le processus ; Lucas doit conseiller sur le workflow du closer.).

8. Investigation des écarts de conversion restants et alignement des filtres de date • 0:19:45

- Boris va standardiser les filtres de date d’ici demain et, si les écarts persistent, il investiguera avec Uber pour comprendre comment les conversions sont suivies (par exemple click-to-pay vs page de paiement réelle). (Boris doit piloter l’investigation ; Raphaël doit fournir des exemples.).
- Raphaël a confirmé que WOP remonte des événements de conversion natifs, y compris après la page de paiement, et l’équipe vérifiera donc l’emplacement des pixels ainsi que la page utilisée par Uber pour enregistrer les conversions. (Raphaël doit fournir les détails WOP ; Boris doit vérifier les pixels.).
- Ils ont reconnu la possibilité d’un bug technique à l’origine des écarts de conversion et ont convenu d’examiner la chaîne de tracking si l’alignement des filtres ne suffit pas. (Boris doit déboguer ; escalade vers Uber si nécessaire.).

9. Intégration finale du VSL et prise en compte des futurs canaux • 0:22:01

- Raphaël a confirmé que le VSL final est en ligne et qu’il dispose déjà d’un événement dédié dans iClosed, donc le tracking est correctement branché.
- Boris a averti que le lancement de campagnes sur de nouvelles plateformes, comme LinkedIn, pourrait nécessiter des configurations supplémentaires et impacter la cohérence des dépenses et des données. (Boris doit vérifier les exigences avant d’ouvrir un nouveau canal.).

10. Livrables et prochaines étapes pratiques • 0:24:17

- Boris créera des comptes d’accès individuels pour Raphaël sur le tableau de bord afin qu’il puisse basculer entre les vues et vérifier lui-même les améliorations visuelles. (Boris doit créer les accès.).
- Raphaël a demandé à Boris d’envoyer des liens directs, et pas seulement des captures d’écran, pour les assets et les schémas mis à jour.
- Boris a demandé à Raphaël de partager les liens d’embed et les cheat-charts afin qu’ils puissent remplacer partout les anciens embeds ; ils doivent également mettre à jour les UTMs en conséquence. (Échange de liens à effectuer des deux côtés.).
%% notes:fin %%
