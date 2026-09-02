---
type: call
date: 2026-09-02
source: sembly
participants: ["jordan@entrepreneurs.com", "boris@entrepreneurs.com"]
sensitivity: confidential
tags: [call, sembly]
---

# Jordan X Boris - Ops Meeting

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (02/09/2026 14:24).

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 02/09/2026 14:24 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

L’équipe a passé en revue l’onboarding et la montée en compétence de nouveaux agents de recouvrement, avec un accent sur le monitoring des appels, le coaching en direct et la clarification des scripts et des responsabilités. Elle a également discuté d’un projet de tableau de bord bancaire automatisé pour agréger les flux de trésorerie mensuels et mieux attribuer les encaissements entre nouvelles ventes, contrats antérieurs et recouvrements. En parallèle, Jordan et Boris ont abordé la conception d’un dashboard orienté ID (WebSpot/DealUpSpot) pour donner de la visibilité quasi temps réel aux ventes sur les commissions, ainsi que les dépendances techniques, les coûts liés à l’IA et le besoin de formaliser un cahier des charges. Décisions et actions clés : donner à Jordan les accès superviseur Aircall, renforcer le reporting recouvrement ce mois-ci, rechercher une solution de connexion bancaire avec Mohamed, et explorer l’appui d’un expert/mentor recouvrement pour accélérer la montée en compétence de l’équipe.

📋 Outline

1. Onboarding des deux agents de recouvrement • 0:00:00

- Deux nouveaux agents basés au Togo ont été onboardés cette semaine et resteront jusqu’à vendredi ; Jordan a piloté la configuration initiale et les accès.
- Le coût des agents est d’environ 5 $/heure ou moins selon la région, ce qui en fait une ressource peu coûteuse pour les appels sortants.
- Les premières sessions ont révélé des problèmes d’organisation : scripts à renforcer, tâches plus clairement assignées et coaching en direct pendant les appels.
- Jordan a animé une session de coaching en direct de 3,5 heures et prévoit qu’Angèle prenne le relais l’après-midi pour transférer progressivement la responsabilité.

2. Coûts horaires et budget de staffing • 0:00:51

- Le coût horaire effectif de certains profils offshore a été estimé entre 2,50 € et 4,20 € selon le prestataire et le pays.
- L’équipe envisage de recruter un support comptable à temps partiel (une demi-journée par mois) dans un marché à bas coût, probablement en Inde, pour environ 700 à 800 € par mois.
- Les modèles de rémunération diffèrent selon les rôles : Jade est payé sur un pourcentage des montants recouvrés, tandis qu’Angèle a un salaire fixe, ce qui influence les comportements et les incentives.

3. Formation, process d’appel et premières métriques d’activité • 0:01:09

- Jordan utilise un fichier Excel pour attribuer les lignes clients et suivre en temps réel les résultats d’appel pendant les sessions de coaching.
- Les agents ont réalisé 45 appels sortants en une journée ; Jordan juge ce rythme correct pour démarrer, mais attend une amélioration avec la poursuite du coaching.
- Les retours d’appel les plus fréquents étaient des incompréhensions (clients pensant à un prélèvement automatique) ou des affirmations de non-réception des factures, ce qui indique un risque d’escalade faible pour les comptes actuels.
- Jordan poursuivra les analyses approfondies pendant les deux prochains mois, à mesure que les outils se connectent, afin de mieux coacher l’équipe et quantifier les recouvrements.

4. Accès Aircall et monitoring des appels • 0:03:19

- Jordan a demandé l’accès à Aircall afin d’écouter et d’analyser les enregistrements et transcriptions d’appels à des fins de coaching.
- Boris a confirmé et a fait passer Jordan en mode superviseur sur tous les comptes dans Aircall, puis a résolu un problème d’invitation expirée pour lui permettre d’accéder aux appels.
- L’absence d’accès empêchait Jordan de revoir les appels et limitait jusqu’ici l’efficacité du coaching à distance.

5. Performance individuelle, tactiques et incentives • 0:07:31

- Jade, basé à Aix-en-Provence, se concentre sur les dettes anciennes (60 à 90 jours et plus) et utilise des tactiques créatives, par exemple réouvrir temporairement des comptes pour obtenir un paiement imminent ; il est rémunéré à la commission sur les montants récupérés.
- Jade utilise souvent son numéro personnel et WhatsApp pour les relances, car certains clients cessent de répondre aux numéros de l’entreprise.
- Il a réalisé un très bon mois précédemment et s’attend à ce que sa paie d’août soit la plus élevée à ce jour grâce aux montants recouvrés.
- L’équipe a reconnu que certaines tactiques informelles peuvent générer un meilleur taux de recouvrement que des méthodes plus strictes, tout en devant arbitrer les pertes sur certains comptes contre les gains sur un plus grand nombre d’autres.

