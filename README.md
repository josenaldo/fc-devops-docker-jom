# Docker

- [Docker](#docker)
  - [Building the Docker images](#building-the-docker-images)
    - [Nginx](#nginx)
    - [Laravel](#laravel)
  - [Running](#running)
    - [Creating the network](#creating-the-network)
    - [Running the containers](#running-the-containers)

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
