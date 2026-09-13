---
type: call
date: 2026-09-08
source: sembly
participants: ["boris@entrepreneurs.com", "mohamed@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Mohamed X Boris - Cybersecurity

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (08/09/2026 12:02).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 08/09/2026 12:02 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a examiné l’avancement du nettoyage des stockages cloud et des comptes inactifs, et a convenu de renforcer l’application des limites de stockage temporaires ainsi que la désactivation des utilisateurs inutilisés afin d’éviter l’enlisement d’ici fin septembre. En parallèle, un chantier de visibilité a été lancé sur les coûts SaaS par utilisateur, la cartographie des outils et de l’organigramme, ainsi que l’intégration des paiements bancaires dans la plateforme Jordan pour mieux piloter les dépenses. Sur le volet sécurité, l’équipe a confirmé la poursuite des simulations de phishing, la réduction des risques DLP et des partages excessifs, l’audit des permissions d’applications tierces, et un audit dev/sécurité ciblé avec accès GitHub si nécessaire. Des responsables ont été assignés pour l’application des restrictions, la cartographie SaaS/org chart, l’intégration des paiements et l’audit sécurité.

📋 Outline

1. Nettoyage de l’usage du stockage et plan d’application des restrictions • 0:00:39

- Mohamed a indiqué que de nombreux éditeurs ne répondent pas et qu’il appliquera le 15 septembre une règle de stockage : les utilisateurs au-dessus de 500 Go seront ramenés à 5 Go afin de forcer le nettoyage, avec l’objectif d’éviter la stagnation d’ici fin septembre. (Responsable : Mohamed).
- Mohamed a partagé un export Excel montrant quels comptes ont déjà réduit leur stockage et lesquels restent volumineux, ce qui confirme une progression partielle du nettoyage. (Responsable : Mohamed).
- Mohamed a cité des utilisateurs ayant déjà réduit leur consommation de stockage, par exemple Théo et Nicolas, et d’autres qui restent autour de volumes élevés, comme Mehdi et Guillaume à environ 510 Go, lesquels se sont engagés à déplacer leurs données vers Shade. (Responsable : Mohamed).
- Mohamed appliquera la limitation aux non-responsables d’équipe, tout en conservant des exemptions pour les responsables (Alec, Océane, Anis) afin de préserver un accès prioritaire. (Responsable : Mohamed).

2. Comptes inactifs et suppression des closers Alchimie • 0:03:47

- Boris et Mohamed ont discuté de la suppression des closers ajoutés sur le projet Alchimie qui possèdent encore des comptes actifs mais ne sont plus pertinents ; ils ont convenu qu’ils peuvent être retirés directement. (Responsable : Boris / Mohamed).
- Une liste de noms a été évoquée comme candidats à la suppression de compte et éventuellement à la suppression du Drive : Asma, Asad, Ada, Sou, Emma, Pedro, etc. (Responsable : Mohamed).
- Mohamed continuera à relancer certains utilisateurs inactifs ciblés — Imane, Sylvain, Cédric et Fiona — avant d’archiver ou de supprimer définitivement leurs comptes. (Responsable : Mohamed).

3. Procédure de blocage temporaire et communication utilisateur • 0:06:18

- Mohamed mettra en place une bannière de blocage visible pour les utilisateurs ciblés au seuil de 5 Go afin qu’ils contactent l’IT pour récupérer l’accès ou réduire leurs fichiers ; il accordera une fenêtre de déblocage de 24 heures si la moitié des fichiers est supprimée. (Responsable : Mohamed).
- Mohamed a indiqué avoir déjà échangé avec Google et attendre une offre formelle ainsi que les prochaines étapes aujourd’hui ou demain pour gérer les reversions de licences et les complications associées. (Responsable : Mohamed).
- Boris a autorisé Mohamed à utiliser son nom ou à escalader publiquement si nécessaire pour obtenir la conformité, et a confirmé que Mohamed dispose d’une légitimité totale pour appliquer ces mesures. (Responsable : Boris / Mohamed).

4. Intégration de la plateforme de paiements pour Jordan • 0:08:28

- Mohamed avance avec les intégrateurs pour connecter un agrégateur (outil basé aux Émirats arabes unis) afin de remonter l’ensemble des paiements et transactions bancaires dans la plateforme Jordan pour une visibilité consolidée. (Responsable : Mohamed / Jordan / Intégrateurs).
- L’intégration prévue permettra de visualiser les paiements sortants et entrants, de filtrer par SaaS, par paiements clients ou par fournisseur spécifique, et pourra donner un accès à Boris et Fabrice pour le pilotage financier. (Responsable : Mohamed / Jordan / Fabrice / Boris).
- Mohamed estime que cette intégration fera gagner un temps significatif et améliorera le suivi financier des opérations de Jordan. (Responsable : Mohamed / Jordan).

5. Plateforme MSP/cybersécurité et coût des licences SaaS par utilisateur • 0:09:49

- Mohamed construit une vue plateforme pour la partie MSP/cybersécurité incluant Zendesk, Slack, HubSpot et d’autres SaaS, afin d’identifier quels comptes disposent de licences et lesquels n’en ont pas. (Responsable : Mohamed).
- L’objectif à terme est de calculer le coût par utilisateur et par mois sur les 5 à 10 SaaS les plus coûteux, pour connaître le coût réel mensuel et annuel de la boîte à outils de chaque collaborateur. (Responsable : Mohamed / Finance).
- Boris a convenu que la visibilité du coût par utilisateur est essentielle pour maîtriser les dépenses et identifier les utilisateurs disposant de licences excessives ou inutilisées. (Responsable : Boris).

6. Cartographie SaaS et organigramme avec responsabilités • 0:12:20

- Mohamed a expliqué que l’organisation ne dispose pas d’une cartographie SaaS ni d’un organigramme à jour avec photos permettant d’identifier clairement qui est responsable de chaque outil et qui contacter pour le suivi. (Responsable : Mohamed).
- Boris s’est engagé à coordonner avec Anis pour héberger l’organigramme sur Work (ou un outil similaire) et produire des cartes visuelles reliant les personnes à leurs responsabilités. (Responsable : Boris / Anis).
- Mohamed construira la cartographie SaaS au sein de la plateforme pour suivre quels SaaS sont payés, qui détient des licences et où les coûts se concentrent. (Responsable : Mohamed).

7. Audit dev/sécurité et accès GitHub • 0:14:13

- Mohamed a proposé de mener un audit combinant des contrôles automatisés par IA et des techniques manuelles ciblées afin de révéler les problèmes cachés, et a proposé de le réaliser si un accès GitHub lui est donné. (Responsable : Mohamed / Quentin / Anis).
- Mohamed a recommandé de rester prudent vis-à-vis des contraintes légales concernant les techniques de sécurité trop agressives et de privilégier, lorsque pertinent, des diagnostics Linux ou en ligne de commande autorisés. (Responsable : Mohamed).
- Boris et Mohamed ont convenu de se concentrer immédiatement sur les trois ou quatre sujets prioritaires discutés et de planifier le travail d’audit avec l’équipe dev/sécurité comme prochaine étape. (Responsable : Boris / Mohamed / Quentin).

8. Propriété intellectuelle et charte numérique • 0:16:28

- Une charte numérique / IT doit être signée par l’ensemble des collaborateurs afin d’indiquer que les travaux produits par les employés appartiennent à l’entreprise, comme l’a proposé Mohamed Guendouzi. (Responsable : Boris / Juridique / RH).
- Boris a confirmé que la cession de propriété intellectuelle est déjà incluse dans les contrats existants, mais a demandé une vérification pour s’assurer que la charte couvre bien tous les actifs numériques. (Responsable : Boris / Juridique).

9. Centralisation de la documentation Riot dans le wiki Works • 0:16:41

- Mohamed a accès à Works et créera une nouvelle page Riot dans le Wiki pour centraliser la documentation et les assets. (Responsable : Mohamed).
- Boris a expliqué que Works fonctionne comme Notion et prend en charge les images, vidéos et le texte enrichi, et a demandé à Mohamed de le prévenir une fois la page créée pour décider de l’emplacement du dossier. (Responsable : Boris / Mohamed).
- Mohamed s’est engagé à ajouter la documentation Riot sur la page d’accueil dès aujourd’hui afin que l’équipe y ait accès immédiatement. (Responsable : Mohamed).

10. Résultats de la campagne de phishing et adoption de la formation • 0:18:01

- Une campagne de phishing est active depuis le 10 août et de nombreux utilisateurs ont cliqué sur les liens ou saisi leurs mots de passe, ce qui montre des lacunes de sensibilisation. (Responsable : Mohamed pour le reporting).
- Deux utilisateurs ont signalé la tentative de phishing sur une campagne, et 11 utilisateurs ont terminé le module de formation ; Mohamed a identifié Mariam et Neyma comme des signalantes régulières. (Responsable : Mohamed).
- Certains collaborateurs ont félicité les attaques simulées a posteriori, ce qui indique une compréhension et un engagement mitigés vis-à-vis des exercices. (Responsable : Mohamed).
- Boris a proposé d’augmenter la promotion des modules de formation et d’encourager les managers à pousser leurs équipes à terminer les cours afin d’améliorer les taux de complétion. (Responsable : Boris / Managers).

11. Prévention de la perte de données (DLP) et risques de partage excessif • 0:22:36

- Le module sonar/DLP a signalé de nombreux fichiers partagés avec des comptes personnels, y compris des partages historiques remontant à 2020, ce qui montre une exposition ancienne et durable. (Responsable : Mohamed).
- Certains utilisateurs ont été identifiés avec un nombre extrêmement élevé de fichiers partagés — par exemple une adresse avec environ 48 409 fichiers et une autre avec environ 33 000 fichiers — créant un risque élevé de compromission si ces comptes personnels sont piratés. (Responsable : Mohamed pour l’export et l’analyse ; Boris pour la revue des partages).
- Des éléments montrent que certains partages datent des premières périodes, avant que les utilisateurs externes n’aient des adresses d’entreprise, et ces partages hérités doivent être nettoyés. (Responsable : Mohamed pour l’audit ; Boris pour valider les suppressions).
- Mohamed exportera les données de partage, réalisera une analyse complète puis un tri ciblé afin de supprimer ou réaffecter les partages à risque. (Responsable : Mohamed).
- Boris a identifié au moins un dossier de branding qu’il avait partagé et a accepté de supprimer immédiatement les accès externes inappropriés. (Responsable : Boris).

12. Permissions des applications tierces et options de blocage • 0:29:49

- L’outil de sécurité affiche de nombreuses applications tierces connectées avec des permissions larges, comme la consultation, la modification ou la création dans Google Drive, ce qui constitue un niveau d’accès dangereux. (Responsable : Mohamed).
- Mohamed a démontré qu’il peut bloquer ou approuver directement des applications depuis l’outil afin d’arrêter les intégrations à risque. (Responsable : Mohamed).
- L’équipe a noté la présence de plusieurs comptes et applications peu utilisés (Glovo, Peerply, etc.) qui doivent être revus et supprimés si elles ne sont pas nécessaires. (Responsable : Mohamed / IT).

13. Efficacité de l’outil, coût et nettoyage des licences/comptes • 0:31:11

- Mohamed a indiqué que l’outil de sécurité est efficace et peu coûteux au regard de la valeur qu’il apporte. (Responsable : Mohamed).
- La facturation actuelle montre 228 licences pour un coût d’environ 3 830 $, alors que l’effectif actif est perçu comme bien inférieur, ce qui indique des comptes en double ou inutilisés et donc des économies potentielles. (Responsable : Mohamed / Boris pour rapprochement).
- L’équipe a convenu d’arrêter la pratique consistant à multiplier les comptes par utilisateur et de nettoyer les comptes redondants afin de réduire les coûts d’abonnement et le risque de sécurité. (Responsable : Boris / IT).

14. Prochaines étapes, communication et responsabilités • 0:33:28

- Mohamed tiendra Boris informé de l’avancement du nettoyage des partages de fichiers et l’alertera si certains utilisateurs se plaignent lorsque l’accès sera restreint. (Responsable : Mohamed).
- Mohamed a réitéré un objectif de calendrier pour faire avancer les travaux d’ici le 20 septembre et finaliser les rapprochements de facturation d’ici la fin septembre. (Responsable : Mohamed / Finance).
- Boris a demandé à être informé si Mohamed a besoin d’aide et a confirmé les actions de suivi sur les partages et les comptes/licences. (Responsable : Boris).
%% notes:fin %%
