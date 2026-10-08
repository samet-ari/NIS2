# Violation de données personnelles — RGPD, articles 33 et 34

**Pièce 4 — Notification à la CNIL (72 h), complément, et information des personnes concernées**
**Lien avec NIS2 :** même incident que les pièces 1 à 3, mais autre régime, autre autorité, autre point de départ (voir la chronologie, section 2).

| | |
|---|---|
| **Destinataire** | CNIL, téléservice de notification des violations de données personnelles |
| **Prise de connaissance de la violation** | Samedi 18 mars 2028, 16 h 40 |
| **Échéance des 72 h** | Mardi 21 mars 2028, 16 h 40 |
| **Notification initiale déposée** | Lundi 20 mars 2028, 10 h 30 (marge 30 h 10) |
| **Complément déposé** | Mercredi 22 mars 2028, 10 h 00 |
| **Information des personnes** | Jeudi 23 mars 2028, 09 h 00 |
| **Référence interne** | HYDRO-CRISE-2028-03-17 / registre des violations n° 2028-003 |

---

## Partie A — Notification initiale (lundi 20 mars 2028, 10 h 30)

### A.1 Responsable de traitement et contact

| Champ | Valeur |
|---|---|
| Organisme | HydroRégie, régie directe (établissement public) |
| Activité | Production et distribution d'eau potable |
| Délégué à la protection des données | dpo@hydroregie.example — +33 4 00 00 00 03 |
| Notification à titre | Responsable de traitement ; aucun sous-traitant n'est à l'origine de la violation |

### A.2 Nature de la violation

| Champ | Valeur |
|---|---|
| Type | Atteinte à la **confidentialité** (accès et exfiltration par un tiers non autorisé) et à la **disponibilité** (chiffrement par rançongiciel) |
| Cause | Acte externe malveillant (rançongiciel avec exfiltration) |
| Début estimé | Au plus tard le 14 mars 2028 (première sortie de données observée) ; la compromission initiale est antérieure et en cours de datation |
| Date de découverte | Vendredi 17 mars 2028 pour l'attaque ; samedi 18 mars 2028, 16 h 40 pour la confirmation de l'exfiltration de données personnelles |
| Violation toujours en cours | Non. Les accès de l'attaquant sont coupés depuis le 17/03 à 22 h 40 |
| Circonstances | Détournement d'une session de maintenance d'un fournisseur, déplacement dans le SI de gestion, extraction de la base des abonnés, puis chiffrement |

### A.3 Personnes et données concernées

| Champ | Valeur |
|---|---|
| Catégories de personnes | Abonnés particuliers au service de l'eau |
| Nombre de personnes | Environ 190 000 (estimation à confirmer) |
| Catégories de données | Nom, adresse, téléphone, courriel, numéro de contrat, historique de consommation ; coordonnées bancaires (IBAN) pour une partie des abonnés (estimation : 112 000) |
| Volume | Environ 41 Go de données extraites |
| Données sensibles (art. 9), mineurs identifiés | Non |
| Données chiffrées ou protégées | Non : la base était exploitable en l'état |
| Personnes établies hors de France | Non identifiées |

### A.4 Conséquences probables