6. Encaissements d’août et besoins de reporting • 0:09:59

- La finance a indiqué un très bon mois d’août en encaissements, estimé entre 1,1 M€ et 1,2 M€.
- Jordan produira un histogramme mensuel qui répartira les encaissements totaux entre les contrats signés dans le mois, les premiers versements, les mois précédents et les recouvrements.
- La métrique manquante est une quantification claire de la part des encaissements mensuels provenant du recouvrement ; Jordan tentera de présenter cette donnée ce mois-ci, maintenant que les systèmes sont davantage connectés.
- Boris a demandé une ventilation en pourcentage des origines d’encaissement (signé ce mois, mois antérieurs, recouvrement) pour améliorer la visibilité financière.

7. Projet d’agrégation bancaire et tableau de bord finance • 0:14:02

- L’équipe a discuté de la centralisation de plusieurs flux bancaires (IBANFirst, Wayo, ADCB, etc.) dans un tableau de bord unique pour automatiser l’agrégation quotidienne au lieu d’exports CSV manuels.
- Les connecteurs tiers existants ne couvrent pas forcément toutes les banques, notamment certaines banques fermées ou spécifiques des Émirats arabes unis ; une solution hybride ou un prestataire spécialisé est donc à l’étude.
- Jordan exporte actuellement des CSV chaque matin et utilise un agent cloud pour normaliser et agréger les données, ce qui prend du temps et n’est pas totalement automatisé.
- Mohamed a été proposé comme lead technique pour chercher une solution capable d’agréger les lignes, d’ajouter des catégories et de produire les axes analytiques utilisés en réunion finance.

8. Sensibilité des données et enjeux de confiance • 0:15:55

- Jordan a exprimé une inquiétude concernant le partage de fichiers de paie et de données financières très sensibles avec Mohamed, tout en reconnaissant qu’il dispose d’un historique d’accès et des compétences adéquates.
- Boris a rassuré l’équipe en indiquant que si Mohamed avait eu une intention malveillante, des problèmes seraient probablement apparus depuis longtemps compte tenu du niveau d’accès dont il dispose.
- Le tableau de bord devra inclure une colonne automatique de catégorisation et prendre en charge au moins sept à huit catégories analytiques afin de correspondre au reporting finance.

9. Architecture du dashboard et usage des ID WebSpot/DealUpSpot • 0:17:27

- Jordan utilise actuellement deux tables liées : l’une source les paiements clients et l’autre stocke un DealUpSpot ID pour suivre les transactions de bout en bout ; il considère cela comme son dispositif idéal.
- Boris construit de nouveaux dashboards basés sur l’ID WebSpot et peut donc relier chaque paiement client si l’identifiant est présent.
- L’équipe s’est accordée sur le principe que chaque enregistrement doit être ancré par un deal ID plutôt que seulement par un contact ID, afin d’assurer la traçabilité entre ventes, CSM et finance.

10. Visibilité des commissions en temps réel pour les ventes • 0:17:59

- Les équipes commerciales n’ont actuellement pas de visibilité fiable sur les paiements réellement encaissés et ne peuvent donc pas voir précisément les commissions acquises à date, ce qui crée de la frustration et un risque d’erreur de paie.
- Jordan a promis aux ventes un dashboard quasi temps réel montrant les commissions jusqu’à la veille afin qu’elles puissent estimer leur rémunération mensuelle.
- La base de ce dashboard est la table des paiements encaissés, alimentée dans Looker et reliée aux rôles commerciaux afin que les commissions soient calculées automatiquement lorsque les données sont correctes.

11. Dépendance aux agents Claude et risque de transfert de connaissance • 0:19:20

- Jordan a construit de nombreuses automatisations avec plusieurs agents Claude (IA), qui exécutent aujourd’hui des transformations critiques mais créent un risque car la connaissance et la configuration restent concentrées chez lui.
- Jordan souhaite rendre le système indépendant d’une personne afin qu’un autre membre de l’équipe, Angèle par exemple, puisse prendre le relais sans devoir acheter des abonnements individuels coûteux à l’IA.
- Boris a proposé un modèle de compte partagé de type « Claude Team » pour centraliser le coût et l’accès aux outils IA, ce qui réduirait la dépendance à une seule personne.

12. Coûts IA, outils et cahier des charges • 0:20:30

- Les coûts en tokens pour l’usage de l’IA sont faibles par rapport aux abonnements, mais les coûts globaux des outils et des modèles d’accès doivent être évalués avant un déploiement plus large.
- Boris a demandé à Jordan de produire un document de spécifications écrit et une maquette visuelle décrivant le dashboard souhaité et les fonctionnalités IA attendues pour guider l’implémentation technique.
- Le choix technique final (Looker, site custom ou autre) dépendra des besoins exprimés par Jordan plutôt que d’une technologie présélectionnée.

