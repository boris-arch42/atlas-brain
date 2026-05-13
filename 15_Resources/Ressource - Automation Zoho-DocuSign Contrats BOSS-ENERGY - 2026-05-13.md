---
type: ressource-automation
source: build session Boris ×Claude — 12-13 mai 2026
date-build: 2026-05-12 / 2026-05-13
date-analyzed: 2026-05-13 (J12)
status: V1.2 — en production (2 scénarios Make, funnel Kelly Launch complet)
participants: "Boris Arduy"
context: "automatisation génération contrats MÉTHODE BOSS (scénario 1) + log des ventes fermées (scénario 2). Funnel Kelly Launch complet bout-en-bout dans Google Sheets : Tally → RDV → Contrats envoyés → Ventes fermées."
sensitivity: confidential
tags: [zoho, docusign, make, automation, contrats, kelly-launch, boss-energy, google-sheets, funnel, ventes, J12, aries-consulting, ops]
related: "[[Alec Henry]], [[Kelly Launch]], [[BOSS-ENERGY]], [[Mohamed]] (audit IT)"
---

# ⚙️ Automation Zoho ↔ Make ↔ DocuSign / Sheets — Funnel Kelly Launch V1.2

> **Contexte** : construction le 12-13 mai 2026 de **2 pipelines d'automatisation** complémentaires pour le pipeline Kelly Launch — Agences Externes (Entrepreneurs.com / ARIES Consulting FZCO) :
> 1. **Scénario 1** : génération + envoi automatique des contrats MÉTHODE BOSS quand un Deal passe à `Engagé` dans Zoho
> 2. **Scénario 2** : log des ventes finalisées quand un Deal passe à `Fermé Gagné` dans Zoho
>
> Les deux alimentent un **funnel Google Sheets centralisé** à 4 étapes (Tally → RDV → Contrats → Ventes). Architecture pensée pour 50-200 contrats/mois.
>
> **Pourquoi cette note** : référence technique + runbook + journal de debugging. À consulter en cas d'incident, d'évolution V2, ou pour onboarder un dev/admin.

---

## ⚡ Synthèse en 30 secondes

- 🟢 **Funnel Kelly Launch complet en prod** : Tally → RDV → Contrats envoyés → Ventes fermées (4 onglets Sheets dans le même fichier `Stockage Tally`)
- 🟢 **Scénario 1 — Contrats (5 modules)** : Zoho `Engagé` → Webhook → Get Deal → DocuSign API (envelope from template + tabs pré-remplis + routing client/Alec) → update Zoho `Statut contrat = Envoyé` → log Sheets `Contrats envoyés`
- 🟢 **Scénario 2 — Ventes fermées (3 modules)** : Zoho `Fermé Gagné` → Webhook → Get Deal → log Sheets `Ventes fermées`
- 🟢 **0 ligne de Deluge** — tout no-code Make + API calls bruts
- 🟢 **Tests bout-en-bout validés** : envelope DocuSign (08h34), ligne `Contrats envoyés` (09h12), ligne `Ventes fermées` (11h33) — toutes le 13 mai 2026
- 🟢 **Garde-fou anti-doublon scénario 1** : condition `Statut contrat ≠ Envoyé`
- 🟡 **Pas de garde-fou anti-doublon scénario 2** — passage en Fermé Gagné rare, doublon dans le sheet non-critique
- 🟡 **`Date 1er paiement` en saisie manuelle directe dans le sheet** (Feuille 4) par la compta/admin — pas remontée depuis Zoho car non systématiquement remplie côté CRM
- 🔴 **Tab "Alec Henry"** dans template DocuSign mis de côté volontairement — utilité non documentée
- 🔴 **Recipient 2 DocuSign = `sales@entrepreneurs.com` au nom d'Alec** : à transitionner vers l'assistante dédiée

---

## 🏗️ Architecture en un coup d'œil

### Scénario 1 — Génération contrats MÉTHODE BOSS

