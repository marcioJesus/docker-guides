## Comandos para Produção
```
docker-compose run app bundle exec rails assets:precompile RAILS_ENV=production

docker-compose run app bundle exec rails db:create RAILS_ENV=production

docker-compose run app bundle exec rails db:migrate RAILS_ENV=production
```
### Observações
Para mudar o ambiente basta alterar o arquivo [.env](https://github.com/marcioJesus/docker-guides/blob/master/rails-production/.env)