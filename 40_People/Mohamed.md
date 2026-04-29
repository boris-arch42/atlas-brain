---
type: person
full-name: "Mohamed [nom à compléter]"
role: "IT / Cybersécurité / Admin systèmes — Entrepreneurs.com (sortant)"
team: "Entrepreneurs.com — IT (externe)"
manager: "[[Fabrice Jaeger]] (relation opérationnelle) / [[Alec Henry]] (décision)"
reports: 
started: à-compléter
end-date-prévue: "fin mai / début juin 2026 (décision Alec)"
status: outgoing
source: entrepreneurs-com
sensitivity: rh-nominatif
tags: [it, cybersec, admin-systeme, sortant, passation-cybersec, lien-tang-suspect, stub]
---

# Mohamed

> 🔴 **Sortant — passation cybersécurité critique avant fin mai/début juin** — Mandat Boris explicite (cf. [[Ressource - Replay Boris Fabrice 28 avril 2026]]).

## ⚡ Synthèse en 30 secondes

- **Rôle** : IT / cybersécurité / admin systèmes (poste externe / freelance)
- **Décision Alec** : arrêt de la collaboration **fin mai / début juin 2026** (économie ~24K€/an mentionnée au replay Alec/Fabrice 27/4)
- **Mandat Boris** : récupérer **avant son départ** un système clean cyber secure (audit accès, certificats, MFA, backups, infra, passwords, scripts cron, comptes admin)
- **⚠️ Warning Boris** : Boris a **personnellement travaillé avec Mohamed hors entrepreneurs.com**, sur un projet IA confié par Tang. Lien historique avec Tang à garder en tête.
- **🟢 Rassurance Fabrice** : Fabrice a eu un échange frontal avec Mohamed au moment du conflit Tang. Mohamed s'est positionné professionnel : *"Mon job c'est la sécurité, la confidentialité, c'est mon métier."*
- **Risque résiduel** : un IT sortant frustré par l'empilement de projets sans sens (cf. épisode NAS/Shade) peut laisser des bombes (backdoors, accès résiduels, scripts cron, certificats partagés).

## Contexte de la passation

### Pourquoi Alec veut arrêter

- Mentionné dans le replay Alec/Fabrice du 27/4 : *"Il faut donner cette tâche à Boris ou à je ne sais pas qui, avec Mohamed d'Haïti, qu'on le rentabilise le mec."* → Alec considère que Mohamed n'est pas suffisamment rentabilisé (3 semaines avec juste 3 calls entre Mohamed IT et Alexis sur la nego SaaS, sans appeler les fournisseurs).
- Économie mentionnée : ~24K€/an dans la cible 70-100K€/an d'économies SaaS (cf. mandat audit Boris).

### La position de Mohamed (rapportée par Fabrice 28/4)

Verbatim Fabrice rapportant Mohamed :
> *"Moi mon job c'est la sécurité, la confidentialité, c'est mon métier. Je peux pas me cramer auprès de... Je vais pas me tirer une balle dans le pied tu vois en faisant des trucs. Ça c'est vos trucs, c'est vos problèmes, moi j'interviens pas là-dessus."*

→ Mohamed s'est positionné comme **professionnel neutre** au moment du conflit Tang. Pas de loyauté affichée envers Tang. Fabrice considère que la dégradation de la dynamique avec Mohamed vient de **l'empilement de projets sans sens d'Alec** (cf. cas NAS/Shade), pas d'un alignement Tang.

### Le warning Boris (à garder en tête)

