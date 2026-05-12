---
type: operational-reference
project: "[[_Index|Lancement Kelly]]"
owner: "[[Boris Arduy]]"
created: 2026-05-10
last-updated: 2026-05-10
status: active
tags: [lancement, kelly, closers, iclosed, zoho, operational, mapping]
sensitivity: highly-confidential
related-docs: ["[[Scenario A2 - iClosed vers Zoho]]", "[[Infrastructure - Setup en cours]]", "[[Partenaires - Vue d'ensemble 3 agences]]"]
---

# Closers Kelly — Liste opérationnelle

> Liste complète des 42 closers actifs sur Kelly Launch (17 mai 2026) répartis entre les 3 agences partenaires. Source of truth pour le mapping iClosed ↔ Zoho, le suivi opérationnel et les analyses post-event.

## Vue d'ensemble

| Agence | Closers actifs | Manager(s) |
|---|---|---|
| Tip Talent | 10 | Romain Nussmann (fondateur), Julien (CRO) |
| Momentum | 21 | Lucas Cureau (fondateur), Hélène (CCM) |
| Next Sales | 11 | Axel Greiber (fondateur) |
| **Total** | **42** | |

**Cible call volume** : 2 500 à 3 000 calls répartis sur ~8 jours d'absorption à partir du 17 mai 2026.

**Capacité théorique** : ~60 calls/closer sur la période, soit 7-8 calls/closer/jour.

## Architecture des accès

### Convention emails

Tous les closers ont reçu un email pro `prenom.nom@entrepreneurs.com` (créé spécifiquement pour Kelly Launch). Cet email est :

- ✅ L'email **iClosed** utilisé comme host
- ✅ L'email **Zoho** qui servira au matching Deal Owner dynamique (cf. [[Scenario A2 - iClosed vers Zoho]])
- ✅ L'email **Google Workspace** entrepreneurs.com pour les communications

L'alignement parfait entre iClosed et Zoho garantit que le module API Call + Iterator + Filter du scenario A2 trouve le bon user pour chaque booking.

### Profile et Role Zoho

Tous les closers ont :
- **Profile** : `Sales External` (pas de droits export, mass actions, suppression, sync agenda perso)
- **Role** : `Sales [Agence]` (Sales Tip Talent / Sales Momentum / Sales Next Sales)

L'étanchéité par agence est garantie par les Data Sharing Rules Zoho (mode Privé sur tous les modules critiques).

### ⚠️ Note importante sur les prénoms Tip Talent

Plusieurs closers Tip Talent utilisent un **prénom d'usage différent du préfixe de leur email**. C'est volontaire (prénoms anglophones pour le sales B2B). On utilise les prénoms réels dans Zoho.

## Liste Tip Talent (10 closers)

| # | Prénom (usuel) | Nom | Email Entrepreneurs.com | MDP provisoire iClosed |
|---|---|---|---|---|
| 1 | Ilyan | Maarouf | amr.maarouf@entrepreneurs.com | Amr@Mk9#2024 |
| 2 | Asma | Haidar | asmaa.haidara@entrepreneurs.com | Asm@Hd7!2024 |
| 3 | Assim | Salhi | assim.salhi@entrepreneurs.com | Ass@Sl3#2024 |
| 4 | Ryan | Basri | hamza.basri@entrepreneurs.com | Ham@Bs5!2024 |
| 5 | Johana | Bititi | jihane.bititi@entrepreneurs.com | Jih@Bt2#2024 |
| 6 | Myriam | Abdou | meryem.abdou@entrepreneurs.com | Mer@Ab8!2024 |
| 7 | Mounir | El Mrabet | mounir.elmrabet@entrepreneurs.com | Mou@El4#2024 |
| 8 | Saad | Mouhim | saad.mouhim@entrepreneurs.com | Saa@Mh6!2024 |
| 9 | Sue | Belhouk | soukaina.belhouk@entrepreneurs.com | Sou@Bh1#2024 |
| 10 | David | Naam | yassine.naam@entrepreneurs.com | Yas@Nm0!2024 |

**Manager opérationnel** : Romain Nussmann (à Bangkok) + Julien (CRO), interlocuteur quotidien.

**Commission agence** : 10%.

**Approche commerciale** : nurturing R1-R4 (cycle long).

## Liste Momentum (21 closers)

