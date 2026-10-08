# Rapport final d'incident — Directive NIS2, article 23, paragraphe 4, point d

**Pièce 3 — Délai : un mois après le dépôt de la notification d'incident**
**Marquage :** TLP:AMBER — diffusion restreinte à l'ANSSI et aux destinataires désignés

| | |
|---|---|
| **Destinataire** | ANSSI — CSIRT national (autorité compétente NIS2) |
| **Date et heure de dépôt** | Mardi 18 avril 2028, 11 h 00 (heure de Paris) |
| **Type de déclaration** | Rapport final |
| **Référence interne** | HYDRO-CRISE-2028-03-17 |
| **Notification d'incident de référence** | Dimanche 19 mars 2028, 16 h 00 |
| **Échéance réglementaire** | Mercredi 19 avril 2028, 16 h 00 (le lundi 17 avril est férié) |
| **État de l'incident** | Clos le vendredi 7 avril 2028 ; aucun rapport d'étape nécessaire |

---

## 1. Résumé de direction

Entre le 7 et le 17 mars 2028, un attaquant a pris le contrôle du système d'information de gestion d'HydroRégie à partir d'une session de maintenance détournée d'un fournisseur, a exfiltré la base des abonnés, puis a déployé un rançongiciel le 17 mars. La production, la distribution et la qualité de l'eau potable n'ont pas été affectées : l'environnement industriel est resté hors d'atteinte, et la seule tentative de passage vers lui a échoué. Le SI de gestion a été rétabli de manière progressive entre le 21 et le 24 mars, et l'incident a été clos le 7 avril.

**Le point faible principal est la détection :** l'attaquant est resté dix jours dans le SI avant le déclenchement du chiffrement, sans alerte.

---

## 2. Description détaillée de l'incident

### 2.1 Gravité et impact

| Domaine | Impact |
|---|---|
| Service d'eau potable | Aucun impact sur la production, la distribution et la qualité |
| SI de gestion | 94 serveurs sur 156 et 212 postes sur 240 touchés ; annuaire, messagerie, facturation et relation usagers indisponibles |
| Durée d'indisponibilité | Annuaire et messagerie : 4 jours (du 17 au 21/03). Facturation : 7 jours (rétablie le 24/03). Rétablissement complet : 7 avril |
| Abonnés | ≈ 190 000 concernés ; coordonnées, contrat, historique de consommation ; IBAN pour ≈ 112 000 |
| Données publiées | Échantillon de la base publié le 21/03 sur un site de fuite ; demande de retrait déposée |
| Coût direct provisoire | ≈ 1,0 M€ (prestataire, reconstruction, renforts, courriers, communication), hors rançon (non versée) et avant prise en charge par l'assureur |
| Gravité globale | Élevée pour le SI de gestion et les données ; faible pour l'environnement industriel |

### 2.2 Chronologie

| Date | Événement |
|---|---|
| Mar. 07/03 | Compromission d'une session de maintenance d'un éditeur après 23 demandes d'authentification multifacteur répétées, dont une est validée |
| 08/03 au 16/03 | Reconnaissance, collecte d'identifiants, obtention de droits d'administration de domaine |
| 14/03 au 16/03 (nuits) | Exfiltration d'environ 41 Go |
| Ven. 17/03, 21 h 38 | Déploiement du rançongiciel |
| Ven. 17/03, 21 h 52 | Première détection (supervision de sécurité) |
| Ven. 17/03, 22 h 25 à 22 h 40 | Isolement du SI de gestion, coupure de l'accès sortant, révocation des comptes |
| Ven. 17/03, 22 h 31 et 22 h 47 | Tentatives vers l'environnement industriel, bloquées |
| Ven. 17/03, 23 h 10 | Qualification d'incident important |
| Sam. 18/03, 12 h 20 | Alerte précoce déposée |
| Sam. 18/03, 16 h 40 | Confirmation de l'exfiltration |
| Dim. 19/03, 16 h 00 | Notification d'incident déposée |
| Lun. 20/03 | Notification CNIL ; plainte déposée ; début de la reconstruction |
| Mar. 21/03 | Publication d'un échantillon par l'attaquant ; annuaire et messagerie rétablis |
| Jeu. 23/03 | Information individuelle des personnes concernées |
| Ven. 24/03 | Facturation rétablie |
| Ven. 07/04 | Incident clos |

---

## 3. Cause racine

