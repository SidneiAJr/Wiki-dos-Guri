# ⚡ JavaScript | Async & Await

O async/await é uma forma moderna e simples de controlar operações assíncronas no JavaScript.
Ele torna o código mais legível do que callbacks ou .then().

## 🔹 O que é async?

A palavra-chave async transforma uma função em assíncrona, fazendo com que ela retorne automaticamente uma Promise.

````js
async function saudacao() {
    return "Olá, mundo!";
}

saudacao().then(console.log); // "Olá, mundo!"
````

## O que é await?

A palavra-chave await pausa a execução dentro da função async até que a Promise seja resolvida.

````js
async function carregarDados() {
    const resposta = await fetch("https://api.example.com/dados");
    const json = await resposta.json();
    console.log(json);
}
````

## 🧪 Exemplo Completo (com try/catch)
````js
async function buscarUsuario() {
    try {
        const resposta = await fetch("https://jsonplaceholder.typicode.com/users/1");
        const usuario = await resposta.json();
        console.log("Usuário carregado:", usuario);
    } catch (erro) {
        console.error("Erro ao buscar usuário:", erro);
    }
}

buscarUsuario();
````

⏳ Usando await com funções internas
````js
function esperar(ms) {
    return new Promise(resolve => setTimeout(resolve, ms));
}

async function executar() {
    console.log("Iniciou...");
    await esperar(2000); 
    console.log("2 segundos depois...");
}

executar();
````

| Erro                                   | Explicação                                   |
| -------------------------------------- | -------------------------------------------- |
| ❌ Usar `await` fora de função async    | await só funciona dentro de `async function` |
| ❌ Esquecer try/catch                   | Promises rejeitadas quebram a função         |
| ❌ Encadear muitos awaits independentes | use `Promise.all()`                          |

