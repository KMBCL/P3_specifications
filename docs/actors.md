# Acteurs identifiés :

![Acteurs](diagrams/actors/actors.svg)

## Visiteur : 
Utilisateur anonyme non authentifié et / ou n'ayant pas de compte.

N'a accès à **aucune** page sécurisée.

Peut s'inscrire ou se connecter.

## Tuteur :
Utilisateur inscrit et authentifié pour fournir un soutien scolaire aux élèves.

- Suivre un ou plusieurs élèves.
- Planifier les rendez-vous avec les élèves
- Assigner une ou plusieurs tâches à l'élève entre chaque rendez-vous

## Elève :
Utilisateur inscrit et authentifié pour obtenir un soutien scolaire.

- Est assigné à un tuteur
- Doit assister aux rendez-vous planifiés
- Doit réaliser les tâches assignées

## Utilisateur :
Utilisateur authentifié au sens large, élève ou tuteur.

- Peut envoyer / recevoir des messages
- Peut planifier des tâches personnelles

# Hors périmètre

## Administrateur :
Cet utilisateur est identifié comme pontentiel besoin, mais ne fait pas partie des demandes initiales. Peut être ajouté dans de futures mises à jour avec ses fonctionnalités propres.

Utilisateur système ayant des droits étendus.

- Gestion des demanques / problématiques utilisateurs
- Validation des rôles tuteurs / élèves lors de l'inscription