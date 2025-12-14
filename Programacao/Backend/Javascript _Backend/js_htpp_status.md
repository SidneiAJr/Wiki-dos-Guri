# JavaScript | HTTP Status

## O que são Status HTTP?

Os **status HTTP** são códigos numéricos enviados pelo servidor para informar ao cliente o **resultado da requisição**.

Eles ajudam o frontend, o backend e outras APIs a entenderem se a operação:

* deu certo
* falhou por erro do cliente
* falhou por erro do servidor

---

## Categoria dos Status

* **2xx** → Sucesso
* **3xx** → Redirecionamento
* **4xx** → Erro do cliente
* **5xx** → Erro do servidor

---

## Status 2xx — Sucesso

### 200 OK

Requisição realizada com sucesso.

```js
res.status(200).json(usuarios);
```

---

### 201 Created

Recurso criado com sucesso.

```js
res.status(201).send("Usuário criado com sucesso");
```

---

### 204 No Content

Requisição realizada com sucesso, mas sem retorno.

```js
res.status(204).end();
```

---

## Status 4xx — Erro do Cliente

### 400 Bad Request

Erro nos dados enviados pelo cliente.

```js
res.status(400).send("Dados inválidos");
```

---

### 401 Unauthorized

Usuário não autenticado.

```js
res.status(401).send("Não autorizado");
```

---

### 403 Forbidden

Usuário autenticado, mas sem permissão.

```js
res.status(403).send("Acesso negado");
```

---

### 404 Not Found

Recurso não encontrado.

```js
res.status(404).send("Usuário não encontrado");
```

---

## Status 5xx — Erro do Servidor

### 500 Internal Server Error

Erro inesperado no servidor.

```js
res.status(500).send("Erro interno do servidor");
```

---

## Boas Práticas

* Sempre retorne o status correto
* Não use `200` para erros
* Use `201` para criação de recursos
* Use `400` para erros de validação

---

## Resumo rápido

* `200` → sucesso
* `201` → criado
* `204` → sucesso sem retorno
* `400` → erro do cliente
* `401` → não autenticado
* `403` → sem permissão
* `404` → não encontrado
* `500` → erro do servidor
