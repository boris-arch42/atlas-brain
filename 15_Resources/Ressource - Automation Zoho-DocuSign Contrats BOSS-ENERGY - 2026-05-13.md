---
type: ressource-automation
source: build session Boris ×Claude — 12-13 mai 2026
date-build: 2026-05-12 / 2026-05-13
date-analyzed: 2026-05-13 (J12)
status: V1.3 — en production (2 scénarios Make + dashboard live Vercel)
participants: "Boris Arduy"
context: "automatisation complète Kelly Launch — Agences Externes : génération contrats DocuSign sur Engagé, log ventes fermées, funnel Sheets 4 onglets, dashboard React Vercel avec auth + token. Architecture pensée pour 50-200 contrats/mois."
sensitivity: confidential
tags: [zoho, docusign, make, automation, contrats, kelly-launch, boss-energy, google-sheets, funnel, ventes, dashboard, vercel, apps-script, J12, aries-consulting, ops]
related: "[[Alec Henry]], [[Kelly Launch]], [[BOSS-ENERGY]], [[Mohamed]] (audit IT)"
---

# ⚙️ Automation Zoho ↔ Make ↔ DocuSign / Sheets / Dashboard — Funnel Kelly Launch V1.3

> **Contexte** : construction le 12-13 mai 2026 de l'infrastructure complète Kelly Launch :
> 1. **Scénario 1** : génération + envoi automatique des contrats MÉTHODE BOSS quand un Deal passe à `Engagé`
> 2. **Scénario 2** : log des ventes finalisées quand un Deal passe à `Fermé Gagné`
> 3. **Funnel Google Sheets centralisé** à 4 étapes (Tally → Bookings → Contrats → Ventes)
> 4. **Dashboard analytics React** déployé sur Vercel avec auth + token, data via Apps Script
>
> Architecture pensée pour 50-200 contrats/mois.
>
> **Pourquoi cette note** : référence technique + runbook + journal de debugging. À consulter en cas d'incident, d'évolution V2, ou pour onboarder un dev/admin.

---

## ⚡ Synthèse en 30 secondes

- 🟢 **Funnel Kelly Launch complet en prod** : Tally → Bookings → Contrats envoyés → Ventes fermées (4 onglets Sheets dans `Stockage Tally`)
- 🟢 **Scénario 1 — Contrats (5 modules)** : Zoho `Engagé` → Webhook → Get Deal → DocuSign API (envelope from template + tabs pré-remplis + routing client/Alec) → update Zoho `Statut contrat = Envoyé` → log Sheets `Contrats envoyés`
- 🟢 **Scénario 2 — Ventes fermées (3 modules)** : Zoho `Fermé Gagné` → Webhook → Get Deal → log Sheets `Ventes fermées`
- 🟢 **Dashboard React live** : `https://kelly-dashboard-sigma.vercel.app` — funnel viz, KPI cards, time series 30 jours, breakdowns Format/Agence, tableau détail CA — auto-refresh 60s — fond blanc + accents noir/rouge Entrepreneurs.com
- 🟢 **3 couches de sécurité dashboard** : Vercel Authentication (Standard Protection) + URL Apps Script secrète + token de vérification
- 🟢 **0 ligne de Deluge** — tout no-code Make + API calls bruts + Apps Script web app
- 🟢 **Tests bout-en-bout validés 13 mai** : envelope DocuSign (08h34), ligne `Contrats envoyés` (09h12), ligne `Ventes fermées` (09h33), dashboard live (13h)
- 🟢 **Garde-fou anti-doublon scénario 1** : condition `Statut contrat ≠ Envoyé`
- 🟡 **Pas de garde-fou anti-doublon scénario 2** — passage en Fermé Gagné rare, doublon dans le sheet non-critique
- 🟡 **`Date 1er paiement` en saisie manuelle** dans le sheet Feuille 4 par compta/admin
- 🔴 **Tab "Alec Henry"** dans template DocuSign mis de côté volontairement
- 🔴 **Recipient 2 DocuSign = `sales@entrepreneurs.com` au nom d'Alec** : à transitionner vers assistante dédiée

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
                         │ payload {deal_id, stage, deal_name}
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
│  Action : Webhook POST → Make                               │
└────────────────────────┬────────────────────────────────────┘
                         │ payload {deal_id, stage, deal_name}
                         ▼
