---
type: ressource-automation
source: build session Boris ×Claude — 12-13 mai 2026
date-build: 2026-05-12 / 2026-05-13
date-analyzed: 2026-05-13 (J12)
status: V1 — en production
participants: "Boris Arduy"
context: "automatisation génération contrats MÉTHODE BOSS pour pipeline Kelly Launch — déclenchée par passage Stage=Engagé dans Zoho CRM"
sensitivity: confidential
tags: [zoho, docusign, make, automation, contrats, kelly-launch, boss-energy, J12, aries-consulting, ops]
related: "[[Alec Henry]], [[Kelly Launch]], [[BOSS-ENERGY]], [[Mohamed]] (audit IT)"
---

# ⚙️ Automation Zoho → Make → DocuSign — Contrats MÉTHODE BOSS V1

> **Contexte** : construction le 12-13 mai 2026 d'un pipeline d'automatisation complet pour générer + envoyer automatiquement les contrats MÉTHODE BOSS (ARIES Consulting FZCO) dès qu'un Deal passe au stage **Engagé** dans Zoho CRM. Architecture pensée pour 50-200 contrats/mois sur le pipeline Kelly Launch — Agences Externes.
>
> **Pourquoi cette note** : référence technique + runbook + journal de debugging. À consulter en cas d'incident, d'évolution V2, ou pour onboarder un dev/admin sur le système.

---

## ⚡ Synthèse en 30 secondes

- 🟢 **Pipeline complet en prod** : Zoho Workflow Rule → Webhook → Make scenario (4 modules) → DocuSign API (envelope from template avec tabs pré-remplis) → routing client puis Alec/assistante → Zoho update `Statut contrat = Envoyé`
- 🟢 **0 ligne de Deluge** — tout en no-code Make + API call DocuSign brute
- 🟢 **Premier contrat de test validé** : 13 mai 2026 08h34 UTC. Envelope `c26f5ecb-25b8-886a-8242-2c9b8715ae59` envoyée, status 201, tabs 100% pré-remplis correctement
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
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
              DocuSign envoie email signataire
              Client signe (routing order 1)
              Alec/Assistante signe (routing order 2)
              Envelope completed
```

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

## ⚙️ Configuration Make — 4 modules

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

### "Volume mensuel élevé — quotas saturés"

- DocuSign : vérifier `Account → Plan & Billing` → envelope allowance/an. Plan Business Pro typique = 100-200/user/an. À 200/mois → 2400/an, plan Enterprise nécessaire
- Make : vérifier le plan → operations/mois. 1 contrat = ~4 opérations Make (webhook + get + post + update). À 200 contrats/mois = 800 ops/mois — fits easily dans plan Pro (10K ops)

---

## 🔄 Backlog V2 (à arbitrer)

### Priorité haute

- [ ] **Webhook retour DocuSign Connect** → quand client signe, update Zoho `Statut contrat = Signé` + `Date de signature`. Et quand Alec/assistante signe → `Statut contrat = Contrat complet`
- [ ] **Identifier l'assistante dédiée** et la basculer comme recipient 2 (au lieu de `sales@entrepreneurs.com` + nom Alec)
- [ ] **Error handler Make** sur module 3 et 4 → notification Slack/email à Boris si échec d'envoi
- [ ] **Activer le scénario en ON permanent** dans Make (toggle ON en bas à gauche)

### Priorité moyenne

- [ ] **Multi-produits** : quand Oscar ou autre programme arrive, le scénario actuel devient une branche. Router Make selon `Code Produit` Zoho → templateId différent
- [ ] **Bascule Fermé Gagné automatique** quand : contrat signé + 1er paiement reçu (intégration Stripe ou virement bancaire à concevoir avec compta)
- [ ] **Clarifier le tab "Alec Henry"** dans le template DocuSign — utilité actuelle inconnue
- [ ] **Champ Zoho custom "DocuSign Envelope ID"** pour stocker l'ID retourné par Module 3 (traçabilité + debug)

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
- **Durée build** : ~3h cumulées (champs Zoho + workflow + Make scénario + debug)
- **Tests réussis** : 1 envoi de test bout-en-bout validé (envelope `c26f5ecb-25b8-886a-8242-2c9b8715ae59`, 13 mai 2026 08h34 UTC)
- **À tester en prod réelle** : 2-3 affaires Kelly Launch réelles avant de considérer V1 stable
- **Next steps immédiats** : (1) activer scénario Make en ON, (2) error handler, (3) test affaire réelle, (4) identifier l'assistante
