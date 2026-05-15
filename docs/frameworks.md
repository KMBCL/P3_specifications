# Framework et outils

## **Frontend** Solutions existantes:
- React :
    - Bibliothèque UI.
    - Impose de choisir d'autres composants et bibliothèques
    - Conventions et structure de développement à la discrétion de l'équipe
    - Ecosystème large
- Vue :
    - Conventions et structure définies par le framework
    - Ecosystème plus réduit que React
    - Adapté aux petites et moyennes équipes
- Angular :
    - Framework complet, avec cadre et structure strict
    - Adapté a des projets d'entreprises
    - Adapté aux moyennes équipes
- ...

## **Backend** Solutions existantes :
- FastAPI :
    - Orienté API
    - Nécessite d'autres outils et bibliothèques, authentification, ORM, etc. 
    - Rapide
    - Conventions et structure de développement à la discrétion de l'équipe 
- Flask :
    - Framework minimaliste
    - Nécessite d'autres outils et bibliothèques, authentification, ORM, etc.
    - Conventions et structure de développement à la discrétion de l'équipe 
- Django :
    - Framework complet avec authentification, ORM, etc.
    - Interface admin
    - Conventions et structure imposées
    - Peut être configuré en API


### Solutions existantes:
- Oracle : sous licence. Très perfomant, mais très cher, complexe et adaptée aux grandes entreprises.
- SQLServeur : sous licence. Perfomant, mais très cher, complexe et adaptée aux grandes entreprises. Plus adapté également un environnement Microsoft.
- PostgreSQL : libre. Performant, scalable.
- MySQL : licence libre possible pour la version communautaire. 
- MarioDB :
- ...

# Solutions retenues

## Frontend : **Vue**:
- Le projet est bien délimité, bien qu'évolutif, il n'a pas vocation à devenir un projet d'entreprise multisites. 

L'équipe de développement frontend étant de 2 personnes, pour limiter la dispersion dans les outils et bibliotèques, un ecosystème moins vaste facilite la structure du projet. 

De plus le framework **Vue** encourage une logique de décomposition script/template/CSS, qui permet naturellement de bien séparer les responsabilités.

## Backend : **Django en API**:
- Le projet peut démarrer rapidement et avec fiabilité avec la structure et les composants **Django**. 

Les points d'entrées sont exposés par l'API et le système d'authentification et l'ORM intégré permettent de se focaliser sur les besoins métier, plutôt que l'architecture globale.

L'interface administrateur intégrée permet également rapidement à un utilisateur admin du projet de modifier des données afin de répondre aux besoins utilisateurs.

## Base de données: PostgreSQL:
- Le projet utilisant **Django**, PostgreSQL est nativement supporté est compatible avec les instructions de **Django**.

De plus le développement est libre, communautaire et actif, avec une très bonne documentation et de nombreux outils de suivi et diagnostique.
PostgreSQL gère très bien l'intégrité référentielle.