```
┌─────────────────────────────────────────────────────────────┐
│  ZOHO CRM                                                   │
│  Affaire passe Stage = "Engagé"                             │
│  Workflow Rule "Trigger DocuSign — Affaire Engagée"         │
│  Condition : Statut contrat ≠ "Envoyé"                      │
│  Action : Webhook POST → Make                               │
└────────────────────────┬────────────────────────────────────┘
                         │ payload JSON {deal_id, stage, deal_name}
                         ▼
┌─────────────────────────────────────────────────────────────┐
│  MAKE — "Zoho → DocuSign — Contrats BOSS-ENERGY" (5 modules)│
│                                                             │
│  [1] Webhooks Custom — reçoit le payload                    │
│  [2] Zoho Get an Object — récupère le Deal complet          │
│  [3] DocuSign API Call — POST envelope from template        │
│  [4] Zoho API Call — PUT Statut contrat = Envoyé            │
│  [5] Google Sheets Add a Row — log Feuille 3                │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
              DocuSign envoie email signataire
              Client signe (routing 1) → Alec/Assistante (routing 2)
```

### Scénario 2 — Log ventes fermées

```
┌─────────────────────────────────────────────────────────────┐
│  ZOHO CRM                                                   │
│  Affaire passe Stage = "Fermé Gagné"                        │
│  Workflow Rule "Trigger Log Vente — Fermé Gagné"            │
│  Condition : aucune (Tous les Affaires)                     │
│  Action : Webhook POST → Make                               │
└────────────────────────┬────────────────────────────────────┘
                         │ payload JSON {deal_id, stage, deal_name}
                         ▼
┌─────────────────────────────────────────────────────────────┐
│  MAKE — "Zoho → Sheets — Ventes fermées" (3 modules)        │
│                                                             │
│  [1] Webhooks Custom — reçoit le payload                    │
│  [2] Zoho Get an Object — récupère le Deal complet          │
│  [3] Google Sheets Add a Row — log Feuille 4                │
└─────────────────────────────────────────────────────────────┘
```

**Ordre des modules volontaire (scénario 1)** : le log Sheets vient **après** le succès DocuSign + update Zoho. Si DocuSign échoue, pas de log → on évite les fausses lignes pour des contrats qui ne sont jamais partis.

**Pourquoi 2 scénarios séparés et pas 1 avec Router** : déclencheurs métier distincts (envoi vs closing), garde-fous différents, troubleshooting indépendant. Si un scénario casse, l'autre continue.

---

## 📊 Funnel Kelly Launch dans Google Sheets

Le fichier `0.01 Projets / 4. Lancement Kelly / Stockage Tally` contient **4 onglets** qui matérialisent les étapes du funnel :

| Étape | Onglet Sheets | Source | Module concerné |
|---|---|---|---|
| **1. Qualif inbound** | Feuille 1 — `Tally complétés` | Tally form responses | Scénario Tally → Sheets pré-existant |
| **2. Closing call planifié** | Feuille 2 — `RDV bookés` | Booking iClosed (ou équivalent) | Scénario pré-existant |
| **3. Contrat envoyé** | Feuille 3 — `Contrats envoyés` | Make scénario 1, module 5 | Module 5 du scénario 1 |
| **4. Vente fermée** | Feuille 4 — `Ventes fermées` | Make scénario 2, module 3 | Module 3 du scénario 2 |

→ Permet de mesurer les taux de conversion étape par étape directement dans Sheets, sans dépendance Zoho.

---

## 🔑 IDs critiques (à ne pas perdre)

### Scénario 1 — Contrats

| Élément | Valeur |
|---|---|
| **Make webhook URL (scénario 1)** | `https://hook.eu2.make.com/pyov1anmew3yzsodlwrs4fboqw7lofx1` |
| **DocuSign API Account ID** | `c2e38f7c-edb4-435e-87f7-7ac6615901aa` |
| **DocuSign Template ID (Contrat MÉTHODE BOSS)** | `6717eab6-540a-489b-9cc8-fbb32f2235fe` |
| **DocuSign Base URI** | `https://eu.docusign.net` (instance EU) |
| **DocuSign Connection name (Make)** | `Sales Docusign (sales@entrepreneurs.com)` |

