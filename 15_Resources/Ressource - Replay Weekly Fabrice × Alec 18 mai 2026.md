---
type: ressource-replay
date: 2026-05-18
date-precision: "inférée du contexte (Sembly export sans date)"
duree: ~30 min
participants: ["[[Alec Henry]]", "[[Fabrice Jaeger]]", "[[Boris Arduy]]"]
canal: Zoom
source: Sembly AI (export PDF)
sensitivity: confidential-max
tags: [replay, weekly, fabrice, alec, boris, cybersecurite, mohamed, iclose, nicolas-farolfi, nas, jordan, kelly-lancement, exposition-rgpd, 82000-fichiers]
status: archive
---

# Ressource — Replay Weekly Fabrice × Alec 18 mai 2026

> Weekly post-lancement Kelly. **3 blocs majeurs** :
> 1. Revue financière des lancements (Tapis pipeline 1.4M signés / 947K engagés, 700K€ marketing, 1.1M€ sortie 45j, panier moyen Tapis tombé à 13K€ vs 15K historique)
> 2. **Crise cybersécurité massive** révélée par l'audit Mohamed (82 000 fichiers publics, redirections email vers boîtes privées, slug iClose responsable du crash Kelly)
> 3. **Nicolas Farolfi écarté immédiatement** (cadre juridique demandé, accès retirés jeudi-vendredi nuit, paiement réglé le 10 du mois suivant, équipe Boris relai 2-3 semaines)
>
> ⚠️ **Plus haute densité d'urgences sécurité depuis prise de poste**. Plan d'action cybersec Boris + Mohamed à livrer sous 1-2 jours.

---

## 🎯 Décisions actées

### 1. Cybersécurité — verrouillage par défaut acté, déploiement étalé pour ne pas casser les lancements

**Découverte audit Mohamed (Boris en porte la voix)** :
- **~82 000 fichiers actuellement accessibles publiquement** sur Entrepreneurs.com — *"une grande partie des documents de l'entreprise et pas seulement de quelques fichiers isolés"*
- **Enregistrements d'appels clients accessibles via liens partagés** — peuvent contenir info sensibles
- **Redirections email entreprise vers boîtes privées** (Yahoo, Outlook) — supprimées immédiatement par Boris

**Décision Alec** : **verrouillage par défaut de toute la plateforme**, accès public uniquement si explicitement nécessaire.

**Méthode arbitrée (Boris)** : remise à plat **dossier par dossier, sous-dossier par sous-dossier** — sinon risque de centaines de tickets support. Précédent invoqué par Fabrice : un audit similaire passé avait cassé des flux clients légitimes.

**Timing** : Boris demande de **reporter le changement global après la période de lancement** — *"vendredi, voire dimanche, serait plus prudent qu'une action immédiate"*. Cédric a déjà été impacté pendant une session live quand un accès a sauté (plus de vidéos, plus de workbooks).

**Plan cybersec global** : Boris et Mohamed construisent un plan d'action plus large **dans les 1-2 prochains jours** — sujet dépasse un seul incident, plusieurs angles morts SaaS identifiés.

> Verbatim Boris : *"Pour une activité entièrement numérique servant majoritairement des clients français et soumise au RGPD, une faille de sécurité majeure pourrait être existentielle."*

### 2. Plan transfer NAS — owner et échéance demandés par Alec

- ~70 To de vidéos à sauvegarder sur NAS
- Alec demande explicitement **qui porte le projet** et **échéance claire** — *"le sujet est repoussé depuis trop longtemps"*
- Avis à recueillir avant le départ d'Alec pour Dubai la semaine suivante : **Mohamed + Boris + Greg + éventuellement Mehdi**
- À articuler avec la migration outils INPA → DOODU mentionnée par Fabrice

### 3. Domaines séparés pour collaborateurs externes — pistée mais non tranchée

- Idée : conserver le domaine principal pour l'équipe cœur, sous-domaine ou autre domaine pour coachs, closers, prestataires externes
- Cible : ~100+ utilisateurs externes basculés sur **licences Google moins coûteuses** (vs licences entreprise)
- Bonus : frontière de sécurité entre internes et contributeurs externes
- **Alec recadre** : *"Est-ce qu'un domaine ou une structure de nommage est réellement nécessaire ? Le vrai sujet pourrait simplement être le plan de transfert NAS."* → la décision domaine est subordonnée au plan NAS

