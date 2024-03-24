# Docker

- [Docker](#docker)
  - [Building the Docker images](#building-the-docker-images)
    - [Nginx](#nginx)
    - [Laravel](#laravel)
  - [Running](#running)
    - [Creating the network](#creating-the-network)
    - [Running the containers](#running-the-containers)
  - [Removing the containers](#removing-the-containers)
  - [Docker Compose](#docker-compose)

## Building the Docker images

### Nginx

From the root directory of the project, execute the following command to build the Nginx Docker image:

```bash
docker build -t josenaldo/nginx:prod nginx -f nginx/Dockerfile.prod
```

Alternatively, if you prefer to run the command from the `nginx` directory:

```bash
cd nginx

docker build -t josenaldo/nginx:prod . -f Dockerfile.prod
```

### Laravel

From the root directory of the project, execute the following command to build the Laravel Docker image:

```bash
docker build -t josenaldo/laravel:prod laravel -f laravel/Dockerfile.prod
```

Alternatively, if you prefer to run the command from the `laravel` directory:

```bash
cd laravel

docker build -t josenaldo/laravel:prod . -f laravel/Dockerfile.prod
```

## Running

### Creating the network

Before running the Docker containers, create a network to connect them:

```bash
docker network create laranet
```

### Running the containers

To run the Docker containers, use the following commands:

```bash
docker run -d --network laranet --name laravel josenaldo/laravel:prod

docker run -d --network laranet --name nginx -p 8080:80 josenaldo/nginx:prod
```

## Removing the containers

To remove the containers, use the following commands:

```bash
docker rm $(docker ps -a -q) -f
```

## Docker Compose

Alternatively, you can use Docker Compose to build and run the containers. To do so, execute the following command:

```bash
 docker compose up -d --build
```

If you want to remove the containers created by Docker Compose, use the following command:

```bash
docker compose down
```

To execute Docker COmpose command for another file, use the following command:

```bash
docker compose -f docker-compose.laravel.yml up -d --build
``

## Logs

To see the logs of the containers, use the following command:

```bash
docker logs <container_id>
```

