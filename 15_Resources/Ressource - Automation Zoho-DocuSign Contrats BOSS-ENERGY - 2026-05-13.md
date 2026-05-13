---
type: ressource-automation
source: build session Boris ×Claude — 12-13 mai 2026
date-build: 2026-05-12 / 2026-05-13
date-analyzed: 2026-05-13 (J12)
status: V1.1 — en production (5 modules)
participants: "Boris Arduy"
context: "automatisation génération contrats MÉTHODE BOSS pour pipeline Kelly Launch — déclenchée par passage Stage=Engagé dans Zoho CRM. Avec log Google Sheets dans le funnel Kelly Launch."
sensitivity: confidential
tags: [zoho, docusign, make, automation, contrats, kelly-launch, boss-energy, google-sheets, J12, aries-consulting, ops]
related: "[[Alec Henry]], [[Kelly Launch]], [[BOSS-ENERGY]], [[Mohamed]] (audit IT)"
---

# ⚙️ Automation Zoho → Make → DocuSign — Contrats MÉTHODE BOSS V1.1

> **Contexte** : construction le 12-13 mai 2026 d'un pipeline d'automatisation complet pour générer + envoyer automatiquement les contrats MÉTHODE BOSS (ARIES Consulting FZCO) dès qu'un Deal passe au stage **Engagé** dans Zoho CRM. Avec log Google Sheets centralisé pour reporting + résilience hors-Zoho. Architecture pensée pour 50-200 contrats/mois sur le pipeline Kelly Launch — Agences Externes.
>
> **Pourquoi cette note** : référence technique + runbook + journal de debugging. À consulter en cas d'incident, d'évolution V2, ou pour onboarder un dev/admin sur le système.

---

## ⚡ Synthèse en 30 secondes

- 🟢 **Pipeline complet en prod** : Zoho Workflow Rule → Webhook → Make scenario (**5 modules**) → DocuSign API (envelope from template avec tabs pré-remplis) → routing client puis Alec/assistante → Zoho update `Statut contrat = Envoyé` → log Google Sheets
- 🟢 **0 ligne de Deluge** — tout en no-code Make + API call DocuSign brute
- 🟢 **Premier contrat de test validé** : 13 mai 2026 08h34 UTC. Envelope `c26f5ecb-25b8-886a-8242-2c9b8715ae59` envoyée, status 201, tabs 100% pré-remplis correctement
- 🟢 **Log Google Sheets opérationnel** : chaque contrat envoyé crée une ligne dans `Stockage Tally / Contrats envoyés` — 10 colonnes (date, IDs, signataire, format, montant). Funnel Kelly Launch complet : Feuille 1 = Tally complétés → Feuille 2 = RDV bookés → Feuille 3 = Contrats envoyés
- 🟢 **Garde-fou anti-doublon armé** : condition `Statut contrat ≠ Envoyé` dans la règle Zoho
- 🟡 **Volume cible** : 50-200 contrats/mois — surveiller les quotas DocuSign (envelopes/an) et Make (operations/mois)
- 🟡 **À faire avant prod 100%** : activer le scénario en ON permanent, configurer error handler Make, valider sur 2-3 affaires réelles
- 🔴 **Tab "Alec Henry"** dans template DocuSign mis de côté volontairement — utilité non documentée, à clarifier si problème de rendu contrat
- 🔴 **Recipient 2 = Alec Henry mais email = sales@entrepreneurs.com** : à transitionner vers l'assistante dédiée dès qu'identifiée

---

## 🏗️ Architecture en un coup d'œil

```
┌─────────────────────────────────────────────────────────────┐
│  ZOHO CRM                                                   │
│  Affaire passe Stage = "Engagé"                             │
│  Workflow Rule "Trigger DocuSign — Affaire Engagée"         │
│  Condition : Statut contrat ≠ "Envoyé"                      │
│  Action  : Webhook POST → Make                              │
└────────────────────────┬────────────────────────────────────┘
                         │ payload JSON {deal_id, stage, deal_name}
                         ▼
┌─────────────────────────────────────────────────────────────┐
│  MAKE — Scénario "Zoho → DocuSign — Contrats BOSS-ENERGY"   │
│                                                             │
│  [1] Webhooks — Custom webhook                              │
│      URL : https://hook.eu2.make.com/pyov1anmew3y...        │
│                                                             │
│  [2] Zoho CRM — Get an Object                               │
│      Module = Deals, ID = {{1.deal_id}}                     │
│      → récupère toute la fiche (50+ champs)                 │
│                                                             │
│  [3] DocuSign — Make an API Call                            │
│      POST /v2.1/accounts/{accountId}/envelopes              │
│      → crée envelope + tabs pré-remplis + status=sent       │
│                                                             │
│  [4] Zoho CRM — Make an API Call                            │
│      PUT /v2/Deals/{{2.id}}                                 │
│      → met Statut contrat = "Envoyé"                        │
│                                                             │
│  [5] Google Sheets — Add a Row                              │
│      Spreadsheet = Stockage Tally / Contrats envoyés        │
│      → log 10 colonnes par contrat envoyé                   │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
              DocuSign envoie email signataire
              Client signe (routing order 1)
              Alec/Assistante signe (routing order 2)
              Envelope completed
```

