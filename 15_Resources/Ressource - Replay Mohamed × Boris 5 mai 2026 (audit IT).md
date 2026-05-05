---
type: ressource-replay
source: Sembly transcript (31 min)
date-meeting: 2026-05-05 10h34-11h05
date-analyzed: 2026-05-05 (J4)
duration: 31 min
status: analysé
participants: "Boris Arduy, Mohamed Guendouzi"
context: kick-off audit IT — 1er point Boris↔Mohamed depuis mandat 29/4
sensitivity: confidential-max
tags: [replay, sembly, mohamed, J4, audit-it, cybersecurite, saas, vulnerabilites-critiques, transmission-knowledge, sortie-mohamed-31-mai]
---

# 📊 Replay audit IT Mohamed × Boris — 5 mai 2026 (31 min)

> **Contexte** : 1er point Boris↔Mohamed depuis le mandat audit IT acté par vocal Alec du 29 avril. Mohamed sort le 31 mai 2026. Cf. [[Mohamed]] pour l'historique.
>
> **Lecture du replay** : ce qui devait être un kick-off d'audit SaaS s'est révélé être un **diagnostic cybersécurité d'urgence**. Mohamed a posé devant Boris 6 vulnérabilités critiques bien plus graves que le scope initial.

## ⚡ Synthèse en 30 secondes

- 🟢 **Mohamed est lucide, mature et en attente d'un interlocuteur sérieux** — capital relationnel acquis dès ce 1er point
- 🟢 **Audit SaaS partiel déjà livré il y a 2 semaines** par Mohamed à Fabrice (sur Slack) — non remonté à Alec
- 🔴 **6 vulnérabilités cybersécurité critiques** identifiées qui dépassent largement le scope coût (70-100K€/an) → **risque opérationnel grave + existentiel**
- 🟢 **Plan d'action complet à venir** — Mohamed va envoyer plan + deadlines + audit de sécurité fait à l'arrivée Boris
- 🟢 **Distribution claire des rôles** : Boris = orchestration politique + déblocage accès / Mohamed = expertise technique + livraison
- 🔴 **27 jours avant sortie Mohamed** : Boris doit absolument capter la matière avant 31 mai sinon le savoir part
- 🟢 **Cas concret de faille démontré en direct** : Boris accède encore à `alec@entrepreneurs.com` 18 mois après son départ initial
- 🟢 **Mohamed a proposé une campagne de phishing interne** à Fabrice — refusée/ignorée — Boris valide en séance

## 🔴 Les 6 vulnérabilités critiques identifiées

### 1. Pas de 2FA (double authentification) sur les comptes critiques

Verbatim Mohamed 08:27 :
> *"Aujourd'hui la sécurité chez Entrepreneur, on est en mode catastrophe. [...] Les doubles authentifications sur les solutions, il y en a pas. Tu te connectes, que tu sois au Nigeria ou en Afrique du Sud, tu as aucune double authentification. Et ça, c'est critique."*

Verbatim Mohamed 12:19 :
> *"J'ai essayé de pousser des trucs, la double authentification sur Google, je l'active. Après, on vient me voir, on me dit non mais faut la désactiver."*

→ **Mohamed a essayé d'activer la 2FA, on lui a demandé de la désactiver**. Pattern de gouvernance défaillante (la sécurité demande des arbitrages que la direction ne soutient pas).

### 2. Boîtes mail critiques partagées entre 4-5 personnes

Verbatim Mohamed 08:27 :
> *"Pour les boîtes mail critiques comme Revenu, ou les boîtes mail comme celle de Drive, etc. Je suis pratiquement sûr qu'il y a 4-5 personnes qui ont la boîte mail, et c'est même pas légitime qu'ils aient accès à ce type de boîte mail."*

→ Pas de comptes utilisateurs uniques. Impossibilité de logger qui fait quoi.

### 3. 12 leaks de mots de passe sur le domaine entrepreneurs.com (récents 2026)

Verbatim Mohamed 10:19 :
> *"Sur le web et sur le domaine par exemple des mots de passe entrepreneurs, tu en as 12. Tu as 12 leaks, tu vois, et c'est récent, c'est 2026. Tu as ceux qui se sont inscrits sur Apollo en 2024, tu as une grosse brèche de sécurité chez Apollo et ils ont récupéré tous les mots de passe."*

