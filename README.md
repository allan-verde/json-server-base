<h1 align="center">
  <img alt="KenzieHub" title="KenzieHub" src="https://kenzie.com.br/images/logoblue.svg" width="100px" />
</h1>

<h1 align="center">
  API
</h1>

<p align = "center">
Este é o backend de uma aplicação teste - O objetivo dessa aplicação é conseguir cadastrar usuário e tarefas
</p>

<p align="center">
  <a href="#endpoints">Endpoints</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</p>

## **Endpoints**

A API tem um total de 4 endoints.
O url da API é https://json-server-first-api-fake.herokuapp.com/

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

`POST /register` <br/>
`POST /signup` <br/>
`POST /users`

#### formato da requisição: 
```json
{
	"email": "kenzojr@mail.com",
	"password": "123456",
	"name": "Kenzo junior",
	"age": 4
}
```

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.


### Login

`POST /login` <br/>
`POST /signin`

#### Formato da requisição:
```json
{
	"email": "kenzojr@mail.com",
	"password": "123456"
}
```

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### Consultar Tarefas

`GET /tasks`

### Consultar tarefas específicas de cada usuário

`GET /tasks?id=:user_id`

#### formato da requisição:

- não necessário

## Rotas que necessitam de autorização

Rotas que necessitam de autorização deve ser informado no cabeçalho da requisição o campo "Authorization", dessa forma:

> Authorization: Bearer {token}

### Cadastro de novas tarefas

`POST /tasks`

#### formato da requisição:
```json
{
	"name": "passear com o dog",
	"difficulty": "médio",
	"userId": 2
}
```
