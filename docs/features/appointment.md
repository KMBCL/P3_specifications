# Domaine : Rendez-vous

## Gestion des rendez-vous

![Gestion des rendez-vous](../diagrams/appointment/appointment.svg)

## Fonctionnalité: Planifier un rendez-vous

```gherkin

    En tant que tuteur connecté à mon espace personnel
    Je veux planifier un rendez-vous avec un élève que j'accompagne
    Afin de faire le point sur ses devoirs et l'avancement de ses tâches

    Scénario: Planifier un rendez-vous avec des données valides

        Etant donné que je suis sur le formulaire de planification de rendez-vous
        Et que j'ai choisi un élève existant
        Et que j'ai complété les champs obligatoires

        Lorsque je valide le formulaire

        Alors le rendez-vous est créé
        Et le rendez-vous est visible dans le calendrier
        Et une notification est envoyée par email à l'élève

    Scénario: Refus sans destinataire

        Etant donné que je suis sur le formulaire de planification de rendez-vous
        Et que j'ai complété les champs obligatoires
        Mais que je n'ai pas choisi d'élève

        Lorsque je valide le formulaire

        Alors le rendez-vous n'est pas créé
        Et le champ élève est mis en valeur
        Et je suis invité à choisir un élève

    Scénario: Refus lorsque la date est antérieure à la date courante

        Etant donné que je suis sur le formulaire de planification de rendez-vous
        Et que j'ai choisi un élève
        Et que j'ai complété les champs obligatoires
        Mais que la date est antérieure à la date courante

        Lorsque je valide le formulaire

        Alors le rendez-vous n'est pas créé
        Et la date est mise en valeur
        Et je suis invité à spécifier une date postérieure à la date courante

    Scénario: Refus lorsque le créneau horaire est déjà pris

        Etant donné que je suis sur le formulaire de planification de rendez-vous
        Et que j'ai choisi un élève
        Et que j'ai complété les champs obligatoires
        Mais que j'ai déjà un rendez-vous avec un autre élève sur cette plage horaire

        Lorsque je valide le formulaire

        Alors le rendez-vous n'est pas créé
        Et la date / heure est mise en valeur
        Et je suis informé que j'ai déjà un rendez-vous prévu sur cette plage horaire

```

## Fonctionnalité: Modifier un rendez-vous

```gherkin

    En tant que tuteur connecté à mon espace personnel
    Je veux modifier un rendez-vous avec un élève
    Afin de le reporter ou de l'avancer

    Scénario: Modifier la date d'un rendez-vous

        Etant donné que j'ai déjà un rendez-vous convenu avec un élève
        Et que j'ai avancé / reculé la date

        Lorsque je valide le formulaire

        Alors la date est modifiée
        Et une notification est envoyée par email à l'élève

    Scénario: Refus lorsque la date modifiée est antérieure à la date courante

        Etant donné que j'ai déjà un rendez-vous convenu avec un élève
        Et que j'ai avancé / reculé la date
        Mais que la date est antérieure à la date courante

        Lorsque je valide le formulaire

        Alors le rendez-vous n'est pas modifié
        Et la date est mise en valeur
        Et je suis invité à spécifier une date postérieure à la date courante

```

## Fonctionnalité: Consulter ses rendez-vous

```gherkin

    En tant qu'utilisateur connecté à mon espace personnel
    Je veux voir tous mes rendez-vous dans un calendrier
    Afin de ne pas les oublier, me préparer et m'organiser

    Scénario: Consultation de mes rendez-vous dans le calendrier

        Etant donné que j'ai 5 rendez-vous planifiés à venir ce mois-ci
        Et que j'ai 2 rendez-vous passés ce mois-ci

        Lorsque je consulte le calendrier

        Alors mes 7 rendez-vous du mois sont affichés dans le calendrier à leur date
        Et ceux à venir sont mis en valeur

        
    Scénario: Consultation de mes rendez-vous avec absence de rendez-vous planifiés

        Etant donné que je n'ai aucun rendez-vous planifié ce mois-ci

        Lorsque je consulte le calendrier

        Alors aucun rendez-vous n'est affiché
        Et un message me prévient que je n'ai aucun rendez-vous planifié

```