Boris a **bossé personnellement avec Mohamed hors entrepreneurs.com** :
- Projet IA confié par Tang à Boris (à l'époque où la dynamique avec Tang était encore positive)
- Boris a donc vu Mohamed exécuter et a pu observer ses pratiques

Verbatim Boris à Fabrice 28/4 (rapporté) :
> *"Au vu de tout le bazar, tu sais qui est ce gars et ce qu'il fait, et à quel point sa proximité avec Tang est très forte ?"*

→ Cette proximité historique avec Tang est documentée mais Fabrice considère qu'elle ne s'est pas matérialisée en risque. **À surveiller quand même** dans la passation.

## Cas d'école NAS/Shade — pourquoi la dégradation s'est faite

Documenté dans [[Ressource - Replay Boris Fabrice 28 avril 2026]] (sujet long aparté). En résumé :
- Alec a balancé *"vous êtes des couillons"* à Océane parce qu'Amine paye 150€/mois pour 4-5 To, alors qu'entrepreneurs.com paye plus pour 70 To
- Sans tenir compte des specs : Shade (IA vidéo, transcoding propriétaire) ≠ Blackbaize (hosting backend) ≠ Google Drive (storage hôte)
- Mohamed a hérité de l'embourbement de projets contradictoires
- Fabrice : *"Il s'est retrouvé un petit peu bloqué sur de l'embourbement de projets à la noix."*

→ Mohamed est probablement frustré, lassé, mais professionnel. Pas hostile.

## 🎯 Mandat Boris — passation cybersécurité

### Verbatim Fabrice qui pose le mandat

> *"L'objectif c'est qu'on arrête avec Mohamed, ce sera probablement fin mai début juin. Mais ce qui veut dire que toi, il faut que tu récupères, t'assurer que d'un point de vue système et tout, lui il a pu laisser, qu'on soit clean cyber secure."*

### Checklist passation cybersec à réaliser avant fin mai

- [ ] **Audit complet des accès admin** (Google Workspace, Microsoft, AWS/GCP, serveurs, NAS, plateformes SaaS)
- [ ] **Inventaire des comptes service / impersonation** créés par Mohamed (à reprendre ou supprimer)
- [ ] **Inventaire des clés API + tokens d'accès** distribués / partagés / hard-codés
- [ ] **Audit MFA** : qui a la 2FA sur quels comptes critiques, transfert vers compte boîte si Mohamed l'avait
- [ ] **Audit certificats** (SSL, signatures, certificats Apple/Google si app mobile)
- [ ] **Audit backups** : où sont-ils, qui y a accès, sont-ils restaurables
- [ ] **Inventaire des scripts cron / automation** (potentiel pour bombes à retardement)
- [ ] **Audit des accès VPN / réseau** s'il y en a
- [ ] **Audit Wayo** (si Mohamed avait des accès historiques aux cartes coupées il y a 5 mois)
- [ ] **Documentation de toutes les solutions hébergées** (sur quelle infra, qui paye, qui a accès)
- [ ] **Logs d'activité Mohamed** sur les 3 derniers mois (revue préventive)
- [ ] **Lettre de fin de collaboration** propre (clauses de confidentialité, NDA, restitution de matériel)

### Risques à monitorer post-départ

- **Backdoors résiduels** (comptes admin oubliés, scripts cron qui pingent vers une infra extérieure)
- **Tokens API qui survivent** (clés statiques non révoquées)
- **Certificats partagés** non transférés
- **Email de transfert** qui peut continuer à recevoir des notifications sensibles
- **Accès Wayo** ou anciennes cartes (peu probable — coupées il y a 5 mois — mais à confirmer)

## Coordination

- **Validation Alec au call 1er mai** sur le mandat passation + planning S2-S4
- **Coordination Fabrice** : Fabrice a la relation historique avec Mohamed, il peut faciliter l'introduction "passation Boris" sans tension
- **Choix successeur** : à arbitrer avec Alec et Fabrice — IT externe remplaçant ? Internalisation ? NAS physique (1K€) déjà décidé pour économies Google → qui l'opère ?

## Ce que je ne sais PAS encore

- **Nom de famille** de Mohamed
- **Date de début** de la collaboration avec entrepreneurs.com
- **Statut contractuel** (freelance ? prestataire ? salarié ?)
- **Localisation** ("Mohamed d'Haïti" mentionné par Alec — probablement basé Haïti, à confirmer)
- **Étendue exacte des accès** (scope IT vs scope sécurité vs scope infra)
- **Lien actuel avec Tang** s'il y en a un
- **Volume de travail réel** (combien de jours/mois facturés)

## 🔗 Notes liées

- [[Fabrice Jaeger]] — relation opérationnelle, source d'information sur Mohamed
- [[Alec Henry]] — décideur de la passation, à valider planning au call 1er mai
- [[Boris Arduy]] — relation hors entrepreneurs.com (projet IA Tang)
- [[Ressource - Replay Boris Fabrice 28 avril 2026]] — mandat posé + warning lien Tang
- [[Ressource - Replay Alec Fabrice 27 avril 2026]] — décision arrêt fin mai (économie 24K€/an)

## 📝 À mettre à jour avant la passation

- [ ] Récupérer son nom de famille
- [ ] Cartographier scope exact (IT / sécu / infra)
- [ ] Premier échange Boris ↔ Mohamed (cordial, professionnel, transparent sur le calendrier)
- [ ] Statut contractuel + clauses (préavis, NDA, confidentialité)
- [ ] Date butoir précise (à valider Alec)
- [ ] Successeur identifié (IT externe / internalisation / pas de remplacement)