Verbatim Mohamed 09:38 :
> *"J'ai remonté 10 mails où les mots de passe ils ont été leakés, mais je suis pratiquement sûr à 1000% qu'ils ont pas changé des mots de passe. [...] Je mets ma main à couper qu'ils ont pas été changés les mots de passe."*

→ Mohamed surveille le domaine via outils de cybersécurité. Il a remonté les leaks. **Probable que les mots de passe leakés ne soient toujours pas changés**.

### 4. Accès non révoqués aux ex-collaborateurs — démonstration en direct par Boris

Verbatim Boris 09:12 (cas concret démontré en séance) :
> *"Moi, ça faisait, ça fait un an et demi que je suis parti d'entrepreneurs. Hier, j'ai besoin de la boîte mail alec@entrepreneurs.com pour une raison ou pour une autre. J'ai pris le mot de passe qui est encore enregistré sur mon ordi, je me suis connecté direct au compte. Mais tu imagines, j'ai eu aucune demande, rien. Et Drive, la même chose, je l'ai fait pas plus tard que ce matin d'ailleurs pour un autre sujet."*

Verbatim Mohamed 09:38 (réaction) :
> *"Demain, demain tu te fâches grave avec Entrepreneur. Bref, tu as été malmené, on t'a traité comme une *** etc. Tu as ton ego, en fait, tu vois, j'ai accès à tout, je vais tout *** en fait. Le mec, tu vois, les mecs ils m'ont pris pour un ***."*

→ **Faille systémique majeure**. Boris démontre la vulnérabilité avec son propre compte 18 mois après son départ initial. Cas applicable à tous les ex-collaborateurs.

### 5. APIs jamais désactivées pour les ex-collaborateurs

Verbatim Mohamed 06:00 :
> *"J'ai demandé pareil à Wassim [audit des APIs]. Parce que je lui ai dit, j'en suis sûr à 99%, qu'il y a des API que vous avez donné à des gens qui sont plus là, et les API, ils ont pas été désactivés."*

Verbatim Mohamed 06:44 :
> *"Et ça, c'est le mec qui se barre avec une API. Ça se trouve qu'il utilise l'API d'Entrepreneur, mais personne va s'en rendre compte sur la facturation. Ça va être ah ben c'est normal, on utilise l'API ChatGPT parce qu'on fait x, y ou x, y choses avec tu vois."*

Verbatim Boris 06:59 (extension) :
> *"Ouais, ou si ça se trouve, même pire, il a partagé la clé API sur Claude ou sur ChatGPT pour résoudre un problème. Et là, c'est encore pire parce qu'on a une faille qui est énorme pour le coup."*

→ **Audit des APIs en cours** côté Wassim (info nouvelle).

### 6. Prélèvements SaaS continus sur des outils désactivés depuis 2024

Verbatim Mohamed 02:03 :
> *"Il y a des prélèvements qui se font sur des outils. J'ai des accès, mais moi les outils sont désactivés depuis 2024. Donc ça veut dire qu'il y a des gens qui ont créé encore un accès style ScoreUp, par exemple, tu vois. ScoreUp, sur le compte d'Alec, c'est désactivé depuis 2024, mais il me dit qu'il a encore des prélèvements. Des prélèvements tous les mois."*

→ **Du cash qui sort tous les mois pour des outils non utilisés**. Confirme la fourchette 70-100K€/an d'économies SaaS identifiables.

## 🟠 Pattern de gouvernance IT défaillante

Mohamed a décrit un pattern systémique qui **dépasse le sujet IT** :

### Pas de garde-fou sur les accès
Verbatim Mohamed 05:27 :
> *"Il passe jamais par moi. Donc du coup, ils vont directement aller voir Cédric ou Océane ou autre, par réflexe ils vont le donner, mais on n'a pas de garde-fou aujourd'hui, tu vois. Et ça, c'est un problème critique. Moi, j'ai pas de visibilité."*

→ **L'IT Manager n'est pas dans la boucle des décisions d'accès**. Les heads (Cédric, Océane) donnent des accès directement.

### Partage de comptes au lieu de comptes uniques
Verbatim Mohamed 06:00 :
> *"Moi, ce que je veux à terme, c'est loguer tous les accès, qu'on donne pas un accès générique, parce que l'accès générique, demain il y a un gars qui a téléchargé, je sais pas, une liste de quelque chose, on sait pas c'est qui."*

### Direction qui ne va pas dans la même direction sur la sécurité
Verbatim Mohamed 12:51 (pivot critique) :
> *"Pour que ça marche, il faut que le socle, tu vois, la direction, elle va dans la même direction, tu vois. Parce que si on a des failles, ça lui dit A, l'autre il dit B, l'autre il dit C, tu sais, l'audit, ça va jamais marcher."*