**Ordre des modules volontaire** : le log Sheets vient **après** le succès DocuSign + update Zoho. Si DocuSign échoue (module 3), pas de log → on évite les fausses lignes pour des contrats qui ne sont jamais partis.

---

## 🔑 IDs critiques (à ne pas perdre)

| Élément | Valeur |
|---|---|
| **Make webhook URL** | `https://hook.eu2.make.com/pyov1anmew3yzsodlwrs4fboqw7lofx1` |
| **DocuSign API Account ID** | `c2e38f7c-edb4-435e-87f7-7ac6615901aa` |
| **DocuSign Template ID (Contrat MÉTHODE BOSS)** | `6717eab6-540a-489b-9cc8-fbb32f2235fe` |
| **DocuSign Base URI** | `https://eu.docusign.net` (instance EU) |
| **DocuSign Connection name (Make)** | `Sales Docusign (sales@entrepreneurs.com)` |
| **Zoho Connection name (Make)** | `Zoho CRM` |
| **Zoho instance** | `zoho.eu` |
| **Module Zoho** | `Affaires` (Deals) |
| **Google Sheets spreadsheet** | `0.01 Projets / 4. Lancement Kelly / Stockage Tally` |
| **Google Sheets onglet log contrats** | `Contrats envoyés` (Feuille 3) |
| **Google Sheets connection (Make)** | `Boris (boris@entrepreneurs.com)` |

⚠️ **Toutes ces valeurs sont à protéger** — leur compromission permettrait à un tiers d'envoyer des contrats au nom d'ARIES. Si exposition suspectée, révoquer l'API key DocuSign + régénérer le webhook Make.

---

## 🛠️ Configuration Zoho CRM

### Workflow Rule

**Chemin** : `Setup → Automatisation → Règles de workflow → "Trigger DocuSign — Affaire Engagée"`

| Paramètre | Valeur |
|---|---|
| Module | Affaires |
| Quand | Action d'enregistrement → **Édition** → champ spécifique = `Stage` modifié vers `Engagé` |
| Répéter si modifié | **Non coché** (déclenchement unique) |
| Condition | `Statut contrat` n'est pas égal à `Envoyé` |
| Actions instantanées | Webhook → `Send to Make for DocuSign` |

### Webhook config (côté Zoho)

| Paramètre | Valeur |
|---|---|
| Nom | `Send to Make for DocuSign` |
| Méthode | `POSTER` (POST) |
| URL à notifier | URL Make (voir tableau IDs critiques) |
| Type d'autorisation | Général |
| Corps Type | **Brut** + Format **JSON** |
| Corps content | Voir bloc ci-dessous |

**Body JSON envoyé par Zoho** (à coller dans le champ Corps brut) :

```json
{
  "deal_id": "${Affaires.ID Affaire}",
  "stage": "${Affaires.Stage}",
  "deal_name": "${Affaires.Nom de l'Affaire}"
}
```

⚠️ Les `${...}` sont des champs de fusion Zoho qui s'insèrent via la touche `#` dans l'éditeur, **pas du texte tapé manuellement**.

---

## ⚙️ Configuration Make — 5 modules

### Module 1 — Webhooks > Custom webhook

| Champ | Valeur |
|---|---|
| Webhook name | `Zoho Deal Engagé` |
| Connection | (vide, public) |
| Output attendu | `{deal_id, stage, deal_name}` |

### Module 2 — Zoho CRM > Get an Object

| Champ | Valeur |
|---|---|
| Connection | `Zoho CRM` (OAuth, autorisé via super-admin) |
| Module | `Deals` (Affaires) |
| Object ID | `{{1.deal_id}}` (pilule mappée depuis Module 1) |

