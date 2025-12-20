# JavaScript | Callbacks vs Promises

## O que é um Callback?

Um **callback** é uma função passada como parâmetro para outra função, que será executada após uma operação.

### 📌 Exemplo com callback

```js
function buscarUsuarios(callback) {
    connection.query('SELECT * FROM usuarios', (erro, resultado) => {
        if (erro) return callback(erro);
        callback(null, resultado);
    });
}
```

---

## Problema dos Callbacks

* Código difícil de ler
* Muitos níveis de função
* Callback Hell

---

## O que é uma Promise?

Uma **Promise** representa uma operação assíncrona que pode ter sucesso ou erro.

### 📌 Exemplo com Promise

```js
function buscarUsuarios() {
    return new Promise((resolve, reject) => {
        connection.query('SELECT * FROM usuarios', (erro, resultado) => {
            if (erro) reject(erro);
            else resolve(resultado);
        });
    });
}
```

---

## Usando async / await

```js
async function listarUsuarios(req, res) {
    try {
        const usuarios = await buscarUsuarios();
        res.json(usuarios);
    } catch (erro) {
        res.status(500).send('Erro ao buscar usuários');
    }
}
```

---

## Comparação rápida

| Callback                | Promise       |
| ----------------------- | ------------- |
| Difícil de ler          | Mais legível  |
| Callback Hell           | Código linear |
| Difícil de tratar erros | try/catch     |

---

## Qual usar?

✔ Prefira **Promises + async/await** em projetos modernos.

---

## Resumo rápido

* Callback = função passada como parâmetro
* Promise = objeto assíncrono
* async/await = forma moderna e limpa