→ **Mohamed identifie le même problème qu'Alec dans son Slack tripartite** : décisions distribuées qui ne convergent pas. C'est exactement ce que la verticale Data/IA/Tech/Ops doit résoudre.

### Pas de documentation à la sortie des collaborateurs
Verbatim Mohamed 03:10 :
> *"Souvent chez Entrepreneurs, les gens arrivent, font des trucs, ils partent, ils documentent rien."*

→ **Cette phrase concerne Mohamed lui-même qui sort le 31 mai**. Si Boris ne capte pas la matière, le pattern se répète.

### PC perso + comptes mélangés
Verbatim Mohamed 13:04 :
> *"Les gens bossent avec des PC perso, donc je pense pas qu'en termes de, de, je pense que tout est mélangé sur leur Outlook par exemple, leur boîte mail de Mac. Demain, le gars il reçoit un mail de phishing, quand ça va pomper, quand ça va pomper son carnet d'adresses, c'est tout le carnet d'adresses qui va, d'entrepreneurs, ce qui va être pris."*

### Convention de nommage adresses mail non posée
Verbatim Mohamed 13:04 :
> *"Pour les adresses mail, j'aurais dit arrêtez de donner des prénoms aux adresses mail [...] faut toujours partir sur une base où tu mets nom-prénom ou prénom.nom."*

→ Petit sujet mais révélateur : zéro convention = pollution opérationnelle (signature Sembly, désambiguïsation Mohamed/mohamed.gendouzi).

## 🟢 Solutions et outils déjà en place ou en cours

Mohamed a aussi mentionné ce qui marche déjà ou est en cours :

| Élément | Status |
|---|---|
| **Keeper (password manager)** | ✅ Mis en place par Mohamed à son arrivée |
| **Audit SaaS partiel** (Slack analyzed : qui utilise / nb jours / nb messages) | ✅ Livré à Fabrice il y a 2 semaines (sur Slack) — non remonté à Alec |
| **Audit de sécurité fait à l'arrivée Boris** | ✅ Existe, à transmettre à Boris |
| **Scripting Google onboarding/offboarding** | ✅ Bossé avec Wassim — *"je crois qu'ils ont un truc qu'ils avaient mis en place sur N8N qui fonctionne"* |
| **Doc onboarding/offboarding** | ✅ À transmettre à Boris |
| **Surveillance domaine via outils cybersec** | ✅ En place |
| **Groupe de sécurité partagé Anisse** | ✅ Créé pour les calendriers |
| **Audit des APIs côté Wassim** | 🟠 Demandé par Mohamed, en cours |
| **Campagne de phishing interne** | ❌ Proposée à Fabrice, refusée/ignorée — Boris valide |

## 🎯 Distribution des rôles posée en séance

### Boris — orchestration politique + déblocage
Verbatim Boris 11:07 :
> *"Moi, comme ça, on collabore ensemble là-dessus pour que moi je fasse la partie, on va dire, politique, pour m'assurer que tu es bien tout ce qu'il te faut, les accès, les machins, les trucs. S'il faut des négociations, deal avec X ou Y personne, n'hésite pas à faire appel à moi à ce moment-là."*

### Mohamed — expertise technique + livraison
Verbatim Boris 11:52 :
> *"Et toi, tu peux gérer la partie sécurité, accès, machin, ce qui fait ta force et ta spécialité aujourd'hui."*

### Validation Mohamed
Verbatim Mohamed 11:58 :
> *"Ouais, c'est parfait."*

→ **Distribution acquise sans friction**. Mohamed accepte que Boris devienne owner permanent post-31 mai sans que Mohamed perde la main sur les 27 jours qui restent.

## 📦 Ce que Mohamed va envoyer à Boris

| Document | Délai | Statut |
|---|---|---|
| Audit SaaS partiel (déjà sur Slack) | Aujourd'hui ou demain | À demander explicitement |
| Audit de sécurité fait à l'arrivée Boris | Aujourd'hui ou demain | À demander explicitement |
| Plan d'action avec deadlines | Quelques jours | Demande Boris explicite — base de travail commune |
| Doc onboarding/offboarding scripting Google | Aujourd'hui ou demain | À demander explicitement |

