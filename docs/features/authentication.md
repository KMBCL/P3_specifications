# Domaine : Compte utilisateur

## Gestion de l'authentification

![Authentification](../diagrams/authentication/authentication.svg)

## Gestion des données personnelles

![Gestion des données personnelles](../diagrams/authentication/data_management.svg)

## Fonctionnalité: Inscription d'un nouvel utilisateur

```gherkin

    En tant que visiteur
    Je veux créer un nouveau compte
    Afin d'accéder aux fonctionnalités du site

    Scénario: Inscription avec des données valides

        Etant donné que je suis sur le formulaire d'inscription
        Et que j'ai renseigné tous les champs obligatoires avec des données valides
     
        Lorsque je valide le formulaire
        
        Alors l'inscription est validée
        Et mon compte est créé
        Et je suis invité à me connecter

    Scénario: Refus avec donées obligatoires manquantes
        Etant donné que je suis sur le formulaire d'inscription
        Mais que j'ai partiellement renseigné les champs obligatoires avec des données valides
     
        Lorsque je valide le formulaire      
        
        Alors l'inscription est refusée
        Et les données manquantes sont mises en valeur
        Et je suis averti que ces données sont obligatoires

    Scénario: Refus avec des données au mauvais format
        Etant donné que je suis sur le formulaire d'inscription
        
        Lorsque je saisis des données dans un format invalide
        
        Alors le formulaire met en valeur le champ
        Et le format attendu m'est spécifié

    Scénario: Refus avec une adresse email déjà existante
        Etant donné que je suis sur le formulaire d'inscription
        Et que j'ai renseigné tous les champs obligatoires avec des données valides
        Mais qu'un compte avec la même adresse email existe déjà
        
        Lorsque je valide le formulaire complété
        
        Alors l'inscription est refusée
        Et je suis informé que l'adresse email est déjà utilisée
        Et je suis invité à me connecter au lieu de créer un nouveau compte
```

## Fonctionnalité: Connexion à mon espace personnel

```gherkin

    En tant qu'utilisateur déconnecté
    Je veux me connecter à mon compte
    Afin d'accéder à mon espace client

    Scénario: Connexion avec identifiants valides
        Etant donné que je suis sur la page de connexion
        Et que j'ai complété le formulaire de connexion
        Et que mon identifiant et mot de passe sont valides

        Lorsque je valide le formulaire de connexion

        Alors la connexion est autorisée
        Et j'accède à mon espace personnel

    Scénario: Refus avec des identifiants invalides
        Etant donné que je suis sur la page de connexion
        Et que j'ai complété le formulaire de connexion
        Mais que mon identifiant ou mot de passe est invalide

        Lorsque je valide le formulaire de connexion
        
        Alors la connexion est refusée
        Et je suis informé que l'identifiant et mot de passe ne sont pas valides
        Et je suis invité à réessayer

    Scénario: Refus avec des identifiants incomplets
        Etant donné que je suis sur la page de connexion
        Mais que j'ai partiellement complété le formulaire de connexion

        Lorsque je valide le formulaire de connexion
        
        Alors la connexion est refusée
        Et je suis informé que le champ manquant est obligatoire
```

## Fonctionnalité: Déconnexion de mon espace personnel

```gherkin

    En tant qu'utilisateur connecté
    Je veux me déconnecter
    Afin de mettre fin à ma session

    Scénario: Déconnexion
        Etant donné que je suis connecté

        Lorsque je clique sur "déconnecter"
        
        Alors je suis déconnecté
        Et un message confirme la déconnexion
        Et je n'ai plus accès à mon espace personnel
```

## Fonctionnalité: Mise à jour du mot de passe

```gherkin

    En tant qu'utilisateur connecté
    Je veux mettre à jour mon mot de passe
    Afin de le renouveler par sécurité

    Scénario: Modification de mot de passe
        Etant donné que je suis connecté
        Et que j'ai ouvert le formulaire de modification de mot de passe
        Et que j'ai saisi le nouveau mot de passe
        Et que j'ai confirmé le nouveau mot de passe
        Et que j'ai saisi mon mot de passe actuel

        Lorsque je valide le formulaire

        Alors le mot de passe est mis à jour
        Et un message m'avertit que le mot de passe est mis à jour
        Et je suis déconnecté
        Et je suis invité à me reconnecter

    Scénario: Refus lorsque le mot de passe actuel est faux
        Etant donné que je suis connecté
        Et que j'ai ouvert le formulaire de modification de mot de passe
        Et que j'ai saisi le nouveau mot de passe 
        Et que j'ai confirmé le nouveau mot de passe 
        Mais que j'ai saisi un mot de passe actuel incorrect

        Lorsque je valide le formulaire

        Alors le mot de passe n'est pas mis à jour
        Et je suis averti que le mot de passe actuel est faux

    Scénario: Refus lorsque le mot de passe actuel est manquant
        Etant donné que je suis connecté
        Et que j'ai ouvert le formulaire de modification de mot de passe
        Et que j'ai saisi le nouveau mot de passe 
        Et que j'ai confirmé le nouveau mot de passe
        Mais que je n'ai pas saisi le mot de passe actuel dans le champ requis

        Lorsque je valide le formulaire

        Alors le mot de passe n'est pas mis à jour
        Et je suis averti que ce champ est obligatoire

    Scénario: Refus lorsque le nouveau mot de passe ne correspond pas avec la confirmation
        Etant donné que je suis connecté
        Et que j'ai ouvert le formulaire de modification de mot de passe
        Et que j'ai saisi mon mot de passe actuel
        Et que j'ai saisi le nouveau mot de passe "test_mdp"
        Mais que j'ai confirmé le nouveau mot de passe "test_mdpppp"

        Lorsque je valide le formulaire

        Alors le mot de passe n'est pas mis à jour
        Et je suis averti que le nouveau mot de passe ne concorde pas avec la confirmation

    Scénario: Refus lorsque la confirmation de mot de passe est manquante
        Etant donné que je suis connecté
        Et que j'ai ouvert le formulaire de modification de mot de passe
        Et que j'ai saisi mon mot de passe actuel
        Et que j'ai saisi le nouveau mot de passe
        Mais que je n'ai pas confirmé le nouveau mot de passe

        Lorsque je valide le formulaire

        Alors le mot de passe n'est pas mis à jour
        Et je suis averti qu'il faut confirmer le nouveau mot de passe
```

## Fonctionnalité: Modification des données personnelles

```gherkin

    En tant qu'utilisateur connecté
    Je veux modifier mes informations personnelles
    Afin de refléter les changements de mes coordonnées

    Scénario: Modification des données personnelles avec données valides
        Etant donné que je suis connecté
        Et que je suis sur le formulaire de mes données personnelles
        Et que j'ai saisi des données à modifier avec des données sont valides
        
        Lorsque je valide le formulaire
        
        Alors les données sont modifiées
        Et j'ai un message de confirmation
        Et je suis redirigé vers mes données personnelles

    Scénario: Refus lorsque l'adresse email est invalide
        Etant donné que  je suis connecté
        Et que je suis sur le formulaire de mes données personnelles
        Et que j'ai saisi une nouvelle adresse email
        Mais que le format de l'adresse est invalide
        
        Lorsque je valide le formulaire
        
        Alors les données ne sont pas modifiées
        Et je suis averti que le format de l'adresse n'est pas valide
```

## Fonctionnalité: Réinitialiser mon mot de passe
