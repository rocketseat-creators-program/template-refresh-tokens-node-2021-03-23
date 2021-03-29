## [Template] Implementando Refresh Tokens em Node.js

<img src="https://storage.googleapis.com/golden-wind/experts-club/capa-github.svg" />

*Esse repositório não contém o código finalizado e sim o template para dar início à aula.*

Refresh tokens são muito importantes quando queremos manter o nível de segurança da nossa aplicação alto, porém sem prejudicar a experiência dos usuários. Eles são usados para que as pessoas continuem "logadas", ou seja, sem precisarem ficar usando usuário e senha muitas vezes, mas ao mesmo tempo mantendo o tempo de expiração dos access tokens baixos.

Nesta aula veremos uma implementação de refresh tokens usando Node.js e um banco PostgreSQL. Ao final será possível gerar um refresh token com expiração e que será passado via cookies httponly, também teremos endpoints para invalidar os refresh tokens no caso de um logout.

## Expert

| [<img src="https://avatars.githubusercontent.com/u/711732?s=460&u=6b1039f8a921c5733d92d13b2971c55157fee005&v=4" width="75px;"/>](https://github.com/askmon) |
| :-: |
|[André Spanguero Kanayama](https://github.com/askmon)|

### Requisitos

- Node.js v14 (`.nvmrc` incluso no projeto)
- Conta na AWS (utilizaremos IAM e DynamoDB)
- Um banco PostgreSQL (existe um docker-compose no projeto, para quem quiser rodar usando Docker)

### Como rodar

0. Antes de tudo, rode o comando `npm install`;
0. Caso queira rodar o banco localmente com Docker, pode-se utilizar o comando `docker-compose up` para subir o banco;
0. Renomeie o arquivo `.env.example` para `.env` e edite as variáveis para conexão com o banco;
0. Rode o comando `npm run sequelize:migrate` para gerar as tabelas;
0. Rode o comando `npm run sequelize:seed` para criar dados de exemplo nas tabelas;
0. Rode o comando `npm run dev` para rodar o projeto usando nodemon.

### Próximos passos

Aqui estão alguns assuntos que não foram abordados na aula, mas fica o desafio!

0. Que tal criar um endpoint para os usuários com role de admin no qual é possível deslogar determinados usuários?
0. Como podemos ter muitos acessos ao nosso banco de dados, seria interessante criar índices na tabela `users` e na tabela `tokens`
0. Pode ser interessante colocar mais informações na tabela dos refresh tokens, para auditoria e segurança. Consegue pensar em quais seriam interessantes?

### Referências

- [Artigo da Auth0 explicando brevemente o conceito (em inglês)](https://auth0.com/learn/refresh-tokens/)
