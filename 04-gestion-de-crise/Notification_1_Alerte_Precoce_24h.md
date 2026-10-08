# Alerte précoce — Directive NIS2, article 23, paragraphe 4, point a

**Pièce 1 — Délai : 24 heures après la prise de connaissance de l'incident important**
**Marquage :** TLP:AMBER — diffusion restreinte à l'ANSSI et aux destinataires désignés

| | |
|---|---|
| **Destinataire** | ANSSI — CSIRT national (autorité compétente NIS2) |
| **Date et heure de dépôt** | Samedi 18 mars 2028, 12 h 20 (heure de Paris) |
| **Type de déclaration** | Alerte précoce (première déclaration) |
| **Référence interne** | HYDRO-CRISE-2028-03-17 |
| **Échéance réglementaire** | Samedi 18 mars 2028, 23 h 10 |

---

## 1. Entité déclarante

| Champ | Valeur |
|---|---|
| Dénomination | HydroRégie |
| Forme juridique | Régie directe (établissement public) |
| Secteur et sous-secteur | Annexe I — secteur 6, eau potable |
| Qualité au titre de NIS2 | Entité essentielle (statut confirmé par l'autorité nationale) |
| Référence d'enregistrement | NIS2-EE-2026-04512 (référence fictive du cas) |
| Population desservie | 450 000 habitants |
| Point de contact principal | RSSI — rssi@hydroregie.example — +33 4 00 00 00 01 (24 h/24) |
| Point de contact suppléant | DSI — dsi@hydroregie.example — +33 4 00 00 00 02 |

---

## 2. Incident

| Champ | Valeur |
|---|---|
| Heure de la première détection technique | Vendredi 17 mars 2028, 21 h 52 |
| **Heure de prise de connaissance de l'incident important** | **Vendredi 17 mars 2028, 23 h 10** |
| Nature présumée | Attaque par rançongiciel avec chiffrement des systèmes du SI de gestion ; exfiltration de données suspectée |
| État à l'heure du dépôt | En cours de traitement ; propagation arrêtée par isolement du SI de gestion |

**Résumé factuel.** Le vendredi 17 mars 2028 à 21 h 52, le service de supervision de sécurité a détecté un chiffrement massif de serveurs du système d'information de gestion d'HydroRégie. Le SI de gestion a été isolé des réseaux industriels et d'Internet à partir de 22 h 25. Une tentative de connexion vers l'environnement industriel depuis le SI de gestion a été détectée et a échoué. L'incident a été qualifié d'important à 23 h 10.

---

## 3. Informations requises par l'article 23, paragraphe 4, point a

| Question | Réponse |
|---|---|
| L'incident est-il suspecté d'être dû à des actes illicites ou malveillants ? | **Oui.** Rançongiciel actif, avec note de rançon présente sur les systèmes touchés |
| L'incident est-il susceptible d'avoir un impact transfrontalier ? | **Non identifié à ce stade.** L'entité ne dessert que le territoire national, et aucun système ni abonné établi hors de France n'est connu comme affecté |

---

## 4. Impact connu à ce stade

| Domaine | Situation |
|---|---|
| Production et distribution d'eau potable | **Non affectées.** Les réseaux industriels sont séparés du SI de gestion ; les sites fonctionnent en conduite normale |
| Qualité de l'eau | **Non affectée.** Contrôle sanitaire maintenu |
| SI de gestion | Fortement dégradé : annuaire, messagerie, facturation, relation usagers indisponibles |
| Données | Exfiltration suspectée, en cours de qualification. Une déclaration relative aux données personnelles sera, le cas échéant, adressée séparément à la CNIL |

---

## 5. Mesures déjà prises

- Isolement du SI de gestion des réseaux industriels et d'Internet (22 h 25 à 22 h 40).
- Révocation des comptes suspects, dont un compte de maintenance d'un fournisseur.
- Vérification de l'intégrité de l'environnement industriel : aucune anomalie constatée.
- Préservation des éléments de preuve (machines isolées, journaux).
- Mobilisation de la cellule de crise et d'un prestataire de réponse à incident.
- Information de la tutelle, de la préfecture et de l'agence régionale de santé, à titre de précaution.

---

## 6. Informations non encore disponibles

Vecteur d'accès initial, date de début de la compromission, volume et nature exacts des données exfiltrées, identification de la famille de rançongiciel. Ces éléments seront précisés dans la notification d'incident des 72 heures.

---

## 7. Suites prévues

| Étape | Échéance |
|---|---|
| Notification d'incident (évaluation initiale, indicateurs de compromission) | Avant le lundi 20 mars 2028, 23 h 10 |
| Réponse à toute demande d'information de l'ANSSI | Sans délai, via le point de contact |
| Rapport final | Un mois après le dépôt de la notification d'incident |

**Assistance demandée à l'ANSSI :** aucune assistance opérationnelle requise à ce stade. L'entité demande un interlocuteur désigné pour l'échange d'indicateurs de compromission.

---

Dépôt effectué par : le RSSI, point de contact NIS2 d'HydroRégie, après validation du Directeur général.
