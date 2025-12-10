# TypeScript | Função & Promise

Neste tutorial, vamos aprender como trabalhar com **funções** e **Promises** em **TypeScript**. Vamos abordar como declarar funções, lidar com valores assíncronos e como usar **Promises** para tratar operações assíncronas.

---

## 🧑‍💻 **Funções em TypeScript**

### O que é uma Função?

Uma **função** é um bloco de código que pode ser executado em qualquer momento, e pode ou não retornar um valor. Em TypeScript, você pode declarar funções com tipagem explícita para garantir que os parâmetros e o retorno estejam no formato correto.

### 1. **Função Simples**

A declaração básica de uma função em TypeScript:

```typescript
function saudacao(nome: string): string {
    return `Olá, ${nome}!`;
}

console.log(saudacao("João")); // Saída: "Olá, João!"
```

### Funções com Parâmetros Opcionais

````ts
function saudacao(nome: string, idade?: number): string {
    if (idade) {
        return `Olá, ${nome}, você tem ${idade} anos!`;
    } else {
        return `Olá, ${nome}!`;
    }
}

console.log(saudacao("João")); // Saída: "Olá, João!"
console.log(saudacao("Maria", 30)); // Saída: "Olá, Maria, você tem 30 anos!"
````

### ⚡ Promises em TypeScript

O que é uma Promise?

- Uma Promise em JavaScript (e TypeScript) é uma representação de um valor que pode estar disponível agora, ou no futuro, após uma operação assíncrona ser completada. As Promises são úteis para lidar com operações assíncronas como chamadas de API, leitura de arquivos, etc.

#### Criando uma Promise

Aqui está um exemplo simples de uma Promise em TypeScript:

````ts
function fetchData(): Promise<string> {
    return new Promise((resolve, reject) => {
        let sucesso = true;

        if (sucesso) {
            resolve("Dados carregados com sucesso!");
        } else {
            reject("Erro ao carregar os dados.");
        }
    });
}

fetchData()
    .then((resultado) => {
        console.log(resultado); // Saída: "Dados carregados com sucesso!"
    })
    .catch((erro) => {
        console.error(erro); // Saída: "Erro ao carregar os dados."
    });
````
- Promise<string>: A Promise retorna um valor do tipo string quando resolvida.

- resolve: Resolve a Promise com o valor desejado.

- reject: Rejeita a Promise com uma mensagem de erro.

### Usando async e await com Promises

O async e await facilitam o trabalho com Promises, tornando o código assíncrono mais legível.

````ts
async function obterDados(): Promise<string> {
    let resultado = await fetchData();
    return resultado;
}

obterDados()
    .then((dados) => {
        console.log(dados); // Saída: "Dados carregados com sucesso!"
    })
    .catch((erro) => {
        console.error(erro);
    });
````

### Encadeamento de Promises

````ts
function passo1(): Promise<string> {
    return new Promise((resolve) => resolve("Passo 1 concluído"));
}

function passo2(): Promise<string> {
    return new Promise((resolve) => resolve("Passo 2 concluído"));
}

function passo3(): Promise<string> {
    return new Promise((resolve) => resolve("Passo 3 concluído"));
}

passo1()
    .then((resultado1) => {
        console.log(resultado1);
        return passo2(); // Chama o próximo passo
    })
    .then((resultado2) => {
        console.log(resultado2);
        return passo3(); // Chama o próximo passo
    })
    .then((resultado3) => {
        console.log(resultado3); // Exibe o último passo
    })
    .catch((erro) => {
        console.error("Erro:", erro);
    });
````

### 🧱 Diferenças entre Funções e Promises

| **Função**                                 | **Promise**                                       |
| ------------------------------------------ | ------------------------------------------------- |
| Funções são chamadas de forma síncrona     | Promises lidam com operações assíncronas          |
| Retorna um valor imediatamente             | Retorna um valor que será resolvido no futuro     |
| Pode ser usada para cálculos simples       | Ideal para chamadas de API ou operações demoradas |
| **Exemplo**: `function soma(a, b): number` | **Exemplo**: `fetchData().then((dados) => {...})` |
