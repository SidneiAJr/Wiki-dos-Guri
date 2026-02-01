# JavaScript | Tratamento de Erros

## Por que tratar erros no backend?

O tratamento de erros garante que:

* O servidor não quebre
* O cliente receba respostas claras
* Problemas sejam mais fáceis de debugar

No backend JavaScript, erros podem vir de:

* Banco de dados
* Validações
* Requisições inválidas
* Falhas internas do servidor

---

## Tratamento de erros com try/catch

Usado principalmente com **async/await**.

```js
app.get('/usuarios', async (req, res) => {
    try {
        const usuarios = await buscarUsuarios();
        res.status(200).json(usuarios);
    } catch (erro) {
        res.status(500).send('Erro ao buscar usuários');
    }
});
```

---

## Tratamento de erros com callbacks

```js
connection.query('SELECT * FROM usuarios', (erro, resultado) => {
    if (erro) {
        return res.status(500).send('Erro no banco de dados');
    }
    res.json(resultado);
});
```

---

## Middleware de erro global

Centraliza o tratamento de erros da aplicação.

```js
app.use((err, req, res, next) => {
    console.error(err);
    res.status(500).json({ erro: err.message });
});
```

---

## Erros comuns

* Não retornar resposta em caso de erro
* Usar status 200 para erro
* Não tratar exceções assíncronas

---

## Boas práticas

* Sempre retornar um status HTTP adequado
* Nunca expor erros sensíveis ao cliente
* Logar erros no servidor

---

## Resumo rápido

* Use `try/catch` com async/await
* Trate erros de banco e validação
* Use middleware de erro global
