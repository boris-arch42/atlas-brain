---
type: decision
statut: draft
date: 2026-08-25
source: jarvis
call: "[[2026-08-25 - Cédric & Boris]]"
tags: [decision, draft]
---

# SLA SDR 60–90 secondes et suivi du time-to-lead

> Brouillon proposé par Jarvis depuis un call — à valider, compléter, puis ranger dans 20_Decisions (ou supprimer).

## Contexte
Les leads opt-in Evergreen ne sont pas rappelés assez rapidement, ce qui impacte la conversion. Aucun SLA ni métrique de time-to-lead n'étaient formellement suivis.

## Décision
- **SLA fixé** : un SDR doit appeler tout nouveau lead opt-in Evergreen sous **60 à 90 secondes**.
- **KPI** : le **time-to-lead** devient une métrique suivie en continu.
- **Responsabilités** : Alexandre implémente le tracking et les notifications urgentes dans le SDR Hub ; managers SDR appliquent le SLA.
- Cédric et Boris suivent l'efficacité SDR via ce KPI et ajustent effectif/processus si nécessaire.

## Conséquences
- Amélioration attendue du taux de conversion leads → rendez-vous.
- Besoin de notifications push/alertes temps réel dans le SDR Hub.
- Charge opérationnelle accrue sur les SDR ; surveiller burnout et dimensionnement équipe.
- Dépendance critique à la fiabilité de l'infrastructure de notifications (Customer.io, webhooks).

## À valider par Boris
- [ ] SLA 60–90s est-il réaliste pour toutes les plages horaires ?
- [ ] Qui audite le respect du SLA et avec quelle fréquence ?
- [ ] Besoin d'un escalade-process si SLA non respecté ?
