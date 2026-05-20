---
type: sop
domain: Sales
owner: "[[Boris Arduy]]"
executant: "[[Karelie]]"
status: active
date-created: 2026-05-20
tags: [sales, karelie, contrats, docusign, zoho, process-operationnel]
---

# Process — Suivi des contrats clients

> Ce doc est pour toi, Karelie. Il décrit tout ce que tu fais sur les contrats — de leur arrivée jusqu'à la bascule "Closed Won" sur Zoho. Si tu as un doute sur quoi que ce soit, ping-moi (cf. dernière section).

## Ce que tu fais, en gros

Les closers déposent les contrats clients dans le Google Sheet **Stockage Tally**. Toi tu :

1. Vérifies que le contrat est bien rempli
2. L'envoies en signature au client via DocuSign
3. Le contre-signes côté EC une fois que le client a signé
4. Ajoutes l'URL du contrat signé dans le Google Sheet **Ventes Fermées**
5. Quand le paiement client arrive, tu passes le deal en "Closed Won" sur Zoho

C'est tout. À faire chaque matin, ~30-45 min.

---

## Routine du matin (dans cet ordre)

1. **Stockage Tally** — nouveaux contrats à traiter ? → étapes 1 à 3
2. **DocuSign** — un client a signé ? → étape 4 (contre-signature EC)
3. **Ventes Fermées** — une mise à jour à faire après contre-signature ? → étape 5
4. **Mail + Pennylane** — paiements reçus ? → étapes 6 et 7 (Ventes Fermées + Zoho Closed Won)

---

## Étape 1 — Récupérer les nouveaux contrats

- Ouvre le Sheet **Stockage Tally**
- Filtre les lignes statut = "Nouveau" (ou triées par date d'ajout)
- Pour chaque nouvelle ligne, ouvre le contrat (URL ou pièce jointe)

---

## Étape 2 — Vérifier que le contrat est conforme

Avant d'envoyer en signature, passe la checklist (10 points) :

- [ ] Nom client + raison sociale + SIRET
- [ ] Adresse client complète
- [ ] Montant correct (croise avec le deal Zoho)
- [ ] Description de la prestation présente
- [ ] Date de début + durée
- [ ] Modalités de paiement (échéancier + mode)
- [ ] **Nom du closer indiqué** — c'est lui qui touche la commission, point critique
- [ ] Mentions légales EC présentes (entité, RCS, etc.)
- [ ] Emplacements de signature activés côté client ET côté EC
- [ ] Aucune rature, mention manuscrite ou champ vide non justifié

**Si tout est bon** → étape 3.
**Si un point manque** → marque la ligne "À corriger" dans Stockage Tally + message Slack au closer pour qu'il corrige. **N'envoie pas en signature tant que ce n'est pas refait.**

Template Slack au closer :
```
Salut [prénom] 👋
Contrat [client] : pas envoyable en l'état.
À corriger :
• [point 1]
• [point 2]
Redépose dans Stockage Tally + ping-moi. 🙏
```

---

## Étape 3 — Envoyer le contrat en signature au client

- Prépare l'enveloppe DocuSign et envoie au client
- Marque la ligne Stockage Tally : "Envoyé en signature" + date

**Relances** : DocuSign relance automatiquement à J+2 et J+5 (déjà configuré, tu n'as rien à faire). Si pas de signature à J+7 → tu me ping.

---

## Étape 4 — Contre-signer côté EC (quand le client a signé)

Quand tu reçois la notif DocuSign "Signé par client" :

1. Ouvre le document dans DocuSign
2. **Vérifie que le client n'a rien modifié** : pas de mention manuscrite ajoutée, montant inchangé, prestation inchangée
3. Si tout est intact → appose la signature EC (compte délégué)
4. DocuSign envoie automatiquement le PDF final aux deux parties

**⚠️ Si le client a modifié quoi que ce soit (rature, mention, montant)** → marque "Litige potentiel" dans Stockage Tally + ping-moi immédiatement. **Ne signe pas.**

---

## Étape 5 — Ajouter l'URL dans Ventes Fermées

- Récupère l'URL du contrat signé depuis DocuSign (lien permanent du PDF)
- Ouvre le Sheet **Ventes Fermées**
- Crée une ligne avec : date de signature, client, montant, closer, URL du contrat, statut = "Contrat signé — paiement attendu"
- Mets à jour la ligne Stockage Tally correspondante : "Signé — en attente paiement"

---

## Étape 6 — Vérifier la preuve de paiement

Quand le paiement client arrive (virement, Stripe, Mollie, SEPA…) :

1. Vérifie que **montant payé = montant du contrat** (ou première échéance si paiement fractionné)
2. Mets à jour Ventes Fermées :
   - Paiement intégral → statut "Payé"
   - Paiement fractionné → statut "1er paiement reçu" + note la prochaine échéance attendue

**Si le montant payé ne correspond pas (en plus ou en moins)** → ping-moi. **Ne passe pas en Closed Won.**

---

## Étape 7 — Passer le deal en "Closed Won" sur Zoho

Condition impérative : contrat signé des deux côtés **ET** paiement reçu (1er paiement minimum si fractionné).

1. Ouvre Zoho, cherche le deal par nom client
2. Vérifie la cohérence : nom du closer, montant, prestation
3. Bascule le deal en statut "Closed Won"
4. Remplis : date de fermeture, montant fermé, URL du contrat signé
5. Ajoute une note Zoho : `Contrat signé le [date] — paiement reçu le [date] — preuve : [type] — closer : [nom]`

**⚠️ Jamais de Closed Won si l'une des deux conditions manque** (signature ou paiement). Sinon la commission du closer part à tort.

---

## Quand tu me ping (DM Slack, pas mail)

Tout de suite dans ces cas :

- Le client a modifié le contrat avant de signer
- Le montant payé ne correspond pas au contrat
- Un closer insiste pour qu'on passe outre un point bloquant
- Tu as un doute sur l'identité du client (SIRET introuvable, société non vérifiable)
- Plus de 7 jours sans signature après envoi DocuSign
- Deux closers revendiquent la même commission
- Tout cas pas couvert par ce doc

Format du message d'escalade :
```
🚨 [type de cas]
Client : [nom]
Montant : X €
Closer : [nom]
Lien : [URL contrat ou ligne Stockage Tally]
Contexte (3 lignes max) : …
Ce que tu attends de moi : [arbitrage / décision à prendre]
```

---

## Récap hebdo (vendredi avant 17h)

Tu m'envoies en DM Slack :

```
📊 Pipeline contrats — semaine [dates]
📥 Reçus : X
✍️ Signés double : X
💰 Paiements reçus : X
✅ Closed Won Zoho : X
💵 Cumul fermé : X €
⚠️ En cours / anomalies : [liste ou RAS]
```

5 min à lire pour moi, et ça me permet de te débloquer si besoin sans qu'on doive se voir.

---

## Tes accès (que je t'ouvre directement)

- Google Sheet *Stockage Tally* — édition
- Google Sheet *Ventes Fermées* — édition
- DocuSign — compte délégué avec droit de contre-signature
- Zoho CRM — édition deals
- Pennylane — lecture (pour vérifier les paiements)
- Slack EC — canal #sales-bis + DM Boris
- Mail @entrepreneurs.com — pour notifications DocuSign et paiements
