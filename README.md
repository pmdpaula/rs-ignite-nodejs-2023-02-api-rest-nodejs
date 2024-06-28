# Projeto do módulo API Rest e Rotas HTTP - Node.JS - Rocketseat


## :package: Pacotes

- fastify (framework)
- knex (query builder)
- sqlite3 (banco de dados)
- dotenv (variáveis de ambiente)
- zod (validação de dados)
- @fastify/cookie (cookies)


## Banco de dados

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
