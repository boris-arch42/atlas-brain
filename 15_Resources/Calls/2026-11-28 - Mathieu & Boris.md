---
type: call
date: 2026-11-28
source: sembly
participants: ["[[Boris Arduy]]", "Mathieu"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-11-28
---

# Mathieu & Boris

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (28/11/2026 12:47).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 28/11/2026 12:52 — corrige librement hors des marqueurs.

**Résumé** — Discussion sur l'intégration technique entre la plateforme de Mathieu et les outils internes (Ngram, HubSpot). Boris valide la faisabilité et convient d'automatiser la remontée des appels gagnés depuis HubSpot vers la plateforme de Mathieu, avec transmission des transcriptions Ngram.

**Décisions**
- HubSpot reste la source de référence pour les données commerciales et processus contrats
- Flux de données unidirectionnel HubSpot → plateforme Mathieu pour limiter complexité et erreurs
- Transmission des transcriptions Ngram vers plateforme Mathieu pour analyses automatisées
- Automatisation de la remontée des appels gagnés depuis HubSpot

**Actions**
- [ ] **Mathieu** : Envoyer les spécifications de données, format et destination pour l'intégration API (échéance 2026-11-29)
- [ ] **Boris** : Mobiliser les équipes pour mettre en place l'automatisation de remontée des appels gagnés après réception des specs (échéance 2026-11-30)
- [ ] **Boris** : Examiner la possibilité d'accès API iClosed pour récupérer les introductions d'appels si nécessaire

**Risques & vigilances**
- Perte de données et manque de traçabilité dans les intégrations
- Enjeux de sécurité dans la circulation des données
- Complexité potentielle d'une synchronisation bidirectionnelle
- Erreurs de traduction entre systèmes si mauvaise correspondance des champs

Tags : #integration-api #hubspot #ngram #automatisation #plateforme-sales
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 28/11/2026 12:47 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

Les participants ont retenu une intégration où les transcriptions de Ngram et les outcomes des appels pourront alimenter la plateforme de Mathieu, tandis que HubSpot reste la référence pour les données commerciales et les processus liés aux contrats. Boris mettra en place l’automatisation de remontée des appels gagnés après réception des spécifications de données et de destination fournies par Mathieu.

📋 Outline

1. Données nécessaires et contraintes de l’intégration • 0:00:00

- Mathieu souhaite automatiser la circulation des données issues des notes de réunion et du CRM vers sa plateforme et HubSpot.
- Les principaux risques identifiés sont la perte de données, le manque de traçabilité et les enjeux de sécurité.
- Boris indique que l’intégration est techniquement envisageable et que sa faisabilité dépendra des données requises, de leur structure et de leur mode de transmission.

2. Transcriptions Ngram et analyse des appels • 0:01:12

- Le système de Mathieu utilise Google Agenda pour associer les appels au CRM, mais cette intégration ne couvre pas l’analyse des appels.
- Mathieu a besoin des transcriptions des appels pour lancer automatiquement ses propres analyses.
- Boris confirme que Ngram, le note-taker interne, peut transmettre les enregistrements et les transcriptions, sous réserve de recevoir le format de données et les modalités d’envoi attendus.
- Mathieu précise que son analyse repose sur une importante base de données et ne peut pas être reproduite simplement à partir de la structure de notation de sa plateforme.
- La réception des transcriptions par Mathieu suffit à lui permettre d’automatiser ses analyses de son côté.

3. HubSpot comme source des données commerciales • 0:03:40

- Boris souligne qu’une synchronisation vers HubSpot dépend de la structure du pipeline et de la correspondance entre les champs des deux systèmes.
- HubSpot déclenche plusieurs opérations internes, notamment l’envoi des contrats, l’ouverture des accès clients et la facturation, ce qui nécessite que les closers y renseignent les informations requises.
- Les participants privilégient une circulation des données depuis HubSpot vers la plateforme de Mathieu pour limiter les frictions, les erreurs de traduction et la complexité d’une synchronisation bidirectionnelle.
- Mathieu présente sa plateforme, qui centralise notamment les résultats et analyses d’appels, les objections, les indicateurs de performance et les ressources de formation des closers.

4. Automatisation des appels et remontée des résultats • 0:11:31

- Les fiches contact, lead et deal sont déjà créées automatiquement dans HubSpot à partir des données saisies dans iClosed et des appels réservés.
- Les closers doivent encore renseigner manuellement l’outcome de l’appel, notamment s’il est gagné, ainsi que les informations nécessaires au processus de contrat.
- Mathieu demande une connexion API permettant de récupérer dans sa plateforme l’information indiquant si un appel a été gagné.
- Boris confirme qu’il peut faire mettre en place une automatisation pour transmettre les appels gagnés.
- Mathieu doit envoyer à Boris les spécifications sur les données à transmettre, leur format et leur destination; Boris prévoit de mobiliser ses équipes entre aujourd’hui et demain après réception de ces éléments.
- L’accès éventuel à l’API iClosed pour récupérer les introductions des appels est évoqué comme une possibilité à examiner si des données supplémentaires sont nécessaires.
%% notes:fin %%
