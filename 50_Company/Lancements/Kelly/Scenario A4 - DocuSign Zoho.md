---
type: technical-scenario-spec
project: "[[_Index|Lancement Kelly]]"
owner: "[[Boris Arduy]]"
created: 2026-05-10
last-updated: 2026-05-10
status: scoped-not-built
version: V1 — planification
tags: [lancement, kelly, infrastructure, make, scenario, zoho, docusign, automation, A4]
sensitivity: confidential
related-docs: ["[[Scenario A2 - iClosed vers Zoho]]", "[[Produit - Méthode Boss Energy]]", "[[Infrastructure - Setup en cours]]"]
---

# Scenario Make A4 — DocuSign automation depuis Zoho

> Génération automatique du contrat DocuSign Méthode Boss Energy quand le Deal Zoho passe en stage `Engagé`. Update du Deal Zoho après signature. **Chantier planifié post-event Kelly Launch.**

## Statut

**🔴 Non construit — Scope défini le 10 mai 2026**

Sera attaqué après la fin de l'event Kelly Launch (~26 mai 2026), une fois les retours du terrain capitalisés et le système A2 stabilisé.

## Objectif business

Aujourd'hui (V1 Kelly Launch sans A4) : les closers générent les contrats DocuSign manuellement après chaque deal négocié. Friction + risque d'erreur dans le pré-remplissage + délai entre négociation et envoi du contrat.

Avec A4 : dès que le closer passe le Deal Zoho en stage `Engagé`, DocuSign reçoit le déclencheur, génère l'envelope, l'envoie au lead. Le Statut_contrat du Deal s'update automatiquement à "Envoyé" puis "Signé" via webhook DocuSign retour.

**Gain estimé** : 5-10 minutes par deal × 200-500 deals gagnés sur Kelly Launch + futurs lancements.

## Décisions architecturales actées (10 mai)

| Décision | Choix | Justification |
|---|---|---|
| Compte DocuSign | Compte existant Entrepreneurs.com | Pas de création supplémentaire |
| Template DocuSign | **Template dédié Méthode Boss Energy** | Distinct des templates internes (Scaling, etc.) — produit différent, cible différente |
| Trigger génération | **Stage Deal Zoho = `Engagé`** | Approche proactive. Le closer pousse le Deal en Engagé quand le lead a confirmé son intention de payer. |
| Source des données | Custom fields Deal Zoho déjà créés | Pas de saisie redondante : Boris a anticipé en créant les champs (Modalites_paiement, Nb_mensualites, Date_demarrage, etc.) |
| Statuts à tracker | Statut_contrat custom field Zoho (En préparation / Envoyé / Signé / Refusé) | Champ déjà créé sur le Deal |

## Architecture cible

```
┌────────────────────────────────────────────┐
│ Closer met le Deal Zoho en stage "Engagé"  │
└────────────────────────────────────────────┘
                  ↓
        [Webhook Zoho → Make]
                  ↓
┌────────────────────────────────────────────┐
│ Scenario A4 — Génération DocuSign          │
│                                             │
│ 1. Search Deal in Zoho (par Deal ID)       │
│    - Récupère Account, Contact lié          │
│    - Récupère custom fields                 │
│                                             │
│ 2. DocuSign : Create Envelope               │
│    - Template "Méthode Boss Energy"         │
│    - Recipient : Contact.email              │
│    - Tabs (variables pré-remplies) :        │
│        • {nom_complet}                      │
│        • {email}                            │
│        • {telephone}                        │
│        • {raison_sociale} (Account.name)    │
│        • {montant_total} = 5700             │
│        • {nb_mensualites}                   │
│        • {montant_mensuel}                  │
│        • {date_demarrage}                   │
│                                             │
│ 3. Send Envelope                            │
│                                             │
│ 4. Update Deal Zoho :                       │
│    - Statut_contrat = "Envoyé"              │
│    - Date_envoi_contrat = now()             │
│    - DocuSign_envelope_id = {id}            │
└────────────────────────────────────────────┘

         ... attente signature ...

┌────────────────────────────────────────────┐
│ [Webhook DocuSign → Make]                  │
│ Trigger : "envelope-completed"             │
└────────────────────────────────────────────┘
                  ↓
┌────────────────────────────────────────────┐
│ Scenario A4bis — Post-signature update     │
│                                             │
│ 1. Search Deal in Zoho (par envelope_id)   │
│                                             │
│ 2. Update Deal :                            │
│    - Statut_contrat = "Signé"               │
│    - Stage = "Fermé Gagné"                  │
│    - Probabilité = 100                      │
│    - Date_signature = now()                 │
│                                             │
│ 3. Optionnel : déclencher scenario A5      │
│    (push HubSpot pour delivery interne)    │
└────────────────────────────────────────────┘
```

## Mapping champs Deal Zoho → Template DocuSign

Le template DocuSign "Méthode Boss Energy" devra inclure ces variables (tabs) :

| Variable DocuSign | Source Zoho | Notes |
|---|---|---|
| `{nom_complet}` | Contact.First Name + Last Name | Personne physique signataire |
| `{email}` | Contact.Email | Adresse de signature (où DocuSign envoie le lien) |
| `{telephone}` | Contact.Phone | Pour identification |
| `{raison_sociale}` | Account.Account Name | Si vide ou `[À compléter]`, à enrichir avant envoi |
| `{adresse_postale}` | Account.Billing Address | À enrichir post-call si vide |
| `{ville}` | Account.Billing City | Idem |
| `{code_postal}` | Account.Billing Code | Idem |
| `{numero_fiscal}` | Account.Tax ID | Pour facturation entreprise |
| `{produit}` | "Méthode Boss Energy" | Hardcoded ou dérivé de Deal.Product Details |
| `{montant_total_ht}` | "5700" | Hardcoded V1 (1 seul produit, 1 seul prix) |
| `{nb_mensualites}` | Deal.Nb_mensualites | Le closer remplit ce champ pendant la négociation |
| `{montant_mensuel}` | Deal.Modalites_paiement | Idem |
| `{date_demarrage}` | Deal.Date_demarrage | Idem |
| `{date_signature}` | now() | Date de signature électronique |
| `{nom_closer}` | Deal Owner (User name) | Pour traçabilité du commercial |

