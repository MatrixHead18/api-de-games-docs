# API de Games

## EndPoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parametros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo de resposta:
```
{
  "user": {
    "id": 1,
    "email": "victor@udemy.com"
  },
  "games": [
    {
      "id": 23,
      "title": "Call of duty MW",
      "year": 2019,
      "price": 60
    },
    {
      "id": 65,
      "title": "Sea of thieves",
      "year": 2018,
      "price": 40
    },
    {
      "id": 2,
      "title": "Minecraft",
      "year": 2012,
      "price": 20
    }
  ]
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que acoteceu alguma falha durante o processo de autenticação de requisição. Motivos: Token inválido, Token expirado.

Exemplo de resposta:
```
{
  "err": "Token Inválido"
}
```
### POST /auth
Esse endpoint é responsável por retornar fazer o processo de login.
#### Parametros
email: E-mail do usuário cadastrado o sistema.
password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo:
```
{
	"email": "victor@udemy.com",
	"password": "nodejs<3"
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para acesso aos endpoints na API.

Exemplo de resposta:
```
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ2aWN0b3JAdWRlbXkuY29tIiwiaWF0IjoxNTk0MzgxMzg3LCJleHAiOjE1OTQ1NTQxODd9.gvFoZA_WV45bfrCPkcDHu2MsLITBmrbeX0MDHEDtqlI"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que acoteceu alguma falha durante o processo de autenticação de requisição. Motivos: Senha ou email incorretos.

Exemplo de resposta:
```
{
  "err": "Credenciais Inválidas"
}
```