### 4. iClose — incident de lancement attribué au changement de slug, pas aux permissions

**Diagnostic Boris** :
- Le crash du live Kelly est dû au **changement de slug iClose** (de structure "Entrepreneurs" à structure "CGM")
- Seuls **6-7 super-administrateurs** pouvaient modifier le slug
- Le changement a cassé : **intégrations embarquées + redirections + pages associées**
- Boris doit encore examiner les logs iClose pour déterminer **qui a fait le changement et quand**

**Impact estimé par Alec** : **plusieurs centaines de milliers d'euros, potentiellement supérieurs à 1M€**. Demande une investigation technique complète.

**Volume d'appels effectivement récupérés** (Boris) :
- Total appels : ~1 100 (Boris) + 750-800 (sales via Calendly)
- Total candidats : ~4 600
- Appels réservés Boris : 1 106
- Segments touchés : "inactifs" et "<50K€" (reliés équipes externes + iClose)
- **Contournement temporaire Cédric** (calendrier alternatif) + **CTA dans le fichier** = limitation perte significative

### 5. Nicolas Farolfi — sortie immédiate actée + cadre juridique

**Décisions actées en séance** :
- Lettre d'avertissement à **mettre à jour avec les derniers problèmes** (sécurité + non-réponse)
- **Tous les accès retirés dans la fenêtre jeudi → vendredi nuit** (compte Google maintenu si nécessaire pour ne pas casser les automatisations)
- **Document juridique clair** à préparer pour justifier la décision
- **Notification** : appel + email **vendredi**
- **Paiement réglé le 10 du mois suivant** sur la base des jours travaillés
- **Licenciement immédiat** (verbatim Alec)

**Posture Boris en séance** : a **mis en garde contre l'attribution de l'incident iClose à Nicolas sans preuve**, mais reconnaît que comportement global + absence d'implication rendent son maintien impossible.

**Relai opérationnel** : **Boris et son équipe pourraient devoir assurer un relai temporaire pendant 2-3 semaines**, le temps de recruter un nouveau responsable Marketing Ops. → cohérent avec 3 profils déjà shortlistés par Cédric via Aikho mentionnés au weekly 11/5.

---

## 💰 Revue financière des lancements — chiffres bruts

| Item | Montant | Note |
|---|---|---|
| Marketing initial lancements (~6 semaines) | ~700 k€ | Très élevé |
| Pipeline Tapis signé | 1,4 M€ | Annoncé |
| Pipeline Tapis engagé (encaissé partiel) | 947 k€ | Insuffisant pour protéger les marges |
| Dépenses publicitaires totales | ~800 k€ | + 10-15% outils & setup |
| **Panier moyen Tapis** | **~13 k€** | **vs 15 k€ historique** |
| Encaissement initial | Affaibli | — |
| **Sortie de trésorerie 45 derniers jours** | **~1,1 M€** | Pubs + outils + immersions |

**Action demandée Alec → Fabrice** : relancer Aziz sur Slack pour comprendre l'écart sur la perte d'engagement et confirmer les bons filtres + indicateurs.

---

## 👥 Point équipe et projets opérationnels

- **Départ Alice** réduit la pression sur l'équipe et allège une partie de la charge opérationnelle
- **Houdou** : intégration terminée
- **Jordan** : a rejoint l'équipe, Fabrice convaincu qu'il apporte vraie valeur ajoutée. Plan d'onboarding solide, suivi dans la semaine.
- Chantiers à venir listés par Fabrice :
  - Refactorisation outils de recovery
  - Analyse d'appels par IA
  - Migration INPA → DOODU
  - Sauvegarde NAS (~70 To vidéo)
- Alec : avancer rapidement dès que priorités lancement + cybersec stabilisées

---

## 🔍 Signaux faibles & implications structurelles

1. **🔴 HO39 (crise data systémique) confirmée et amplifiée** : aux 6 problèmes data déjà identifiés s'ajoutent maintenant **3 angles cybersec** (fichiers publics, redirections email, contrôle d'accès SaaS). La verticale Ops/IT/Tech/Data/IA hérite d'une **dette de gouvernance cybersécurité massive**.

2. **🔴 Test de la posture Boris IT permanent** : ce weekly est le premier où Boris parle de l'audit Mohamed comme un livrable consolidé. L'angle pris (verrouillage par défaut + remise à plat méthodique + tempo respectant les lancements) est validé par Alec. **Crédit politique consolidé sur le mandat IT.**

