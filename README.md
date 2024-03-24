# Docker

- [Docker](#docker)
  - [Nginx](#nginx)
  - [Laravel](#laravel)
  - [Runing](#runing)

## Nginx

Da pasta raiz do projeto, execd nginxcute o seguinte comando para construir a imagem Docker:

```bash
docker build -t josenaldo/nginx:prod nginx -f Dockerfile.prod
```

Ou, se preferir executar o comando a partir do diretório `nginx`:

```bash
cd nginx

docker build -t josenaldo/nginx:prod . -f Dockerfile.prod
```

## Laravel

Da pasta raiz do projeto, execute o seguinte comando para construir a imagem Docker:

```bash
docker build -t josenaldo/laravel:prod laravel -f laravel/Dockerfile.prod
```

Ou, se preferir executar o comando a partir do diretório `laravel`:

```bash
cd laravel

docker build -t josenaldo/laravel:prod . -f laravel/Dockerfile.prod
```

## Runing
