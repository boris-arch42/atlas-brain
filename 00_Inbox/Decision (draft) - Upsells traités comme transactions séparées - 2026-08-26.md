---
type: decision
statut: draft
date: 2026-08-26
source: jarvis
call: "[[2026-08-26 - Résolutions problèmes Sales]]"
tags: [decision, draft]
---

# Upsells traités comme transactions séparées

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte

Actuellement, lors d'un upsell, le contrat est remplacé sur la transaction existante. Penny Lane ne lit que le premier contrat et ne capte pas correctement les upsells, perdant traçabilité des montants et dates. Les upsells devraient augmenter avec la montée en gamme des programmes.

## Décision

- Les **upsells seront traités comme transactions séparées** plutôt que remplacement du contrat
- Permet de conserver date d'origine transaction initiale et montants distincts
- En attendant formalisation process, contournement manuel : générer contrat/PDF Onflow et envoyer à comptabilité via Penny Lane

## Conséquences

**Positives :**
- Traçabilité correcte historique client et revenue
- Compatibilité avec Penny Lane et reporting financier
- Permet analytics distincts acquisition vs expansion

**Négatives :**
- Augmente nombre transactions dans CRM
- Nécessite formalisation workflow (génération contrat, envoi compta)
- Process manuel temporaire jusqu'à automation

**À valider par Boris :** Validation workflow formalisé et automation génération contrats upsells avec Léa et Angèle
