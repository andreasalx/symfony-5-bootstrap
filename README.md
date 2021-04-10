# symfony-5-bootstrap
This is a simple project from where to start to build your Symfony 5 application.

## Requirements
To setup the application you need:
* docker: https://docs.docker.com/engine/install/
* docker-compose: https://docs.docker.com/compose/install/

## Setup
First of all you have to create a `.env` file in which store your environment variables; you can start from the `.env.dist` file which contains all the vaiables needed by the application.

You can build your project containers using the command:

`$ docker-compose up --build -d`

After the build, when the containers are up and running you can navigate your `localhost` to access the application.

To stop running containers use the command:

`$ docker-compose stop`

## Traefik
In order to work with Traefik, you have to add following lines to the machine's host file:

```
127.0.0.1 symfony_app
127.0.0.1 symfony_app.phpmyadmin
```

`symfony_app` is the default domain address for this bootstrap project.
