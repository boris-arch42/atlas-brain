---
type: call
date: 2026-09-07
source: sembly
participants: ["[[Boris Arduy]]", "stivel@consulting-sd.com"]
sensitivity: confidential
tags: [call, sembly]
enrichi: true
enrichi_le: 2026-11-20
---

# Stivel & Boris

> 📞 Call ingéré automatiquement par Jarvis depuis Sembly (07/09/2026 17:56).

%% synthese:debut %%
## 🧭 Synthèse Atlas
> Générée par Jarvis le 20/11/2026 10:48 — corrige librement hors des marqueurs.

**Résumé** — Call de débogage sur le tracking du quiz diagnostique : l'URL de la page résultats n'est pas correctement suivie. Solution court terme retenue : utiliser la page de réservation comme objectif de conversion ; à long terme, séparer quiz/résultats/réservation en pages distinctes.

**Décisions**
- Court terme : définir la page de réservation (rendez-vous) comme objectif de conversion pour le suivi des leads qualifiés
- Long terme : standardiser l'architecture en séparant quiz, page de résultats et page de réservation en pages distinctes

**Actions**
- [ ] **Stivel** : Configurer le tracking avec la page de réservation comme conversion et mettre à jour les paramètres
- [ ] **Stivel** : Publier une mise à jour dans le groupe équipe pour informer Charlotte ou Océane des changements de tracking
- [ ] **Boris** : Revoir la structure du tunnel lors des prochains lancements pour implémenter la séparation des pages

**Risques & vigilances**
- Bug probable de la plateforme qui ne reflète pas les changements de pages dans l'URL/slug
- L'ajout de pages supplémentaires dans le tunnel pourrait impacter négativement les taux de conversion en prise de rendez-vous
- Le tracking actuel ne permet pas de distinguer les leads ayant complété le diagnostic de ceux ayant simplement opté-in

Tags : #tracking #quiz-diagnostique #conversion #gtm #debugging
%% synthese:fin %%

%% notes:debut %%
## 📝 Notes (Sembly)
> Màj 07/09/2026 17:56 — section gérée par Jarvis, ne pas éditer entre les marqueurs.

✨ Summary

La réunion a porté sur un problème de suivi de la page de résultats du quiz diagnostique : l’URL/slug de cette page n’est pas tracée comme prévu. L’équipe a convenu d’utiliser immédiatement la page de réservation (rendez-vous) comme objectif de conversion, tout en prévoyant à plus long terme de séparer le quiz, la page de résultats et la page de réservation pour fiabiliser le tracking. Les actions retenues sont : mettre à jour l’objectif de conversion vers la page de réservation, configurer le paramétrage et le suivi par Stivel, puis prévenir Charlotte ou Océane une fois la configuration terminée.

📋 Outline

1. Besoin de suivre la page de résultats du quiz diagnostique • 0:00:00

- Stivel a expliqué qu’il utilise un quiz diagnostique et souhaite que l’URL de la page de résultats soit suivie afin de pouvoir récupérer dans ses campagnes les leads ayant complété le diagnostic ; responsable : Stivel.
- L’objectif est de capter des leads qualifiés ayant terminé le diagnostic puis étant passés à la réservation, et non de simples leads génériques ; responsable : Stivel.

2. Slug d’URL, UTM et possible bug de la plateforme • 0:00:38

- Boris a inspecté le slug et les UTM et s’est demandé si un changement de slug aurait un impact sur le tracking, en notant que le chemin actuel affiche « /p/diagnostic-60-heures-rdv » ; responsable : Boris.
- Stivel a supprimé les UTM pour vérifier le slug visible et a constaté des incohérences qui laissent penser à un bug de la plateforme, où le changement de page apparent n’est pas reflété dans l’URL ; responsable : Stivel.
- Les deux ont convenu que le paramétrage de la plateforme semble incorrect, car la page paraît nouvelle côté front-end mais le back-end n’enregistre pas de vrai changement de page ; responsables : Boris et Stivel.

3. Solution intermédiaire : utiliser la page de réservation comme cible de conversion • 0:04:33

- Boris a recommandé, comme solution la plus rapide, de définir la page de réservation (rendez-vous) comme objectif de conversion afin de suivre les leads arrivés jusqu’à la prise de rendez-vous ; responsable : Boris.
- Boris a confirmé que Google Tag Manager (GTM) est présent sur toutes les pages et peut être utilisé pour capter les événements de conversion sur la page de réservation ; responsable : Boris.
- Stivel a reconnu que cette solution n’est pas idéale à long terme, mais qu’elle est acceptable à court terme pour préserver le suivi des conversions et le niveau de qualification ; responsable : Stivel.

4. Correction long terme : séparer le quiz, les résultats et la réservation • 0:04:33

- Les deux participants ont convenu que la bonne solution à long terme consiste à séparer le quiz, la page de remerciement/résultats et la page de réservation en pages distinctes, afin de rendre l’entonnoir et le tracking back-end cohérents ; responsables : Boris et l’équipe de développement.
- Boris a indiqué que plusieurs actifs existants utilisent déjà cette structure et qu’ils bénéficieraient d’une architecture de pages standardisée pour les futurs tunnels ; responsable : Boris.

5. Qualification des leads et détails de suivi pour les campagnes • 0:05:34

- Stivel a précisé qu’il suit à la fois les leads froids (après opt-in) et les leads plus qualifiés qui atteignent la réservation, et qu’il utilise les paramètres UTM ainsi que Calendly / HighClose pour suivre les réservations ; responsable : Stivel.
- Il a insisté sur l’importance de préserver les taux de conversion et sur le fait que l’ajout de pages supplémentaires ne doit pas nuire à la conversion en prise de rendez-vous ; responsable : Stivel.

6. Prochaines étapes immédiates et communication • 0:06:49

- Stivel va configurer le tracking pour utiliser la page de réservation comme conversion et procéder dès maintenant à la mise en place des paramètres ; responsable : Stivel.
- Une fois les changements effectués, Boris a demandé à Stivel de publier une brève mise à jour dans le groupe de l’équipe afin que Charlotte ou Océane en aient connaissance ; responsable : Stivel.
- Les deux se sont accordés pour revoir la structure du tunnel lors des prochains lancements afin d’implémenter une séparation plus claire des pages ; responsables : Boris et Stivel.
%% notes:fin %%