## Décisions à prendre avant la build (questions ouvertes)

### Q1 — Plan DocuSign

Quel plan DocuSign actuel ? Standard / Business Pro / Advanced ?
- Le Standard ne permet pas l'API DocuSign Connect → bloquant pour les webhooks retour
- Business Pro ou supérieur recommandé pour le scenario A4 complet
- À vérifier avec l'équipe IT Entrepreneurs.com

### Q2 — Connecteur Make ↔ DocuSign

DocuSign a un module natif Make ou il faudra passer par API REST + module générique HTTP ? À investiguer.

### Q3 — Cycle de signature : signataire unique ou multiple ?

- Cas 1 : signataire = le Contact (lead) uniquement
- Cas 2 : signataire = le Contact ET un représentant Entrepreneurs.com (Boris ? Alec ?)

Si cas 2, le scenario doit gérer 2 envelopes (séquentielles ou parallèles).

### Q4 — Validation pré-envoi obligatoire ?

Quand le Deal passe en `Engagé` et qu'A4 se déclenche :
- **Option A — Envoi automatique direct** : DocuSign part immédiatement au lead. Risque : si le closer a fait une erreur de saisie (mauvais montant, mauvaise date), le lead reçoit un contrat erroné.
- **Option B — Étape de validation** : A4 génère l'envelope en mode "Draft" dans DocuSign. Le closer reçoit une notif Slack/Email pour valider et déclencher l'envoi manuel.
- **Option C — Validation par le Manager d'agence** : idem mais validation par le manager Tip Talent / Momentum / Next Sales.

**Recommandation à débattre** : Option B en V1 pour sécuriser, Option A en V2 quand on a confiance dans la qualité de saisie des closers.

### Q5 — Gestion des relances DocuSign

- Combien de jours avant relance automatique du lead ? (DocuSign le permet nativement)
- Combien de relances max ?
- Que faire si pas de signature après N jours : Stage Zoho passe automatiquement en "Closed Lost - Pas de signature" ?

## Roadmap d'exécution

### Phase 1 — Validation contexte (1h) — semaine du 26 mai

- Vérifier le plan DocuSign actuel + accès admin
- Identifier les templates existants (Scaling, etc.) pour s'en inspirer
- Investigation Make ↔ DocuSign (module natif ou API ?)
- Trancher Q3 / Q4 / Q5

### Phase 2 — Création du template DocuSign (2-3h)

- Rédaction du contrat Méthode Boss Energy (juridique : à valider avec Alec et/ou avocat)
- Placement des tabs (variables) dans le template
- Test manuel : créer une envelope from template, pré-remplir manuellement, envoyer à un test perso

### Phase 3 — Build scenario A4 dans Make (2-3h)

- Trigger : webhook Zoho on Deal stage change to "Engagé"
- Module DocuSign : Create Envelope from Template
- Module Zoho : Update Deal (Statut_contrat = Envoyé)

### Phase 4 — Build scenario A4bis dans Make (1h)

- Trigger : webhook DocuSign on envelope completed
- Module Zoho : Update Deal (Statut_contrat = Signé, Stage = Fermé Gagné)

### Phase 5 — Tests end-to-end + corrections (2h)

- Booking test → Deal Engagé → DocuSign envelope → Signature test → Update Zoho
- Vérification de tous les champs pré-remplis correctement

**Effort total estimé** : 8-10h spread sur 1 semaine post-event.

## Dépendances

A4 dépend de :

- ✅ Module Deals Zoho avec custom fields (déjà fait, V1 A2)
- ✅ Module Products Zoho avec catalogue Boss Energy (à finaliser cette semaine)
- ✅ Stages pipeline incluant `Engagé` (déjà fait)
- ⏳ Plan DocuSign avec API access (à vérifier)
- ⏳ Template DocuSign dédié Boss Energy (à créer)

## Roadmap V2 — Améliorations possibles

- **Multi-signataire** : si EC doit aussi signer le contrat
- **Notification Slack post-signature** vers le closer + son manager
- **Gestion des modifications** : si le lead demande à modifier les termes après envoi, comment annule-t-on le contrat actuel et regénère-t-on ?
- **Tracking visualisation** : webhook DocuSign on "envelope viewed" → notif Slack au closer ("le lead vient de voir ton contrat")
- **Génération PDF locale** post-signature pour archivage Atlas-Brain ou Google Drive Kelly

## Liens

- [[_Index|Hub projet Kelly]]
- [[Scenario A2 - iClosed vers Zoho]] — scenario amont (création des Deals)
- [[Produit - Méthode Boss Energy]] — catalogue produit lié
- [[Infrastructure - Setup en cours]] — log de setup
- [[Architecture - Funnel parallèle closers externes]] — vue globale

## Historique

- **2026-05-10** — Scope défini lors de la session pair-programming Kelly avec Boris. 4 décisions architecturales actées (compte existant, template dédié, trigger sur stage Engagé, mapping via custom fields existants). Build planifié post-event Kelly (semaine du 26 mai 2026). Document placeholder créé pour capitaliser le contexte.
