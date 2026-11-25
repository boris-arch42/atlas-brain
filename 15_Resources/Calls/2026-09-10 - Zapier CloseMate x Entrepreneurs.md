---
type: call
date: 2026-09-10
source: sembly
participants: ["pierrenauts@gmail.com", "[[Boris Arduy]]"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-11-20
---

# Zapier CloseMate x Entrepreneurs

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (10/09/2026 11:51).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 20/11/2026 10:48 — corrige librement hors des marqueurs.

**Résumé** — Mise en place d'une intégration Zapier entre la landing page YouTube et CloseMate pour automatiser la création et mise à jour des contacts avec tags appropriés. Configuration des webhooks, mapping des champs (téléphone, nom, tag 'youtube') et tests à réaliser avant déploiement.

**Décisions**
- Utiliser Zapier pour connecter la landing page 'Secrets d'entreprise' à CloseMate
- Mapper systématiquement les champs téléphone, nom et tag 'youtube' pour les leads YouTube
- Pas d'intégration prévue pour Instagram à ce stade

**Actions**
- [ ] **Pierre** : Envoyer le lien Zapier/CloseMate pour activer l'intégration
- [ ] **Pierre** : Générer et partager la clé API CloseMate pour l'authentification Zapier
- [ ] **Pierre** : Envoyer l'invitation d'accès CloseMate à Boris (user ID 252)
- [ ] **Pierre** : Confirmer les champs personnalisés obligatoires à transférer vers CloseMate
- [ ] **Boris** : Configurer le webhook de la landing page YouTube comme déclencheur Zapier
- [ ] **Boris** : Configurer l'action 'create/update contact' dans Zapier avec connexion CloseMate
- [ ] **Boris** : Mapper les champs contacts (téléphone, nom) et appliquer le tag 'youtube'
- [ ] **Boris** : Réaliser les tests de remontée des données dans CloseMate
- [ ] **Boris** : Donner accès à Pierre aux applications CloseMate pour vérification des mappages

**Risques & vigilances**
- La génération de la clé API CloseMate peut prendre du temps ou se bloquer
- Variabilité possible dans l'identifiant utilisé par l'outil (email vs autre clé)
- Des champs personnalisés peuvent apparaître et nécessiter une décision d'intégration

Tags : #zapier #closemate #automatisation #integration #landing-page-youtube
%% synthese:fin %%

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
