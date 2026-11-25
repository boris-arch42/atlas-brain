---
type: call
date: 2026-11-17
source: sembly
participants: ["[[Boris Arduy]]", "[[Mohamed]]"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-11-20
---

# Mohamed X Boris - Cybersecurity

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (17/11/2026 13:52).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 20/11/2026 10:48 — corrige librement hors des marqueurs.

**Résumé** — Point cybersécurité complet couvrant l'audit des plateformes, l'inventaire de 66 SaaS (250k€), les résultats de la campagne de phishing d'octobre (10 personnes ont saisi leur mot de passe, niveau record) et la planification d'une sensibilisation collective.

**Décisions**
- Organiser une masterclass de sensibilisation au phishing pour tous les coachs (non ciblée pour ne stigmatiser personne)
- Limiter les droits de superadministrateur, notamment pour les développeurs
- Vérifier et attribuer les propriétaires des 66 SaaS identifiés
- Paramétrer les futures réunions pour que seul l'organisateur autorise les participants

**Actions**
- [ ] **Mohamed** : Réauditer le dépôt GitHub plateforme V2 (échéance 2026-11-17)
- [ ] **Mohamed** : Transmettre le fichier Excel des SaaS complet à Wassim pour vérification des propriétaires
- [ ] **Mohamed** : Envoyer le rapport PDF de la campagne phishing d'octobre à Alec sur Slack
- [ ] **Mohamed** : Envoyer à Boris 2-3 créneaux pour la masterclass phishing semaine suivante (échéance 2026-11-24)
- [ ] **Mohamed** : Préparer le contenu de la masterclass phishing (30 min) (échéance 2026-11-24)
- [ ] **Boris** : Vérifier et attribuer les propriétaires des 66 SaaS identifiés
- [ ] **Boris** : Coordonner avec Claire l'organisation de la masterclass phishing pour tous les coachs
- [ ] **Boris** : Relancer Jordan sur la plateforme financière lors du prochain échange
- [ ] **Wassim** : Réaliser l'audit de sécurité de Work

**Risques & vigilances**
- Paramètres de réunions permettant à des participants non autorisés de rejoindre
- Failles de sécurité V1 non corrigées lors du passage V2
- 10 personnes ont saisi leur mot de passe lors du test phishing (niveau record)
- Plusieurs outils SaaS sans propriétaires clairement identifiés (250k€ de dépenses jan-oct)
- Accès superadministrateur trop largement distribués
- Mots de passe LinkedIn à risque pour certains collaborateurs

**Projets liés** : [[Sprint Cybersec & phishing]] · [[Audit SaaS-IT — économies]]

Tags : #cybersécurité #phishing #audit-saas #sensibilisation #gestion-accès
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 17/11/2026 13:52 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

Les échanges ont porté sur le renforcement de la sécurité des réunions et des plateformes, la revue des dépenses SaaS et des accès, ainsi que sur les outils financiers et les incidents de phishing. Mohamed va réauditer le dépôt GitHub, poursuivre les vérifications et préparer un rapport et une masterclass de sensibilisation, tandis que Boris examinera les propriétaires des outils et coordonnera la session destinée à tous les coachs.

📋 Outline

1. Sécurisation de l’accès aux réunions • 0:00:14

- Mohamed a testé l’accès à une réunion en navigation privée, sans adresse professionnelle, et a pu rejoindre le processus d’admission sous un nom emprunté après qu’un participant l’a autorisé.
- L’invitation avait aussi été modifiée par une personne de la liste, notamment au niveau de l’horaire, ce qui soulève un risque de confusion ou d’intrusion.
- Il faut vérifier les paramètres des prochaines réunions afin que seul l’organisateur puisse autoriser les participants.

2. Audit de sécurité des plateformes • 0:02:44

- Des modifications ont été déployées sur la plateforme après un transfert de la V1 vers la V2, mais certaines failles n’auraient pas été corrigées lors du changement de version.
- Mohamed a indiqué qu’il réauditerait le dépôt GitHub le jour même.
- L’audit de Work n’avait pas encore été réalisé ; Mohamed a demandé à Wassim de traiter le sujet.

3. Inventaire des abonnements et attribution des propriétaires • 0:03:43

- Mohamed a transmis sur Slack un fichier Excel construit à partir des paiements SaaS des deux derniers mois, en excluant les services qui ne sont plus utilisés.
- La liste recense 66 SaaS et des dépenses de 250 489 euros entre janvier et octobre, selon les paiements visibles dans l’export de Jordan.
- Boris a demandé d’intégrer toute la liste, puis prévoit de vérifier et d’attribuer les propriétaires des outils un par un.
- Mohamed doit transmettre le fichier à Wassim pour vérifier si les propriétaires peuvent être modifiés directement dans la plateforme.
- Boris a signalé que plusieurs dépenses importantes ont déjà été supprimées ou sont à vérifier, notamment Clap, Calendly et Dialogue ; Dialogue reste associé à l’envoi de WhatsApp.

4. Création de comptes et gestion des droits d’accès • 0:07:52

- Mohamed prévoit de placer des éléments dans un Drive dédié, avec des accès limités, afin de pouvoir créer les 15 comptes prévus.
- Boris a suggéré d’utiliser une adresse dédiée sur le domaine de l’entreprise, et Mohamed a indiqué que les accès au Drive seraient réservés à un petit nombre de personnes.
- La réouverture d’un abonnement Google reste en négociation ; Google aurait suggéré de souscrire puis de renégocier l’année suivante.
- Les droits HubSpot ont été réduits pour certaines personnes, dont Léa ; Boris a indiqué que les demandes d’accès devaient être vues avec Rachid.
- Les participants ont souligné qu’il fallait limiter les droits de superadministrateur, notamment pour les développeurs, et privilégier des accès adaptés aux besoins techniques.

5. Sécurité du dashboard et périmètre du module finance • 0:10:54

- Mohamed a indiqué que le dashboard était désormais propre sur le plan de la sécurité et qu’il suivait les développements de Quentin et de Work avec des audits réalisés avec Foucault.
- Boris a précisé que les travaux évoqués concernaient le module finance destiné aux clients, et non l’outil financier interne, auquel l’équipe concernée ne doit pas avoir accès.
- Mohamed attend un retour de Jordan sur la plateforme financière qu’il a développée ; Boris a prévu de le relancer lors de leur prochain échange.

6. Connexion bancaire et incidents sur les outils • 0:12:41

- Mohamed échange avec des banques ne disposant pas d’API et pense qu’une connexion API avec WIO Bank devrait être possible.
- L’absence d’API bancaire a constitué un frein récurrent aux opérations.
- Mohamed attend des nouvelles concernant la formation de Shane et doit relancer les interlocuteurs.
- Un ticket a été ouvert après un problème de téléchargement de fichiers dont les noms contiennent des accents.
- Mohamed n’a pas reçu de retour de Quentin sur l’audit de Shade et les améliorations possibles du stockage ; le travail reste pour l’instant concentré sur la plateforme.

7. Résultats de la campagne de phishing d’octobre • 0:14:26

- Mohamed prépare un rapport de la campagne d’octobre et a indiqué que 10 personnes avaient saisi leur mot de passe, le niveau le plus élevé observé jusqu’alors.
- Plusieurs participants ont cliqué sur des liens ou saisi leurs identifiants ; Mohamed a une liste des personnes concernées et doit transmettre le rapport PDF à Alec sur Slack.
- Dans le cas d’Amina Chour, le message frauduleux imitait une notification de contenu signalé liée au DMCA ; la personne a ouvert le courriel, cliqué deux fois sur le lien et saisi son mot de passe.
- Boris a estimé qu’Amina avait probablement cliqué pour examiner la méthode, compte tenu de son expérience en cybersécurité.
- Mohamed a relevé que le mot de passe LinkedIn associé était considéré comme très risqué et a proposé de recommander son changement.

8. Sensibilisation des coachs au phishing • 0:16:51

- Mohamed a proposé une masterclass d’environ 30 minutes sur les conséquences du phishing et les risques liés à la saisie de mots de passe.
- Boris a proposé d’organiser la session pour l’ensemble des coachs plutôt que de cibler uniquement les personnes ayant échoué au test, afin de ne stigmatiser personne.
- Boris doit coordonner la mise en place avec Claire ; Mohamed lui enverra sur Slack deux ou trois créneaux pour la semaine suivante et préparera le contenu.
%% notes:fin %%
