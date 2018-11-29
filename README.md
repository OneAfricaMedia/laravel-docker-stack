# Laravel Docker Stack

This repository provides you a development environment without requiring you to install PHP,
 a web server, and any other server software on your local machine. 
 
 For this, it requires Docker and Docker Compose
 
 ## Docker Images
 -  `rimucore/lara-php:7.2-fpm` - This image extends [`php:7.2-fpm`](https://hub.docker.com/_/php/) to add some PHP extensions
 -  `rimucore/lara-php:7.2-fpm-alpine` - This image extends [`php:7.2-fpm-alpine`](https://hub.docker.com/_/php/) to add some PHP extensions
 -  `rimucore/node:11.1-alpine` - This image extends [`node:11.1-alpine`](https://hub.docker.com/_/node/) to add needed dependencies
 - `rimucore/lara-nginx:1.15-alpine` - This image extends [`nginx:1.15-alpine`](https://hub.docker.com/_/nginx/)
 
 ## Usage
 1. The following are required on your system: [`docker`](https://docs.docker.com/install/) and [`docker-compose`](https://docs.docker.com/compose/install/)
 2. Download this repo or copy docker-compose.yml into your laravel project root.
 3. To run application inside container use command within root directory of project:
```
$ docker-compose up
```
4. To view running application in browser open [`http://localhost:9090/`](http://localhost:9090/) 
or you can map host `laravel.test` to `127.0.0.1` on your hosts file, save file then open [`http://laravel.test:9090/`](http://laravel.test:9090/)
5. To bring running application container down use command within root directory of project:
```
$ docker-compose down
```