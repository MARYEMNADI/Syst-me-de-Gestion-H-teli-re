# Système de Gestion Hôtelière

## Description du projet

Ce projet consiste à concevoir et implémenter une base de données relationnelle pour un hôtel. L'objectif est de remplacer les registres papier et les fichiers Excel par une solution centralisée permettant de gérer efficacement les clients, les chambres, les réservations, les paiements et les séjours.

La réalisation du projet s'appuie sur la méthode MERISE pour l'analyse et la modélisation des données, ainsi que sur MySQL pour l'implémentation de la base de données.

---

## Problématique

L'hôtel utilise actuellement des méthodes manuelles de gestion basées sur des registres papier et plusieurs fichiers Excel.

Cette organisation entraîne plusieurs problèmes :

* Informations dispersées et difficiles à retrouver.
* Risque de duplication des données.
* Erreurs dans les réservations.
* Difficulté de suivi des chambres disponibles.
* Gestion manuelle des paiements.
* Production lente des statistiques.
* Perte de temps lors des recherches d'informations.

---

## Objectifs

Les objectifs principaux du système sont :

* Centraliser toutes les données de l'hôtel.
* Faciliter la gestion des clients.
* Assurer le suivi des chambres.
* Gérer les réservations efficacement.
* Enregistrer les paiements.
* Suivre les séjours des clients.
* Produire rapidement des statistiques fiables.
* Garantir l'intégrité et la cohérence des données.

---

## Fonctionnalités

### Gestion des clients

* Ajouter un client.
* Modifier un client.
* Consulter les informations d'un client.

### Gestion des chambres

* Ajouter une chambre.
* Consulter l'état des chambres.
* Mettre à jour la disponibilité.

### Gestion des réservations

* Enregistrer une réservation.
* Modifier une réservation.
* Annuler une réservation.

### Gestion des paiements

* Enregistrer un paiement.
* Consulter l'historique des paiements.

### Gestion des séjours

* Enregistrer les dates de séjour.
* Suivre les entrées et sorties.

### Consultation et statistiques

* Afficher les réservations.
* Générer des rapports et statistiques.

---

## Analyse et conception

### Acteurs

#### Réceptionniste

* Gère les clients.
* Enregistre les réservations.
* Consulte les chambres disponibles.

#### Gestionnaire de l'hôtel

* Consulte les statistiques.
* Contrôle l'activité globale de l'hôtel.

#### Administrateur de base de données

* Gère la base de données.
* Assure la maintenance et la sécurité.

---

### User Stories

* En tant que réceptionniste, je veux enregistrer un client afin de conserver ses informations.
* En tant que réceptionniste, je veux créer une réservation afin de réserver une chambre.
* En tant que réceptionniste, je veux consulter les chambres disponibles afin d'éviter les conflits.
* En tant que réceptionniste, je veux enregistrer un paiement afin de suivre les règlements.
* En tant que gestionnaire, je veux consulter les statistiques afin d'analyser l'activité.
* En tant qu'administrateur, je veux garantir l'intégrité des données afin d'éviter les erreurs.
* En tant que réceptionniste, je veux modifier une réservation afin de répondre aux demandes des clients.
* En tant que réceptionniste, je veux annuler une réservation afin de mettre à jour le planning.
* En tant que gestionnaire, je veux connaître les chambres les plus réservées afin d'améliorer l'offre.
* En tant que gestionnaire, je veux suivre le chiffre d'affaires afin d'évaluer les performances.

---

### Cas d'utilisation

* Gérer les clients.
* Gérer les chambres.
* Gérer les réservations.
* Gérer les paiements.
* Gérer les séjours.
* Consulter les statistiques.
* Générer des rapports.

---

## Modélisation

### MCD (Modèle Conceptuel de Données)

Le MCD contient les entités suivantes :

* CLIENT
* CHAMBRE
* RESERVATION
* PAIEMENT
* SEJOUR

Relations :

* CLIENT effectue RESERVATION
* CHAMBRE concerne RESERVATION
* RESERVATION génère PAIEMENT
* RESERVATION donne lieu à SEJOUR

Cardinalités :

* CLIENT (0,N) ↔ RESERVATION (1,1)
* CHAMBRE (0,N) ↔ RESERVATION (1,1)
* RESERVATION (1,1) ↔ PAIEMENT (0,1)
* RESERVATION (1,1) ↔ SEJOUR (0,1)

---

### MLD (Modèle Logique de Données)

Tables :

#### CLIENT

* id_client (PK)
* nom
* prenom
* telephone
* email

#### CHAMBRE

* id_chambre (PK)
* numero
* type_chambre
* prix_nuit
* statut

#### RESERVATION

* id_reservation (PK)
* date_reservation
* date_arrivee
* date_depart
* statut
* id_client (FK)
* id_chambre (FK)

#### PAIEMENT

* id_paiement (PK)
* date_paiement
* montant
* mode_paiement
* id_reservation (FK)

#### SEJOUR

* id_sejour (PK)
* date_checkin
* date_checkout
* observations
* id_reservation (FK)

---

## Structure de la base de données

| Table       | Description               |
| ----------- | ------------------------- |
| CLIENT      | Informations des clients  |
| CHAMBRE     | Informations des chambres |
| RESERVATION | Gestion des réservations  |
| PAIEMENT    | Gestion des paiements     |
| SEJOUR      | Gestion des séjours       |

---

## Technologies utilisées

* MySQL
* phpMyAdmin
* XAMPP
* MERISE
* Looping

---

## Installation

### 1. Installer XAMPP

Télécharger et installer XAMPP.

### 2. Démarrer les services

Lancer :

* Apache
* MySQL

### 3. Ouvrir phpMyAdmin

Accéder à :

```text
http://localhost/phpmyadmin
```

### 4. Importer la base de données

* Créer une nouvelle base.
* Importer le fichier `database.sql`.

---

## Exécution

Pour exécuter les requêtes SQL :

1. Ouvrir phpMyAdmin.
2. Sélectionner la base `hotel_db`.
3. Cliquer sur l'onglet SQL.
4. Exécuter les requêtes souhaitées.

---

## Requêtes réalisées

* SELECT
* WHERE
* LIKE
* IN
* BETWEEN
* ORDER BY
* GROUP BY
* HAVING
* INNER JOIN
* UPDATE
* DELETE

---

## Statistiques réalisées

* Nombre total de clients.
* Nombre total de chambres.
* Nombre total de réservations.
* Chiffre d'affaires total.
* Paiements par mois.
* Chambres les plus réservées.
* Nombre de réservations par client.
* Taux d'occupation des chambres.

---

## Structure du projet

```text
project/
│
├── database.sql
├── README.md
├── MCD.png
└── MLD.png
```

---

## Auteur

Nom de l'étudiant : ....................................

Formation : Développeur Web et Web Mobile

---

## Conclusion

Ce projet a permis de mettre en œuvre les différentes étapes de conception d'une base de données relationnelle en utilisant la méthode MERISE. La solution proposée améliore l'organisation de l'hôtel grâce à une gestion centralisée des données, une meilleure cohérence des informations et une production rapide des statistiques nécessaires à la prise de décision.