### Scénario 2 — Ventes

| Élément | Valeur |
|---|---|
| **Make webhook URL (scénario 2)** | `https://hook.eu2.make.com/exh9u435l7gcj6bte8e0hfzo74sbkmin` |

### Communs aux 2 scénarios

| Élément | Valeur |
|---|---|
| **Zoho Connection name (Make)** | `Zoho CRM` |
| **Zoho instance** | `zoho.eu` |
| **Module Zoho** | `Affaires` (Deals) |
| **Google Sheets spreadsheet** | `0.01 Projets / 4. Lancement Kelly / Stockage Tally` |
| **Google Sheets onglet Contrats** | `Contrats envoyés` (Feuille 3) |
| **Google Sheets onglet Ventes** | `Ventes fermées` (Feuille 4) |
| **Google Sheets connection (Make)** | `Boris (boris@entrepreneurs.com)` |

⚠️ **Toutes ces valeurs sont à protéger** — leur compromission permettrait à un tiers d'envoyer des contrats au nom d'ARIES ou de polluer les sheets. Si exposition suspectée, révoquer l'API key DocuSign + régénérer les webhooks Make.

---

## 🛠️ Configuration Zoho CRM — 2 Workflow Rules

### Workflow Rule 1 — Trigger DocuSign

**Chemin** : `Setup → Automatisation → Règles de workflow → "Trigger DocuSign — Affaire Engagée"`

| Paramètre | Valeur |
|---|---|
| Module | Affaires |
| Quand | Action d'enregistrement → **Édition** → champ spécifique = `Stage` modifié vers `Engagé` |
| Répéter si modifié | **Non coché** |
| Condition | `Statut contrat` n'est pas égal à `Envoyé` |
| Action instantanée | Webhook → `Send to Make for DocuSign` |

### Workflow Rule 2 — Trigger Log Vente

**Chemin** : `Setup → Automatisation → Règles de workflow → "Trigger Log Vente — Fermé Gagné"`

| Paramètre | Valeur |
|---|---|
| Module | Affaires |
| Quand | Action d'enregistrement → **Édition** → champ spécifique = `Stage` modifié vers `Fermé Gagné` |
| Répéter si modifié | **Non coché** |
| Condition | Aucune (`Tous les Affaires`) |
| Action instantanée | Webhook → `Send to Make for Log Vente` |

### Body JSON commun aux 2 webhooks

Les 2 webhooks envoient le même payload minimal — Make refetch le Deal complet ensuite via `Get an Object`.

```json
{
  "deal_id": "${Affaires.ID Affaire}",
  "stage": "${Affaires.Stage}",
  "deal_name": "${Affaires.Nom de l'Affaire}"
}
```

⚠️ **À INSÉRER via la touche `#`** dans l'éditeur Zoho, pas en copier-coller texte brut — sinon Zoho refuse "Nom de l'Affaire" à cause de l'apostrophe (cf. piège #10 du debugging journal).

---

## ⚙️ Configuration Make — Scénario 1 (5 modules)

### Module 1 — Webhooks > Custom webhook

| Champ | Valeur |
|---|---|
| Webhook name | `Zoho Deal Engagé` |
| Output attendu | `{deal_id, stage, deal_name}` |

### Module 2 — Zoho CRM > Get an Object

| Champ | Valeur |
|---|---|
| Connection | `Zoho CRM` |
| Module | `Deals` (Affaires) |
| Object ID | `{{1.deal_id}}` |

### Module 3 — DocuSign > Make an API Call

| Champ | Valeur |
|---|---|
| Connection | `Sales Docusign (sales@entrepreneurs.com)` |
| URL | `/v2.1/accounts/{accountId}/envelopes` |
| Method | `POST` |
| Headers | `Content-Type: application/json` |

