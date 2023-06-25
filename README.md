# API de Games
Esta API é utilizada para listar uma lista de games.
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados
#### Parametros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta
```
    "games": 
    [
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
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado.

Exemplo de resposta
```
{
    "err": "Token inválido!"
}
```

# API de Games
Esta API é utilizada para listar uma lista de games.
## Endpoints
### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parametros
email: E-mail do usuário cadastrado no sistema

password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo: 
```
{
   "email": "fulano123@gmail.com",
   "password": "nodejs<3"
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo de resposta
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJmdWxhbm8xMjNAZ21haWwuY29tIiwiaWF0IjoxNjg3NzA0Mjk5LCJleHAiOjE2ODc4NzcwOTl9.47Uw_0K-mPo2RZs_JUzHow17bOIvCRsr75wM1CXs9A8"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou E-mails incorretos.

Exemplo de resposta
```
{
  err: "Credenciais inválidas!"
}
```