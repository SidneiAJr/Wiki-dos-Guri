# JavaScript | Middlewares

## O que é um Middleware?

Um **middleware** é uma função que fica entre a **requisição (req)** e a **resposta (res)**.

Ele pode:

* Modificar a requisição
* Modificar a resposta
* Encerrar a requisição
* Passar para o próximo middleware

---

## Estrutura de um Middleware

```js
(req, res, next) => {
    // código
    next();
}
```

* `req` → requisição
* `res` → resposta
* `next()` → chama o próximo middleware

---

## Middleware nativo do Express

### express.json()

Permite ler JSON do corpo da requisição.

```js
app.use(express.json());
```

---

## Middleware de log

```js
app.use((req, res, next) => {
    console.log(req.method, req.url);
    next();
});
```

---

## Middleware por rota

```js
function autenticar(req, res, next) {
    if (!req.headers.authorization) {
        return res.status(401).send('Não autorizado');
    }
    next();
}

app.get('/admin', autenticar, (req, res) => {
    res.send('Área administrativa');
});
```

---

## Ordem dos middlewares

A ordem importa!

```js
app.use(express.json());
app.use(middleware1);
app.use(middleware2);
```

---

## Boas práticas

* Use middlewares para responsabilidades específicas
* Evite lógica pesada
* Sempre chame `next()` quando necessário

---

## Resumo rápido

* Middleware = intermediário entre req e res
* Pode ser global ou por rota
* Ordem de execução importa
