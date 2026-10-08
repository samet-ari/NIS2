# Analyse d'écart et feuille de route de mise en conformité NIS2 — HydroRégie

**Bloc 2 — Couverture des mesures de l'article 21, priorisation des écarts, plan d'actions daté et responsabilisé**
**Destinataires :** Direction générale, DSI, RSSI, direction technique et exploitation
**Date de la note :** 7 octobre 2026
**Statut de référence :** Entité essentielle (voir note de qualification, Bloc 1)

---

## 1. Hypothèses de cadrage

L'état des lieux ci-dessous est établi sur les hypothèses de travail suivantes, retenues pour le cas.

| Élément | Hypothèse retenue |
|---|---|
| Maturité cyber globale | Moyenne : PSSI à jour, sauvegardes et antivirus déployés, premières démarches ISO 27001 côté IT, aucune certification |
| Gouvernance cyber | RSSI à temps plein, rattaché à la direction générale ; son périmètre d'action ne couvre pas l'OT |
| Environnement OT | Mixte : une partie des automates et du SCADA a été renouvelée, une partie est ancienne ; inventaire incomplet |
| Horizon du programme | 18 mois, du 1er novembre 2026 au 30 avril 2028 |
| Enveloppe budgétaire | 3 à 4 M€ (estimation centrale détaillée en section 5) |

Les montants et délais sont des ordres de grandeur du cas, à confirmer par devis et par les contraintes réelles de la commande publique.

---

## 2. Méthode

**Référentiel :** article 21, paragraphe 2, de la directive (UE) 2022/2555 (dix mesures minimales, lettres a à j), complété par l'article 20 (gouvernance) et l'article 23 (notification des incidents).

**Échelle de maturité :**

| Niveau | Définition |
|---|---|
| 0 | Inexistant |
| 1 | Initial : pratiques ad hoc, non documentées |
| 2 | Partiel : défini mais incomplet ou non appliqué partout |
| 3 | Défini et appliqué : documenté, déployé, suivi |
| 4 | Maîtrisé : mesuré et amélioré en continu |

**Cible à 18 mois : niveau 3** sur tous les domaines.

**Score retenu :** score global pondéré entre IT et OT ; le détail par périmètre figure dans la colonne « Constat ».

**Priorité :** croisement de trois facteurs : impact d'une défaillance sur la continuité du service d'eau potable, exposition réglementaire, taille de l'écart.
- **P1** : à traiter en premier (impact fort ou prérequis d'autres actions)
- **P2** : à traiter dans le programme
- **P3** : à planifier, impact moindre

---

## 3. Analyse d'écart

| Domaine (réf. directive) | Constat | Actuel | Cible | Écart | Priorité |
|---|---|---|---|---|---|
| **Gouvernance** (art. 20) | RSSI en poste et rattaché à la direction. Organe de direction non formé à la cybersécurité, pas de validation formelle des mesures, pas de comité cyber régulier. | 2 | 3 | 1 | **P1** |
| **a) Analyse de risques et politiques de sécurité** | PSSI à jour. Analyse de risques menée sur une partie du périmètre IT ; OT non couvert. | 2 | 3 | 1 | **P1** |
| **b) Gestion des incidents** | Procédure IT existante, sans supervision 24h/24 ni détection OT. Aucune procédure de notification calée sur les délais NIS2 (24 h / 72 h / 1 mois). | 2 | 3 | 1 | **P1** |
| **c) Continuité d'activité et gestion de crise** | Sauvegardes IT en place, PRA non testé. Mode dégradé OT (conduite manuelle) non formalisé. Aucun exercice de crise cyber. | 2 | 3 | 1 | **P1** |
| **d) Sécurité de la chaîne d'approvisionnement** | Pas de clauses de sécurité dans les marchés. Accès de télémaintenance des fournisseurs OT non maîtrisés. Fournisseurs critiques non recensés. | 1 | 3 | 2 | **P1** |
| **e) Acquisition, développement, maintenance et gestion des vulnérabilités** | IT : correctifs réguliers, scans ponctuels. OT : correctifs quasi inexistants, systèmes anciens non patchables, pas de processus de divulgation des vulnérabilités. | 2 | 3 | 1 | **P1** |
| **f) Évaluation de l'efficacité des mesures** | Pas d'audit récurrent, pas de test d'intrusion, pas d'indicateurs de suivi. | 1 | 3 | 2 | P2 |
| **g) Cyberhygiène et formation** | Sensibilisation annuelle limitée aux agents du siège. Aucune formation dédiée au personnel d'exploitation OT. | 2 | 3 | 1 | P2 |
| **h) Cryptographie et chiffrement** | IT : TLS et chiffrement des postes. OT : protocoles industriels en clair. Pas de politique de gestion des clés. | 2 | 3 | 1 | P3 |
| **i) Sécurité RH, contrôle d'accès, gestion des actifs** | Inventaire IT partiel, inventaire OT incomplet, comptes génériques sur le SCADA, revues de droits irrégulières. | 1 | 3 | 2 | **P1** |
| **j) Authentification multifacteur et communications sécurisées** | MFA sur la messagerie et les accès administrateur IT. Pas de MFA sur la télémaintenance OT. Pas de canal de crise hors bande. | 2 | 3 | 1 | P2 |

