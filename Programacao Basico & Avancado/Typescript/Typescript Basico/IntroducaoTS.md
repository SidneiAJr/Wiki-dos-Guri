# 💻 Introdução a TypeScript (Delírio Coletivo)

TypeScript é um **superset do JavaScript** criado pela Microsoft que adiciona **tipagem estática**, **interfaces**, **classes** e **recursos avançados de orientação a objetos**.  
Ele é compilado para **JavaScript puro**, sendo totalmente compatível com navegadores e Node.js.

---

## 📦 Tipos de Variáveis

| Tipo        | Descrição                                | Exemplo                              |
|--------------|------------------------------------------|--------------------------------------|
| `string`     | Texto                                   | `let nome: string = "Ana";`         |
| `number`     | Números inteiros e decimais             | `let idade: number = 30;`           |
| `boolean`    | Verdadeiro ou falso                     | `let ativo: boolean = true;`        |
| `any`        | Aceita qualquer tipo (⚠️ evite usar)   | `let valor: any = 5;`               |
| `unknown`    | Tipo desconhecido, precisa verificação  | `let dado: unknown;`                |
| `void`       | Usado em funções sem retorno            | `function log(): void {}`           |
| `array`      | Lista de elementos                      | `let numeros: number[] = [1,2,3];`  |
| `tuple`      | Array com tipos fixos por posição        | `let pessoa: [string, number] = ["Maria", 30];` |
| `enum`       | Enumeração de valores nomeados          | `enum Cor { Vermelho, Verde, Azul }`|
| `null`       | Valor nulo                              | `let nulo: null = null;`            |
| `undefined`  | Valor indefinido                        | `let indef: undefined;`             |

---

## 🔢 Declaração de Variáveis

```ts
var nome = "João";   // Escopo de função — evite usar
let idade = 25;      // Escopo de bloco, mutável
const ativo = true;  // Constante, imutável



```TS
function soma(a: number, b: number): number {
  return a + b;
}
```

```TS
Função anônima / arrow function
const multiplicar = (a: number, b: number): number => a * b;
```

```TS
Condicional
if (idade > 18) {
  console.log("Maior de idade");
} else {
  console.log("Menor de idade");
}
```

```TS
let numeros: number[] = [1, 2, 3];
let nomes: Array<string> = ["Ana", "Carlos"];

// Tupla - array com tipos fixos em posições fixas
let pessoa: [string, number] = ["Maria", 30];
```

```TS
let numeros: number[] = [1, 2, 3];
let nomes: Array<string> = ["Ana", "Carlos"];

// Tupla - array com tipos fixos em posições fixas
let pessoa: [string, number] = ["Maria", 30];

```

```TS
for (let i = 0; i < numeros.length; i++) {
  console.log(numeros[i]);
}

// Usando forEach
numeros.forEach((num) => console.log(num));
```

```TS
interface Pessoa {
  nome: string;
  idade: number;
  ativo?: boolean; // opcional
}

const pessoa1: Pessoa = {
  nome: "João",
  idade: 28,
};
```

```TS
Classes
class Animal {
  nome: string;

  constructor(nome: string) {
    this.nome = nome;
  }

  mover(distancia: number): void {
    console.log(`${this.nome} moveu ${distancia} metros.`);
  }
}

const cachorro = new Animal("Rex");
cachorro.mover(10);
```

```TS
Manipulação do DOM
const botao = document.getElementById("btn") as HTMLButtonElement;

botao.addEventListener("click", () => {
  alert("Botão clicado!");
});
```
