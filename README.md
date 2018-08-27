# Development environment for Drupal 8 build with Docker Compose

## Dependencies

* [Docker](https://www.docker.com/)
* [Docker Compose](https://docs.docker.com/compose/install/)

## How to use

### Download this repository

	$ git clone https://github.com/elissaheller/Docker-Drupal8.git Drupal8-Docker
	$ cd Drupal8-Docker

### Copy drupal code into web/app folder

Copy the Drupal 8 code into the ./web/app folder.

	$ git clone --branch 8.6.x http://git.drupal.org/project/drupal.git web/app

### Start the docker containers

This command will build the containers and start the web, phpmyadmin and mysql servers. 

	$ docker-compose up -d

### install Drupal composer updates

	$ docker-compose exec web composer install -o

### Install Drupal 8

	$ docker-compose exec web drupal site:install --db-host=mysql --db-name=drupal8 --db-user=root --db-pass=root

### Connect to Database in Sequel Pro

Host: 0.0.0.0
Username: root
Password: root