**Synthèse :**

| Indicateur | Valeur |
|---|---|
| Maturité moyenne actuelle | 1,7 / 3 |
| Maturité cible | 3,0 / 3 |
| Écart moyen | 1,3 point par domaine |
| Domaines P1 | 7 sur 11 |
| Domaines les plus en retard (écart de 2) | Chaîne d'approvisionnement, évaluation de l'efficacité, gestion des actifs |

**Constat transversal :** les écarts les plus lourds se concentrent côté OT (inventaire, accès tiers, vulnérabilités, détection). C'est précisément le périmètre hors de l'action actuelle du RSSI, ce qui impose de rattacher formellement l'OT à la gouvernance cyber dès les premiers mois.

---

## 4. Feuille de route

### Rôles

| Sigle | Rôle |
|---|---|
| DG | Direction générale |
| RSSI | Responsable de la sécurité des systèmes d'information |
| DSI | Direction des systèmes d'information |
| DET | Direction technique et exploitation (responsable de l'OT) |
| Achats | Service achats / commande publique |
| Juridique | Service juridique |
| DRH | Direction des ressources humaines |

### Phase 0 — Quick wins (mois 1 à 3 : 1er novembre 2026 – 31 janvier 2027)

| ID | Action | Domaine | Responsable | Échéance | Livrable |
|---|---|---|---|---|---|
| A01 | Vérifier et compléter l'enregistrement sur MonEspaceNIS2, désigner le point de contact | Art. 20 | RSSI | 30/11/2026 | Preuve d'enregistrement |
| A02 | Constituer le comité de pilotage cyber (réunion trimestrielle) | Art. 20 | DG | 31/12/2026 | Charte du comité, première réunion |
| A03 | Former l'organe de direction et faire valider formellement le programme de conformité | Art. 20 | DG, RSSI | 31/01/2027 | Attestations de formation, délibération |
| A04 | Rédiger la procédure de notification d'incident NIS2 (24 h / 72 h / 1 mois), modèles et annuaire de crise | b | RSSI | 31/01/2027 | Procédure, modèles de notification |
| A05 | Activer la MFA sur la télémaintenance et les comptes à privilèges, supprimer les comptes génériques SCADA critiques | i, j | DSI, DET | 31/01/2027 | Rapport de déploiement |
| A06 | Recenser et justifier les accès des fournisseurs OT, fermer les accès non justifiés | d, i | DET, RSSI | 31/01/2027 | Registre des accès tiers |
| A07 | Mettre en place des sauvegardes hors ligne ou immuables des configurations SCADA, automates et systèmes critiques | c | DSI, DET | 31/01/2027 | Test de restauration réussi |

### Phase 1 — Fondations (mois 4 à 9 : 1er février – 31 juillet 2027)

| ID | Action | Domaine | Responsable | Échéance | Livrable |
|---|---|---|---|---|---|
| A08 | Inventorier les actifs OT, sites critiques en priorité | i | DET | 30/04/2027 (sites critiques), 30/06/2027 (complet) | Inventaire OT |
| A09 | Mener l'analyse de risques EBIOS RM sur IT et OT, périmètre critique d'abord | a | RSSI | 31/05/2027 | Rapport d'analyse de risques |
| A10 | Réviser la PSSI (volet OT), rédiger la politique de cryptographie et de gestion des clés | a, h | RSSI | 30/06/2027 | PSSI v2, politique de cryptographie |
| A11 | Marché de supervision SOC/MDR 24h/24 : lancer la procédure, notifier le contrat | b | DSI, Achats | Lancement 28/02/2027, notification 30/06/2027 | Contrat notifié |
| A12 | Concevoir l'architecture segmentée IT/OT (Bloc 3) et lancer le marché de déploiement | e, i | DSI, DET | Conception 30/04/2027, marché lancé 31/05/2027 | Dossier de conception, DCE |
| A13 | Intégrer des clauses de sécurité NIS2 dans les marchés (modèles CCAP/CCTP), recenser les fournisseurs critiques | d | Achats, Juridique | 31/07/2027 | Clauses types, liste des fournisseurs critiques |
| A14 | Instaurer le cycle de gestion des vulnérabilités IT (scans mensuels, délais de correction) | e | DSI | 30/06/2027 | Procédure, tableau de suivi |

### Phase 2 — Structuration (mois 10 à 15 : 1er août 2027 – 31 janvier 2028)

| ID | Action | Domaine | Responsable | Échéance | Livrable |
|---|---|---|---|---|---|
| A15 | Mettre le SOC IT en service | b | DSI, RSSI | 31/08/2027 | Procès-verbal de recette |
| A16 | Réviser le PCA/PRA, documenter et tester le mode dégradé OT | c | DET, DSI | 30/09/2027 | PCA/PRA, procédures de conduite manuelle |
| A17 | Déployer la segmentation IT/OT, vague 1 (sites de production et de traitement) | e, i | DSI, DET | Marché notifié 30/09/2027, déploiement 31/01/2028 | Recette technique |
| A18 | Raccorder des sondes de détection OT passives au SOC | b, e | RSSI, DET | 30/11/2027 | Recette |
| A19 | Définir des mesures compensatoires pour les systèmes OT obsolètes non patchables | e | DET, RSSI | 31/12/2027 | Registre des mesures compensatoires |
| A20 | Mettre en place la gestion des accès à privilèges (PAM) sur IT et OT | i, j | DSI | 31/12/2027 | Recette |
| A21 | Former le personnel d'exploitation OT et sensibiliser l'ensemble des agents | g | DRH, RSSI | 31/12/2027 | Taux de participation |

### Phase 3 — Consolidation (mois 16 à 18 : 1er février – 30 avril 2028)

| ID | Action | Domaine | Responsable | Échéance | Livrable |
|---|---|---|---|---|---|
| A22 | Déployer la segmentation IT/OT, vague 2 (sites secondaires, réservoirs, stations de relevage) | e | DSI, DET | 30/04/2028 | Recette technique |
| A23 | Conduire un exercice de crise cyber impliquant la direction | b, c, Art. 20 | RSSI, DG | 31/03/2028 | Retour d'expérience |
| A24 | Réaliser un test d'intrusion IT et un audit de sécurité OT | f | RSSI | 31/03/2028 | Rapports d'audit |
| A25 | Réaliser l'audit interne de conformité article 21, la revue de direction et constituer le dossier de preuves pour l'ANSSI | f, Art. 20 | RSSI, DG | 30/04/2028 | Rapport d'audit, tableau de bord |

### Chemin critique

**A08 (inventaire OT) → A12 (conception et marché) → A17 (vague 1) → A22 (vague 2).** Tout retard sur l'inventaire ou sur la passation du marché de segmentation décale l'ensemble du volet OT.

### Jalons de pilotage

| Jalon | Date | Critère de réussite |
|---|---|---|
| J1 | 31/01/2027 | Quick wins clos : direction formée, MFA télémaintenance active, procédure de notification publiée |
| J2 | 31/08/2027 | Analyse de risques validée, SOC IT opérationnel, inventaire OT complet |
| J3 | 31/01/2028 | Segmentation vague 1 déployée, détection OT en service, PCA/PRA testés |
| J4 | 30/04/2028 | Exercice de crise réalisé, audit interne passé, dossier de preuves prêt |

---

## 5. Budget indicatif

| Chantier | Montant (M€) |
|---|---|
| Gouvernance, pilotage et assistance à maîtrise d'ouvrage | 0,15 |
| Analyse de risques et révision documentaire | 0,20 |
| Segmentation IT/OT (pare-feu industriels, DMZ, intégration) | 1,00 |
| Supervision et détection (SOC/MDR, sondes OT) | 0,80 |
| Accès à privilèges, MFA, télémaintenance sécurisée | 0,35 |
| Inventaire OT et gestion des vulnérabilités | 0,25 |
| PCA/PRA, sauvegardes immuables, exercices de crise | 0,30 |
| Chaîne d'approvisionnement (clauses, audits fournisseurs) | 0,10 |
| Formation et sensibilisation | 0,10 |
| Audits et tests d'intrusion | 0,15 |
| **Sous-total** | **3,40** |
| Réserve pour aléas (≈ 10 %) | 0,35 |
| **Total programme** | **3,75** |

**Coûts récurrents non inclus :** après le programme, la supervision SOC, les licences et la maintenance représentent une charge annuelle d'exploitation, estimée dans le cas à 0,4 à 0,6 M€ par an (hypothèse), à inscrire au budget de fonctionnement.

---

## 6. Risques du programme

| Risque | Conséquence | Parade |
|---|---|---|
| Systèmes OT anciens non patchables | Maturité OT limitée sur ces actifs malgré le programme | Mesures compensatoires (A19) : segmentation, surveillance passive, accès restreints ; renouvellement à programmer au plan pluriannuel d'investissement |
| Délais de commande publique | Décalage du SOC et de la segmentation, qui sont sur le chemin critique | Lancer les procédures dès le mois 4 ; s'appuyer sur des accords-cadres existants lorsque c'est possible |
| Fenêtres d'intervention limitées sur l'OT (service d'eau continu) | Déploiements étalés, risque de dépassement de calendrier | Interventions planifiées site par site, mode dégradé validé avant chaque intervention (A16) |
| Charge concentrée sur un RSSI unique | Point de défaillance, retards en cascade | Renfort par un chef de projet et une assistance à maîtrise d'ouvrage externe (inclus au budget) |
| Faible appropriation par la direction | Arbitrages et budgets bloqués | Comité trimestriel, formation de la direction, reporting par jalons |

---

## 7. Conclusion

HydroRégie part d'un niveau de maturité moyen (1,7 sur 3), avec des fondations IT correctes mais un périmètre OT largement hors du champ de la gouvernance cyber. Le programme proposé, d'une durée de 18 mois et d'un coût de l'ordre de 3,75 M€ réserve comprise, vise le niveau 3 sur les onze domaines.

**Limite à assumer :** viser le niveau 3 partout en 18 mois est réaliste pour la gouvernance et l'IT, mais ambitieux pour l'OT. L'objectif prudent est le niveau 3 sur les sites OT critiques à avril 2028 et le niveau 2 sur les sites secondaires et les systèmes obsolètes, avec une trajectoire de consolidation à poursuivre au-delà du programme.

La segmentation IT/OT (actions A12, A17, A22) est le chantier le plus coûteux et le plus structurant du plan ; elle fait l'objet du Bloc 3.
