# Guias de projetos com Docker-Compose
Estrutura docker-compose para cada tipo de projeto

## Rails-Development
Feito para projeto Rails e database Postgres

### Passos Iniciais
* Baixe o conteúdo dentro da pasta [rails-development](https://github.com/marcioJesus/docker-guides/tree/master/rails-development)
* Crie uma pasta com nome 'database' no mesmo local onde se encontra o arquivo docker-compose.yml
* Copie seu projeto para dentro da pasta 'app'
* Altere o arquivo 'database.yml' de seu projeto
```
adapter: postgresql
encoding: unicode
host: db
username: postgres
password:
pool: 5
```
* Caso tenha feito alterações no 'Gemfile' remova o conteúdo do 'Gemfile.lock' antes dos próximos passos
* Na pasta raiz(onde está o 'docker-compose.yml') rode os comandos:
```
docker-compose build
docker-compose up -d
docker-compose run app rails tmp:cache:clear tmp:pids:clear
docker-compose run app rails db:create db:migrate
docker attach <NAME_APP_CONTAINER>
```
### No uso diário
```
docker-compose up -d
docker attach <NAME_APP_CONTAINER>
docker-compose down
```
### Se atualizar o Gemfile
```
docker-compose down
docker-compose build
docker-compose up -d
docker attach <NAME_APP_CONTAINER>
```
### Outros
Comandos adicionais
```
docker-compose run app rails c
```
#### Observações
Caso esteja inciando um novo projeto use o guia do [docker for ruby](https://docs.docker.com/compose/rails/) modificando a estrutura e os arquivos 'Docker' conforme este guia.

Vai que é sucesso :)