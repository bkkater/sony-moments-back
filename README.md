# Sony Moments - backend

**Para testar, siga os passos abaixo**

```bash
# Clone esse repositório

# Instale as dependencias usando:
$ yarn

# Faça uma cópia da '.env.example' para '.env'
# e adicione SUAS variaveis de ambiente

# Crie uma instancia postgreSQL usando docker
$ docker run --name moments-postgres -e POSTGRES_USER=docker \
              -e POSTGRES_DB=moments -e POSTGRES_PASSWORD=docker \
              -p 5432:5432 -d postgres

# Crie uma instancia do mongoDB usando docker
$ docker run --name moments-mongodb -p 27017:27017 -d -t mongo

# Crie uma instancia do redis usando docker
$ docker run --name moments-redis -p 6379:6379 -d -t redis:alpine

# Crie uma cópia do 'ormconfig.example.json' para 'ormconfig.json'
# e adicione os valores dos campos não preenchidos
# para conectar com o container do docker
$ cp ormconfig.example.json ormconfig.json

# Quando os serviços estiverem rodando, rode as migrations
$ yarn typeorm migration:run

# Para finalizar, rode a api
$ yarn dev:server
```
