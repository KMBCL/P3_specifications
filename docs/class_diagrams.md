# Diagrammes de classes:

## Utilisateur
![Utilisateur](diagrams/classes/user.svg)

Représente l'entité **Utilisateur** et ses spécialisations **Tuteur** et **Elève**

## Tutorat
![Tutorat](diagrams/classes/tutor_assignment.svg)

Représente la relation de **tutorat** entre un **Elève** et son **Tuteur**. Bien qu'un élève ait normalement un seul tuteur, cette relation intermédiaire permet de retracer l'historique des tuteurs assignés à l'élève.

## Message
![Message](diagrams/classes/message.svg)

Représente l’entité **Message** et ses relations avec l’**Utilisateur** en tant qu’expéditeur et destinataire.

## Tâche
![Tâche](diagrams/classes/task.svg)

Représente la relation entre l'entité **Utilisateur** et **Tâche**, qu'elle soit **personnelle** ou **assignée** par un tuteur.

## Rendez-vous
![Rendez-vous](diagrams/classes/appointment.svg)

Représente la relation entre l'entité **Rendez-vous** et **Utilisateur**. Dans le périmètre initial, le rendez-vous est entre deux parties, l'élève et son tuteur.