| # | Prénom | Nom | Email Entrepreneurs.com | MDP provisoire iClosed |
|---|---|---|---|---|
| 1 | chirine | Messalti | chirine.messalti@entrepreneurs.com | Chi@Me5#2024 |
| 2 | Romane | Brechemier | romane.brechemier@entrepreneurs.com | Rom@Br4#2024 |
| 3 | Guillaume | Oliete | guillaume.oliete@entrepreneurs.com | Gui@Ol7!2024 |
| 4 | Nicolas | Marmion | nicolas.marmion@entrepreneurs.com | Nic@Ma2#2024 |
| 5 | Laura | Grangier | laura.grangier@entrepreneurs.com | Lau@Gr9!2024 |
| 6 | Romain | Dubois | romain.dubois@entrepreneurs.com | Roi@Du5#2024 |
| 7 | Arnaud | Roman | arnaud.roman@entrepreneurs.com | Arn@Ro3!2024 |
| 8 | Rachid | kallel | rachid.kallel@entrepreneurs.com | Rac@Ka8#2024 |
| 9 | Paul | Vignes | paul.vignes@entrepreneurs.com | Pau@Vi6!2024 |
| 10 | Hugo | Bourgeois | hugo.bourgeois@entrepreneurs.com | Hub@Bo1#2024 |
| 11 | Ruben | Moussai | ruben.moussai@entrepreneurs.com | Rub@Mo4!2024 |
| 12 | Thibault | Boury | thibault.boury@entrepreneurs.com | Thi@Bo7#2024 |
| 13 | Hafida | Mindset | hafida.mindset@entrepreneurs.com | Haf@Mi2!2024 |
| 14 | zahira | kouchy | zahira.kouchy@entrepreneurs.com | Zah@Ko9#2024 |
| 15 | Lucas | Dijon | lucas.dijon@entrepreneurs.com | Luc@Di5!2024 |
| 16 | Didier | Venerosy | didier.venerosy@entrepreneurs.com | Did@Ve3#2024 |
| 17 | Florent | Campos | florent.campos@entrepreneurs.com | Flo@Ca8!2024 |
| 18 | Thibaut | Noel | thibaut.noel@entrepreneurs.com | Thb@No6#2024 |
| 19 | Nawel | Hamdi | nawel.hamdi@entrepreneurs.com | Naw@Ha1!2024 |
| 20 | Coralie | Provenzano | coralie.provenzano@entrepreneurs.com | Cor@Pr4#2024 |
| 21 | Lucas | Constant | lucas.constant@entrepreneurs.com | Luc@Co7!2024 |

**Manager opérationnel** : Lucas Cureau (fondateur) + Hélène (CCM), contact technique quotidien.

**Commission agence** : 13% (2% setting + 11% closing/upsells).

**Approche commerciale** : R1-to-close (cycle court).

**Backup setting** : jusqu'à 10 setters supplémentaires si besoin.

## Liste Next Sales (11 closers)

| # | Prénom | Nom | Email Entrepreneurs.com | MDP provisoire iClosed | Statut iClosed |
|---|---|---|---|---|---|
| 1 | Said | Dahmani | said.dahmani@entrepreneurs.com | Sai@Da2#2024 | ✅ |
| 2 | Sami | El Hadaoui | sami.elhadaoui@entrepreneurs.com | Sam@El9!2024 | ✅ |
| 3 | Giovanny | Louissaint | giovanny.louissaint@entrepreneurs.com | Gio@Lo5#2024 | ✅ |
| 4 | Anthony | Shehata | anthony.shehata@entrepreneurs.com | Ant@Sh3!2024 | ✅ |
| 5 | Sylvie | Velot | sylvie.velot@entrepreneurs.com | Syl@Ve8#2024 | ✅ |
| 6 | Uhaina | Deguiche | uhaina.deguiche@entrepreneurs.com | Uha@De6!2024 | ✅ |
| 7 | Arthur | Hoscheid | arthur.hoscheid@entrepreneurs.com | Art@Ho1#2024 | ✅ |
| 8 | Nabil | Semrani | nabil.semrani@entrepreneurs.com | Nab@Se3!2024 | ✅ |
| 9 | Guilian | Charpentier | guilian.charpentier@entrepreneurs.com | Gui@Ch7#2024 | ✅ |
| 10 | Axel | Saint Hilaire | axel.sainthilaire@entrepreneurs.com | Axe@Sa9!2024 | ✅ |
| 11 | Walid | Mellal | walid.mellal@entrepreneurs.com | Wal@Me6#2024 | ⚠️ Pas encore actif |

**Manager** : Axel Greiber (fondateur).

**Commission agence** : à confirmer (recommandation Boris : 10-11%).

**Nom commercial** : "Next Sales" (l'agence d'Axel). Axel reste le nom du fondateur. Tout l'écosystème technique utilise "Next Sales" : slug iClosed `kelly-nextsales`, page CF `closer-equipe-no-activity-next-sales`, role Zoho `Sales Next Sales`, UTM `nextsales`.

⚠️ **Walid Mellal** : son accès iClosed n'est pas encore actif (status FALSE). À activer côté iClosed avant le go-live 17 mai. Une fois actif, le scenario A2 matchera automatiquement les bookings qu'il prendra avec son user Zoho. Si non activé à temps, ses deals seront created par défaut sans Owner, à réassigner manuellement.

## Statut accès au 10 mai 2026

| Système | Statut |
|---|---|
| iClosed (host actif) | 🟡 41/42 actifs — Walid Mellal en attente d'activation |
| Email Entrepreneurs.com créé | ✅ Les 42 emails actifs |
| MDP provisoire transmis | ✅ Communiqué aux closers (à changer à la 1ère connexion) |
| Zoho user créé | ✅ 42/42 importés (10 mai, en 2 batches après upgrade licences) |
| Zoho user activé (compte personnel) | ⏳ En attente d'activation par chaque closer via leur email d'invitation |

