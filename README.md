# UmanIT PHP Stack with Docker

## Presentation
This repository is used to start a new web project. It will launch a Nginx server with PHP-FPM and PostgreSQL.

## Requirements
In order to use this stack, you must:
* Install [Docker compose](https://docs.docker.com/compose/) ;
* install [umanit/docker-reverse-proxy](https://github.com/umanit/docker-reverse-proxy).

## Installation
* Clone or download the repository ;
* create a `.env` file based on `.env.dist` ;
* Instantiate your PHP project in the `www` directory (Nginx will serves the content of `www/web`).

## Usage
To launch the stack, simply type `docker-compose up -d` in your terminal.

There are several configuration available in the `.env` file:

|Name|Description|Required?|
|--|--|--|
|COMPOSE_PROJECT_NAME|Name of your project. Used to distinct multiple projects from each others.  |✔|
|SITE_URL|Access URL of the website. Don't forget to declare your host in `/etc/hosts` file!|✔|
|POSTGRES_DB|Name of the PostgreSQL database to use.|✔|
|POSTGRES_USER|Name of the PostgreSQL user to use.||
|POSTGRES_PASSWORD|Password of the PostgreSQL user to use.||
|PHP_TAG|[Docker tag of the PHP version to use.](https://hub.docker.com/_/php/) **MUST** be a `-fpm-alpine` version!|✔|
|POSTGRES_TAG|[Docker tag of the PostgreSQL version to use.](https://hub.docker.com/_/postgres/) **MUST** be a `-alpine` version!|✔|
|NGINX_TAG|[Docker tag of the Nginx version to use.](https://hub.docker.com/_/nginx/) **MUST** be a `-alpine` version!|✔|

Et voilà! Your website should be accessible if [umanit/docker-reverse-proxy](https://github.com/umanit/docker-reverse-proxy) is launched!