→ **Action Boris cette semaine** : créer un dossier `15_Resources/IT-Audit-Mohamed/` et y archiver tout ce que Mohamed envoie. Sinon le savoir part avec lui le 31 mai.

## 🟢 Dynamique relationnelle — capital acquis

### Signal final extrêmement positif

Verbatim Mohamed 18:47 (clôture du call) :
> *"Parfait, c'est magnifique. C'est ce que j'attendais, c'était de l'action."*

→ **Mohamed était en attente d'un interlocuteur sérieux**. Boris incarne ça. Capital relationnel acquis sur les 4 dernières semaines de Mohamed dans la boîte.

### Boris valide une idée que Fabrice avait ignorée

Verbatim Boris 16:03 (validation campagne phishing) :
> *"C'est une super idée le coup d'avoir des fakes comme ça [...] mais c'est juste de se dire après, si on doit reformer les gens, au moins on sait sur quoi on doit être vigilant et sur quoi on doit les reformer potentiellement au niveau de la boîte de manière générale."*

→ **Excellent signal** : Boris valide une idée que Mohamed avait remontée à Fabrice et qui n'avait pas été suivie. Incarne le mandat de challenge constructif sans dévaloriser Fabrice (Fabrice n'est pas mentionné comme refuseur).

### Mohamed signale qu'il sollicitera Boris au besoin

Verbatim Mohamed 18:11 :
> *"Moi, comme ça, je te solliciterai si tu peux. Si toi, ton rôle permet d'avoir des choses plus rapidement, je te solliciterai."*

→ Acquis : Mohamed va utiliser Boris comme levier de déblocage sur les 27 jours qui restent.

## 🎯 Implications stratégiques

### Implication 1 — Le sujet IT n'est pas un coût mais un risque existentiel