**Output utile** : tous les champs custom de l'Affaire (~50 champs dont les 16 du contrat).

### Module 3 — DocuSign > Make an API Call

| Champ | Valeur |
|---|---|
| Connection | `Sales Docusign (sales@entrepreneurs.com)` |
| Account | `Alec Henry` (account sélectionné via OAuth) |
| URL | `/v2.1/accounts/{accountId}/envelopes` |
| Method | `POST` |
| Headers | `Content-Type: application/json` |
| Body | Voir bloc JSON ci-dessous |

⚠️ **NE PAS** mettre `/restapi` au début de l'URL ni l'Account ID en dur — Make remplace `{accountId}` automatiquement et préfixe `/restapi` lui-même. L'URL relative correcte est `/v2.1/accounts/{accountId}/envelopes`.

**Body JSON complet** (référence de production) :

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

⚠️ Les `{{2.xxx}}` sont des **pilules Make** mappées depuis Module 2, pas du texte brut. Sinon Make envoie la chaîne littérale à DocuSign.

### Module 4 — Zoho CRM > Make an API Call

| Champ | Valeur |
|---|---|
| Connection | `Zoho CRM` |
| URL | `/v2/Deals/{{2.Object ID}}` |
| Method | `PUT` |
| Body type | Raw → JSON |
| Body | Voir bloc ci-dessous |

⚠️ **NE PAS** mettre `/crm` au début (Make le préfixe déjà) — sinon `/crm/crm/v2/...` = 400 Invalid URL.

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

**Pourquoi ce module** : créer une source de vérité hors-Zoho. Source unique pour le reporting funnel Kelly Launch (taux de conversion Tally → RDV → Contrat), audit, résilience si Zoho casse.

| Champ | Valeur |
|---|---|
| Connection | `Boris (boris@entrepreneurs.com)` (même que Tally → Sheets) |
| Drive | `My Drive` |
| Spreadsheet | `0.01 Projets / 4. Lancement Kelly / Stockage Tally` |
| Sheet | **`Contrats envoyés`** (Feuille 3 — ne pas confondre avec Feuille 1 = Tally complétés ou Feuille 2 = RDV bookés) |
| Table contains headers | `Yes` |
| Use column headers as IDs | `Yes` ⚠️ critique — verrouille le mapping sur les noms de colonnes, pas leur position |

**Mapping des 10 colonnes** :

| Colonne Sheet | Source Make |
|---|---|
| Date envoi | `{{now}}` (timestamp Make) |
| Deal ID | `{{2.Object ID}}` |
| Nom Affaire | `{{2.Nom de l'Affaire}}` |
| Société | `{{2.Nom de l'entreprise}}` |
| Email signataire | `{{2.Email du signataire}}` |
| Nom signataire | `{{2.Nom du signataire}}` |
| Format | `{{2.Format}}` |
| Modalités | `{{2.Modalites paiement}}` |
| Montant HT | `{{2.Montant Total HT}}` |
| DocuSign Envelope ID | `{{3.envelopeId}}` |

**Funnel Kelly Launch dans le même fichier Sheets** :
- Feuille 1 = Tally complétés (qualif)
- Feuille 2 = RDV bookés (closing en cours)
- **Feuille 3 = Contrats envoyés (closing fait)** ← ce module

Permet de mesurer les taux de conversion étape par étape directement dans Sheets, sans dépendance Zoho.

---

## 📋 Mapping complet Zoho ↔ DocuSign

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

**Tabs DocuSign non mappés (volontaire)** : `Alec Henry` — utilité non clarifiée pendant la session, à revoir si nécessaire.

---

## 🐛 Pièges rencontrés & solutions (debugging journal)

> Conservé pour gain de temps si refactoring ou réplication sur autre produit.

