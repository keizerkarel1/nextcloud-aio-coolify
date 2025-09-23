# Installer Nextcloud AIO avec Coolify



[Nextcloud AIO](https://github.com/nextcloud/all-in-one) est la solution d'installation recommandée par Nextcloud pour installer la suite. 



Cependant, les contraintes d'installations le rendent compliqué si l'on souhaite l'intégrer avec une instance [Coolify](https://coolify.io/).

- Le nom du container principal doit être identique
- Le proxy de coolify s'intègre mal avec la spécificité d'AIO



Donc pour ça, voici un docker-compose adapté à la situation et un mini-tutoriel



1. (Bonne pratique) Clonez le repo chez vous
2.  Dans votre instance Coolify, nouveau -> Repository (public si votre repo est public, private si il est private et que vous êtes à l'aise avec les clés de déployement ou github App)
3. Insérez l'url de votre repo



On ne va pas utiliser le proxy de coolify, mais on va créer un tunnel cloudflare à la place

- Récupérer le token du tunnel et le mettre dans les variables d'environnement



Lancer le repo et suivez la procédure



