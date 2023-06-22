# CREATE DOCKER CONTAINER

- docker build -t rentx .
- "rentx" é o nome da imagem que voce quer criar
- "." é onde esta o dockerfile, no caso a raiz

# SEE CONTAINERS

## Active Containers

- docker ps -a

## All Containers

- docker ps

# RUN CONTAINER

- docker run -p 3333:3333 rentx
- docker start <<id_container>>

# REMOVE CONTAINER

- docker rm <<id_container>>
- o container PRECISA estar parado

# OPEN THE BASH OF THE "Dockerfile"

- docker exec -it <<id_container>> /bin/bash

# DOCKER LOGS

- docker logs <<name_container>>
- docker logs <<name_container>> -f . Para ficar observando os logs

# DOCKER COMPOSE

- Orquestrador de containers, util para espelhar mudanças nos arquivos e reiniciar o servidor criado automaticamente
- criar o "docker-compose.yml" com as definições para rodar o app
- Para rodar o container use o "docker-compose up".  "docker-compose up -d" para que ele rode em background
- docker-compose up  --force-recreate para recriar o container
- docker-compose stop
- docker-compose down. Vai remover tudo que foi criado dentro do serviço, ao inves de parar apenas
