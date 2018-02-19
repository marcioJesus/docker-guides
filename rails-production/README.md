## Comandos para Produção
```
docker-compose run app bundle exec rails assets:precompile RAILS_ENV=production

docker-compose run app bundle exec rails db:create RAILS_ENV=production

docker-compose run app bundle exec rails db:migrate RAILS_ENV=production
```