| Risque | Appréciation |
|---|---|
| Hameçonnage et escroqueries ciblées (usage de l'historique de consommation et du contrat) | Élevé |
| Usurpation d'identité (identité complète, adresse, contact) | Élevé |
| Fraude au prélèvement (IBAN associé à l'identité) | Moyen à élevé |
| Atteinte à la disponibilité du service (facturation, relation usagers) | Modérée, temporaire |
| Atteinte à la sécurité du service d'eau | Aucune |

**Conclusion de l'évaluation :** risque **élevé** pour les droits et libertés des personnes, justifiant la notification à la CNIL et l'information individuelle (art. 34).

### A.5 Mesures prises et prévues

- Isolement du SI de gestion, coupure des accès sortants, révocation des comptes compromis.
- Conservation des preuves, investigation par un prestataire de réponse à incident.
- Reconstruction du SI dans un environnement propre, réinitialisation de tous les secrets.
- Surveillance du site de fuite et demande de retrait à l'hébergeur.
- Plainte déposée le 20/03.
- Information des personnes concernées prévue dès confirmation du périmètre, avec conseils pratiques.
- Renforcement de l'authentification des comptes externes et de la détection (voir plan d'actions du rapport final).

### A.6 Autres autorités informées

ANSSI au titre de NIS2 (alerte précoce du 18/03, notification du 19/03). Services d'enquête (plainte du 20/03).

### A.7 Notification en plusieurs temps

La notification est initiale. L'investigation n'est pas terminée, notamment la datation de la compromission initiale, le périmètre exact des données et l'existence éventuelle de publications. Des compléments seront adressés sans retard injustifié (art. 33, §4).

---

## Partie B — Complément de notification (mercredi 22 mars 2028, 10 h 00)

| Élément | Information nouvelle |
|---|---|
| Publication des données | Le **21/03 à 09 h 00**, l'attaquant a publié un échantillon de la base sur un site de fuite et menace de diffuser le reste. Une demande de retrait est en cours auprès de l'hébergeur |
| Personnes concernées | **Confirmées : environ 190 000 abonnés**, dont environ 112 000 avec IBAN et environ 171 000 avec adresse de courriel |
| Début de la compromission | **Mardi 7 mars 2028**, par détournement de la session de maintenance d'un fournisseur ; exfiltration observée sur les nuits du 14 au 16 mars |
| Gravité | Risque élevé **confirmé et aggravé** par la publication |
| Information des personnes | Décision prise le 22/03 à 14 h 00 ; envoi le 23/03 à 09 h 00 |

---

## Partie C — Information des personnes concernées (jeudi 23 mars 2028)

Envoi par courriel via une plateforme externe (environ 171 000 adresses), et par courrier postal pour les autres abonnés dans les dix jours.

> **Objet : Incident de sécurité informatique — vos données personnelles sont concernées**
>
> Madame, Monsieur,
>
> Le 17 mars 2028, HydroRégie a subi une attaque informatique criminelle. **La production et la distribution de l'eau, ainsi que sa qualité, n'ont pas été affectées.** En revanche, des données personnelles d'abonnés ont été dérobées, et vous en faites partie.
>
> **Ce qui s'est passé.** Des personnes malveillantes sont entrées dans notre système de gestion et ont copié des données. Une partie de ces données a été publiée sur Internet par les auteurs de l'attaque.
>
> **Les données concernées.** Votre nom, votre adresse, votre numéro de téléphone, votre adresse de courriel, votre numéro de contrat et votre historique de consommation. Si vous payez par prélèvement, votre IBAN est également concerné. Les mots de passe ne sont pas concernés.
>
> **Les risques.** Vous pouvez recevoir des messages d'hameçonnage ou des appels frauduleux qui utilisent ces informations pour paraître authentiques. Votre IBAN, associé à votre identité, peut servir à tenter des prélèvements non autorisés.
>
> **Ce que nous avons fait.** Nous avons coupé l'accès des attaquants, rétabli nos systèmes à partir de sauvegardes saines, informé l'ANSSI et la CNIL, et déposé plainte.
>
> **Ce que nous vous recommandons.**
> - Soyez vigilant face aux courriels, SMS et appels qui évoquent votre contrat d'eau ou vos factures. HydroRégie ne vous demandera jamais vos coordonnées bancaires ni un paiement par courriel ou par SMS.
> - Vérifiez vos relevés bancaires. En cas de prélèvement que vous n'avez pas autorisé, contactez votre banque pour le contester.
> - N'ouvrez pas les pièces jointes et ne cliquez pas sur les liens de messages suspects.
>
> **Vos questions.** Un numéro d'appel gratuit est disponible du lundi au samedi : 0 800 00 00 00. Notre délégué à la protection des données est joignable à dpo@hydroregie.example. Vous disposez des droits d'accès, de rectification et d'opposition prévus par le RGPD, et vous pouvez introduire une réclamation auprès de la CNIL (www.cnil.fr).
>
> Nous regrettons sincèrement cet incident et mesurons la gêne qu'il vous occasionne.
>
> Le Directeur général d'HydroRégie

---

## Partie D — Registre des violations (art. 33, §5)

| Champ | Valeur |
|---|---|
| Faits | Voir parties A et B |
| Effets | Perte de confidentialité, indisponibilité temporaire |
| Mesures correctives | Voir parties A.5 et rapport final NIS2, section 7 |
| Notification CNIL | Oui : initiale le 20/03, complément le 22/03 |
| Information des personnes | Oui : 23/03 |
| Décision de ne pas notifier | Sans objet |
