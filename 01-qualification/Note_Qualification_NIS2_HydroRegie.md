# Note de qualification réglementaire NIS2 — HydroRégie

**Bloc 1 — Qualification de l'entité au regard de la directive NIS2**
**Destinataires :** Direction générale, DSI, secrétariat général
**Objet :** Déterminer le statut réglementaire d'HydroRégie au titre de la directive (UE) 2022/2555 (NIS2)

---

## 1. Identification de l'entité

| Élément | Valeur |
|---|---|
| Raison sociale | HydroRégie |
| Statut juridique | Régie directe (établissement public), rattachée à une intercommunalité |
| Activité | Production, traitement et distribution d'eau potable |
| Zone desservie | Bassin de vie de 450 000 habitants |
| Effectif | ≈ 200 agents |
| Chiffre d'affaires / budget annuel | ≈ 75 M€ |
| Bilan annuel (actif net) | Non communiqué à ce stade — présumé élevé compte tenu du patrimoine réseau (canalisations, usines de traitement, réservoirs) |
| Architecture SI | IT (gestion) et OT (supervision industrielle) non cloisonnés |
| Statut confirmé par l'autorité nationale | Entité essentielle (courrier reçu) |

---

## 2. Qualification sectorielle

La directive NIS2 répartit les secteurs d'activité en deux annexes :
- **Annexe I** — secteurs hautement critiques → entités **essentielles**
- **Annexe II** — autres secteurs critiques → entités **importantes**

Le secteur 6 de l'Annexe I, *« Eau potable »*, couvre les *« fournisseurs et distributeurs d'eaux destinées à la consommation humaine »* (au sens de la directive (UE) 2020/2184), à l'exclusion des distributeurs pour lesquels cette activité serait accessoire.

**Application à HydroRégie :** l'activité de production et de distribution d'eau potable constitue l'objet social exclusif de la régie. HydroRégie relève donc sans ambiguïté du secteur 6 de l'**Annexe I**, et non de l'Annexe II.

---

## 3. Qualification par la taille

NIS2 (art. 3) s'appuie sur la recommandation 2003/361/CE pour distinguer les catégories d'entreprise :

| Critère | Seuil « grande entreprise » (→ essentielle) | Seuil « moyenne entreprise » (→ importante) | Situation HydroRégie |
|---|---|---|---|
| Effectif | ≥ 250 salariés | ≥ 50 salariés | ≈ 200 — n'atteint pas seul ce seuil |
| Chiffre d'affaires annuel | > 50 M€ **et** bilan > 43 M€ | > 10 M€ (CA ou bilan) | ≈ 75 M€ — dépasse le seuil de 50 M€ |
| Bilan annuel | > 43 M€ | > 10 M€ | Présumé élevé (actifs réseau) — à confirmer |

**Point d'attention méthodologique :** l'effectif d'HydroRégie (≈ 200) ne suffit pas, seul, à atteindre le seuil de la « grande entreprise » (250 salariés). Toutefois, le critère financier alternatif — chiffre d'affaires supérieur à 50 M€ **et** bilan supérieur à 43 M€ — est cumulatif avec l'effectif dans la définition (l'un ou l'autre suffit). Compte tenu de la nature capitalistique de l'activité (réseau de canalisations, usines de traitement, réservoirs), le bilan d'HydroRégie dépasse très vraisemblablement 43 M€. **Sous cette hypothèse, à vérifier avec les données comptables réelles, HydroRégie est classée « grande entreprise »** au sens de la recommandation 2003/361/CE, indépendamment de son effectif.

---

## 4. Voie de qualification indépendante de la taille

Indépendamment du calcul de taille, l'article 3 de NIS2 permet — et dans certains cas impose — de qualifier une entité d'essentielle **quelle que soit sa taille**, notamment lorsque :
- elle est l'**unique fournisseur** d'un service essentiel au maintien d'activités sociétales ou économiques critiques dans un État membre ou une région ;
- une perturbation du service pourrait avoir un **impact significatif sur la santé, la sécurité ou la sûreté publiques**.

HydroRégie, en tant que régie assurant seule la distribution d'eau potable pour 450 000 habitants, répond à ces deux critères de façon autonome : une interruption prolongée du service aurait un impact direct sur la santé publique, sans alternative de substitution rapide pour les usagers concernés.

*Remarque complémentaire :* dans la transposition française, les établissements publics à caractère industriel et commercial (EPIC) sont automatiquement qualifiés d'entités essentielles. HydroRégie ayant été positionnée comme régie directe (et non EPIC), ce fondement spécifique n'est pas mobilisé ici, mais mérite d'être vérifié si le statut juridique définitif de la régie évolue.

---

## 5. Statut retenu

| | |
|---|---|
| **Statut NIS2** | **Entité essentielle (EE)** |
| **Fondement** | (a) Secteur Annexe I (eau potable) + classification « grande entreprise » par le critère financier ; (b) caractère critique intrinsèque du service, indépendant de la taille |
| **Confirmation externe** | Courrier de l'autorité nationale (ANSSI) confirmant le statut d'entité essentielle |

Les deux fondements convergent vers la même conclusion, ce qui sécurise la qualification même si l'un des deux critères venait à être contesté ou révisé (par exemple si le bilan réel s'avérait inférieur à 43 M€).

---

## 6. Obligations associées au statut d'entité essentielle

| Domaine | Obligation | Référence |
|---|---|---|
| Gouvernance | Formation cyber de l'organe de direction ; approbation et supervision des mesures de gestion des risques ; responsabilité personnelle des dirigeants en cas de manquement | Art. 20 |
| Mesures de gestion des risques | Mise en œuvre des 10 domaines minimaux : analyse de risques, gestion des incidents, continuité d'activité (PCA/PRA), sécurité de la chaîne d'approvisionnement, sécurité de l'acquisition/développement/maintenance, évaluation de l'efficacité des mesures, cyber-hygiène et formation, cryptographie, sécurité RH et gestion des accès, authentification renforcée | Art. 21 |
| Notification des incidents | Alerte précoce sous 24h, notification sous 72h, rapport final sous 1 mois | Art. 23 |
| Enregistrement | Inscription auprès de l'ANSSI via MonEspaceNIS2 | Art. 3 §5 |
| Supervision | Contrôle **ex ante et ex post** (audits, inspections, demandes d'information) — régime renforcé par rapport aux entités importantes (contrôle ex post uniquement) | Chap. VII |
| Sanctions | Jusqu'à 10 M€ ou 2 % du chiffre d'affaires mondial (le montant le plus élevé) | Art. 34 |

---

## 7. Conclusion

HydroRégie est qualifiée **entité essentielle** au titre de la directive NIS2, sur un double fondement convergent : son appartenance au secteur hautement critique de l'eau potable combinée à une classification de « grande entreprise » par le critère financier, et le caractère intrinsèquement critique de son activité de distribution d'eau potable pour 450 000 habitants. Ce statut implique le niveau d'exigence le plus élevé prévu par NIS2, tant en matière de gouvernance que de supervision et de sanctions, et constitue le point de départ des Blocs 2 à 4 (analyse d'écart, architecture IT/OT, gestion de crise).

**Point à vérifier avant rendu final :** confirmer le bilan annuel réel d'HydroRégie (>43 M€) pour sécuriser pleinement la voie de qualification par la taille ; à défaut, la voie de qualification indépendante de la taille (section 4) reste suffisante à elle seule.