Avant ce replay, le sujet IT était cadré comme un **sujet de coût** (70-100K€/an d'économies SaaS). Après ce replay, c'est devenu un **sujet de risque existentiel** :
- Leaks de mots de passe non changés (12)
- Accès non révoqués (cas Boris démontré)
- APIs orphelines
- Pas de 2FA
- Boîtes mail critiques partagées
- Pas de garde-fou sur les accès

→ **Cadrage à remonter à Alec** : la dimension sécurité doit être traitée avec la même urgence que la dimension coût. Probablement plus urgente même.

### Implication 2 — Le call demain (5 mai) bénéficie d'un angle IT concret

Si Alec ou Fabrice évoque l'IT/SaaS demain, Boris peut répondre :
> *"J'ai eu un point avec Mohamed ce matin. L'audit SaaS partiel est déjà fait depuis 2 semaines. Au-delà du sujet coût (70-100K€/an), il a identifié 6 vulnérabilités sécuritaires critiques — leaks de mots de passe Apollo récents non changés, pas de 2FA, accès non révoqués sur ex-collaborateurs, APIs orphelines, prélèvements continus sur SaaS désactivés. Mohamed me livre un plan d'action sous quelques jours, et je porte la coordination politique pour qu'il ait les accès et arbitrages dont il a besoin. Échéance : tout consolidé avant son départ le 31 mai."*

→ Cet angle est **factuel, structurant, justifie le mandat IT permanent Boris**, et c'est un signal positif pour Fabrice (Mohamed a bossé) + un signal d'alerte pour Alec (situation grave).

→ **Mais à mentionner en 30 secondes max** demain. Pas le sujet principal du call.

### Implication 3 — Transmission de connaissance Mohamed → Boris devient priorité

C'est plus qu'un audit ponctuel. C'est une **passation d'expertise sur 4 semaines** :
- Mohamed sort le 31 mai
- Boris doit capter : audit SaaS + audit sécurité + plan d'action + scripting Google + cartographie SaaS + comptes/accès/APIs
- Sinon le savoir disparaît et les 6 vulnérabilités restent ouvertes

→ **Cadence proposée** : point hebdo Boris↔Mohamed sur les 4 semaines + livrables documentés à chaque point + dossier IT-Audit-Mohamed dans le vault.

### Implication 4 — Boris doit débloquer politiquement Cédric et Océane pour Mohamed

Mohamed a besoin d'accès aux outils gérés par Cédric et Océane :
- Cédric : ScoreUp et autres outils marketing
- Océane : outils communication

→ **Action Boris cette semaine** : pinger Cédric et Océane pour qu'ils donnent à Mohamed la liste exhaustive des SaaS qu'ils gèrent + les accès admin nécessaires.

### Implication 5 — Wassim plus impliqué que prévu sur les sujets transverses

Mohamed a mentionné avoir bossé avec Wassim sur l'onboarding/offboarding scripting Google + l'audit des APIs.

→ **Information utile** pour la fiche Wassim : il porte plus que de l'IA pure, il a des sujets infra/IT transverses. Cohérent avec le fait que Fabrice "attend de voir" Wassim sur des sujets concrets.

## 📨 Verbatim significatifs supplémentaires

### Sur le mode catastrophe sécurité
- Mohamed 08:27 : *"Aujourd'hui la sécurité chez Entrepreneur, on est en mode catastrophe."*
- Mohamed 04:24 : *"Aujourd'hui [...] tu as un grand nombre de potentiels de concurrents. Je veux pas que demain il y a un gars qui arrive tout gentil, ouais c'est bon, je [me lance] entrepreneur, le mec il t'a pompé les trois quarts de tes données, tu t'en es pas rendu compte, et que 6 mois après tu te rends compte que le mec il a récupéré tes leads, il a récupéré tes trucs."*

### Sur la difficulté de pousser les bonnes pratiques
- Mohamed 06:00 : *"On a mis en place Keeper. Je me bats à chaque fois, je me bats à chaque fois."*
- Mohamed 12:19 : *"On a activé le truc des calendriers. J'ai créé un groupe de sécurité où Anis peut partager parce qu'il me dit que Fantôme, ça marche pas."*

### Sur la nécessité d'un onboarding/offboarding structuré
- Mohamed 07:33 : *"Pour moi, pour les futurs, tout se fait dans l'onboarding. C'est-à-dire qu'on onboard, on fait un formulaire de quel outil il a besoin. [...] Donc on onboard qui a accès à quoi, parce que comme ça demain quand il y a l'offboarding, on sait qu'il a eu accès à quoi. Donc nous, ça nous permet derrière d'aller désactiver tous ces comptes-là et de virer les licences."*

### Sur la campagne de phishing interne
- Mohamed 14:15 : *"Ce que j'avais proposé à Fabrice, pour voir un peu la maturité des gens sur l'aspect du phishing, c'est d'organiser une campagne de phishing, tu vois, en interne. C'est-à-dire qu'on crée un mail, on l'envoie à tous les collaborateurs, et on voit qui est tombé dans le panneau ou pas."*
- Mohamed 15:01 : *"Avec les chiffres qu'on aura [...] est-ce qu'on fait une masterclass encore sur la sécurité, est-ce qu'on met des outils en place, est-ce qu'on fait des rappels dans le meeting mensuel."*

### Sur le pivot relationnel
- Boris 03:25 : *"C'est exactement typiquement le genre de sujet que je voulais voir avec toi sur la suite. [...] Vraiment voir quel process, quel système on peut aujourd'hui mettre en place pour que déjà de 1, tous les accès soient sécurisés."*
- Boris 11:07 : *"Tu peux me faire un plan avec des deadlines typiquement? [...] Un plan d'action en disant, là cette semaine on fait tel truc [...] et au [bout] de, je sais pas, un mois ou un mois et demi on est nickel niveau sécurité, tout le monde est clean et propre et il n'y a plus d'enjeu ou en tout cas c'est considérablement diminué."*

## 🔗 Notes liées

- [[Mohamed]] (MAJ J4 — audit IT démarré + 6 vulnérabilités + plan transmission)
- [[IT-Audit-Mohamed]] (dossier matière à archiver toutes les docs Mohamed)
- [[Cadre - Process IT-SaaS-Cybersec]] (à créer post-livraison plan Mohamed)
- [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] (HO40 nouvelle hypothèse — sécurité IT en mode catastrophe)
- [[Prep - Call Ops IT Tech Data IA 5 mai]] (angle IT prêt à mobiliser si Alec demande)
- [[Wassim]] (info nouvelle — bosse aussi sur onboarding/offboarding + audit APIs)
- [[Anisse Rbibe]] (groupe de sécurité partagé créé pour calendriers)
- [[Fabrice Jaeger]] (a reçu l'audit SaaS partiel sur Slack il y a 2 semaines + a refusé/ignoré la campagne phishing)
- [[Cédric De Saint Jean]] (à pinger pour donner la liste SaaS marketing à Mohamed)
- [[Océane De Queiros]] (à pinger pour donner la liste SaaS communication à Mohamed)
- [[Hub - Mithril]] (sourcing potentiel pour profil IT/cybersec post-Mohamed)
