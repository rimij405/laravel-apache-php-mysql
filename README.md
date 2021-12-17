# Sample Containerized Laravel Application

This is a sample Laravel application containerized with Docker.

This project takes inspiration from the [`docker/awesome-compose/apache-php/`](https://github.com/docker/awesome-compose/tree/master/apache-php) example.

## Laravel Application with Apache2

The project structure is displayed below:

```bash
.
|-- docker-compose.yaml
|-- app
    |-- Dockerfile
    └── index.php
```

This project makes use of the following tools and frameworks:

- Laravel
- Apache2
- MySQL

[`docker-compose.yaml`](/docker-compose.yaml)

```yaml
services:
    web:
        build: app
        ports:
            - '8080:80'
        volumes:
            - ./app:/var/www/html/
```

## Installation

You can install this Laravel application by cloning this repository with `git clone`.

## Deployment

Deploy this project with the `docker-compose` CLI from the application's root directory:

```bash
$ docker-compose up -d
```

Listing the containers should show one container running and the port mapping as presented below:

```bash
$ docker ps

```

Once the application starts, navigate to `http://localhost:<PORT>` in your web browser or run:

```bash
$ curl localhost:80

```

## Deactivation

Stop and remove the containers with the `docker-compose` CLI from the application's root directory:

```bash
$ docker-compose down
```