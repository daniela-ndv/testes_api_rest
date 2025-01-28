## Requisições utilizando curl

### Alguns argumentos do curl

* -X: define o método HTTP da requisição. 
* -i: inclui o conteúdo do Header (cabeçalho da resposta HTTP) na saída.
* -s: “silent mode” (modo silencioso), reove algumas saídas padrão do curl, como progresso da requisição, para deixar a saída mais limpa.
* -d: Especifica os dados que serão enviados no corpo da requisição.
* -H: Adiciona cabeçalhos HTTP à requisição.
---

### Exemplos de requests e responses:

Usuários: 

* Usuário comum: { "email": "usuario@email.com", "senha": "123456" } 
* Usuário administrador: { "email": "admin@email.com", "senha": "654321" }

---

-> Colher token de autenticação de um usuário:

```
curl -X POST -is http://localhost:8089/api/v1/auth -d '{ "email": "admin@email.com", "senha": "654321" }' -H 'Content-Type: application/json'
```
* Resposta:
``` 
HTTP/1.1 200
X-Content-Type-Options: nosniff
X-XSS-Protection: 1; mode=block
Cache-Control: no-cache, no-store, max-age=0, must-revalidate
Pragma: no-cache
Expires: 0
X-Frame-Options: DENY
Content-Type: application/json;charset=UTF-8
Transfer-Encoding: chunked
Date: Tue, 28 Jan 2025 13:33:18 GMT

{"data":{"token":"eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJhZG1pbkBlbWFpbC5jb20iLCJyb2xlIjoiUk9MRV9BRE1JTiIsImNyZWF0ZWQiOjE3MzgwNzExOTUwNzEsImV4cCI6MTczODE3MTE5NH0.mv4y0mBWdo654rVTGNmpmRLwHjqEbIEGMPYxiypOplygvr9sPgwxAhxrkW0PzgIh5lJatBCK0NV775KQEDna1A"},"errors":[]}
```

---

-> Cadastrar uma viagem:
```
curl -X POST -is http://localhost:8089/api/v1/viagens -d '{ "acompanhante": "Teste", "dataPartida": "2025-01-23", "dataRetorno": "2025-01-25", "localDeDestino": "Manaus", "regiao": "Norte" }' -H 'Content-Type: application/json' -H 'Authorization: eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJhZG1pbkBlbWFpbC5jb20iLCJyb2xlIjoiUk9MRV9BRE1JTiIsImNyZWF0ZWQiOjE3MzgwNzIwMjA4MjEsImV4cCI6MTczODE3MjAxOX0.aiUBGyBBhitq5u7_OpFhDDUU9LzU2hCQC85zYNt2CVYTb3-Gh7s0C8tk-z8TUWzGgY2QhpOdrgetOR8M9Yw4DQ'
```
* Resposta: 
```
HTTP/1.1 201
X-Content-Type-Options: nosniff
X-XSS-Protection: 1; mode=block
Cache-Control: no-cache, no-store, max-age=0, must-revalidate
Pragma: no-cache
Expires: 0
X-Frame-Options: DENY
Location: http://localhost:8089/api/v1/viagens/1
Content-Type: application/json;charset=UTF-8
Transfer-Encoding: chunked
Date: Tue, 28 Jan 2025 13:47:32 GMT

{"data":{"id":1,"localDeDestino":"Manaus","dataPartida":"2025-01-23","dataRetorno":"2025-01-25","acompanhante":"Teste","regiao":"Norte"},"errors":[]}
```
---