## CSV d'import Zoho (prêt à l'emploi)

Fichier : `users-zoho-kelly-closers.csv` (situé dans le même dossier Atlas-Brain).

**Procédure d'import** : Zoho → Setup → Users and Control → Users → Import → upload CSV → mapper colonnes → activer "Send invitation email" → Lancer.

**Validation post-import** : 42 succès / 0 échec attendu. Vérifier le report.

## Points de vigilance opérationnels

### 1. Activation Zoho avant dimanche 17 mai 20h

Les invitations Zoho partent automatiquement à l'import. Chaque closer doit cliquer sur le lien et créer son mot de passe **avant le démarrage des bookings Kelly réels** (dimanche soir 17 mai).

Risque si non activé : le closer pourrait prendre des bookings iClosed mais ne pourrait pas accéder à Zoho pour suivre ses deals. Le scenario A2 fonctionnerait quand même (création des deals), mais le closer ne pourrait pas les consulter.

**Action managers** : relayer le message aux équipes pour activation rapide.

### 2. Calendar sync iClosed

Pour que le Round Robin iClosed fonctionne, chaque closer doit avoir synchronisé son calendrier Google ou Outlook avec iClosed. Sinon iClosed ne sait pas quand ils sont dispos et attribue des bookings à des créneaux occupés.

**Action chaque closer** : ~5 min pour synchroniser. À inclure dans l'onboarding ou le coaching du 12 mai.

### 3. Mots de passe provisoires iClosed à changer

Les MDP listés ci-dessus sont **provisoires** et doivent être changés à la 1ère connexion iClosed par chaque closer (best practice sécurité).

### 4. Mismatch potentiel email iClosed ↔ Zoho

Le scenario A2 V1 dépend de l'alignement parfait des emails entre iClosed et Zoho. Si un closer change son email iClosed un jour sans changer côté Zoho (ou inversement), le matching Deal Owner cassera.

**Action préventive** : si un closer change d'email, propager le changement dans les 2 systèmes immédiatement, ou ajouter le user Zoho mis à jour dans le scenario.

### 5. Cas particulier Walid Mellal

Walid n'a pas encore son accès iClosed actif au 10 mai. **Options** :
- L'inclure dans l'import Zoho maintenant → son compte Zoho est prêt quand son accès iClosed sera activé. Pas de risque opérationnel.
- L'exclure de l'import et l'ajouter plus tard.

Choix V1 : inclure dans l'import. Coût marginal nul, moins de friction au moment de l'activation iClosed.

### 6. Prénoms d'usage vs prénoms emails (Tip Talent)

6 closers Tip Talent ont un prénom usuel ≠ préfixe email :
- amr.maarouf → Ilyan
- hamza.basri → Ryan
- jihane.bititi → Johana
- meryem.abdou → Myriam
- soukaina.belhouk → Sue
- yassine.naam → David

Dans Zoho on utilise le **prénom usuel** (celui qu'ils utilisent dans leurs interactions client). Le préfixe email reste tel quel pour ne pas avoir à recréer 6 emails.

## Roadmap post-event (capitalisation données)

Une fois Kelly Launch terminé (~25 mai 2026), prévoir d'enrichir ce doc avec :

- **Performance individuelle par closer** : nombre de calls pris, taux de show-up, taux de closing, montant moyen vendu, retours qualitatifs
- **Performance agrégée par agence** : taux de closing global, ARR généré, qualité saisie Zoho
- **Identification top performers** : pour futurs partenariats (lancement septembre)
- **Identification des cas à corriger** : closers qui ont fait planter le matching A2 (ex: mauvais email iClosed), à documenter pour V2

## Liens

- [[_Index|Hub projet Kelly]]
- [[Scenario A2 - iClosed vers Zoho]] — détail technique du matching Deal Owner
- [[Infrastructure - Setup en cours]] — log de setup
- [[Produit - Méthode Boss Energy]] — produit vendu par les 42 closers
- [[Partenaires - Vue d'ensemble 3 agences]] — contexte business
- [[Partenaires - Tip Talent (Romain Nussmann)]]
- [[Partenaires - Momentum (Lucas Cureau)]]

## Historique

- **2026-05-10** — Création du doc. Listes complètes Tip Talent (10) + Momentum (21) + Next Sales (7) ajoutés à iClosed avec emails `@entrepreneurs.com` et hosts configurés en Round Robin sur les 3 events Kelly. CSV d'import Zoho prêt, import à venir.
- **2026-05-10** — Liste Next Sales enrichie de 4 closers supplémentaires (Nabil Semrani, Guilian Charpentier, Axel Saint Hilaire, Walid Mellal). Walid en attente d'activation iClosed. Total passé à 42 closers. Correction des prénoms usuels Tip Talent (Ilyan, Ryan, Johana, Myriam, Sue, David, Asma) qui diffèrent du préfixe email.
- **2026-05-10** — Import Zoho effectué en 2 batches : Batch 1 (38 users) puis Batch 2 (4 users Next Sales) après upgrade Zoho au-delà du seuil trial 40 users. **42/42 users Zoho actifs.** Accès ouverts pour tous les closers Kelly.