| # | Symptôme | Cause | Solution |
|---|---|---|---|
| 1 | Webhook Make output vide (`Bundle 1 empty`) | Zoho envoyait les paramètres en URL query (`?deal_id=...`), pas dans le body | Passer **Corps Type** de `Aucune` à `Brut` + Format `JSON` + écrire le JSON à la main avec champs de fusion `#` |
| 2 | `BundleValidationError: Missing value of required parameter 'id'` | Module Get an Object recevait `deal_id` vide à cause du #1 | Idem #1 — fix amont |
| 3 | Module `Send Envelope from Template` n'expose pas de section Tabs | Limitation du module Make for DocuSign | Remplacer par `Make an API Call` brut sur `/v2.1/accounts/{accountId}/envelopes` |
| 4 | `BundleValidationError: Array of objects expected in parameter 'templateRoles'` | Mode Map JSON Make n'accepte pas tous les payloads | Passer en `Make an API Call` brut |
| 5 | DocuSign 404 sur URL `/restapi/v2.1/accounts/...` | Make préfixe déjà `/restapi` — doublon | URL doit être `/v2.1/accounts/{accountId}/envelopes` (sans `/restapi`, avec `{accountId}` littéral) |
| 6 | DocuSign 400 avec GET sur `/envelopes` | Endpoint liste les envelopes, demande filtres date/id obligatoires | Normal — la requête de **création** est en POST, pas GET. Le GET de test sans filtre échoue mais ne signale pas une mauvaise URL |
| 7 | Zoho 400 `Invalid URL /crm/crm/v2/Deals/...` | URL Make doublonnée par préfixe automatique | URL doit être `/v2/Deals/{{2.Object ID}}` (sans `/crm`) |
| 8 | Champs custom non visibles dans le module Zoho `Update an Object` | Layout par défaut du module n'expose pas les champs custom | Contourné via `Make an API Call` brut côté Zoho aussi (cohérent avec côté DocuSign) |
| 9 | Google Sheets module n'écrit nulle part / ne trouve pas le sheet | Renommage de l'onglet sans rafraîchir le module Make | Toujours **rafraîchir** la liste des sheets dans Make après un renommage, ou utiliser `Use column headers as IDs = Yes` pour minimiser l'impact |

---

## 📖 Runbook opérationnel

### "Un contrat ne part pas après passage en Engagé"

1. Aller sur l'Affaire Zoho → vérifier que `Statut contrat ≠ Envoyé` (sinon garde-fou actif, c'est normal)
2. Vérifier `Setup → Notifications → Webhooks → Journal` dans Zoho → status du dernier appel ?
3. Si erreur côté Make : ouvrir Make → onglet History du scénario → cliquer sur la dernière exécution → identifier le module en rouge
4. Vérifier que tous les **16 champs requis** sont remplis sur l'Affaire (cf. [[Checklist Closer Kelly Launch V1]])
5. Si erreur DocuSign : message verbeux dans Make → souvent un `tabLabel` qui ne match plus le template (renommage), ou template supprimé

### "Le contrat est envoyé mais des champs sont vides"

- Cause #1 : un `tabLabel` dans le JSON ne match plus celui du template DocuSign (sensible à la casse + accents + espaces)
- Cause #2 : le champ Zoho est vide sur l'Affaire (cf. checklist closer)
- Fix : ouvrir le template DocuSign → onglet Recipients → cliquer sur chaque tab → vérifier le label exact → corriger dans le body JSON Module 3 Make

### "Erreur d'authentification DocuSign"

- Connexion OAuth expirée → reconnecter via Make → module 3 → Connection → Edit → Reauthorize
- Si le compte `sales@entrepreneurs.com` change de mdp ou que l'assistante prend la main : créer une nouvelle connexion Make dédiée

### "Le scénario tourne en boucle et envoie 10 contrats"

- Vérifier que **Module 4** (update Statut contrat = Envoyé) fonctionne bien → c'est le garde-fou anti-doublon
- Vérifier que la condition Zoho `Statut contrat ≠ Envoyé` est bien sur la Workflow Rule
- Désactiver le scénario Make en urgence (interrupteur ON/OFF en bas à gauche)

### "La ligne n'apparaît pas dans le sheet Contrats envoyés"

- Cause #1 : onglet `Contrats envoyés` renommé sans rafraîchir le module Make → ouvrir Module 5, cliquer Refresh sur la liste des sheets, ré-sélectionner le bon onglet
- Cause #2 : Module 3 (DocuSign) ou Module 4 (Zoho update) en erreur → le scénario s'arrête avant le module 5. Aller voir History Make
- Cause #3 : Connection Google Sheets `Boris (boris@entrepreneurs.com)` expirée → reconnect via Make
- Cause #4 : les colonnes du sheet ne matchent plus les en-têtes attendus → vérifier l'ordre + le libellé exact dans la ligne 1 du sheet

### "Volume mensuel élevé — quotas saturés"

