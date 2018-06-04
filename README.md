# Symfony-blog 4.0

My application to try some stuffs about Symfony 4
In this project, I'm trying to use various components of Symfony like :
* [Authentication](https://symfony.com/doc/current/security.html)
* [Service container](http://symfony.com/doc/current/service_container.html)
* [Subscriber](http://symfony.com/doc/current/doctrine/event_listeners_subscribers.html)
* [Data transormers](https://symfony.com/doc/current/form/data_transformers.html)
* [Monolog](https://symfony.com/doc/current/logging.html)
* [Guard Authentication](https://symfony.com/doc/current/security/guard_authentication.html)

this list should evolve.

Also, to improve this project, I'm using some tools like :
* [Bulma.io](https://bulma.io/)
* [SASS](http://sass-lang.com/documentation/file.SASS_REFERENCE.html)
* [Gulp](https://github.com/gulpjs/gulp/blob/master/docs/API.md)
* [Font-awesome](http://fontawesome.io/)
* [Browserify](http://browserify.org/)


## Getting Started

### Installing

This project require 
* [Docker](https://docs.docker.com/)
* [Docker-compose](https://docs.docker.com/compose/)

#### Clone the project
```
$ git clone https://github.com/pifaace/symfony-blog.git
```

#### Run dependencies
```
$ docker-compose run --rm --no-deps blog-server composer install
$ npm install
$ gulp
```

### Running docker containers

#### Update database configuration
go to the .env file and put these paramaters into DATABASE_URL
```
DATABASE_URL=mysql://root:secret@db:3306/symfony-blog
```
#### Running containers
```
$ docker-compose up -d
$ start http://localhost:8000/ # Windows
$ open http://localhost:8000/ # Mac
```

#### Stopping containers
```
$ docker-compose stop
```

### Dump database

```
$ docker-compose exec blog-server php bin/console doctrine:migrations:migrate
```

And run datafixtures

```
$ docker-compose exec blog-server php bin/console doctrine:fixtures:load
```

### Routes
To access to the dashboard admin go to the following url :

[http://localhost:8000/admin/dashboard](http://localhost:8000/admin/dashboard)
```
login : admin
password : password
```

### Running tests
```
$ docker-compose run --rm blog-server ./vendor/bin/simple-phpunit
```