⚠️ Pas de `/restapi` au début (Make l'ajoute), Account ID à laisser littéral `{accountId}` (Make remplace par la connexion).

**Body JSON complet** :

```json
{
  "templateId": "6717eab6-540a-489b-9cc8-fbb32f2235fe",
  "emailSubject": "Contrat MÉTHODE BOSS - {{2.Nom de l'entreprise}}",
  "emailBlurb": "Bonjour, veuillez trouver ci-joint votre contrat MÉTHODE BOSS à signer. Cordialement, ARIES Consulting.",
  "status": "sent",
  "templateRoles": [
    {
      "email": "{{2.Email du signataire}}",
      "name": "{{2.Nom du signataire}}",
      "roleName": "Client",
      "routingOrder": "1",
      "tabs": {
        "textTabs": [
          { "tabLabel": "Nom de la société", "value": "{{2.Nom de l'entreprise}}" },
          { "tabLabel": "Adresse postale", "value": "{{2.Adresse postale}}" },
          { "tabLabel": "Ville", "value": "{{2.Ville}}" },
          { "tabLabel": "Code postal", "value": "{{2.Code postal}}" },
          { "tabLabel": "Pays", "value": "{{2.Pays}}" },
          { "tabLabel": "Numéro d'immatriculation", "value": "{{2.Numéro d'immatriculation}}" },
          { "tabLabel": "Représenté par", "value": "{{2.Nom du signataire}}" },
          { "tabLabel": "Fonction", "value": "{{2.Fonction du signataire}}" },
          { "tabLabel": "Adresse mail", "value": "{{2.Email du signataire}}" },
          { "tabLabel": "Téléphone", "value": "{{2.Téléphone du signataire}}" },
          { "tabLabel": "Montant HT", "value": "{{2.Montant Total HT}}" },
          { "tabLabel": "Modalités de paiements", "value": "{{2.Modalité de paiement (texte)}}" }
        ]
      }
    },
    {
      "email": "sales@entrepreneurs.com",
      "name": "Alec Henry",
      "roleName": "CEO",
      "routingOrder": "2"
    }
  ]
}
```

### Module 4 — Zoho CRM > Make an API Call

| Champ | Valeur |
|---|---|
| URL | `/v2/Deals/{{2.Object ID}}` |
| Method | `PUT` |

⚠️ Pas de `/crm` au début (Make l'ajoute).

**Body** :

```json
{
  "data": [
    {
      "Statut_contrat": "Envoyé"
    }
  ]
}
```

### Module 5 — Google Sheets > Add a Row

| Champ | Valeur |
|---|---|
| Connection | `Boris (boris@entrepreneurs.com)` |
| Spreadsheet | `Stockage Tally` |
| Sheet | **`Contrats envoyés`** (Feuille 3) |
| Use column headers as IDs | **Yes** |

**Mapping des 10 colonnes** :

| Colonne | Source Make |
|---|---|
| Date envoi | `{{now}}` |
| Deal ID | `{{2.Object ID}}` |
| Nom Affaire | `{{2.Nom de l'Affaire}}` |
| Société | `{{2.Nom de l'entreprise}}` |
| Email signataire | `{{2.Email du signataire}}` |
| Nom signataire | `{{2.Nom du signataire}}` |
| Format | `{{2.Format}}` |
| Modalités | `{{2.Modalites paiement}}` |
| Montant HT | `{{2.Montant Total HT}}` |
| DocuSign Envelope ID | `{{3.envelopeId}}` |

---

## ⚙️ Configuration Make — Scénario 2 (3 modules)

### Module 1 — Webhooks > Custom webhook

| Champ | Valeur |
|---|---|
| Webhook name | `Zoho Deal Fermé Gagné` |
| Output attendu | `{deal_id, stage, deal_name}` |

### Module 2 — Zoho CRM > Get an Object

| Champ | Valeur |
|---|---|
| Connection | `Zoho CRM` (réutilise celle du scénario 1) |
| Module | `Deals` |
| Object ID | `{{1.deal_id}}` |

### Module 3 — Google Sheets > Add a Row

| Champ | Valeur |
|---|---|
| Connection | `Boris (boris@entrepreneurs.com)` |
| Spreadsheet | `Stockage Tally` |
| Sheet | **`Ventes fermées`** (Feuille 4) |
| Use column headers as IDs | **Yes** |

**Mapping des 13 colonnes** :

| Colonne | Source Make |
|---|---|
| Date closing | `{{now}}` |
| Deal ID | `{{2.Object ID}}` |
| Nom Affaire | `{{2.Nom de l'Affaire}}` |
| Société | `{{2.Nom de l'entreprise}}` |
| Email signataire | `{{2.Email du signataire}}` |
| Nom signataire | `{{2.Nom du signataire}}` |
| Format | `{{2.Format}}` |
| Modalités | `{{2.Modalites paiement}}` |
| Montant HT | `{{2.Montant Total HT}}` |
| Mensualités | `{{2.Mensualités}}` |
| Source / Agence | `{{2.Agence_Assignee}}` |
| **Date 1er paiement** | **(non mappé)** — saisie manuelle directe dans le sheet par la compta/admin |
| Closer | `{{2.Gestionnaire de l'Affaire.name}}` ⚠️ avec `.name` (champ Collection) |

**Choix design `Date 1er paiement` saisie manuelle** : ce champ n'est pas systématiquement rempli dans Zoho côté CRM (l'admin a parfois l'info en direct sans passer par Zoho). Saisie manuelle dans le sheet = source unique côté finance, évite de devoir double-saisir Zoho juste pour que Make recopie.

---

## 📋 Mapping complet Zoho ↔ DocuSign (scénario 1)

| # | Champ Zoho Affaire | Tab DocuSign | Recipient cible |
|---|---|---|---|
| 1 | `Nom de l'entreprise` | `Nom de la société` | Client |
| 2 | `Adresse postale` | `Adresse postale` | Client |
| 3 | `Ville` | `Ville` | Client |
| 4 | `Code postal` | `Code postal` | Client |
| 5 | `Pays` | `Pays` | Client |
| 6 | `Numéro d'immatriculation` | `Numéro d'immatriculation` | Client |
| 7 | `Nom du signataire` | `Représenté par` | Client |
| 8 | `Fonction du signataire` | `Fonction` | Client |
| 9 | `Email du signataire` | `Adresse mail` + Recipient email | Client |
| 10 | `Téléphone du signataire` | `Téléphone` | Client |
| 11 | `Montant Total HT` | `Montant HT` | Client |
| 12 | `Modalité de paiement (texte)` | `Modalités de paiements` | Client |

**Tabs DocuSign non mappés (volontaire)** : `Alec Henry` — utilité non clarifiée.

---

## 🐛 Pièges rencontrés & solutions (debugging journal)

| # | Symptôme | Cause | Solution |
|---|---|---|---|
| 1 | Webhook Make output vide (`Bundle 1 empty`) | Zoho envoyait les paramètres en URL query, pas dans le body | Passer **Corps Type** de `Aucune` à `Brut` + Format `JSON` + écrire le JSON via touche `#` |
| 2 | `BundleValidationError: Missing value of required parameter 'id'` | Module Get an Object recevait `deal_id` vide | Idem #1 — fix amont |
| 3 | Module `Send Envelope from Template` n'expose pas de section Tabs | Limitation du module Make for DocuSign | Remplacer par `Make an API Call` brut |
| 4 | `BundleValidationError: Array of objects expected in parameter 'templateRoles'` | Mode Map JSON Make n'accepte pas tous les payloads | Passer en `Make an API Call` brut |
| 5 | DocuSign 404 sur URL `/restapi/v2.1/accounts/...` | Make préfixe déjà `/restapi` — doublon | URL = `/v2.1/accounts/{accountId}/envelopes` (sans `/restapi`, avec `{accountId}` littéral) |
| 6 | DocuSign 400 avec GET sur `/envelopes` | Endpoint liste les envelopes — filtres date/id obligatoires | Normal — la création est en POST, le GET de test sans filtre échoue mais ne signale pas mauvaise URL |
| 7 | Zoho 400 `Invalid URL /crm/crm/v2/Deals/...` | URL Make doublonnée par préfixe automatique | URL = `/v2/Deals/{{2.Object ID}}` (sans `/crm`) |
| 8 | Champs custom non visibles dans Zoho `Update an Object` | Layout par défaut n'expose pas les champs custom | Contourné via `Make an API Call` brut |
| 9 | Google Sheets module n'écrit nulle part | Renommage onglet sans rafraîchir le module Make | Toujours **rafraîchir** la liste des sheets dans Make après renommage, ou `Use column headers as IDs = Yes` |
| 10 | Zoho refuse `${Affaires.Nom de l'Affaire}` à l'enregistrement webhook | Copier-coller texte brut au lieu d'insertion via `#` — l'apostrophe casse le parsing | **Toujours utiliser la touche `#`** pour insérer les champs de fusion, jamais en texte brut |
| 11 | Workflow Rule scénario 2 ne se déclenche pas | Libellé Stage choisi (`Gagnés Fermés`) ≠ libellé exact du pipeline (`Fermé Gagné`) | Vérifier dans le dropdown que la valeur match **exactement** un stage du pipeline custom Kelly Launch |

---

## 📖 Runbook opérationnel

### Scénario 1 (contrats)

**"Un contrat ne part pas après passage en Engagé"**
1. Vérifier sur l'Affaire que `Statut contrat ≠ Envoyé` (sinon garde-fou actif, normal)
2. `Setup → Notifications → Webhooks → Journal` dans Zoho → status du dernier appel
3. Make → History du scénario 1 → identifier module en rouge
4. Vérifier les **16 champs requis** sur l'Affaire (cf. [[Checklist Closer Kelly Launch V1]])
5. Si erreur DocuSign : souvent un `tabLabel` qui ne match plus le template

**"Le contrat est envoyé mais des champs sont vides"**
- Cause #1 : `tabLabel` dans le JSON ne match plus celui du template (sensible casse/accents/espaces)
- Cause #2 : champ Zoho vide sur l'Affaire
- Fix : ouvrir template DocuSign → onglet Recipients → vérifier labels exacts

**"Le scénario tourne en boucle"**
- Vérifier que Module 4 (update Statut contrat) fonctionne
- Vérifier la condition Zoho `Statut contrat ≠ Envoyé`
- Désactiver le scénario Make en urgence

**"La ligne n'apparaît pas dans Contrats envoyés"**
- Cause #1 : onglet renommé sans refresh module Make
- Cause #2 : Module 3 ou 4 en erreur → scénario s'arrête avant module 5
- Cause #3 : Connection Sheets expirée
- Cause #4 : en-têtes du sheet modifiés

### Scénario 2 (ventes)

**"Le webhook ne se déclenche pas en Fermé Gagné"**
- Vérifier que le libellé exact du Stage dans la Workflow Rule = celui du pipeline (`Fermé Gagné`, pas "Gagnés Fermés" ou autre)
- Vérifier dans `Setup → Notifications → Webhooks → Journal` qu'aucune tentative n'a eu lieu

**"La ligne dans Ventes fermées est incomplète"**
- `Date 1er paiement` vide = normal, c'est de la saisie manuelle
- Si autres champs vides : le champ n'est pas rempli sur l'Affaire → mettre à jour côté Zoho puis re-déclencher (Stage → autre → Fermé Gagné)
- `Closer` vide ou affiche un ID : mapping doit utiliser `.name` (champ Collection)

### Communs

**"Erreur d'authentification DocuSign ou Zoho"**
- OAuth expirée → reconnecter via Make → module concerné → Connection → Edit → Reauthorize

**"Volume mensuel élevé — quotas saturés"**
- DocuSign : `Account → Plan & Billing` → envelope allowance/an
- Make : 1 contrat = 5 ops (scénario 1) + 3 ops (scénario 2 si fermé gagné). À 200 contrats/mois max = ~1600 ops/mois, fits plan Pro (10K ops)

---

## 🔄 Backlog V2 (à arbitrer)

### Priorité haute

- [ ] **Webhook retour DocuSign Connect** → quand client signe, update Zoho `Statut contrat = Signé` + `Date de signature`. Idéalement update aussi la ligne `Contrats envoyés` (matcher sur Envelope ID)
- [ ] **Identifier l'assistante dédiée** et basculer comme recipient 2 (au lieu de `sales@entrepreneurs.com` au nom d'Alec)
- [ ] **Error handler Make** sur les 2 scénarios → notif Slack/email à Boris si échec
- [ ] **Activer les scénarios en ON permanent** dans Make (toggle bas-gauche)

### Priorité moyenne

- [ ] **Multi-produits** : router scénario 1 selon `Code Produit` Zoho → templateId DocuSign différent (Oscar, autres programmes)
- [ ] **Bascule Fermé Gagné automatique** quand contrat signé + 1er paiement reçu (intégration Stripe ou virement bancaire à concevoir avec compta) — éliminerait la saisie manuelle de `Date 1er paiement`
- [ ] **Clarifier le tab "Alec Henry"** dans le template DocuSign
- [ ] **Champ Zoho custom "DocuSign Envelope ID"** pour traçabilité bidirectionnelle CRM ↔ Sheets
- [ ] **Dashboard funnel Kelly Launch** dans Sheets : formules de conversion entre les 4 onglets (Tally → RDV → Contrats → Ventes). Sparkline hebdo, taux de closing, CA réalisé
- [ ] **Garde-fou scénario 2** : condition `Statut contrat = Signé` avant log Vente fermée — évite les fausses ventes loggées

### Priorité basse

- [ ] **Loom 5 min** : comment refaire les 2 scénarios from scratch si tout casse
- [ ] **Tests automatisés** en sandbox Make
- [ ] **Migration vers JWT Auth DocuSign** si volume > 500/mois
- [ ] **Reporting hebdomadaire** Make → Notion ou email récap funnel

---

## 🔗 Liens & ressources connexes

- [[Checklist Closer Kelly Launch V1]] — checklist PDF 1 page (16 champs à remplir avant passage Engagé)
- [[BOSS-ENERGY]] — fiche produit MÉTHODE BOSS (15 SKU, grille Solo/Duo/Trio × x1-x6)
- [[Kelly Launch]] — pipeline commercial cible
- [[Alec Henry]] — CEO ARIES Consulting FZCO, signataire ARIES
- [[Mohamed]] — audit IT en cours, contexte gouvernance SaaS
- [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] — contexte cybersecurity / SaaS

---

## 📝 Méta

- **Construction** : session Boris × Claude, 12 mai 2026 (soir) + 13 mai 2026 (matin/midi)
- **Durée build** : ~4h cumulées (champs Zoho + workflow + 2 scénarios Make + debug + log Sheets x2)
- **Versions** :
  - V1 (13 mai 2026 09h) — 4 modules Make scénario 1, premier envoi DocuSign validé
  - V1.1 (13 mai 2026 11h) — ajout module 5 Sheets `Contrats envoyés`
  - **V1.2 (13 mai 2026 11h35) — ajout scénario 2 "Ventes fermées" (3 modules), funnel Kelly Launch complet à 4 étapes**
- **Tests réussis** :
  - 13 mai 08h34 UTC — envelope DocuSign `c26f5ecb-25b8-886a-8242-2c9b8715ae59` envoyée (status 201, tabs OK)
  - 13 mai 09h12 UTC — ligne `Contrats envoyés` créée (10 colonnes)
  - 13 mai 09h33 UTC — ligne `Ventes fermées` créée (12 colonnes hors Date 1er paiement manuelle)
- **À tester en prod réelle** : 2-3 affaires Kelly Launch réelles avant de considérer V1.2 stable
- **Next steps immédiats** : (1) activer les 2 scénarios Make en ON, (2) error handler sur tous les modules critiques, (3) test affaire réelle, (4) identifier l'assistante DocuSign
