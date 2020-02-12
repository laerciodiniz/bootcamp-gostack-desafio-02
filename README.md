![](https://camo.githubusercontent.com/8c13dc2618dbd7f76d1d574350b98fdee1335ce5/68747470733a2f2f726f636b6574736561742d63646e2e73332d73612d656173742d312e616d617a6f6e6177732e636f6d2f626f6f7463616d702d6865616465722e706e67) | ![](https://cdn.iconscout.com/icon/free/png-256/nodejs-2-226035.png?w=199)
:-------------- | ------------:

#### bootcamp-gostack-desafio-02
Backend - Transportadora Fastfeet- Desafio 2 do Bootcamp GoStack da Rocketseat **1/4**

### Estrutura
```
yarn add express
yarn add nodemon sucrase -D
```

- acrescentar no package.json

```
"scripts": {
    "dev": "nodemon src/server.js",
    "dev:debug": "nodemon --inspect src/server.js"
  },
```

- configurar o launch.json do debug

```
"configurations": [
    {
      "request": "attach",
      "protocol":"inspector",
      "restart": true
      ],
    }
  ]
```

### Docker

- Instalar [docker](https://docs.docker.com/install/)
- Instalar [Postgres](https://hub.docker.com/_/postgres)

*criando o container*
```
docker run --name database -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres
```
- instalar [Postbird](https://www.electronjs.org/apps/postbird)

### Ferramentas

- [ESLint, Prettier, & EditorConfig](https://github.com/laerciodiniz/ferramentas-vscode/blob/master/README.md)

### Configurar Sequelize
```
yarn add sequelize
yarn add sequelize-cli -D
```

- criar arquivo na raiz do projeto .sequelizerc
```
const { resolve } = require('path');

module.exports = {
  config: resolve(__dirname, 'src', 'config', 'database.js'),
  'models-path': resolve(__dirname, 'src', 'app', 'models'),
  'migrations-path': resolve(__dirname, 'src', 'database', 'migrations'),
  'seeders-path': resolve(__dirname, 'src', 'database', 'seeds'),
};
```

```
yarn add pg pg-hstore
```

### Migration / Seed
- Migration (Gera o código que cria a tabela users)
```
yarn sequelize migration:create --name=create-users
```
- após editar a migration e definir os campos necessários
```
yarn sequelize db:migrate
```
- caso tenha erro na migration gerada é possivel desfazer a ultima migration
```
yarn sequelize db:migrate:undo
```

- **Extensão para gerar hash no node**
```
yarn add bcryptjs
```

- Seed (Gera o codigo que cria registros padroes nas tabelas)
```
yarn sequelize seed:generate --name admin-user
yarn sequelize db:seed:all
```

### Autenticação

```
yarn add jsonwebtoken
```
- [Criar hash](https://www.md5online.org/)

- Validação
```
yarn add yup
```


