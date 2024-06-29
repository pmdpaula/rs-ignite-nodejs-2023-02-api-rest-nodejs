# Projeto do módulo API Rest e Rotas HTTP - Node.JS - Rocketseat

## 🚀 Início e lint

- typescript, @types/node

```bash
yarn add typescript @types/node -D
npx tsc --init
```

Alterasmos o `target` no arquivo `tsconfig.json` para `es2020` e adicionamos a propriedade `module` com o valor `ESNext`.

```json
{
  "target": "es2020",
  "module": "ESNext",
  "moduleResolution": "node",
}
```

- tsup (bundler)
- tsx
- eslint

```bash
yarn create @eslint/config@latest
```

Isto criará um arquivo `eslint.config.js` na raiz do projeto, que aqui foi renomeado para `eslint.config.mjs`.


- prettier

```bash
yarn add prettier eslint-config-prettier -D
```


## 📦 Pacotes

- fastify (framework)
- dotenv (variáveis de ambiente)
- knex (query builder)
- sqlite3 (banco de dados)
- zod (validação de dados)
- @fastify/cookie (cookies)
- vitest (testes)
- supertest, @types/supertest (testes)


## 🛢️ Banco de dados

Inicialização do banco de dados:

```bash
npx knex migrate:make create-documents
```

O comando acima irá criar um arquivo de migração na pasta `migrations` com o nome `create-documents`.
Neste arquivo será criado duas funções `up` e `down` que são responsáveis por executar a alteração no banco de dados e desfazer a alteração, respectivamente.
O local do arquivo das migrações estará onde configuramos no arquivo `knexfile.js` da raiz do projeto.

Como na etapa as funções `up` e `down` estão vazias, devemos preenchê-las com as instruções SQL para criar a tabela `documents` e desfazer a criação da tabela, respectivamente.
Após preenchimento das funções, devemos executar o comando abaixo para executar as alterações no banco de dados.

```bash
npx knex migrate:latest
```

Caso seja preciso fazer um rollback antes de enviar a migração para produção ou para os demais desenvolvedores, execute o comando abaixo.

```bash
npx knex migrate:rollback
```