┌─────────────────────────────────────────────────────────────┐
│  MAKE — "Zoho → Sheets — Ventes fermées" (3 modules)        │
│                                                             │
│  [1] Webhooks Custom                                        │
│  [2] Zoho Get an Object                                     │
│  [3] Google Sheets Add a Row — log Feuille 4                │
└─────────────────────────────────────────────────────────────┘
```

### Dashboard live

```
┌─────────────────────────────────────────────────────────────┐
│  GOOGLE SHEETS "Stockage Tally" (4 onglets)                 │
│  privé — accès via Apps Script uniquement                   │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│  APPS SCRIPT "Kelly Launch API"                             │
│  - Web App, accès "Toute personne"                          │
│  - Exécuté en tant que Boris (accède au sheet privé)        │
│  - Vérification token avant chaque requête                  │
│  - Retourne JSON des 4 onglets                              │
└────────────────────────┬────────────────────────────────────┘
                         │ HTTPS GET ?token=KL-7f9a2c...
                         ▼
┌─────────────────────────────────────────────────────────────┐
│  DASHBOARD REACT (Vite)                                     │
│  - Hébergé sur Vercel (kelly-dashboard-sigma.vercel.app)    │
│  - GitHub repo privé boris961/kelly-dashboard               │
│  - fetch + credentials: 'omit' (évite cookies Google)       │
│  - Auto-refresh 60s + bouton manuel                         │
│  - Vercel Authentication (Standard Protection) active       │
└─────────────────────────────────────────────────────────────┘
```

**Ordre des modules volontaire (scénario 1)** : log Sheets vient **après** DocuSign + Zoho. Si DocuSign échoue, pas de log → pas de fausses lignes.

**Pourquoi 2 scénarios Make séparés et pas 1 avec Router** : déclencheurs métier distincts, troubleshooting indépendant. Si un scénario casse, l'autre continue.

**Pourquoi 3 couches de sécurité dashboard** : Vercel Auth empêche l'accès sauvage à l'URL Vercel · URL Apps Script secrète (100+ caractères random) · Token de vérification empêche quelqu'un qui aurait deviné l'URL d'y accéder direct.

---

## 📊 Funnel Kelly Launch dans Google Sheets

Fichier `0.01 Projets / 4. Lancement Kelly / Stockage Tally` — 4 onglets :

| Étape | Onglet Sheets | Source |
|---|---|---|
| **1. Qualif inbound** | `Tally` | Tally form responses (scénario pré-existant) |
| **2. Closing call planifié** | `Bookings` | iClosed (scénario pré-existant) |
| **3. Contrat envoyé** | `Contrats envoyés` | Make scénario 1, module 5 |
| **4. Vente fermée** | `Ventes fermées` | Make scénario 2, module 3 |

→ Source unique pour mesurer les taux de conversion étape-par-étape, sans dépendance Zoho.

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

### Dashboard

| Élément | Valeur |
|---|---|
| **URL Dashboard live** | `https://kelly-dashboard-sigma.vercel.app` |
| **GitHub repo** | `https://github.com/boris961/kelly-dashboard` (privé) |
| **Apps Script web app URL** | `https://script.google.com/macros/s/AKfycbzMugJCbnzeOBGL0gjCKWYuAWiwXaTsO58-PYl1vgbDkfszMBYd_uW9vO-4IIfVItK7yw/exec` |
| **Token d'auth Apps Script** | `KL-7f9a2c4e8b6d1f3a-2026` ⚠️ secret partagé |
| **Vercel project** | `boris961's projects / kelly-dashboard` (Hobby plan, gratuit) |
| **Vercel Authentication** | Active — Standard Protection (Require Log In) |

### Communs