13. Données éditables et correction des erreurs IA • 0:21:23

- Jordan a besoin de pouvoir corriger manuellement les correspondances de deals HubSpot assignées par l’IA lorsque celle-ci se trompe, car des noms de clients identiques ou des cas limites génèrent actuellement des erreurs.
- Looker Studio n’offre pas la flexibilité nécessaire pour permettre des modifications en ligne ou des annotations, d’où le développement de nouveaux dashboards supportant des overrides manuels lorsque c’est nécessaire.

14. DealUpSpot ID comme identifiant persistant du cycle de vie • 0:22:26

- Boris a décrit le numéro DealUpSpot comme un équivalent d’un numéro de commande Amazon : créé lorsqu’un appel est réservé et conservé tout au long du cycle client jusqu’au paiement.
- Cet identifiant agrégera les données provenant des systèmes de booking et du CRM afin de maintenir une source de vérité unique pour chaque deal dans tous les outils.
- Jordan impose que toute question liée aux commissions ou à la facturation mentionne systématiquement l’ID DealUpSpot afin d’améliorer la traçabilité et de réduire les frictions.

15. Blocage court terme — reconnexion Inpay et charge opérationnelle • 0:24:18

- La reconnexion du système de paiement Inpay à la plateforme est une priorité immédiate, car elle débloquera plusieurs flux et réduira les points de blocage.
- Jordan se sent actuellement isolé dans sa fonction et consacre du temps à des tâches administratives non essentielles, ce qui réduit sa capacité à livrer la feuille de route.
- Les lacunes en délégation signifient que Jordan n’a pas de relais de confiance pour gérer les tâches de bout en bout ; un travail sur la capacité d’équipe et le plan de passation est donc nécessaire.

16. Recouvrement — qualité des données et causes liées au produit • 0:25:41

- Jordan cartographiera les raisons pour lesquelles les créances sont élevées, car il estime qu’une partie importante des factures impayées provient de la conception produit et des promesses commerciales plutôt que d’un simple problème de processus de paiement.
- L’équipe ne dispose pas encore des bonnes données ni des bons indicateurs (DSO, rapports Inpay propres) pour juger de l’efficacité des actions de recouvrement, ce qui empêche une action éclairée.
- Certains clients ne paient pas car ils n’ont réellement pas les fonds, et d’autres impayés sont dus à des promesses excessives lors de la vente, entraînant ensuite des coûts en remboursements, charge CSM et recouvrement.

17. Proposition d’expertise externe ou de mentorat en recouvrement • 0:26:53

- Boris a proposé deux voies pour acquérir rapidement des compétences en recouvrement : recruter un consultant spécialisé pour un audit et des processus, ou organiser des sessions de mentorat ciblé pour transférer rapidement du savoir actionnable.
- Une session courte et à forte valeur ajoutée avec un expert peut fournir immédiatement une liste de vérifications prioritaires et d’indicateurs à suivre, pendant que la montée en compétence interne se poursuit sur plusieurs semaines ou mois.
- Jordan est d’accord mais souhaite disposer d’abord d’une base de données minimale afin que la session avec un expert soit productive et débouche sur des actions concrètes.

18. Coûts cachés et priorisation de l’acquisition de compétences • 0:31:13

- Boris a souligné que les remboursements, les reprises de travail, le temps support et les recouvrements ad hoc génèrent des coûts cachés qui réduisent l’efficacité opérationnelle et doivent être pris en compte lors de l’évaluation des changements produit et commerciaux.
- Il a recommandé d’investir dans l’acquisition ciblée de compétences externes (mentors/consultants) plutôt que dans des recrutements à temps plein, comme solution plus rentable pour combler rapidement les écarts de capacité.
- Jordan a confirmé sa volonté d’apprendre et de faire intervenir des experts une fois les données de base disponibles, en ajoutant que l’amélioration des promesses produit réduira la pression future sur le recouvrement.

19. Prochaines étapes et responsabilités de suivi • 0:34:27

- Boris recherchera dans son réseau des experts potentiels en recouvrement et étudiera des options de mentorat ou de consultation pour soutenir Jordan et l’équipe.
- Jordan produira le document de besoins du dashboard ainsi qu’un support visuel pour définir les besoins en commission et en édition de données avant l’implémentation technique.
- L’équipe poursuivra les améliorations incrémentales du recouvrement et des dashboards avec les ressources internes, tout en évaluant une aide externe à mesure que les données et les besoins se précisent.
%% notes:fin %%
