# Acteurs identifiés :

![Acteurs](diagrams/actors/actors.svg)

## Visiteur : 
Utilisateur anonyme non authentifié et / ou n'ayant pas de compte.

N'a accès à **aucune** page sécurisée.

Peut s'inscrire ou se connecter.

## Tuteur :
Utilisateur inscrit et authentifié pour fournir un soutien scolaire aux élèves.

- Suit un ou plusieurs élèves
- Planifie les rendez-vous avec les élèves
- Assigne une ou plusieurs tâches à l'élève entre chaque rendez-vous

## Elève :
Utilisateur inscrit et authentifié pour obtenir un soutien scolaire.

- Est assigné à un tuteur
- Assiste aux rendez-vous planifiés
- Réalise les tâches assignées par le tuteur

## Utilisateur :
Utilisateur authentifié au sens large, élève ou tuteur.

- Envoi / reçoit des messages
- Gère ses tâches personnelles

## Hors périmètre initial

### Administrateur :
Cet utilisateur est identifié comme potentiel besoin, mais ne fait pas partie des demandes initiales. Il peut être ajouté dans de futures mises à jour avec ses fonctionnalités propres.

Utilisateur système ayant des droits étendus.

- Gère des demandes / problématiques utilisateurs
- Valide les rôles de tuteurs / élèves lors de l'inscription