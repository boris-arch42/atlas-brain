---
type: meeting-synthese
domaine: SIDE
projet: "[[Partenariat Aikho]]"
date: 2026-06-24
seance: "Jour 1 — matinée (07:43 → 10:39)"
participants:
  - "[[Hugues Pringault]] (CEO Aikho — vente/business)"
  - "Julien (co-fondateur Aikho — produit/tech, build V2)"
  - "[[Boris Arduy]] (facilitateur — structure/ops/doc)"
  - "[[Alec Henry]] (co-facilitateur — positionnement/réseau)"
  - "Jonathan (dev Aikho — lead V1 / Echo) — mentionné, absent"
source: "Transcriptions Sembly (3 fichiers) — diarisation imparfaite, attributions reconstruites au contenu"
statut: brouillon-à-valider
sensitivity: confidential
tags: [aikho, seminaire, strategie, positionnement, produit, gtm, jour1]
---

# Aikho — Séminaire stratégique · Jour 1 (matinée) — Synthèse

> **Périmètre** : couvre uniquement la **matinée du Jour 1** (3 enregistrements Sembly, 07:43→10:39, fin sur pause déjeuner « on revient à 13h30 »). L'après-midi (pricing, GTM, objectifs 12 mois, plans d'engagement) n'est **pas** dans ces transcriptions.
> **Cadre Alec** : *« dans ces deux jours, j'agis comme si on était déjà associé »* — focus création de valeur, le deal capital se traite à part.
> **Note diarisation** : Sembly mélange les locuteurs (Speaker 0 = tantôt Hugues, tantôt Alec). Attributions reconstruites au contenu, à recouper si besoin. Vocabulaire transcription : *Aiko / Echo / Alco / ICO / AECO = Aikho* (produit actuel = « V1 / Echo ») ; *V2 / ICO2 = nouvelle plateforme*.

---

## 1. Objectif du séminaire (cadrage Boris)

7 points à figer sur 2 jours (par ordre logique) :
0. **Vision** : cash machine vs valo/levée (tout en découle)
1. **Positionnement figé** : une phrase « on vend X à Y parce que Z », tenable devant toutes les audiences
2. **Focus produit** : la seule chose qu'on garde si tout tombe (ce qu'on montre en démo)
3. **Modèle de pricing** : unité de valeur facturée + panier moyen cible par segment
4. **Priorité géographique** : où passe 80 % de l'effort sur 6 mois, qu'est-ce qu'on écarte
5. **Motion GTM** : 1-2 maximum, qui vend et comment
6. **Objectifs 12 mois chiffrés** : ARR, clients, recrutements, marché
7. **Plans d'engagement** : un owner, une échéance, un livrable par chantier

→ Logique de **« parking »** assumée : ce qui n'est pas prioritaire est noté et retraité plus tard.
→ **Pain point structurel reconnu par les fondateurs** : *« on a toujours été en mode build et itération très rapide, jamais mis en place aucun process, jamais acté un positionnement clair ni une matrice de décision »*. L'enjeu du séminaire est d'**acter**.

---

## 2. Bloc 0 — Vision & ambition

Le vrai premier sujet : **cash machine rentable vs go-big asymétrique avec levée**.

- **Julien** : pas besoin de cash, moteur = **construire un produit / réalisation perso**. Une petite boîte (20 M€ / 20 % EBITDA) « le fait chier ». Veut un axe stratégique avec **une chance d'aller très haut** : cible une valo de l'ordre du **milliard**, min **~100 M€** pour ses ~25 %. Constat lucide : *« aujourd'hui on n'a pas cette stratégie ; il y a un an peut-être »* ; des concurrents ont levé 15-30 M€, Aikho est resté bootstrap.
- **Hugues** : moteur = **entreprendre / créer**, taper fort et vite (« produit high, il faut aller vite »). Reconnaît que **le scale / la levée est précisément ce qu'ils ne savent pas exécuter**. Fallback assumé : serait « très content » d'une boîte de service RH automatisé par l'IA si ça ne scale pas.
- **Alec** : pose le binaire net. Entrepreneurs.com = sa cash machine bootstrap (100 %, 0 dette, rentable J1, ×2/an). Mais pour Aikho il pousse le **pari maximal asymétrique** : *« si on a une stratégie avec 95 % de chances de se planter et 5 % de valoir un milliard dans 18 mois, ça ira »*. Une boîte tech aujourd'hui qui ne tape pas fort = un échec.

