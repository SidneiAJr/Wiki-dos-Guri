# JavaScript | Backend — Request e Response

## O que é `req` e `res`?

No backend JavaScript (principalmente com **Node.js + Express**), `req` e `res` são objetos fundamentais usados para **receber dados do cliente** e **enviar respostas**.

---

## `req` (Request)

O objeto `req` representa a **requisição feita pelo cliente** (browser, app mobile, Postman, etc.).

Com ele, o backend consegue acessar:

* Dados enviados pelo cliente
* Parâmetros da URL
* Corpo da requisição
* Cabeçalhos (headers)

### Exemplos comuns de uso do `req`

```js
req.params   // Parâmetros da rota
req.query    // Parâmetros da URL (?id=1)
req.body     // Dados enviados no corpo (POST, PUT)
req.headers  // Cabeçalhos da requisição
req.method   // Método HTTP (GET, POST, PUT, DELETE)
req.url      // URL acessada
```

---

## `res` (Response)

O objeto `res` representa a **resposta que o servidor envia para o cliente**.

Com ele, o backend pode:

* Retornar dados
* Retornar mensagens
* Definir status HTTP
* Encerrar a requisição

### Exemplos comuns de uso do `res`

```js
res.send()      // Envia resposta simples
res.json()      // Envia resposta em JSON
res.status()    // Define o status HTTP
res.end()       // Finaliza a resposta
```

---

## Exemplo básico com Express

```js
app.get('/usuarios', (req, res) => {
    res.send('Lista de usuários');
});
```

### O que acontece nesse código?

1. O cliente faz uma requisição GET para `/usuarios`
2. O servidor recebe essa requisição pelo objeto `req`
3. O servidor responde usando o objeto `res`

---

## Exemplo usando dados do `req`

```js
app.get('/usuarios/:id', (req, res) => {
    const id = req.params.id;
    res.json({ usuarioId: id });
});
```

---

## Fluxo Request → Response

1. Cliente faz a requisição
2. O servidor recebe (`req`)
3. O backend processa os dados
4. O servidor responde (`res`)
5. A conexão é encerrada

---

## Resumo

* `req` = tudo que **vem do cliente**
* `res` = tudo que **vai para o cliente**
* Toda rota sempre recebe `(req, res)`

---

## Observação

⚠ Uma requisição **sempre deve ter uma resposta**. Se o `res` não for enviado, a requisição ficará travada.