| Élément | Valeur |
|---|---|
| **Zoho Connection name (Make)** | `Zoho CRM` |
| **Zoho instance** | `zoho.eu` |
| **Module Zoho** | `Affaires` (Deals) |
| **Google Sheets spreadsheet** | `Stockage Tally` (`1XTVJvuabrKtScKaLNFl9bBo3n-75Gz7O2C3WyU0H0aI`) |
| **Onglets Sheets** | `Tally · Bookings · Contrats envoyés · Ventes fermées` |
| **Google Sheets connection (Make)** | `Boris (boris@entrepreneurs.com)` |

⚠️ **Toutes ces valeurs sont sensibles** — leur compromission permettrait à un tiers d'envoyer des contrats au nom d'ARIES, lire les data du funnel, ou polluer le sheet. Si exposition suspectée :
- Révoquer l'API key DocuSign + régénérer les webhooks Make
- Régénérer le token Apps Script (changer la constante `SECRET_TOKEN` dans le code Apps Script + dans `App.jsx` du dashboard + push)
- Régénérer un nouveau déploiement Apps Script (génère une nouvelle URL `/exec`)

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

```json
{
  "deal_id": "${Affaires.ID Affaire}",
  "stage": "${Affaires.Stage}",
  "deal_name": "${Affaires.Nom de l'Affaire}"
}
```

⚠️ **À INSÉRER via la touche `#`** dans l'éditeur Zoho, pas en copier-coller texte brut — sinon Zoho refuse "Nom de l'Affaire" à cause de l'apostrophe (cf. piège #10).

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

