# 💻 Introdução ao JavaScript

JavaScript é uma linguagem de programação amplamente utilizada para desenvolvimento web,  
tanto no front-end (navegador) quanto no back-end (Node.js).  
É uma linguagem dinâmica, interpretada e orientada a objetos baseada em protótipos.

---

## 🧩 Tipos de Variáveis

- `var`: Escopo global ou de função. Pode ser reatribuída (mutável).  
- `let`: Escopo de bloco. Mutável.  
- `const`: Escopo de bloco. Imutável (não pode ser reatribuída).

---

## 📦 Tipos de Dados

| Tipo       | Descrição                         | Exemplo                  |
|------------|----------------------------------|--------------------------|
| `string`   | Texto                            | `"Olá, mundo"`           |
| `number`   | Números (inteiros e decimais)    | `42`, `3.14`             |
| `boolean`  | Verdadeiro ou falso              | `true`, `false`          |
| `undefined`| Variável declarada sem valor     | `let x;`                 |
| `null`     | Valor nulo                       | `let y = null;`          |
| `object`   | Objetos, arrays, funções         | `{ nome: "Ana" }`, `[1,2,3]` |
| `symbol`   | Identificador único              | `Symbol("id")`           |
| `bigint`   | Números inteiros muito grandes   | `9007199254740991n`      |

---

## ✏️ Declaração de Variáveis

JavaScript não tem tipagem explícita.  
Os tipos são definidos automaticamente em tempo de execução.

Exemplo:
```js
let numero = 10;
const nome = "Sidnei";
var ativo = true;
```

## Loop: 
```JS
for(let i=0; i<=10; i++){
    console.log(`Incrementado ${i}`)
}
```
## Operações Matematicas:

- let n1 = 5;
- let n2 = 5;
- n1 === n2 -> Comparação.
- n1 + n2 -> Soma
- n1 - n2 -> Diminuir
- n1 * n2 -> Multiplicar
- n1 / n2-> Divisão
- n1 > n2 -> Menor que
- n1 < n2 -> Maior que
- n1 <= n2 -> Maior ou igual
- n2 >= n1 -> Menor ou igual 

## Condicao:
```JS
if(n1===n2){
    console.log("Não e Igual")
}else{
    console.log("E igual")
}
```
## Array:
```JS
let array = [1,2,3,5,6,7]
```
| 🧩 Categoria | 🔹 Método / Propriedade | 💬 Descrição                                                                   | 💡 Exemplo                               |
| ------------ | ----------------------- | ------------------------------------------------------------------------------ | ---------------------------------------- |
| **Array**    | `map()`                 | Cria um novo array com base em um existente, aplicando uma função a cada item. | `nums.map(n => n * 2)` → `[2,4,6]`       |
|              | `filter()`              | Filtra elementos de um array com base em uma condição.                         | `nums.filter(n => n > 5)`                |
|              | `reduce()`              | Reduz o array a um único valor (como soma ou média).                           | `nums.reduce((a,b)=>a+b,0)`              |
|              | `forEach()`             | Executa uma função para cada item do array (sem retornar novo array).          | `nums.forEach(n => console.log(n))`      |
|              | `push()`                | Adiciona elemento ao final do array.                                           | `arr.push('novo')`                       |
|              | `pop()`                 | Remove o último elemento do array.                                             | `arr.pop()`                              |
|              | `shift()`               | Remove o primeiro elemento do array.                                           | `arr.shift()`                            |
|              | `unshift()`             | Adiciona elemento no início do array.                                          | `arr.unshift('início')`                  |
|              | `splice()`              | Remove, adiciona ou substitui elementos em posições específicas.               | `arr.splice(1,2,'novo')`                 |
|              | `slice()`               | Retorna uma cópia parcial do array.                                            | `arr.slice(0,3)`                         |
|              | `length`                | Retorna o tamanho do array.                                                    | `arr.length`                             |
| **String**   | `length`                | Retorna o comprimento da string.                                               | `"texto".length`                         |
|              | `toUpperCase()`         | Converte para maiúsculas.                                                      | `"abc".toUpperCase()` → `"ABC"`          |
|              | `toLowerCase()`         | Converte para minúsculas.                                                      | `"ABC".toLowerCase()` → `"abc"`          |
|              | `substring()`           | Extrai parte de uma string.                                                    | `"JavaScript".substring(0,4)` → `"Java"` |
|              | `indexOf()`             | Retorna o índice da primeira ocorrência de uma substring.                      | `"abc".indexOf("b")` → `1`               |
|              | `replace()`             | Substitui parte da string por outra.                                           | `"ola mundo".replace("mundo", "JS")`     |



## Interação com DOM (JS/HTML)
- document.getElementById(): Seleciona um elemento pelo seu id.
- document.getElementsByClassName(): Seleciona elementos pela classe.
- document.querySelector(): Seleciona o primeiro elemento que corresponde ao seletor CSS.
- document.querySelectorAll(): Seleciona todos os elementos que correspondem ao seletor.

## Função:
```JS
Funções
// Declaração de função tradicional
function soma(a, b) {
  return a + b;
}

// Função anônima / arrow function
const multiplica = (a, b) => a * b;
```

## Objetos(Dicionario)
```JS
let pessoa = {
  nome: "Ana",
  idade: 25,
  falar() {
    console.log(`Olá, meu nome é ${this.nome}`);
  }
};

pessoa.falar();
```

## Manipulação de Eventos (DOM)
```JS
// Adiciona um evento de clique a um botão
const btn = document.getElementById('meuBotao');
btn.addEventListener('click', () => {
  alert('Botão clicado!');
});
```

## Promises e Assíncrono
```JS
// Promise simples
const promessa = new Promise((resolve, reject) => {
  setTimeout(() => resolve('Sucesso!'), 1000);
});
promessa.then((resultado) => console.log(resultado));
```

## Async/Await
```JS
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/dados');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Erro:', error);
  }
}
fetchData();
```

## Módulos (import/export)
```JS
// arquivo.js
export const pi = 3.14;
export function soma(a, b) {
  return a + b;
}

// main.js
import { pi, soma } from './arquivo.js';
```
