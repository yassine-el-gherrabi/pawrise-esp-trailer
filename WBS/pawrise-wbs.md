# 📦 **WBS – Pawrise Care**

*Work Breakdown Structure*

Ce WBS décrit **tous les composants techniques et logiques** nécessaires à la réalisation du projet Pawrise Care, depuis le collier connecté jusqu’aux fonctions d’analyse, l’application utilisateur, l’espace vétérinaire et l’infrastructure.

---

# **1. Pawrise Collar – Hardware Layer**

Composants physiques du collier et éléments embarqués.

## 1.1 Capteurs & Mesures

* 1.1.1 GPS / GNSS
* 1.1.2 Accéléromètre / gyroscope
* 1.1.3 Capteur de température corporelle
* 1.1.4 Cardio / rythme cardiaque (si version avancée)
* 1.1.5 Détection d’activité générale (mouvements, posture)
* 1.1.6 Calibration & Validation des capteurs

## 1.2 Système embarqué

* 1.2.1 Microcontrôleur (MCU)
* 1.2.2 Firmware de collecte
* 1.2.3 Drivers capteurs
* 1.2.4 Gestion de la consommation énergétique

## 1.3 Communication du collier

* 1.3.1 Bluetooth / BLE
* 1.3.2 LTE / NB-IoT / LoRa (selon version prototype)
* 1.3.3 Paquets de données structurés (format Pawrise Data Packet)
* 1.3.4 Chiffrement minimal (clé embarquée ou token)

## 1.4 Boîtier & Conception Physique

* 1.4.1 Conception du boîtier (matériaux, ergonomie)
* 1.4.2 Normes de résistance (ex: IP67 pour l'étanchéité à l'eau et à la poussière)
* 1.4.3 Résistance aux chocs et à l'usure
* 1.4.4 Système d'attache / sécurité du collier

## 1.5 Batterie & Autonomie

* 1.5.1 Batterie (capacité, technologie)
* 1.5.2 Circuit de recharge
* 1.5.3 Optimisation firmware de la consommation
    * 1.5.3.1 Modes de veille (deep sleep)
    * 1.5.3.2 Fréquence de transmission adaptative
    * 1.5.3.3 Gestion intelligente des capteurs (activation/désactivation)
* 1.5.4 Monitoring de la batterie & alertes de niveau bas

---

# **2. Collector & Firmware Communication Layer**

Gestion de la transmission des données du collier vers l’écosystème Pawrise.

## 2.1 Acquisition de données

* 2.1.1 Lecture périodique des capteurs
* 2.1.2 Mise en tampon local (edge storage)
* 2.1.3 Détection d’événements (inactivité prolongée, variations brusques)

## 2.2 Transmission & Protocoles

* 2.2.1 Synchronisation Bluetooth (mode basse consommation)
* 2.2.2 Mode data cellulaire (si activé)
* 2.2.3 Formatage JSON / binaire
* 2.2.4 Retry, fallback, resend

## 2.3 Sécurité

* 2.3.1 Authentification du collier
* 2.3.2 Intégrité des messages
* 2.3.3 Horodatage fiable

---

# **3. Backend & API Platform**

Cœur serveur permettant la réception, le stockage et l’exploitation des données.

## 3.1 Ingestion des données

* 3.1.1 API d’ingestion capteurs
* 3.1.2 Pipeline normalisation des données
* 3.1.3 Gestion des retards / doublons
* 3.1.4 Webhooks / callbacks internes

## 3.2 Stockage & Modélisation

* 3.2.1 Base de données time-series
* 3.2.2 Stockage historique long terme
* 3.2.3 Données agrégées (journalières, hebdo)

## 3.3 API App & Vet

* 3.3.1 Endpoints utilisateurs (dashboard, santé, GPS)
* 3.3.2 Endpoints vétérinaires (historique structuré)
* 3.3.3 Endpoints pour notifications intelligentes

## 3.4 Administration

* 3.4.1 Comptes & permissions
* 3.4.2 Gestion des animaux & propriétaires
* 3.4.3 Paramétrage des règles d’analyse

---

# **4. Pawrise Care Engine – IA & Analyse**

Moteur d’interprétation des données et de détection préventive.

## 4.1 Prétraitement des données

* 4.1.1 Nettoyage & smoothing
* 4.1.2 Agrégation temporelle
* 4.1.3 Détection d’anomalies simples

## 4.2 Analyse comportementale

* 4.2.1 Modèle d’activité quotidienne
* 4.2.2 Analyse du sommeil
* 4.2.3 Détection baisse / hausse inhabituelle activité
* 4.2.4 Analyse variations constantes corporelles