- DocuSign : vérifier `Account → Plan & Billing` → envelope allowance/an. Plan Business Pro typique = 100-200/user/an. À 200/mois → 2400/an, plan Enterprise nécessaire
- Make : vérifier le plan → operations/mois. 1 contrat = **5 opérations Make** (webhook + get + post DocuSign + put Zoho + add row sheets). À 200 contrats/mois = 1000 ops/mois — fits easily dans plan Pro (10K ops)

---

## 🔄 Backlog V2 (à arbitrer)

### Priorité haute

- [ ] **Webhook retour DocuSign Connect** → quand client signe, update Zoho `Statut contrat = Signé` + `Date de signature`. Et quand Alec/assistante signe → `Statut contrat = Contrat complet`. Idéalement update aussi la ligne correspondante dans le sheet `Contrats envoyés` (matcher sur DocuSign Envelope ID)
- [ ] **Identifier l'assistante dédiée** et la basculer comme recipient 2 (au lieu de `sales@entrepreneurs.com` + nom Alec)
- [ ] **Error handler Make** sur module 3, 4 et 5 → notification Slack/email à Boris si échec d'envoi
- [ ] **Activer le scénario en ON permanent** dans Make (toggle ON en bas à gauche)

### Priorité moyenne

- [ ] **Multi-produits** : quand Oscar ou autre programme arrive, le scénario actuel devient une branche. Router Make selon `Code Produit` Zoho → templateId différent
- [ ] **Bascule Fermé Gagné automatique** quand : contrat signé + 1er paiement reçu (intégration Stripe ou virement bancaire à concevoir avec compta)
- [ ] **Clarifier le tab "Alec Henry"** dans le template DocuSign — utilité actuelle inconnue
- [ ] **Champ Zoho custom "DocuSign Envelope ID"** pour stocker l'ID retourné par Module 3 (traçabilité + debug). Permet de retrouver une ligne sheet depuis une fiche Zoho et vice-versa
- [ ] **Dashboard funnel Kelly Launch** dans Sheets : formules de conversion entre Feuille 1 (Tally) → Feuille 2 (RDV) → Feuille 3 (Contrats). Sparkline hebdo, taux de closing

### Priorité basse

- [ ] **Documentation video** : Loom 5 min qui montre comment refaire le scénario from scratch si tout casse
- [ ] **Tests automatisés** : monter un scénario Make miroir en sandbox pour valider les évolutions avant prod
- [ ] **Migration vers JWT Auth DocuSign** si volume scale au-delà de 500/mois — plus robuste que OAuth user
- [ ] **Reporting hebdomadaire** Make → Google Sheet ou Notion avec nombre de contrats envoyés/signés/en attente

---

## 🔗 Liens & ressources connexes

- [[Checklist Closer Kelly Launch V1]] — checklist PDF 1 page que les closers doivent valider avant passage en Engagé (16 champs à remplir)
- [[BOSS-ENERGY]] — fiche produit MÉTHODE BOSS (15 SKU, grille de prix Solo/Duo/Trio × x1-x6)
- [[Kelly Launch]] — pipeline commercial cible de l'automation
- [[Alec Henry]] — CEO ARIES Consulting FZCO, signataire ARIES sur les contrats
- [[Mohamed]] — audit IT en cours, contexte gouvernance SaaS plus large
- [[Ressource - Replay Mohamed × Boris 5 mai 2026 (audit IT)]] — contexte cybersecurity et SaaS de la boîte

---

## 📝 Méta

- **Construction** : session Boris × Claude, 12 mai 2026 (soir) + 13 mai 2026 (matin)
- **Durée build** : ~3h30 cumulées (champs Zoho + workflow + Make scénario 5 modules + debug + log Sheets)
- **Versions** :
  - V1 (13 mai 2026 09h) — 4 modules Make, premier envoi DocuSign validé
  - **V1.1 (13 mai 2026 11h) — ajout module 5 Google Sheets, log centralisé funnel Kelly**
- **Tests réussis** :
  - 13 mai 08h34 UTC — envelope `c26f5ecb-25b8-886a-8242-2c9b8715ae59` envoyée et reçue (status 201, tabs OK)
  - 13 mai 09h12 UTC — ligne sheet `Contrats envoyés` créée correctement avec les 10 colonnes
- **À tester en prod réelle** : 2-3 affaires Kelly Launch réelles avant de considérer V1.1 stable
- **Next steps immédiats** : (1) activer scénario Make en ON, (2) error handler sur module 3/4/5, (3) test affaire réelle, (4) identifier l'assistante