**Convergence** : *« Ok, on a calé »* → **on part sur le pari go-big / asymétrique**, pas la petite cash machine. (Nuance : Hugues garde un fallback service-RH plus défensif.)

---

## 3. Le nœud du séminaire — Produit vs Positionnement

### 3.1 État actuel (V1 / Echo)
- **Aikho aujourd'hui = recrutement IA, assessment-first** : interview vocale IA + scoring + screening CV.
- Traction : **~29 000 utilisateurs** passés, **~9 000 interviews**, **~10 clients payants**. Majoritairement **F&B / hôtellerie, Dubaï / GCC, multilingue**.
- Avantage compétitif perçu : l'**interview conversationnelle / vocale**, structurée, **agréable pour le candidat** (vs concurrents type iReview « boring as fuck »), qui remonte les bonnes questions/métriques. Mais **moat fragile** (« ça ne durera pas, des gens intelligents feront aussi bien »). Vrai moat durable = **data verticale + user base** sur une niche.

### 3.2 La V2 (plateforme « journeys » de Julien)
- Julien a passé ~2 mois (ne bosse plus sur Echo, repris par Jonathan) à construire une **plateforme agentique générique** : un *kernel/core* d'abstractions qui permet de monter des **« journeys »** (DAGs de nœuds : sign-up via Hub, upload CV, scoring vs mandat, nœud *Voice Conversation*, etc.).
- Logique : **single-tenant customisé devenu cheap** grâce à Cloud Code + bon harness. Une instance par client → customisation sans l'explosion de paramètres/configuration de la V1. Code spécifique « Hiring Journey » = **~5 % de la code base** ; une journey hiring « from scratch » ≈ **6-12 h** de travail.
- Généralise au-delà du hiring : extraire des infos/métriques de n'importe quel **stakeholder** (candidats, employés, leads, clients). Use cases entrevus : **M&A workforce assessment** (Arnaud / PE : 2 $/employé vs 2 000 $), sales/SDR, prise de RDV, dossiers de financement bancaire.

### 3.3 La tension centrale
- **Trop de configuration tue l'usage** : chaque client veut « ci, ça » → empilement de paramètres → produit ingérable. *« En cherchant à être un fit partout, à être tout pour tout le monde »* → produit illisible.
- **Deux avatars très différents** (Boris) : (a) la boîte qui **sait déjà recruter** et a du volume → veut un outil clé en main, customisable ; (b) le **fondateur TPE/PME qui ne sait pas recruter** → veut un guide qui structure de A à Z. Roadmaps produit incompatibles.
- **Choisir = renoncer** : *« courir deux lièvres (V1 + V2) n'est pas une bonne idée »* → Julien : « moi je ne poursuis pas les deux ».

---

## 4. Côté candidat & idées « marketplace » (débat vif, non tranché)