## 4.3 Analyse santé contextuelle

* 4.3.1 Règles vétérinaires codifiées (expert system)
* 4.3.2 Recommandations contextualisées
* 4.3.3 Seuils d’alerte adaptatifs (âge, race, antécédents)

## 4.4 Chat IA & expertise

* 4.4.1 IA de compréhension (LLM avec RAG sur corpus vétérinaire et données Pawrise)
* 4.4.2 Explications pédagogiques des observations
* 4.4.3 Escalade vers vétérinaires partenaires
* 4.4.4 Génération de rapport préliminaire pour consultation

## 4.5 Export vétérinaire

* 4.5.1 Rapport PDF structuré
* 4.5.2 Version numérique (JSON / HL7-like)
* 4.5.3 Vue chronologique médicale

---

# **5. Mobile App – Propriétaire animal**

Application principale pour le suivi quotidien.

## 5.1 Écran Bien-être

* 5.1.1 Score bien-être global
* 5.1.2 Activité du jour
* 5.1.3 Qualité du sommeil
* 5.1.4 Constantes corporelles

## 5.2 Localisation

* 5.2.1 Carte GPS temps réel
* 5.2.2 Zones sécurisées (geofencing)
* 5.2.3 Alertes de sortie / entrée zone

## 5.3 Notifications & alertes

* 5.3.1 Prévention (signaux faibles)
* 5.3.2 Alerte santé anormale
* 5.3.3 Rappels (vaccins, traitements, habitudes)

## 5.4 Chat & accompagnement

* 5.4.1 Chat IA intelligent
* 5.4.2 Historique des échanges
* 5.4.3 Offramp vers vétérinaire partenaire

---

# **6. Vet Portal – Interface Vétérinaire**

Espace dédié aux professionnels de santé animale.

## 6.1 Vue patient

* 6.1.1 Profil animal (âge, race, historique)
* 6.1.2 Historique complet des données brutes
* 6.1.3 Historique synthétique / courbes

## 6.2 Analyse professionnelle

* 6.2.1 Accès aux alertes générées par Pawrise Care
* 6.2.2 Lecture du rapport automatique
* 6.2.3 Notes vétérinaire

## 6.3 Collaboration

* 6.3.1 Échanges contextualisés avec le propriétaire
* 6.3.2 Recommandations validées médicalement
* 6.3.3 Suivi longitudinal

---

# **7. Infrastructure & Ops**

Support technique pour l’exécution du système.

## 7.1 Hébergement

* 7.1.1 Backend cloud
* 7.1.2 Conteneurisation (Docker)
* 7.1.3 Scalabilité API

## 7.2 Monitoring

* 7.2.1 Logs système
* 7.2.2 Suivi performances API
* 7.2.3 Alertes internes

## 7.3 CI/CD

* 7.3.1 Tests automatiques
* 7.3.2 Build mobile
* 7.3.3 Déploiements

---

# **8. Data, Privacy & Compliance**

Gestion responsable des données et conformité.

## 8.1 Protection des données

* 8.1.1 Anonymisation partielle
* 8.1.2 Consentement du propriétaire
* 8.1.3 Sécurisation du transport et stockage

## 8.2 Transparence & éthique

* 8.2.1 Pas de diagnostic automatique
* 8.2.2 Explicabilité des décisions IA
* 8.2.3 Traçabilité des recommandations

---

# **9. Business & User Lifecycle**

Processus liés à l'acquisition, la gestion et le support des utilisateurs.

## 9.1 Onboarding & Appairage

* 9.1.1 Création de compte utilisateur
* 9.1.2 Processus d'appairage du collier (BLE)
* 9.1.3 Création du profil de l'animal

## 9.2 Gestion de l'abonnement & Facturation

* 9.2.1 Intégration passerelle de paiement (Stripe, etc.)
* 9.2.2 Gestion des différents plans d'abonnement
* 9.2.3 Suivi des statuts de paiement et facturation

## 9.3 Support Client

* 9.3.1 Outil de ticketing / support intégré
* 9.3.2 Base de connaissances (FAQ)

## 9.4 Gestion du matériel (Provisioning)

* 9.4.1 Activation et association des colliers
* 9.4.2 Gestion du cycle de vie du matériel (remplacement, fin de vie)

## 9.5 Partenaires vétérinaires

* 9.5.1 Gestion du réseau de vétérinaires partenaires
* 9.5.2 Attribution des consultations
* 9.5.3 Métriques de performance et satisfaction