| Niveau | Constat |
|---|---|
| **Cause immédiate** | Une demande d'authentification multifacteur par validation simple a été acceptée par un technicien de l'éditeur de l'ERP après des sollicitations répétées (fatigue MFA) |
| **Facteur aggravant 1** | Le compte de l'éditeur avait des droits d'administration locale sur le serveur applicatif de l'ERP, sans limitation de durée ni enregistrement de session. Le modèle de bastion mis en place pour l'environnement industriel n'avait pas été étendu à l'accès des éditeurs au SI de gestion |
| **Facteur aggravant 2** | Un compte de service de sauvegarde, au mot de passe faible et aux privilèges étendus, a permis l'obtention de droits d'administrateur de domaine |
| **Facteur aggravant 3** | Le SI de gestion était peu segmenté en interne : l'attaquant a pu se déplacer d'un serveur à l'autre sans barrière |
| **Facteur de détection** | Aucune règle de détection sur le comportement des comptes de tiers, aucun seuil d'alerte sur les volumes sortants |

**Type de menace :** attaque criminelle par rançongiciel avec double extorsion (chiffrement et menace de publication), exploitant un accès légitime de fournisseur. L'attaquant n'est pas attribué ; la famille de rançongiciel n'a pas pu être confirmée.

---

## 4. Mesures d'atténuation appliquées

| Mesure | Effet |
|---|---|
| Surveillance 24 h/24 par un prestataire de détection | Détection du chiffrement 14 minutes après son début |
| Isolement immédiat du SI de gestion (conduit IT/iDMZ, accès Internet sortant) | Arrêt de la propagation et de l'exfiltration ; préservation de l'environnement industriel |
| Règle « aucun flux direct IT vers OT » et second facteur indépendant au bastion, annuaire industriel distinct | Échec de la tentative de passage vers l'environnement industriel |
| Autonomie locale des usines et des sites distants | Production et distribution maintenues sans interruption |
| Sauvegardes immuables, reconstruction dans un environnement propre | Rétablissement sans paiement de la rançon |
| Prestataire de réponse à incident, cellule de crise, canal de crise hors bande | Gestion coordonnée malgré l'indisponibilité de la messagerie |
| Notifications aux autorités et information des personnes | Respect des délais NIS2 et RGPD |

---

## 5. Impact transfrontalier

**Aucun.** HydroRégie ne dessert que le territoire national. Aucun abonné, fournisseur critique ou système établi dans un autre État membre n'a été identifié comme touché. L'éditeur de l'ERP a été informé de la compromission de son compte et a fait ses propres vérifications.

---

## 6. Enseignements

**Ce qui a fonctionné.**
- La séparation entre le SI de gestion et l'environnement industriel, qui a tenu exactement là où elle était prévue.
- Le délai de détection du chiffrement et la rapidité de l'isolement.
- Le respect des délais de notification, avec des marges de 10 h 50, 31 h 10 et 29 h.

**Ce qui n'a pas fonctionné.**
- Dix jours de présence de l'attaquant sans détection.
- Un accès fournisseur au SI de gestion moins protégé que l'accès à l'environnement industriel.
- Un SI de gestion resté « à plat ».
- Une durée de restauration de la facturation (7 jours) sans objectif de reprise formalisé au préalable.

---

## 7. Plan d'actions correctives

| Réf. | Action | Responsable | Échéance |
|---|---|---|---|
| C1 | Authentification multifacteur résistante à l'hameçonnage (clé de sécurité) pour tous les comptes externes ; fin de la validation simple ; blocage après plusieurs refus | RSSI | 30/06/2028 |
| C2 | Étendre le modèle du bastion (accès limité dans le temps, validation préalable, enregistrement de session) aux accès des éditeurs au SI de gestion | RSSI, DSI | 31/05/2028 |
| C3 | Retirer les droits d'administration locale des comptes de fournisseurs ; élargir la gestion des accès à privilèges à l'ERP | DSI | 30/04/2028 |
| C4 | Règles de détection sur le comportement des comptes de tiers (heures, volumes, destinations) et alertes sur les volumes sortants | RSSI, prestataire de détection | 15/05/2028 |
| C5 | Durcissement de l'annuaire : administration par niveaux, rotation des comptes de service, suppression des mots de passe faibles | DSI | 30/06/2028 |
| C6 | Micro-segmentation interne du SI de gestion (applications, sauvegardes, annuaire) | DSI | 31/10/2028 |
| C7 | Tests de restauration trimestriels et objectifs de reprise formalisés (facturation sous 72 h) | DSI | 30/06/2028 |
| C8 | Audit de sécurité de l'éditeur de l'ERP et clauses de sécurité renforcées dans le contrat (mesure d de l'article 21) | Achats, Juridique | 30/06/2028 |
| C9 | Terminer la vague 2 de segmentation des sites distants (action A22) | DSI, DET | 30/04/2028 |
| C10 | Intégrer ce scénario aux exercices de crise annuels | RSSI | Prochain exercice |

Le suivi est assuré par le comité de pilotage cyber, avec un point à chaque réunion trimestrielle.

---

Dépôt effectué par : le RSSI, point de contact NIS2 d'HydroRégie, après validation du Directeur général.
