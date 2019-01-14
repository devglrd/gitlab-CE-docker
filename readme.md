# Make a CI with Gitlab to your own private server with docker
## Ce projet sert a mettre en place un serveur gitlab ce avec nginx et docker

## /!\ Vous devez avoir docker et docker-compose d'installer sur votre serveur.

### Il mets a disposition gitlab, nginx, runner gitlab

#### En premier lieu

- Cloner le projet dans le dossier `/home` de votre serveur
    - lancer la cmd `git clone https://github.com/devglrd/ci-gitlab-nginx-docker.git`
	- Ensuite rentré dans le dossier `mv ci-gitlab-nginx-docker/ config`
    - Ensuite rentré dans le dossier `cd config`

- Monter le container nginx
    - Pour monter le container nginx rendez vous dans `cd /home/config/docker/nginx`
    - Ensuite faites la command `docker-compose up -d`
    - Cette command va monter le container nginx

- Monter le container gitlab :
    - Rentrer dans le dosier gitlab avec la cmd `cd /home/config/docker/ci`
    - Ensuite faites la comomand `docker-compose up -d`
    - Cette command va monter le container gitlab et le container gitlab-runner


#### Afin de voir si tout c'est bien executé correctement vous pouvez executer la command `docker ps` pour voir les containers qui tourne actuellement sur votre serveur

#### Il devrait afficher les container `gitlab, gitlab-runner, nginx`

#### Essayer ensuite de taper sur votre http://ip-du-serveur:8003 gitlab devrais apparait !

# Feedback

Pour un bug, une demande de suggestion, une nouvelle fonctionnalité, etc... [create an issue](https://github.com/pevglrd/ci-gitlab-nginx-docker/issues)