⚠️ Pas de `/restapi` au début (Make l'ajoute), Account ID à laisser littéral `{accountId}`.

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

⚠️ Pas de `/crm` au début.

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

**Mapping des 10 colonnes** : Date envoi (`{{now}}`) · Deal ID · Nom Affaire · Société · Email signataire · Nom signataire · Format · Modalités · Montant HT · DocuSign Envelope ID (`{{3.envelopeId}}`)

---

## ⚙️ Configuration Make — Scénario 2 (3 modules)

### Module 1 — Webhooks > Custom webhook

Webhook name : `Zoho Deal Fermé Gagné`

### Module 2 — Zoho CRM > Get an Object

Identique scénario 1 (réutilise la même connection).

### Module 3 — Google Sheets > Add a Row

| Champ | Valeur |
|---|---|
| Sheet | **`Ventes fermées`** (Feuille 4) |
| Use column headers as IDs | **Yes** |

**Mapping des 13 colonnes** : Date closing (`{{now}}`) · Deal ID · Nom Affaire · Société · Email signataire · Nom signataire · Format · Modalités · Montant HT · Mensualités · Source / Agence · **Date 1er paiement** (non mappé — saisie manuelle compta) · Closer (`{{2.Gestionnaire de l'Affaire.name}}` avec `.name`)

---

## 🎨 Dashboard React — Configuration complète

### Stack technique

- **Framework** : Vite + React 18
- **Charts** : recharts
- **Icons** : lucide-react
- **Hébergement** : Vercel (plan Hobby gratuit, build auto sur push GitHub)
- **Source** : GitHub repo privé `boris961/kelly-dashboard`
- **Theme** : fond blanc, accents noir/rouge Entrepreneurs.com (`#C8102E`)

### Apps Script (proxy data)

**Fichier dans Apps Script Editor** :

```javascript
// ⚠️ TOKEN SECRET — doit matcher celui du dashboard
const SECRET_TOKEN = "KL-7f9a2c4e8b6d1f3a-2026";

function doGet(e) {
  // Vérification du token
  const providedToken = e && e.parameter && e.parameter.token;
  if (providedToken !== SECRET_TOKEN) {
    return ContentService
      .createTextOutput(JSON.stringify({ error: "Unauthorized" }))
      .setMimeType(ContentService.MimeType.JSON);
  }

  const ss = SpreadsheetApp.getActiveSpreadsheet();
  const sheetNames = ['Tally', 'Bookings', 'Contrats envoyés', 'Ventes fermées'];
  const result = {};

  sheetNames.forEach(name => {
    const sheet = ss.getSheetByName(name);
    if (!sheet) {
      result[name] = { error: 'Sheet not found: ' + name };
      return;
    }
    const data = sheet.getDataRange().getValues();
    if (data.length <= 1) {
      result[name] = [];
      return;
    }
    const headers = data[0];
    result[name] = data.slice(1).map(row => {
      const obj = {};
      headers.forEach((h, i) => { obj[h] = row[i]; });
      return obj;
    });
  });

  return ContentService
    .createTextOutput(JSON.stringify(result))
    .setMimeType(ContentService.MimeType.JSON);
}
```

**Réglages de déploiement obligatoires** :
- Type : Application Web
- Exécuter en tant que : `Moi (boris@entrepreneurs.com)`
- **Qui a accès : `Toute personne`** ⚠️ (PAS "avec un compte Google", PAS "domaine entrepreneurs.com")

### Dashboard React — pattern fetch critique

```javascript
const fetchAllData = async () => {
  const url = `${APPS_SCRIPT_URL}?token=KL-7f9a2c4e8b6d1f3a-2026`;
  const res = await fetch(url, {
    method: 'GET',
    credentials: 'omit',  // ⚠️ critique — évite que cookies Google parasitent la requête
    redirect: 'follow',
  });
  if (!res.ok) throw new Error(`HTTP ${res.status}`);
  const data = await res.json();
  if (data.error) throw new Error(data.error);
  return data;
};
```

⚠️ **`credentials: 'omit'` est CRITIQUE** : sans ça, le navigateur envoie les cookies Google de l'utilisateur, Apps Script tente d'auth ce user, renvoie une page HTML de login au lieu du JSON → dashboard cassé pour tout user loggé Google.

### Sécurisation Vercel

- Vercel project → Settings → Deployment Protection → **Vercel Authentication** → toggle ON → **Standard Protection**
- Seuls les membres du projet Vercel peuvent accéder à l'URL
- Pour ajouter Alec / équipe : Project Members → Invite par email (rôle Member, read-only)

### Setup local pour modifications futures

```bash
cd ~/Documents/kelly-dashboard
npm run dev              # local sur localhost:5173
# ... modifie src/App.jsx ...
git add .
git commit -m "Description"
git push                 # Vercel redéploie auto en 1-2 min
```

---

## 🐛 Pièges rencontrés & solutions (debugging journal)

> Conservé pour gain de temps si refactoring, réplication ou onboarding.

| # | Symptôme | Cause | Solution |
|---|---|---|---|
| 1 | Webhook Make output vide | Zoho envoyait params en URL query | Corps Type `Brut` + Format `JSON` + champs via `#` |
| 2 | `BundleValidationError: Missing 'id'` | Module Get an Object recevait `deal_id` vide | Fix amont #1 |
| 3 | Module DocuSign Send Envelope n'expose pas Tabs | Limitation du module Make | Utiliser `Make an API Call` brut |
| 4 | `BundleValidationError: templateRoles` | Mode Map JSON Make n'accepte pas tous les payloads | `Make an API Call` brut |
| 5 | DocuSign 404 sur `/restapi/v2.1/...` | Make préfixe déjà `/restapi` | URL = `/v2.1/accounts/{accountId}/envelopes` |
| 6 | DocuSign 400 GET sur `/envelopes` | Endpoint demande filtres date/id obligatoires | Normal — la création est en POST |
| 7 | Zoho 400 `/crm/crm/v2/Deals/...` | URL doublonnée | URL = `/v2/Deals/{{2.Object ID}}` (sans `/crm`) |
| 8 | Champs custom invisibles Update Object Zoho | Layout par défaut | Contourné via `Make an API Call` brut |
| 9 | Sheets module n'écrit nulle part | Renommage onglet sans rafraîchir Make | Refresh la liste des sheets ou `Use column headers as IDs = Yes` |
| 10 | Zoho refuse `${Affaires.Nom de l'Affaire}` en texte brut | Apostrophe casse le parsing | **Toujours insérer via touche `#`**, jamais en copier-coller |
| 11 | Workflow Rule scénario 2 ne déclenche pas | Libellé Stage choisi ≠ libellé exact du pipeline | Vérifier dropdown — `Fermé Gagné` exactement |
| 12 | Dashboard "Failed to fetch" en gviz endpoint | CORS bloqué dans claude.ai sandbox | Apps Script web app comme proxy |
| 13 | Apps Script URL avec `/u/3/` ne marche que pour le compte associé | Google insère auto le code du compte loggé | Utiliser **URL canonique sans `/u/X/`** |
| 14 | "Désolé, le fichier que vous avez demandé n'existe pas" | Modifier un déploiement ≠ Nouvelle version pour appliquer les changements | Toujours sélectionner **"Nouvelle version"** dans le dropdown Version lors d'une modif. Si bug persiste, archiver + créer un déploiement neuf |
| 15 | Apps Script en restriction `domaine entrepreneurs.com` | Incompatible avec fetch côté client | Passer en **"Toute personne"** + auth via token URL |
| 16 | Dashboard marche en privé mais data à 0 quand loggé Google | Cookies Google envoyés avec JSONP → Apps Script tente d'auth → renvoie HTML login | **`credentials: 'omit'`** dans fetch standard (pas JSONP) |

---

## 📖 Runbook opérationnel

### Scénario 1 (contrats)

**"Un contrat ne part pas après passage en Engagé"**
1. Vérifier sur l'Affaire que `Statut contrat ≠ Envoyé` (sinon garde-fou actif)
2. `Setup → Notifications → Webhooks → Journal` dans Zoho → status du dernier appel
3. Make → History scénario 1 → identifier module en rouge
4. Vérifier les **16 champs requis** sur l'Affaire (cf. [[Checklist Closer Kelly Launch V1]])

**"Le scénario tourne en boucle"**
- Vérifier que Module 4 (update Statut contrat) fonctionne
- Désactiver le scénario Make en urgence (toggle bas-gauche)

### Scénario 2 (ventes)

**"Le webhook ne se déclenche pas en Fermé Gagné"**
- Vérifier libellé exact du Stage dans la Workflow Rule
- Vérifier `Setup → Notifications → Webhooks → Journal`

### Dashboard

**"Dashboard affiche toutes les data à 0"**
1. Tester URL Apps Script en navigation privée : `[URL]/exec?token=KL-7f9a2c4e8b6d1f3a-2026`
   - Si renvoie JSON ✅ → souci côté React, vérifier `fetch` + `credentials: 'omit'`
   - Si renvoie "Unauthorized" → token mismatch entre Apps Script et `App.jsx`
   - Si renvoie page de login Google → déploiement Apps Script revenu en restriction domaine, repasser sur "Toute personne"
   - Si renvoie "Désolé le fichier n'existe pas" → URL Apps Script périmée (ancienne version archivée), récupérer la nouvelle URL `/exec` du déploiement actif
2. Si Apps Script OK mais Vercel pas à jour → vérifier `git status` local, push si modifs locales en attente

**"Modifier le dashboard (ajouter une colonne, etc.)"**
```bash
cd ~/Documents/kelly-dashboard
npm run dev                            # test en local
# modifie src/App.jsx
git add . && git commit -m "..."
git push                               # Vercel redéploie auto
```

**"Régénérer le token Apps Script"** (en cas de compromission)
1. Apps Script Editor → modifier la constante `SECRET_TOKEN` avec une nouvelle valeur
2. Déployer → Nouvelle version
3. `App.jsx` local → modifier la valeur du token dans `fetchAllData`
4. Git push
5. Vercel redéploie auto

### Communs

**"Erreur OAuth DocuSign / Zoho / Google Sheets"**
- Connection expirée → Make → module concerné → Connection → Edit → Reauthorize

---

## 🔄 Backlog V2 (à arbitrer)

### Priorité haute — avant Marrakech (20-25 mai)

- [ ] **Webhook retour DocuSign Connect** → quand client signe, update Zoho `Statut contrat = Signé` + `Date de signature` + mise à jour ligne `Contrats envoyés` (matcher sur Envelope ID)
- [ ] **Identifier l'assistante dédiée** + basculer comme recipient 2 (au lieu de `sales@entrepreneurs.com` au nom d'Alec)
- [ ] **Activer les 2 scénarios Make en ON permanent**
- [ ] **Error handler Make** sur les 2 scénarios → notif Slack/email à Boris si échec
- [ ] **Diffusion checklist closer PDF V2** à Kelly + équipe (message Slack #kelly-launch déjà rédigé)
- [ ] **Tournage Loom 13min onboarding closers** (script déjà livré)
- [ ] **Test 2-3 affaires Kelly Launch réelles** avant de considérer V1.3 stable
- [ ] **Inviter Alec sur le projet Vercel** (Members → Add → boris@entrepreneurs.com... → wait, Alec's email)
- [ ] **Bookmark dashboard partagé à Alec + équipe pilotage**

### Priorité moyenne

- [ ] **Multi-produits** : router scénario 1 selon `Code Produit` → templateId DocuSign différent (Oscar, autres)
- [ ] **Bascule Fermé Gagné automatique** quand contrat signé + 1er paiement reçu (intégration Stripe/bancaire) — éliminerait la saisie manuelle `Date 1er paiement`
- [ ] **Clarifier tab "Alec Henry"** dans le template DocuSign
- [ ] **Champ Zoho custom "DocuSign Envelope ID"** pour traçabilité bidirectionnelle CRM ↔ Sheets ↔ Dashboard
- [ ] **Dashboard V2** : ajouter filtres par période (J7/J30/J90), drilldown par closer, sparklines hebdo CA
- [ ] **Garde-fou scénario 2** : condition `Statut contrat = Signé` avant log Vente fermée
- [ ] **Custom domain Vercel** : `dashboard.entrepreneurs.com` au lieu de `kelly-dashboard-sigma.vercel.app`

### Priorité basse

- [ ] **Loom 5 min** : refaire les 2 scénarios Make + Apps Script + dashboard from scratch
- [ ] **Tests automatisés** Make sandbox
- [ ] **Migration JWT Auth DocuSign** si volume > 500/mois
- [ ] **Reporting hebdomadaire** Make → Notion ou email récap funnel
- [ ] **Backend serverless intermédiaire** (Vercel Function + service account Google) si on veut un Apps Script en restriction domaine

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

- **Construction** : session Boris × Claude, 12 mai 2026 (soir) + 13 mai 2026 (matin → après-midi)
- **Durée build cumulée** : ~5h (Zoho + workflows + 2 scénarios Make + Apps Script + dashboard + déploiement Vercel + debugging CORS / Apps Script)
- **Versions** :
  - V1 (13 mai 09h) — 4 modules Make scénario 1, premier envoi DocuSign validé
  - V1.1 (13 mai 11h) — ajout module 5 Sheets `Contrats envoyés`
  - V1.2 (13 mai 11h35) — ajout scénario 2 "Ventes fermées" (3 modules), funnel Sheets complet à 4 étapes
  - **V1.3 (13 mai 14h) — dashboard React déployé sur Vercel, Apps Script proxy avec token auth, sécurisation Vercel Authentication, infra prod complète**
- **Tests réussis** :
  - 13 mai 08h34 UTC — envelope DocuSign `c26f5ecb-25b8-886a-8242-2c9b8715ae59` envoyée (status 201, tabs OK)
  - 13 mai 09h12 UTC — ligne `Contrats envoyés` créée (10 colonnes)
  - 13 mai 09h33 UTC — ligne `Ventes fermées` créée (12 colonnes hors Date 1er paiement manuelle)
  - 13 mai 14h UTC — dashboard live `kelly-dashboard-sigma.vercel.app` avec data réelles, marche en privé + loggé Google
- **À tester en prod réelle** : 2-3 affaires Kelly Launch réelles avant de considérer V1.3 stable
- **Next steps immédiats** : (1) activer les 2 scénarios Make en ON permanent, (2) error handlers, (3) test affaire réelle, (4) identifier l'assistante DocuSign, (5) inviter Alec sur Vercel
