# 📘 JavaScript Básico – Função `pedeTudo()`

Este documento explica **passo a passo**, de forma **bem mastigada**, cada parte do código da função `pedeTudo()`. A ideia é servir como **wiki pessoal** para consulta rápida no futuro.

---

## 🔹 1. Declaração da função

```js
function pedeTudo() {
```

* Cria uma função chamada `pedeTudo`
* Tudo que estiver dentro das `{}` só roda quando a função for chamada

---

## 🔹 2. Entrada de dados com `prompt()`

```js
let nome = String(prompt("Insira seu Nome: "));
let idade = Number(prompt("Insira Sua Idade"));
```

* `prompt()` abre uma caixa de texto no **navegador**
* `String()` garante que o valor seja texto
* `Number()` converte texto em número

⚠️ Importante: `prompt()` sempre retorna **string**

---

## 🔹 3. Coleta de notas e cálculo da média

```js
let nota1 = Number(prompt("Insira nota: "))
let nota2 = Number(prompt("Insira nota: "))
let nota3 = Number(prompt("Insira nota: "))

let soma = (nota1 + nota2 + nota3) / 3;
```

* Pede 3 notas
* Soma tudo
* Divide por 3 → média final

---

## 🔹 4. Condicional (if / else if / else)

```js
if (soma >= 7) {
    console.log("Aprovado")
} else if (soma >= 5) {
    console.log("Em Recuperacao")
} else {
    console.log("Reprovado")
}
```

* Decide a situação do aluno
* Fluxo clássico:

  * ≥ 7 → aprovado
  * ≥ 5 → recuperação
  * < 5 → reprovado

---

## 🔹 5. Número par ou ímpar

```js
let numero = Number(prompt("Insira um Numero: "));
let verificaNumero = numero % 2
```

* `%` pega o resto da divisão
* Se resto = 0 → par
* Se resto ≠ 0 → ímpar

```js
if (verificaNumero === 0) {
    console.log("É par")
} else {
    console.log("É impar")
}
```

---

## 🔹 6. Array simples + `for...of`

```js
const frutas = ["Maça", "Banana", "uva"];
```

* Array é uma lista
* Guarda vários valores em uma variável só

```js
for (const fruta of frutas) {
    console.log(frutas)
}
```

⚠️ Observação:

* Aqui está imprimindo o **array inteiro**
* Para imprimir item por item, o ideal seria `console.log(fruta)`

---

## 🔹 7. Laço `for` numérico

```js
for (let i = 0; i <= 10; i++) {
    console.log(i + numero)
}
```

* `i` começa em 0
* Vai até 10
* Soma `i + numero`
* Muito usado para contadores e repetições

---

## 🔹 8. Arrow Function (função curta)

```js
const s = (a, b) => a + b
```

* Função moderna
* Recebe dois valores
* Retorna a soma automaticamente

```js
s(3, 5) // resultado: 8
```

---

## 🔹 9. Template String

```js
console.log(`Olá ${nome} Tudo certo? Média: ${soma}`)
```

* Usa crase `` ` ``
* `${}` injeta variáveis no texto
* Forma moderna de concatenar

---

## 🔹 10. Switch (menu por número)

```js
let diaSemana = Number(prompt("Insira um dia da semana de 1 a 7"))
```

```js
switch (diaSemana) {
    case 1:
        console.log("Segunda")
        break;
    case 2:
        console.log("Terça")
        break;
    case 3:
        console.log("Quarta")
        break;
    case 4:
        console.log("Quinta")
        break;
    case 5:
        console.log("Sexta")
        break;
    case 6:
        console.log("Sabado")
        break;
    case 7:
        console.log("Domingo")
        break;
}
```

* `switch` substitui vários `if`
* Muito usado para menus
* `break` impede cair no próximo caso

---

## 🔹 11. Soma de valores de um array

```js
const numeros = [1, 2, 3, 4, 5];
let somaArray = 0;
```

```js
for (let i = 0; i < numeros.length; i++) {
    somaArray += numeros[i];
}
```

* Percorre o array
* Soma todos os valores
* `length` retorna o tamanho

---

## 🔹 12. Entrada de dados no Node.js (`readline`)

```js
const readline = require('readline');
```

* Só funciona no **Node.js**
* Não funciona no navegador

```js
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});
```

```js
rl.question('Qual o seu nome? ', (nome) => {
    console.log(`Olá, ${nome}! Bem-vindo!`);
    rl.close();
});
```

⚠️ Importante:

* `prompt()` → navegador
* `readline` → terminal Node.js
* Em projeto real, escolha **um dos dois**

---

## 🔹 13. Chamada da função

```js
pedeTudo()
```

* Executa tudo que foi definido acima
* Sem isso, a função não roda

---

## ✅ Resumo rápido

* `prompt()` → entrada no navegador
* `Number()` / `String()` → conversão
* `if / else` → decisão
* `%` → par ou ímpar
* `for` → repetição
* `array` → lista
* `=>` → função curta
* `switch` → menu
* `readline` → entrada no terminal

---


