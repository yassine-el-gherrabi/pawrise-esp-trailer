# 📘 **Pawrise Care – High-Level Functions**

*Fonctions associées au WBS*

Ce document décrit les **fonctions principales** associées à chaque grande composante du WBS.
Il explique non pas *comment* le système est construit, mais *ce qu’il doit accomplir* pour remplir sa mission.

---

# **1. Pawrise Collar – Hardware Layer**

## **1.1 Capteurs & Mesures — Fonctions**

* Mesurer et enregistrer la position GPS de l’animal.
* Détecter l’activité, l’immobilité, les mouvements brusques.
* Mesurer la température et éventuellement le rythme cardiaque.
* Offrir des mesures précises et régulières pour permettre l’analyse comportementale.

## **1.2 Système embarqué — Fonctions**

* Collecter les données capteurs en temps réel.
* Optimiser la consommation énergétique du collier.
* Exécuter un firmware fiable pour lire et structurer les données.
* Assurer une disponibilité continue du système embarqué.

## **1.3 Communication du collier — Fonctions**

* Transmettre les données du collier vers l’application via BLE ou réseau cellulaire.
* Garantir une synchronisation fiable même en cas de perte temporaire de signal.
* Sécuriser l’envoi des données (authentification et intégrité).
* Standardiser le format des messages envoyés au backend.

## **1.4 Boîtier & Conception Physique — Fonctions**

* Protéger le système interne contre l’eau, la poussière et les chocs.
* Offrir un confort optimal pour l’animal (poids, forme, matériau).
* Assurer l’intégration stable des capteurs dans le boîtier.
* Garantir la résistance à une utilisation prolongée en extérieur.

## **1.5 Batterie & Autonomie — Fonctions**

* Assurer une autonomie maximale pour le collier.
* Permettre une recharge simple et rapide.
* Adapter la consommation en fonction de l'usage et de l'environnement.
* Informer l'utilisateur sur le niveau de batterie restant.

---

# **2. Collector & Firmware Communication Layer**

## **2.1 Acquisition de données — Fonctions**

* Récupérer les données brutes des capteurs à intervalles réguliers.
* Détecter des événements significatifs (inactivité anormale, agitation, etc.).
* Conserver localement les données en cas de perte de connexion.

## **2.2 Transmission & Protocoles — Fonctions**

* Assurer une synchronisation fluide avec l’app mobile.
* Utiliser un protocole robuste pour envoyer les données au backend.
* Garantir la transmission même en mode basse consommation.
* Réessayer automatiquement en cas d’échec d’envoi.

## **2.3 Sécurité — Fonctions**

* Vérifier l’identité du collier avant transmission.
* Garantir que les données reçues n’ont pas été altérées.
* Assurer un horodatage exact pour l’analyse comportementale.

---

# **3. Backend & API Platform**

## **3.1 Ingestion des données — Fonctions**

* Recevoir les données brutes envoyées par le collier.
* Normaliser, filtrer et nettoyer ces données pour stockage.
* Gérer les doublons, retards ou incohérences.
* Propager les données pertinentes vers les modules d’analyse.

## **3.2 Stockage & Modélisation — Fonctions**

* Enregistrer les données capteurs sous forme de séries temporelles.
* Maintenir un historique long terme pour l’analyse vétérinaire.
* Générer des données agrégées pour simplifier les calculs.

## **3.3 API App & Vet — Fonctions**

* Fournir aux utilisateurs les données nécessaires (GPS, activité, santé).
* Fournir aux vétérinaires une vue structurée de l’historique santé.
* Alimenter l’app mobile avec les alertes et recommandations.

## **3.4 Administration — Fonctions**

* Gérer les comptes utilisateurs et les animaux associés.
* Permettre la configuration et mise à jour des règles d’analyse.
* Assurer un contrôle d’accès adapté entre propriétaire et vétérinaire.

---

# **4. Pawrise Care Engine – IA & Analyse**

## **4.1 Prétraitement des données — Fonctions**

* Nettoyer les données capteurs (bruit, valeurs aberrantes).
* Regrouper les données en fenêtres temporelles cohérentes.
* Détecter des signaux simples (inactivité prolongée, hausse température).

## **4.2 Analyse comportementale — Fonctions**

* Établir un modèle de comportement normal propre à chaque animal.
* Détecter des anomalies d’activité ou de sommeil.
* Mesurer l’évolution de la vitalité au jour le jour.

## **4.3 Analyse santé contextuelle — Fonctions**

* Appliquer des règles vétérinaires validées (expert system).
* Contextualiser l’état de l’animal selon race, âge, historique.
* Identifier les écarts nécessitant une vigilance ou une action.

