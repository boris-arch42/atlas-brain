---
type: ressource-replay
source: Sembly transcript (48 min)
date-meeting: 2026-05-29 10h00-10h48
date-analyzed: 2026-05-29
duration: 48 min
status: analysé
participants: "Boris Arduy, Mohamed Guendouzi"
context: weekly cybersec récurrent — suivi sprint + plan phishing GDZ
sensitivity: confidential-max
tags: [replay, sembly, mohamed, weekly, cybersec, phishing, mfa, riot, fichiers-publics, mots-de-passe, saas, boites-mail-partagees, dashboard-cyber]
related-scope: "[[Scope - Sprint Cybersec 48-72h - mai 2026]]"
related-plan: "[[Ressource - Plan action Cybersec Phishing GDZ - mai 2026]]"
source-org: entrepreneurs-com
---

# 📊 Replay weekly cybersec Mohamed × Boris — 29 mai 2026 (48 min)

> **Contexte** : point hebdo récurrent Boris ↔ Mohamed sur la cybersec EC. Suivi d'exécution du [[Scope - Sprint Cybersec 48-72h - mai 2026]] + du [[Ressource - Plan action Cybersec Phishing GDZ - mai 2026]]. Mohamed est maintenu (cadre GDZ).
>
> **Décision de cadrage** : le tableau **« Data Dashboard Cyber Sécurité »** devient le **tableau de référence** des échanges. Mohamed le remplit en autonomie chaque **jeudi** (datas de la semaine + % d'avancement par sujet + nouveaux sujets), MAJ exceptionnelle cet après-midi pour cette semaine.

## ⚡ Synthèse en 30 secondes

- 🟢 **MFA obligatoire activée** avec délai 48h → effective dès lundi matin pour tous.
- 🟢 **Modèle de financement Riot trouvé** (idée Mohamed) : licence **cofinancée freelance/EC**, ~41 €/an/user si split (vs ~80 €+ plein). À valider avec Alec, puis déploiement.
- 🟠 **Fichiers publics** : ça progresse mais reste la **vidéo** (Samuel, Grégoire, Océane, Charlotte, Rad… ~7 profils). Découverte grave : drives synchronisés → remontée possible jusqu'aux **vidéos privées d'Alec (Dubai)**.
- 🔴 **Hygiène mots de passe catastrophique** confirmée par la campagne (mots de passe nom/prénom/date/ville triviaux).
- 🟠 **Audit SaaS** : 3 clés API OpenAI + lot de mots de passe stockés dans Keeper, **audit complet visé semaine prochaine**.
- 🟠 **Boîtes mail partagées** : doivent passer en boîtes partagées avec logs (≠ partage de mot de passe). Mohamed fournit la marche à suivre.
- 🟢 **Incident iClosed** : investigation poussée (1 mois de logs Nicolas) → **aucune connexion**, sujet **clos** (PC perso, pas de log machine accessible).
- 🟢 **Absence de RH** = angle mort offboarding → Mohamed recrute une RH ; règle posée : **celui qui recrute est responsable de déclarer le départ**.

## ✅ Acté / fait

| Sujet | Statut |
|---|---|
| **MFA / double authentification obligatoire** | ✅ Activée, délai 48h → effective lundi matin |
| **Investigation iClosed (incident)** | ✅ Close — 1 mois de logs Nicolas sniffés, aucune connexion, PC perso non auditable |
| **3 clés API OpenAI** | ✅ Récupérées et stockées (Keeper) |
| **Lot de mots de passe SaaS** | ✅ Reçus hier, stockés dans Keeper |
| **Effectifs à jour** | ✅ Tableau Boris à jour (remis à plat à l'immersion) |

## 🟠 En cours / arbitrages

### 1. Riot — modèle de financement cofinancé (idée forte de Mohamed)
- Coût ~17,2 K€/an au total → **frein**.
- **Idée** : EC prend **la moitié de la licence**, le freelance paie l'autre moitié. « Bon geste » EC + sécurise mails/fichiers du freelance + accès campagnes de sensibilisation, formations, et agent IA de questions (mail/fichier douteux).
- Math : ~**41 €/an/user si split**, ~**80 €+/an** si EC prend tout.
- À reproduire pour les **futurs outils primordiaux** (EC prend 50 %).
- **Mécanique facturation** : déduction sur la facture freelance → **module à développer côté Odoo**.
- ➡️ Boris valide le principe avec **Alec**, puis déploiement direct.

### 2. Fichiers publics — reste le bloc vidéo
- Greg a beaucoup réduit ; **Rad** relancé hier (s'en occupe « dans les prochains jours »).
- 🔴 **Exposition grave** : drives synchronisés/partagés → on pouvait **remonter jusqu'aux vidéos privées d'Alec (domicile Dubai)**.
- **Règle** : pas de lien public pour des ressources clients → créer un dossier et **ajouter les clients par email**.
- ➡️ **Boris crée un groupe Mohamed ↔ équipe vidéo** : Mohamed lance ses commandes, vérifie l'avancement, relance dans le groupe.

### 3. Audit SaaS complet
- Reprise de l'audit ; **cible : photo complète de tous les SaaS la semaine prochaine**.
- Vigilance **mots de passe génériques** (ex. ancien mot de passe d'Océane sur un outil réseaux sociaux inutilisé / sans accès).
- **Keeper** : licences déjà payées (~2 000 $/an) → **adoption à généraliser + formation de tout le monde**.

### 4. Boîtes mail partagées
- Principe : **vraies boîtes partagées avec logs par personne** (ex. drive@…), **jamais** un mot de passe transmis.
- Une boîte porte encore le nom de Fabrice → décider renommage.
- ➡️ Mohamed regarde la mécanique de partage et envoie la **marche à suivre**.

### 5. Accès & ex-collaborateurs
- 🔴 **Pas de RH aujourd'hui** = pas de visibilité sur qui est encore là → Mohamed **recrute une RH** (rôle critique).
- Boris partage son **tableau effectifs** ; Mohamed fait le ratio avec Google Workspace → **désactive les comptes obsolètes**.
- À ajouter au tableau : **closers / membres externes**.
- Closers **lancement Kelly Masol** : externes, présents 3 sem.–1 mois → **licences supprimées au fil des sorties**.
- Vérifs faites : **Ania** (Congo) légitime (check VPN) ; **Tessy** (adresse « experience ») légitime.
- **Règle de gouvernance posée** : *celui qui recrute une personne est responsable de déclarer son départ.*

## 🔴 Constat campagne phishing — hygiène mots de passe
- Résultats globalement **inquiétants**, surtout sur des **profils clés**.
- Beaucoup de mots de passe **triviaux** (prénom/ville/date de naissance/année). Plusieurs collaborateurs ont **cliqué** sur le lien.
- Profils les plus critiques : **le RAF (« Raph »)** et **l'assistante d'Alec** (cohérent avec le plan GDZ : fraude au virement + fraude au président).
- Lecture partagée : **beaucoup s'en désintéressent** (« ils s'en foutent ») → justifie surveillance large + formation obligatoire.

## 🎯 Suite des campagnes de sensibilisation — cadrage (vecteur humain)
La logique retenue reste celle du [[Ressource - Plan action Cybersec Phishing GDZ - mai 2026]] : **simulations de phishing / sensibilisation continue**, ciblant en priorité les **rôles à risque** (RAF, assistante fondateur, finance : Fabrice & Jordan, + heads : Océane, Anisse, Alec) avec envois **échelonnés** (1 h–1 h 30 d'intervalle) pour limiter l'effet « tu as reçu le mail ? ».

- Format proposé pour les **ads/équipes** : sessions de ~30 min en petit comité (initier, expliquer les besoins réels d'accès, réflexes anti-phishing).
- Objectif d'une campagne = **mesurer + reformer**, pas piéger pour piéger.

> 🚧 **Hors périmètre — non retenu dans ce plan.** La discussion a dérivé sur des idées d'**accès webcam / capture d'image d'un collaborateur**, de **RAT/trojan** et de **ransomware** sur des **machines personnelles**. Ce ne sont **pas** des tests de sensibilisation : déployer un malware ou accéder à la caméra/au poste d'une personne = **intrusion** (et, s'agissant d'images intimes, atteinte grave à la personne), avec un vrai **risque pénal** y compris pour l'exécutant — Mohamed l'a d'ailleurs lui-même écarté (ransomware), et Boris a recadré vers *« la complexité, pas les infos qu'on capte »*. ➡️ **Règle vault** : tout test au-delà du phishing/credential-awareness (intrusion poste, accès périphériques) ne se fait que dans un **cadre pentest formel, avec consentement écrit explicite** des personnes concernées et un scope signé. À acter en Decision Record si on veut un jour aller plus loin.

## 📋 Actions à mener

### Boris
- [ ] Valider avec **Alec** le **modèle Riot cofinancé** (50/50 freelance) → puis déploiement.
- [ ] Cadrer la **déduction facture freelance via Odoo** (voir équipe dev Odoo : module de déduction licence).
- [ ] **Créer le groupe Mohamed ↔ équipe vidéo** (Samuel, Grégoire, Océane, Charlotte, Rad…) pour la remédiation fichiers publics + relances.
- [ ] **Partager le tableau effectifs** à Mohamed + y **ajouter closers/externes**.
- [ ] Acter la **règle « le recruteur déclare le départ »** (+ appui au recrutement RH).
- [ ] Pousser **adoption Keeper généralisée** + plan de **formation cyber pour tous** (licences déjà payées, inutilisées).

### Mohamed (GDZ)
- [ ] **MAJ du Data Dashboard Cyber Sécurité cet après-midi** + cadence **hebdo jeudi** (datas + % + nouveaux sujets).
- [ ] **Confirmer l'enforcement MFA** lundi matin.
- [ ] **Audit SaaS complet** visé **semaine prochaine** (croisement Keeper + clés API + mots de passe reçus).
- [ ] **Boîtes mail partagées** : valider la mécanique de partage avec logs + envoyer la **marche à suivre** ; trancher renommage boîte « Fabrice ».
- [ ] **Ratio effectifs ↔ Google Workspace** → désactivation des comptes obsolètes (après réception du tableau Boris).
- [ ] Piloter la **remédiation fichiers publics vidéo** via le groupe (commandes + relances).
- [ ] Préparer la **prochaine vague de sensibilisation** sur les rôles critiques (cadre phishing/credential uniquement — cf. encadré ci-dessus).

## 🟢 Signaux & lecture
- **Posture sécu encore très immature** (« on n'a même pas la base de la base »). Historique de **liens Notion/Monday publics** diffusés en canal général → risque concurrent.
- **Capital relationnel Mohamed** solide ; il pilote bien et propose des idées à fort levier (modèle Riot cofinancé, dashboard de référence).
- **EC = cible exposée** maintenant qu'elle grossit → Mohamed insiste sur « mettre tous les parapluies » : si incident plus tard, au moins le socle aura été posé.

## 🔗 Notes liées
- [[Scope - Sprint Cybersec 48-72h - mai 2026]] — sprint dont ce weekly suit l'exécution
- [[Ressource - Plan action Cybersec Phishing GDZ - mai 2026]] — vecteur humain / cadre des campagnes
- [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] — origine du diagnostic
- [[Mohamed]] — pilier opérationnel cybersec (GDZ)
- [[Alec Henry]] — sponsor (validation modèle Riot)
- [[Fabrice Jaeger]] — finance (cible sensibilisation prioritaire)
- [[Cadre - Process IT-SaaS-Cybersec]] — pilier cybersec long terme
