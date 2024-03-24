# Docker

## Nginx

## Node

## Laravel

```bash
docker build -t josenaldo/laravel:prod laravel -f laravel/Dockerfile.prod
```

O comando `docker build -t josenaldo/laravel:prod laravel -f laravel/Dockerfile.prod` faz o seguinte:

- `docker build`: Este é o comando principal que diz ao Docker para construir uma nova imagem a partir de um Dockerfile.

- `-t josenaldo/laravel:prod`: A opção `-t` permite que você nomeie e marque sua imagem para que possa ser referenciada facilmente mais tarde. `josenaldo/laravel` é o nome da imagem e `prod` é a tag.

- `laravel`: Este é o contexto de construção, onde o Docker procura arquivos para construir a imagem. Neste caso, é o diretório `laravel`.

- `-f laravel/Dockerfile.prod`: A opção `-f` permite especificar um nome de arquivo ou um caminho para um arquivo Dockerfile. Neste caso, o Dockerfile está localizado em `laravel/Dockerfile.prod`.

Portanto, este comando está dizendo ao Docker para construir uma imagem chamada `josenaldo/laravel` com a tag `prod`, usando o Dockerfile localizado em `laravel/Dockerfile.prod` e o diretório `laravel` como contexto de construção.