## **4.4 Chat IA & Expertise — Fonctions**

* Résumer les données en explications compréhensibles pour l’utilisateur.
* Répondre aux questions en se basant sur les données de l'animal et une base de connaissances vétérinaires (LLM avec RAG).
* Escalader automatiquement vers un vétérinaire partenaire en cas de doute.
* Préparer un rapport synthétique pour consultation médicale.

## **4.5 Export vétérinaire — Fonctions**

* Générer un rapport PDF clair et structuré.
* Offrir un export numérique standardisé pour usage vétérinaire.
* Organiser les données dans une chronologie médicale lisible.

---

# **5. Mobile App – Propriétaire animal**

## **5.1 Écran Bien-être — Fonctions**

* Afficher un score global de bien-être.
* Présenter l’activité, le sommeil et les constantes.
* Offrir une vue simple et compréhensible de l’état actuel de l’animal.

## **5.2 Localisation — Fonctions**

* Montrer la position GPS en temps réel.
* Définir des zones sécurisées et alerter si l’animal en sort.
* Afficher l’historique des déplacements.

## **5.3 Notifications & Alertes — Fonctions**

* Prévenir en cas de signaux faibles (fatigue, stress, inactivité).
* Alerter si un comportement anormal apparaît.
* Rappeler les soins réguliers (vaccins, traitements).

## **5.4 Chat & Accompagnement — Fonctions**

* Permettre l’accès au chat IA pour poser des questions.
* Permettre une interaction fluide entre utilisateur et expert.
* Faciliter la mise en relation avec un vétérinaire partenaire si nécessaire.

---

# **6. Vet Portal – Interface Vétérinaire**

## **6.1 Vue patient — Fonctions**

* Regrouper les informations médicales essentielles de l’animal.
* Fournir un historique détaillé des données capteurs.
* Mettre en avant les tendances importantes (activité, sommeil, constantes).

## **6.2 Analyse professionnelle — Fonctions**

* Permettre au vétérinaire de consulter les alertes générées.
* Lire un rapport automatique et le compléter.
* Ajouter des notes professionnelles au dossier.

## **6.3 Collaboration — Fonctions**

* Faciliter le dialogue entre propriétaire et vétérinaire.
* Proposer des recommandations ciblées.
* Suivre l’évolution de l’état de l’animal dans le temps.

---

# **7. Infrastructure & Ops**

## **7.1 Hébergement — Fonctions**

* Exécuter les services backend de manière fiable et scalable.
* gérer les environnements de développement, production, test.
* Garantir la disponibilité du système.

## **7.2 Monitoring — Fonctions**

* Surveiller les performances et l’usage des APIs.
* Détecter rapidement les anomalies système.
* Tracer les erreurs pour garantir la stabilité.

## **7.3 CI/CD — Fonctions**

* Automatiser tests et déploiements.
* Gérer les versions des applications.
* Faciliter la livraison continue des fonctionnalités.

---

# **8. Data, Privacy & Compliance**

## **8.1 Protection des données — Fonctions**

* Sécuriser les données personnelles des utilisateurs.
* Assurer le chiffrement des données en transit et au repos.
* Respecter les obligations légales (RGPD).

## **8.2 Transparence & Éthique — Fonctions**

* Garantir que l’IA n’émet jamais de diagnostic médical.
* Fournir des explications lisibles des recommandations.
* Assurer une traçabilité claire de toutes les alertes et analyses.

---

# **9. Business & User Lifecycle — Fonctions**

## **9.1 Onboarding & Appairage — Fonctions**

* Permettre une création de compte simple et sécurisée.
* Guider l’utilisateur pour connecter son collier à l’application.
* Faciliter la saisie des informations de l’animal (profilage).

## **9.2 Gestion de l'abonnement & Facturation — Fonctions**

* Gérer les abonnements et les paiements de manière transparente.
* Permettre à l’utilisateur de consulter ses factures et son statut.
* Assurer la sécurité des transactions financières.

## **9.3 Support Client — Fonctions**

* Fournir un moyen simple de contacter le support.
* Offrir des réponses rapides aux questions fréquentes.

## **9.4 Gestion du matériel (Provisioning) — Fonctions**

* Activer un nouveau collier de manière sécurisée.
* Gérer le remplacement ou la désactivation d’un collier.

## **9.5 Partenaires vétérinaires — Fonctions**
* Permettre l’onboarding d’un vétérinaire partenaire.
* Assurer l’attribution des demandes selon disponibilité.
* Garantir un retour d’expérience utilisateur/vétérinaire.
