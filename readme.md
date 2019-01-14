# Make a CI with Gitlab to your own private server with docker
## Ce projet sert a mettre en place un serveur gitlab ce avec nginx et docker

## /!\ Vous devez avoir docker et docker-compose d'installer sur votre serveur.

### Il mets a disposition gitlab, nginx, runner gitlab

#### En premier lieu

- Cloner le projet dans le dossier `/home` de votre serveur
    - lancer la cmd `git clone https://github.com/devglrd/gitlab-CE-docker`
	- Ensuite rentré dans le dossier `mv gitlab-CE-docker/ config`
    - Ensuite rentré dans le dossier `cd config`

- Monter le container nginx
    - Pour monter le container nginx rendez vous dans `cd /home/config/docker/nginx`
    - Rendez vous dans le dossier de conf de nginx `cd /home/config/docker/nginx/conf`
    - Editer le fichier `site.conf` et remplacer les *IP_DU_SERVEUR* par l'ip de votre serveur
    - Remonter ensuite au niveau du docker-compose `cd ..`
    - Ensuite faites la command `docker-compose up -d`
    - Cette command va monter le container nginx

- Monter le container gitlab :
    - Rentrer dans le dosier gitlab avec la cmd `cd /home/config/docker/ci`
    - Vous devez ensuite rentré l'ip de votre serveur dans le *docker-compose*
    - Pour ce faire `cd /home/config/docker/ci && nano docker-compose.yml`
    - Remplacer *URL* par votre IP
    - Ensuite faites la command `docker-compose up -d`
    - Cette command va monter le container gitlab et le container gitlab-runner


#### Afin de voir si tout c'est bien executé correctement vous pouvez executer la command `docker ps` pour voir les containers qui tourne actuellement sur votre serveur

#### Il devrait afficher les container `gitlab, gitlab-runner, nginx`

#### Essayer ensuite de taper sur votre http://ip-du-serveur:8003 gitlab devrais apparait !

# Feedback

Pour un bug, une demande de suggestion, une nouvelle fonctionnalité, etc... [create an issue](https://github.com/pevglrd/ci-gitlab-nginx-docker/issues)

