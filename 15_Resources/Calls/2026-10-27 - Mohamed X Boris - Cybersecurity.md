---
type: call
date: 2026-10-27
source: sembly
participants: ["boris@entrepreneurs.com", "mohamed@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Mohamed X Boris - Cybersecurity

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (27/10/2026 13:37).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 27/10/2026 13:37 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

Décisions et prochaines étapes validées pour résoudre les retards de formation et de support du prestataire Shade, sécuriser les accès et les sauvegardes, et lancer des audits de sécurité et de délivrabilité pour le Data Dashboard et la boîte mail marketing principale. Les responsabilités ont été réparties pour la gestion des accès, les audits et les délais de désactivation. Les priorités immédiates sont : obtenir des sauvegardes externes, finaliser la revue de sécurité du Data Dashboard, auditer la délivrabilité des e-mails, et supprimer ou déléguer les accès utilisateurs avant la fin du mois.

📋 Outline

1. Formation, paiement et réactivité du support Shade • 0:06:36

- Mohamed a signalé que Shade ne répond plus aux e-mails depuis environ une semaine et n’a toujours pas communiqué de date ferme de formation pour les équipes, ce qui bloque l’onboarding ; Mohamed doit relancer.
- Le contrat prévoit un support provisoire et un contact dédié, mais Shade affirme qu’aucune personne n’a été affectée, ce qui crée un risque contractuel ; Mohamed doit escalader avec un e-mail plus ferme.
- Quentin a soulevé un doute sur le coût de Shade, jugé élevé au token et au stockage, et a proposé d’évaluer des options de stockage alternatives partielles ; Quentin et Océane doivent revoir les options et faire un retour.
- Boris a rappelé que Shade apporte aussi des fonctionnalités IA supplémentaires (reconnaissance faciale, recherche) au-delà du simple stockage, et préfère éviter de fragmenter les outils si possible ; la décision finale dépendra des éléments de comparaison.

2. Bugs applicatifs et correctifs récents • 0:07:41

- Mohamed a confirmé que l’équipe marketing ne voit plus les bugs d’upload/download et que les fichiers manquants d’Océane ont été retrouvés sur Google Drive, ce qui indique que les correctifs récents fonctionnent ; Mohamed doit continuer à surveiller les retours.
- Mohamed a relevé des événements « headshot » récurrents dans les campagnes Riot : des utilisateurs déjà signalés sont re-signalés, et il a envoyé un e-mail confidentiel à l’équipe à ce sujet ; Mohamed et Alec doivent analyser la logique de campagne.

3. Revue du codebase et vérifications de vulnérabilités • 0:08:37

- Mohamed a mené une analyse des dépôts GitHub accessibles ainsi que de entrepreneurs.com pour identifier des vulnérabilités PHP / Next.js / JS et a relevé plusieurs points nécessitant une revue plus approfondie ; Mohamed doit poursuivre l’analyse et demander des accès supplémentaires si besoin.
- Le site entrepreneurs.com semble s’appuyer sur un framework qui doit être vérifié pour détecter d’éventuelles failles de sécurité ; Mohamed et Boris doivent coordonner l’accès pour l’audit.

4. Stratégie de sauvegarde et risque de point de défaillance unique • 0:08:58

- Il n’existe actuellement aucune sauvegarde externe en dehors des backups hébergés chez Vercel, ce qui crée un risque majeur de point de défaillance unique si Vercel ou ses sauvegardes sont compromis ; Mohamed doit rechercher des solutions de sauvegarde externes et Boris doit soutenir l’achat.
- La mitigation proposée consiste à créer des sauvegardes externes chez un autre fournisseur et dans une autre région (par exemple Hostinger ou un stockage basé en Allemagne / France) afin de garantir une capacité de restauration en cas de sinistre ; Mohamed doit créer le projet dans Work et ouvrir un Slack si nécessaire pour coordonner avec Quentin et Wassim.
- Quentin et Wassim ont confirmé qu’il n’existe pas de sauvegarde externe au-delà de Vercel, donc une action urgente est nécessaire pour éviter toute perte de données ; Quentin et Wassim doivent aider à la mise en place.

5. Accès aux boîtes mail, délégation et traçabilité • 0:10:45

- Abdel a demandé l’accès à la boîte mail d’Alec, mais n’a obtenu qu’une délégation de calendrier ; les mots de passe ont ensuite été modifiés rapidement par mesure de sécurité ; Mohamed doit gérer les délégations et les rotations de mots de passe.
- Boris ne veut que personne n’ait le mot de passe brut de la boîte mail principale entrepreneurs, et préfère un accès délégué afin que les actions restent traçables et auditables ; Mohamed doit mettre en place les délégations et retirer les accès fondés sur les mots de passe.
- L’équipe va configurer des délégations de boîte mail afin que chacun opère depuis son propre compte tout en visualisant la boîte d’Alec, ce qui améliore la responsabilité ; l’IT / les ops (Quassim / Wassim) doivent configurer les délégations.

6. Déploiement VPS et accès au Data Dashboard • 0:12:26

- Mohamed a obtenu un VPS pour déployer le dashboard de Jordan et créera dans la semaine l’accès de Boris (Elvi) afin de recueillir des retours et d’ajuster les paramètres ; Mohamed doit provisionner les comptes et partager les identifiants.
- Boris a insisté sur l’importance d’accéder au tableau de bord central des données, car il connecte de nombreux outils et doit être surveillé ; Boris doit s’assurer que l’accès au dashboard est bien accordé à Mohamed.

7. Centralisation des accès GitHub, Vercel, MFA et onboarding ops • 0:13:17

- Plusieurs accès GitHub et Vercel sont manquants ou incohérents, et certains comptes Vercel ne disposent pas de MFA, ce qui constitue un risque de sécurité ; Quassim doit fournir l’ensemble des listes d’accès et activer la MFA lorsque c’est possible.
- Boris vérifiera auprès de ses équipes afin de consolider les accès et ajouter Mohamed aux dépôts et projets nécessaires ; Boris et Aman (nouveau responsable projet) doivent coordonner les attributions d’accès.
- Aman a été présenté comme le nouveau project lead pour les Ops et gérera les tâches de projet en cours sans que Mohamed ait besoin de demander une validation pour les décisions opérationnelles ; Aman doit contacter Mohamed pour les éléments de travail.

8. Audit de délivrabilité e-mail et éventuel plan de secours de domaine • 0:16:10

- Boris a demandé un audit de la délivrabilité de la boîte mail entrepreneurs.com, de la réputation du domaine et de son état général, car les e-mails marketing partent de cette adresse et des problèmes pourraient impacter les campagnes ; Mohamed doit produire un rapport de délivrabilité et proposer des correctifs.
- Si la réputation du domaine entrepreneurs.com est dégradée, l’équipe pourrait envisager de provisionner un domaine marketing séparé pour garantir la continuité des envois ; Boris doit approuver l’achat du domaine si cela est recommandé.
- Mohamed contactera EMX (prestataire / partenaire e-mail) si la remédiation nécessite une intervention tierce ; Mohamed doit escalader vers EMX si nécessaire.

9. Audit de sécurité du Data Dashboard et du Data Dashboard Redesign • 0:17:24

- Boris a demandé une analyse de sécurité des projets Data Dashboard et Data Dashboard Redesign afin d’identifier et de corriger les vulnérabilités ; Mohamed doit réaliser l’audit avec l’accès GitHub.
- Mohamed a indiqué avoir détecté des problèmes Next.js / JS et a demandé l’accès au code hub pour les analyser et les remédier ; Boris doit s’assurer que Mohamed est invité dans les dépôts GitHub.
- Boris a déjà invité Mohamed sur GitHub et lui a demandé de se concentrer sur ces dashboards avant de fermer ou d’archiver les autres projets proches de l’obsolescence ; Boris et Mohamed doivent prioriser ce travail.

10. Offboarding utilisateurs, gestion des licences et calendrier • 0:24:28

- Neuf licences ont été provisionnées à la suite d’un récent challenge et ne seront pas supprimées immédiatement ; Mohamed doit programmer des rappels et Sabrina doit prendre en charge les demandes de désactivation de suivi dans environ deux semaines.
- Les accès d’Abdel seront supprimés le soir du 30 comme prévu, et Mohamed a demandé la liste de tous les outils utilisés par Abdel afin de s’assurer qu’aucun accès orphelin ne subsiste ; Mohamed doit collecter la liste et Boris peut aider si besoin.
- Le remplacement du rôle d’Abdel n’est pas encore décidé et ses responsabilités pourraient être réparties entre plusieurs personnes, d’où la nécessité de documenter précisément les outils utilisés ; Mohamed doit rassembler et partager l’inventaire.
%% notes:fin %%
