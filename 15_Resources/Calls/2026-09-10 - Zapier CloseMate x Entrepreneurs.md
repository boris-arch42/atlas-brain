---
type: call
date: 2026-09-10
source: sembly
participants: ["pierrenauts@gmail.com", "boris@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Zapier CloseMate x Entrepreneurs

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (10/09/2026 11:51).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 10/09/2026 11:51 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

Mise en place d’une intégration Zapier entre la page d’atterrissage YouTube et CloseMate afin de créer ou mettre à jour les contacts avec le bon mappage de champs et les tags appropriés. Boris configurera les webhooks et connectera CloseMate dans Zapier, puis réalisera des tests, tandis que Pierre recevra l’accès à l’application pour vérifier les mappages et finaliser les ajustements. Aucun autre canal (Instagram, etc.) ne nécessite d’intégration à ce stade.

📋 Outline

1. Partager le lien Zapier/CloseMate et lancer l’intégration • 0:01:29

- Pierre enverra le lien Zapier permettant d’activer l’intégration avec CloseMate afin que l’équipe puisse démarrer le processus de connexion.
- Boris a confirmé la réception et sa disponibilité pour avancer sur la configuration de l’intégration.
- Responsabilités : Pierre envoie le lien ; Boris confirme et poursuit la mise en place.

2. Définir le déclencheur et le parcours de la page d’atterrissage pour les leads YouTube • 0:02:17

- Les leads provenant de YouTube s’inscriront via la page d’atterrissage « Secrets d'entreprise » et devront être routés vers CloseMate via Zapier.
- La page d’atterrissage servira de déclencheur dans Zapier et devra être reliée à CloseMate comme action.
- Responsabilités : Boris met en place le webhook de la page d’atterrissage ; Pierre valide le flux.

3. Configurer l’action Zapier pour créer ou mettre à jour les contacts dans CloseMate • 0:04:25

- Dans Zapier, l’action doit être configurée sur « create/update contact » afin d’envoyer les données des leads entrants vers CloseMate.
- Une clé API issue de l’intégration CloseMate est nécessaire dans Zapier pour authentifier la connexion ; sa génération peut prendre du temps et il faudra réessayer si elle se bloque.
- Responsabilités : Boris configure l’action ; Pierre génère et partage la clé API.

4. Fournir les identifiants d’accès et les identifiants d’espace de travail • 0:06:09

- Pierre a partagé l’identifiant de l’espace de travail / utilisateur (user ID 252) et a proposé l’adresse e-mail d’invitation afin que Boris puisse finaliser la connexion à CloseMate.
- Boris a confirmé qu’il pouvait exister une variabilité dans l’identifiant utilisé par l’outil (e-mail ou autre clé) et qu’il pouvait poursuivre dès que les bonnes informations seraient fournies.
- Responsabilités : Pierre envoie l’invitation ; Boris utilise les identifiants fournis pour finaliser la connexion.

5. Mapper les champs contacts et les tags requis pour les leads entrants • 0:07:30

- L’intégration doit capturer le numéro de téléphone, le nom et appliquer le tag « youtube » pour identifier la source du lead.
- Si des champs personnalisés apparaissent dans les messages entrants, Boris les identifiera et Pierre indiquera s’ils doivent être transmis à CloseMate.
- Responsabilités : Boris mappe les champs dans Zapier ; Pierre confirme les champs obligatoires et les éventuels champs personnalisés à transférer.

6. Tests, vérification et prochaines étapes • 0:08:08

- Boris vérifiera les webhooks, connectera en priorité le webhook YouTube et lancera les tests pour confirmer que les données remontent correctement dans CloseMate.
- Pierre demande à recevoir l’accès aux applications CloseMate concernées afin de vérifier les mappages, récupérer les réponses au questionnaire si nécessaire et finaliser les ajustements après les tests.
- Une fois les tests validés, le même schéma pourra être réutilisé pour d’autres formulaires du site avec les tags appropriés ; aucune intégration n’est requise pour Instagram à ce stade.
%% notes:fin %%
