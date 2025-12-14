# JavaScript | Promises

## O que são Promises?

Uma **Promise** é um objeto do JavaScript usado para representar uma **operação assíncrona** que pode:

- ✅ Ser resolvida com sucesso  
- ❌ Ser rejeitada com erro  
- ⏳ Ainda estar em execução  

Promises são muito usadas no **backend** para lidar com:
- Banco de dados
- Requisições HTTP
- Leitura de arquivos
- Operações demoradas

---

## Estados de uma Promise

Uma Promise sempre estará em um desses estados:

- **pending** → em execução  
- **fulfilled** → resolvida com sucesso  
- **rejected** → ocorreu um erro  

---

## Criando uma Promise

### 📌 Exemplo básico

```js
const minhaPromise = new Promise((resolve, reject) => {
    const sucesso = true;

    if (sucesso) {
        resolve("Operação realizada com sucesso");
    } else {
        reject("Erro na operação");
    }
});
```

## Consumindo uma Promise com .then() e .catch()
```js
minhaPromise
    .then(resultado => {
        console.log(resultado);
    })
    .catch(erro => {
        console.error(erro);
    });
.then() → executado quando a Promise é resolvida

.catch() → executado quando ocorre erro
```

## Promise com operação assíncrona (setTimeout)
```js
function esperar(ms) {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve(`Esperou ${ms} ms`);
        }, ms);
    });
}
esperar(2000).then(msg => console.log(msg));
```

## Promises no Backend (Exemplo real)
```js
function buscarUsuarios() {
    return new Promise((resolve, reject) => {
        connection.query("SELECT * FROM usuarios", (erro, resultado) => {
            if (erro) {
                reject(erro);
            } else {
                resolve(resultado);
            }
        });
    });
}
```

## async / await (forma moderna)

O async/await é uma forma mais limpa e legível de trabalhar com Promises.
```js
📌 Exemplo
async function listarUsuarios(req, res) {
    try {
        const usuarios = await buscarUsuarios();
        res.json(usuarios);
    } catch (erro) {
        res.status(500).send("Erro ao buscar usuários");
    }
}
```

## Promise.all()

Executa várias Promises em paralelo.
```js
Promise.all([promise1, promise2, promise3])
    .then(resultados => {
        console.log(resultados);
    })
    .catch(erro => {
        console.error(erro);
    });
```