# Spécifications techniques

Le projet prend la forme d'une application web accessible depuis internet.

## Contraintes techniques

- Le cout de développement, de maintenance et des licences logicielles doit être en corrélation avec les moyens financiers de l'association.
- Le projet livré sera accessible depuis internet
- les frameworks, dépendances et librairies utilisés doivent être documentés et maintenus pour faciliter le développement par une petite équipe
- 2 développeurs Frontend
- 2 développeurs Backend

## Contraintes liées aux données

- Le projet manipule des données fortement liées entre-elles: relation tuteur-élève, rendez-vous entre deux utilisateurs, etc.
- La solution de persistane doit permettre la relation entre entités et garantir l'intégrité des données

## Contraintes de sécurité générales

- les frameworks, dépendances et librairies utilisés doivent être maintenus à jour afin de limiter d'éventuelles failles de sécurité
- le projet est accessible sur internet, par n'importe qui: les fonctionnalités et les données sont protégées par l'authentification.

### Règles de sécurité liées aux comptes utilisateurs

- le mot de passe n'est jamais stocké en clair
- la vérification d'un mot de passe saisi se fait à partir de la valeur sécurisée stockée
- les messages de refus d'authentification affichés par l'UI restent génériques afin de ne pas donner d'indices:
    - sur le mot de passe
    - sur l'adresse email    

## Principes d'architecture

Le projet est décomposé en plusieurs couches, ayant chacune un rôle:

- Interface utilisateur (UI)
- API
- Services métier
- Accès aux données
- Base de données

## **Frontend**

### UI:
- Affiche l'interface utilisateur
- Permet de consulter, saisir et modifier les données autorisées
- Valide les données au niveau UI pour améliorer l'expérience utilisateur
- Soumet les requêtes HTTP à l'API
- Affiche les réponses de l'API

## **Backend**

### API:
- Expose les points d'entrée et de sortie du backend
- Reçoit les requêtes HTTP de l'UI
- Vérifie l'authentification de l'utilisateur
- Transforme et valide la structure des données
- Traduit les requêtes HTTP en données métiers pour les services
- Dialogue avec les services métiers
- Traduit les réponses des services en réponses HTTP
- Renvoie les réponses HTTP à l'UI

### Services Métier:
- Reçoit les données de l'API
- Validation des données selon logique métier
- Applique la logique métier
- Dialogue avec les services d'accès aux données
- Renvoie les réponses métier

### Accès aux données: 
- Reçoit les demandes métiers
- Dialogue avec la base de données
- Reçoit les données depuis la base de données
- Renvoie les données aux services métiers

## **Base de données**
- Reçoit les demandes des services d'accès aux données
- Persiste les données
- Renvoie les données

## Architecture générale

![Architecture générale](diagrams/architecture.svg)

## Séquence générique de traitement

![Séquence générique](diagrams/workflow.svg)