- **Idée Alec (récurrente, ~3-4 mois)** : exploiter la base de 29 000 candidats déjà profilés (CV + ~20-30 min d'interview). Modèle **two-agents** : un agent candidat **privé** ↔ un agent entreprise, qui négocient le fit et produisent une **shortlist de confiance**, sans réinterview imposée — pour bypasser les seniors qui refusent « d'être screenés par une IA ». Plus loin : un **3e acteur headhunter** → modèle type **Muzo / Paraform** (marketplace de recrutement full-IA, comm sur transaction).
- **Référence Paraform (US)** : marketplace headhunting boostée IA, **série B ~65 M$ visée (40 M$ closés mars 2026), ×40 CA**, ultra-niche sur jobs **techniques/complexes**, pénètre marché par marché, valeur = base de données. Équivalent FR = **Muzo** (copie de Paraform). Boris très bullish, veut s'en inspirer.
- **Résistance forte de Julien** : *« je ne vois pas le pain point ni la valeur »*. Construire une **user base candidat stable, engagée et monétisable** est **très coûteux, très casse-gueule, nécessite 20-50 M$** (vécu chez Revolut « l'enfer du maraîchage » ; c'est pour ça que les boîtes tech lèvent). Le B2C n'est qu'une **conséquence du B2B**. Sans **masse critique côté entreprises** sur un marché/localisation, **aucun message à passer au candidat**.
- **Synthèse de séance** : on **ne scale pas le candidat avec du marketing payant maintenant**. On alimente la machine **gratuitement** via les clients (les clients paient et nous filent leur flux candidat). → **parking** jusqu'à masse critique entreprises.

---

## 5. Sourcing — état des lieux (réalité actuelle)

Comment la valeur arrive aujourd'hui, par ordre d'efficacité :
1. **Le client poste l'URL sur LinkedIn** (= principal driver) ; ou son ATS déverse (ex. CXG : annonce → 50 000 CV → 1er tri → lien Aikho).
2. **User base interne** (re-sourcing sur CV vectorisés) : marche mal car base trop petite + souvent le même candidat a déjà interviewé chez le même type de client (ex. serveurs = quasi tous via LPM).
3. **Sourcing externe** (emails à froid) : taux de clic **abyssal ~10 %**, « comme du cold calling ».

→ Les clients « **managent le feed** » eux-mêmes. Pas (encore) de **synergie inter-clients** (un bon candidat recalé chez A poussé chez B) — *« le produit ne le permet pas »*.
→ Mécanique data déjà en place : **vectorisation des CV** pour le matching ; relance candidat = email générique (peu engageant).

---

## 6. UX — diagnostic (session 3)

- **Consensus** : *« vous n'avez pas un problème de produit, vous avez un problème de marketing & d'UX »*. La base produit est là.
- **Problème UX** = **complexité exposée** : trop d'écrans, trop de clics, paramétrage éclaté → il faut **1-2 h** pour mettre une offre en ligne, alors que la cible (« Chantal, 50 ans, RH ») doit pouvoir le faire en **5 min**.
- **Désaccord de méthode** :
  - Alec : *« on ne peut pas tout exposer ET être simple — la complexité doit vivre quelque part »*. La V2 **cache** la config (paramétrée par client en back-end) → écran épuré : pipe + shortlist + candidats, *« Ask ICO »* en surface agentique.
  - Mais certains clients **veulent ouvrir le capot** (configurer le rejet, le ton de l'agent…) → seul moyen multi-tenant = **exposer le compte/prompt** ⇒ complexité. Tension non résolue (réglages dans *Company Profile* ? sliders ?).
- **Référence cible** : **PipeDrive** — ultra-visuel, 2-3 fonctionnalités clés, un pipe clair, le reste en back-end.
- **Surface agentique** : *« Ask ICO »* = un agent qui opère toute la plateforme (exposable comme plugin Claude/ChatGPT). Au départ tout devait passer par là, mais LLM pas assez bons à l'époque → écrans créés pour borner le scope.

**Décision de base produit** : on **part de la V2** (plus clean, peu de dette) comme socle du futur. *« Il faut absolument partir de ça »* — accepté.

---

## 7. Clients & signaux marché cités

- **LPM** (serveurs, ~9 000 interviews / 6 mois GCC) · **Blue Coral** · **Glucora / Isabella** (autres clients resto)
- **Jumeirah** : venus après avoir vu les volumes LPM ; veulent de l'**interview custom**, pas générique
- **Dubai Holdings** : ~**80 000 personnes/an** ; demande de budgéter **1 000 recrutements** ; exige **plateforme agnostique** (modèles agnostiques, data residency chez eux, JPA compliance, IA Act, privacy)
- **David Thomas / LPM** : paie **~70 000 $/an LinkedIn** → veut s'en affranchir (driver de l'idée sourcing/base candidats)
- **Paris Society** : ~1 000 recrutements/an, **propale envoyée**
- **Arnaud** (PE / M&A) : intéressé par la journey *workforce assessment* post-acquisition
- **Abu Dhabi — émiratisation** : placement d'Émiratis dans le privé, besoins ultra-spécifiques
- Concurrent benchmark : **iReview** (interview IA générique, ~100 M$ ARR)

---

## 8. Points saillants à trancher (renvoi vers les notes dédiées)

- **Décisions validées + parking** → [[Jour 1 — Décisions validées & parking]]
- **Plan d'action & owners** → [[Jour 1 — Plan d'action & owners]]

---

## 🔗 Notes liées
- [[Partenariat Aikho]] · [[Aikho]] · [[Alec Henry]] · [[Boris Arduy]]
- [[Note de valeur - Partenariat Aikho - 2026-05-30]]
- [[🗼 Tour de contrôle - Projets en cours]]