3. **🟡 Tension Alec sur Nicolas** : Alec a déjà tranché la sortie avant le weekly (verbatim : *"Nicolas doit être licencié immédiatement"*). Le weekly sert à cadrer le **comment** juridique, pas le **si**. Boris reste prudent (pas d'attribution iClose sans preuve) — bonne posture éthique.

4. **🟡 Nouveau pattern Alec sur le NAS** : ton plus dur que d'habitude (*"repoussé depuis trop longtemps"*). Le sujet NAS devient un proxy de la frustration générale sur l'exécution IT. À sécuriser dans le plan cybersec en lui donnant un owner + échéance dans les 48h.

5. **🟢 Capital politique Mohamed** : Boris a défendu publiquement Mohamed (charge cybersec). À continuer — Mohamed est désormais le pilier opérationnel de la remise à niveau.

6. **🔴 Lecture financière à anticiper** : la sortie de 1.1M€ en 45 jours + panier moyen Tapis en baisse + engagement seulement à 67% du signé crée un contexte où **toute économie SaaS / réduction de dépenses prend du poids** (KR2.2). Le reporting consolidé au mensuel du 1er juin devra être net.

---

## 🔗 Articulation avec le Plan trimestriel Q1

| Sujet | KR impacté | Implication |
|---|---|---|
| 82 000 fichiers publics + email redirects + slug iClose | **KR3.3 + nouveau scope cybersec** | Audit IT Mohamed (deadline 31/5) devient audit IT **+ cybersec** consolidé. Plan d'action cybersec à livrer **48-72h** (priorité absolue cette semaine) |
| Plan NAS owner + échéance | **KR3.3** | Demande directe Alec → Boris doit cadrer owner et échéance avant départ Alec Dubai (semaine du 25/5) |
| Sortie Nicolas immédiate + équipe Boris relai 2-3 sem | **KR3.3 (stack équipe verticale)** | Sourcing remplaçant Mithril/Aikho s'accélère ; 3 profils shortlistés Cédric à activer |
| Domaines séparés / licences externes | **KR2.2 (audit SaaS)** | Économie potentielle additionnelle sur les ~100 licences externes — à chiffrer dans l'audit SaaS |
| Lancements pression marge + 1.1M€ sortie | **KR2.2 + KR2.1** | Argument fort pour le reporting d'économies SaaS au mensuel 1/6 + accélération recouvrement Jordan |

---

## 📋 Actions Boris cette semaine (extraites)

1. **Construire le plan d'action cybersec avec Mohamed sous 48h** → consultation Mohamed/Boris/Greg/Mehdi sur le NAS avant départ Alec Dubai
2. **Examiner les logs iClose** pour déterminer qui a changé le slug et quand
3. **Co-piloter la sortie Nicolas** : préparer doc juridique vendredi, coordination retrait d'accès jeudi-vendredi nuit avec Mohamed
4. **Sécuriser le relai marketing ops 2-3 sem** : valider avec Cédric les 3 profils shortlistés Aikho + équipe Boris en backup
5. **Cadrer l'owner du plan NAS** et proposer échéance à Alec avant son départ Dubai
6. **Préparer la première vague de verrouillage de fichiers** (méthode dossier par dossier) post-lancements (vendredi-dimanche)

---

## 🔗 Notes liées

- [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] — origine de l'audit qui a révélé les 82 000 fichiers
- [[Ressource - Vocal Alec 29 avril 2026 - Mandat audit IT Mohamed]] — mandat permanent Boris IT/cybersec
- [[Plan trimestriel Q1 - Boris - V1 (mai-juillet 2026)]] — KR3.3 + nouveau scope cybersec
- [[Note - Guerre Trustpilot mai 2026]] — sujet sécurité connexe (résolu côté avis frauduleux, cf. COMEX 19/5)
- [[Mohamed]] — pilier opérationnel cybersec
- [[Nicolas Farolfi]] — sortie immédiate actée
- [[Alec Henry]] — sponsor cybersec + NAS
- [[Fabrice Jaeger]] — co-pilote finance + observateur cybersec
- [[Diag - Hypothèses que j'ai sur la boîte (à vérifier)]] — HO39 (crise data systémique) amplifiée
