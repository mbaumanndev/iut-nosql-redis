Cours de NoSQL sur Redis
========================

Ce dépôt contient du contenu déstiné à une utilisation pédagogique auprès des étudiants de seconde année du département informatique de l'IUT d'Amiens suivant le parcours orienté en bases de données.

Pré-requis
----------

Pour utiliser le contenu de ce dépôt, vous devez avoir un ordinateur équipé de :

- Docker 17.09.0+
- Docker Compose

Lancement de Docker
-------------------

Notre projet nécéssite le lancement de plusieurs conteneurs :
- Un conteneur redis en mode SGBD (redis dans le fichier de configuration)
- Un conteneur redis en mode cli (rcli dans le fichier de configuration)
- Un conteneur readis (PHP) pour monitorer notre serveur redis
- Un conteneur phpRedisAdmin (PHP) pour interagir avec redis

Docker nous permet de définir des dépendance entre nos conteneurs, ainsi, nos conteneur PHP et notre conteneur redis CLI dépendent tout deux du conteneur redis SGBD.

Afin de lancer notre environement de développement, nous devons éxécuter la commande suivante :

```sh
docker-compose up -d
```

Cette commande va monter notre environement en téléchargeant les conteneurs directement depuis les dépôts de Docker et en démarrant et configurant ceux-ci.

Nous allons maintenant pouvoir nous connecter à notre conteneur redis CLI pour éxécuter des commandes sur notre conteneur redis SGBD par le biais de la commande suivante :

```sh
docker-compose run rcli
```

Nous sommes ainsi connectés dans notre conteneur redis CLI directement dans l'invite de commande de redis. Nous aurons donc uniquement accès [aux commandes mises à disposition par redis](https://redis.io/commands).

À la fin de la séance, pensez à éteindre vos conteneurs avec la commande suivante :

```
docker-compose down
```

