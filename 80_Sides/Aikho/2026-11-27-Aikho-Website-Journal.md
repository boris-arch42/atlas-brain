---
date: 2026-11-27
type: journal-de-projet
tags: [aikho, site-web, conversion]
---

# Aikho Website — Journal des modifications

Projet lié : [[Aikho]]. Cette note récapitule la discussion. Elle ne contient pas la transcription intégrale ni les captures.

## Cadre

- Reproduire et améliorer le site dans un environnement local uniquement. Consigne permanente de Boris : ne jamais publier sur le site live.
- Prévisualisation utilisée : http://127.0.0.1:8098/. En cas de port occupé sur 8097, la prévisualisation a été lancée sur 8098 avec le dossier de sortie `/tmp/aikho-preview-8098`.

## Journal des demandes et décisions

1. **Identité et navigation.** Fond blanc avec halos bleu-violet, contraste des contenus, typographie Montserrat, navigation principale centrée, sélecteur anglais/français/arabe des Émirats. Renforcer le copywriting et le design SaaS tout en préservant le caractère interactif d’Aikho.
2. **Mascotte et démonstration produit.** Garder une mascotte souriante, plus sérieuse et liée au recrutement. Sans casque en haut de l’accueil, corriger la branche des lunettes. Conversation centrée avec bulles distinctes de style messagerie, davantage de messages, animation parole/écoute et déplacement de la mascotte le long des messages d’Aikho jusqu’à la carte *Judgement under pressure*. Ajouter une jauge illustrative et rendre la carte plus large et compacte. Centrer le titre de cette section sur une ligne et réduire le titre principal d’environ 5 %.
3. **Témoignages et transitions.** Une dizaine de témoignages fictifs pour la maquette, en deux rangées défilant en sens inverse sur l’accueil. Maintenir le défilement jusqu’à la section suivante. Réduire les espaces blancs, fondre les transitions et intégrer une animation de la mascotte. Ajouter une rangée sur la page démo et retirer la mention *Fictional testimonials* dans les maquettes.
4. **CTA et réservation.** Harmoniser la couleur des CTA principaux. Garder un style secondaire pour la démo lorsqu’elle est à côté de *Start free*. Remplacer *See the demo* et *Book a call* par *Book a demo*, avec traductions. Les boutons mènent à la page locale de démo. Le calendrier iClosed fourni a refusé l’intégration avec la directive CSP `frame-ancestors 'none'`. La page utilise une maquette de calendrier et une FAQ de réassurance. Réserver un rendez-vous reste à rendre fonctionnel.
5. **Tarifs.** Présenter Starter (gratuit), Growth, Pro et Enterprise sur devis en reprenant les limites du SaaS. Aligner les quatre boutons, mettre Growth en avant et proposer un sélecteur mensuel/annuel réglé sur annuel. Les tarifs mensuels de Growth et Pro sont de 199 $ et 499 $. Les équivalents mensuels annuels habituels affichés sont de 140 $ et 350 $. Starter pointe vers l’inscription, Enterprise vers la démo. Le trajet Growth/Pro ouvre une connexion générique dans la version auditée.
6. **Black Friday.** Offre locale de −50 % par rapport au tarif mensuel avec engagement annuel, soit 99,50 $/mois pour Growth et 249,50 $/mois pour Pro. Compte à rebours jusqu’au 1er décembre à 00 h, heure de Dubaï. Le lien ouvre les tarifs en mode annuel. Bandeau supérieur limité à la première section de chaque page, puis bandeau flottant en bas dès qu’on la quitte. Retour au bandeau supérieur en remontant. Remise appliquée à l’affichage local.
7. **Audit de conversion.** Note de 60/100, dont design 23/30, compréhension 23/30 et conversion 14/40. Priorités : rendre la réservation réelle, transmettre forfait et périodicité jusqu’au paiement, montrer le résultat côté recruteur dès le premier écran, remplacer les témoignages fictifs par des preuves vérifiables, puis accélérer l’accueil et documenter les engagements de confiance. Suivre les démos confirmées, les premiers postes créés et les achats finalisés.

## État

Les modifications ont été apportées à la prévisualisation locale. La réservation réelle et le paiement n’ont pas été validés.
