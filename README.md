# Dashboard de estatísticas
Uma aplicação completa com backend em nodejs utilizando muitas ferramentas como (knex, mongoose, passport, passport jwt, jwt-simple, bcrypt-nodejs, express, consign) e usando recursos do knex como migrations. Como banco de dados foram utilizados o mongodb e postgreeSQL. No frontend foi utilizado o VueJS e outras ferramentas como (axios, bootstrap-vue, vue-mq, vue-toasted, vue-router, vuex).

# Pre-requisitos

 - PostgreeSQL - https://www.postgresql.org/download/
 - Nodejs - https://nodejs.org/en/
 - Mongodb - https://www.mongodb.com/
 
 # Executando o projeto
 **Backend**
Para rodar o backend você precisa criar a base de dados "knowledge", executando os comandos:

    psql -U postgres
   Digite a senha caso tenha
   Caso não funcione dessa forma você pode tentar 
		`sudo su - postgres` e em seguida `psql`
   Logo depois digite
   

    CREATE DATABASE knowledge;
   Saia digitando `\q`
   Depois navegue até a pasta `backend` do projeto `cd backend`
   modique o arquivo env_file para .env e adicione seu usuário e senha, também crie uma senha de autenticação:

>    module.exports = {
>     authSecret: 'suaSenhaDeAuth',
>     db: {
>         host: '127.0.0.1',
>         port: 5432,
>         database: 'knowledge',
>         user: 'seuUser',
>         password: 'suaSenha'
>     } }
>     
Instale as dependencias com o comando `npm install`, execute o serviço do mongodb com o comando `mongod`, em seguida execute o backend com `node index.js`. A mensagem 
> Backend executando...

Deverá aparecer.

**Frontend**
Executar o frontend é mais fácil, basta somente navegar até a pasta frontend do projeto `cd frontend`, instalar as depedencias `npm install` e enfim executar com o comando `npm run serve`, depois abra o navegador e digite `http://localhost:8080`

# Notas
Você precisará criar um novo usuário e para que ele contenha as permissões de administrador é necessário modificar no banco de dados.
Conecte a base: `\c knowledge` e atualize o status "admin" `UPDATE users SET admin = true WHERE id = 1;`. Depois disso saia do dashboard e entre novamente, que será gerado um token de administrador.
 
