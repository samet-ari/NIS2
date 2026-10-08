# Notification d'incident — Directive NIS2, article 23, paragraphe 4, point b

**Pièce 2 — Délai : 72 heures après la prise de connaissance de l'incident important**
**Marquage :** TLP:AMBER — diffusion restreinte à l'ANSSI et aux destinataires désignés

| | |
|---|---|
| **Destinataire** | ANSSI — CSIRT national (autorité compétente NIS2) |
| **Date et heure de dépôt** | Dimanche 19 mars 2028, 16 h 00 (heure de Paris) |
| **Type de déclaration** | Notification d'incident, mise à jour de l'alerte précoce du 18/03/2028, 12 h 20 |
| **Référence interne** | HYDRO-CRISE-2028-03-17 |
| **Échéance réglementaire** | Lundi 20 mars 2028, 23 h 10 |

---

## 1. Entité et contacts

Mêmes informations que l'alerte précoce (HydroRégie, entité essentielle, secteur eau potable, référence NIS2-EE-2026-04512).
Point de contact : RSSI — rssi@hydroregie.example — +33 4 00 00 00 01 (24 h/24).

---

## 2. Mise à jour de l'alerte précoce

| Information | Alerte précoce (18/03) | Mise à jour (19/03) |
|---|---|---|
| Acte malveillant | Suspecté | **Confirmé** : intrusion préméditée, rançongiciel, exfiltration de données, demande de rançon |
| Impact transfrontalier | Non identifié | **Toujours non identifié** : aucun abonné ni système hors de France concerné |
| Exfiltration de données | Suspectée | **Confirmée** : environ 41 Go sortis vers un hébergeur externe (constat du 18/03, 16 h 40) |
| Impact sur l'eau potable | Aucun | **Aucun** : production, distribution et qualité non affectées |

---

## 3. Évaluation initiale

| Critère | Évaluation |
|---|---|
| Gravité globale | **Élevée** pour le système d'information de gestion et les données ; **faible** pour l'environnement industriel |
| Critère d'incident important (art. 23 §3) | Rempli sur les deux critères : perturbation opérationnelle grave de l'entité, et dommages considérables pour d'autres personnes (données des abonnés) |
| Niveau de crise interne | N3 (cellule de crise active) |
| Durée estimée de l'indisponibilité du SI de gestion | Plusieurs jours ; rétablissement progressif prévu à partir du 21/03 |

---

## 4. Description factuelle

**Périmètre touché.**
- 94 serveurs sur 156 et 212 postes sur 240 du système d'information de gestion, chiffrés ou isolés.
- Services indisponibles : annuaire, messagerie, facturation, relation usagers.
- Environnement industriel (production, traitement, distribution, sites distants) : aucune atteinte constatée. Vérification de l'intégrité effectuée le 17/03 à 23 h 20, puis des sites distants le 18/03 à 14 h 10.

**Données concernées.** Base des abonnés : environ 190 000 abonnés ; coordonnées, numéro de contrat, historique de consommation ; coordonnées bancaires (IBAN) pour environ 112 000 d'entre eux. Pas de donnée de santé ni de donnée sur la qualité de l'eau.

**Tentative vers l'environnement industriel.** Vendredi 17/03, 22 h 31 et 22 h 47 : quatorze tentatives de connexion d'un serveur du SI de gestion vers l'environnement industriel, bloquées par le pare-feu, puis six tentatives d'authentification sur le point d'accès de télémaintenance, qui ont échoué (second facteur, annuaire distinct).

---

## 5. Chronologie résumée

| Date et heure | Événement |
|---|---|
| Ven. 17/03, 21 h 38 | Déploiement du rançongiciel |
| Ven. 17/03, 21 h 52 | Première détection par la supervision de sécurité |
| Ven. 17/03, 22 h 25 à 22 h 40 | Isolement du SI de gestion, coupure de l'accès Internet sortant, révocation de comptes |
| Ven. 17/03, 23 h 10 | Qualification d'incident important ; activation de la cellule de crise |
| Sam. 18/03, 00 h 40 | Mobilisation d'un prestataire de réponse à incident |
| Sam. 18/03, 12 h 20 | Dépôt de l'alerte précoce |
| Sam. 18/03, 16 h 40 | Confirmation de l'exfiltration de données |
| Sam. 18/03, 18 h 00 | Communiqué public |
| Dim. 19/03, 16 h 00 | Présente notification |

---

## 6. Indicateurs de compromission disponibles

Les éléments ci-dessous sont des indicateurs établis à ce jour, susceptibles d'évoluer. Les condensats de fichiers et la liste complète sont transmis par le prestataire sur demande de l'ANSSI.

| Type | Valeur | Observation |
|---|---|---|
| Adresse IP | 203.0.113.45 | Origine de la session de maintenance détournée |
| Adresse IP | 198.51.100.17 | Destination de l'exfiltration |
| Domaine | cdn-sync.example | Hébergeur du stockage utilisé pour l'exfiltration |
| Fichier | RESTORE_FILES.txt | Note de rançon déposée dans les répertoires chiffrés |
| Extension | .hydrolck | Extension ajoutée aux fichiers chiffrés ; famille non confirmée |
| Méthode | Déploiement par stratégie de groupe depuis un contrôleur de domaine | Mode de propagation |

---

## 7. Mesures prises et en cours

| Mesure | État |
|---|---|
| Isolement du SI de gestion (réseau industriel et Internet) | Réalisé |
| Révocation des comptes suspects, dont un compte de fournisseur | Réalisé |
| Contrôle d'intégrité de l'environnement industriel et des sites distants | Réalisé ; aucune anomalie |
| Préservation des preuves (images, journaux) | Réalisé |
| Réinitialisation des secrets d'authentification | En cours |
| Reconstruction de l'annuaire dans un environnement propre | Démarrage lundi 20/03 |
| Restauration progressive des services (annuaire, messagerie, facturation) | Prévue à partir du 21/03 |
| Surveillance renforcée de l'environnement industriel | En cours |

---

## 8. Impact sur le service et sur les destinataires

| Sujet | Situation |
|---|---|
| Service d'eau potable | Continuité assurée, sans dégradation |
| Abonnés | Services de relation usagers et de facturation indisponibles ; un communiqué public a été diffusé le 18/03 à 18 h 00 ; un numéro d'appel externalisé est en service |
| Données personnelles | Violation en cours de déclaration à la CNIL (RGPD, art. 33) ; information individuelle des personnes en préparation |

---

## 9. Autres démarches engagées

- Déclaration à l'assureur cyber (18/03).
- Information de la tutelle, de la préfecture et de l'agence régionale de santé (18/03), à titre de précaution.
- Dépôt de plainte prévu le lundi 20/03.
- Notification CNIL prévue le lundi 20/03.

---

## 10. Suites prévues

| Étape | Échéance |
|---|---|
| Rapport d'étape sur demande de l'ANSSI | Sur demande |
| Rapport final (description détaillée, cause racine, mesures, impact transfrontalier) | **Au plus tard le mercredi 19 avril 2028, 16 h 00** ; dépôt visé : le mardi 18 avril |

**Assistance demandée à l'ANSSI :** partage d'éventuels indicateurs connus sur le mode opératoire ; aucune autre assistance requise.

---

Dépôt effectué par : le RSSI, point de contact NIS2 d'HydroRégie, après validation du Directeur général.
