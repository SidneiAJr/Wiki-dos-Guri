# JavaScript | Manipulação de Elementos DOM - Child Nodes

No JavaScript, podemos acessar e manipular os nós filhos de um elemento HTML através da interface DOM (Document Object Model). Aqui, vamos falar sobre os métodos lastChild, firstChild, e outros métodos úteis.

## 🏷️ lastChild

O lastChild é uma propriedade que retorna o último nó filho de um elemento. Isso pode ser um nó de texto, um elemento, ou um comentário.

```js
let element = document.getElementById("meuElemento");
let ultimoFilho = element.lastChild;
console.log(ultimoFilho);
```

## 🏷️ firstChild

O firstChild retorna o primeiro nó filho de um elemento, de forma similar ao lastChild.

```js
let element = document.getElementById("meuElemento");
let primeiroFilho = element.firstChild;
console.log(primeiroFilho);
```

## 🏷️ childNodes

A propriedade childNodes retorna uma coleção de todos os nós filhos de um elemento, incluindo nós de texto, comentários e elementos.
```js
let element = document.getElementById("meuElemento");
let filhos = element.childNodes;
console.log(filhos);
```

## 🏷️children
A propriedade children retorna uma coleção de somente os nós de elementos filhos (excluindo nós de texto ou comentários).
```js
let element = document.getElementById("meuElemento");
let filhosElementos = element.children;
console.log(filhosElementos);
```

## 🏷️lastElementChild

A propriedade lastElementChild retorna o último elemento filho do nó, mas diferentemente de lastChild, ela não retorna nós de texto ou comentários — apenas elementos HTML.
```js
let element = document.getElementById("meuElemento");
let ultimoElemento = element.lastElementChild;
console.log(ultimoElemento);
```

## 🏷️firstElementChild

A propriedade firstElementChild funciona da mesma maneira que o lastElementChild, mas retorna o primeiro elemento filho.

```js
let element = document.getElementById("meuElemento");
let primeiroElemento = element.firstElementChild;
console.log(primeiroElemento);
```

## 🏷️parentNode (para acessar o pai)

A propriedade parentNode retorna o nó pai do elemento especificado.
```js
let element = document.getElementById("meuElemento");
let pai = element.parentNode;
console.log(pai);
```

## 🏷️parentElement (para acessar o pai com elementos)

parentElement também retorna o nó pai, mas é mais específico, já que vai retornar apenas um elemento (sem incluir nós de texto ou comentários).

```js
let element = document.getElementById("meuElemento");
let paiElemento = element.parentElement;
console.log(paiElemento);
```

## 🏷️nextSibling e previousSibling

- nextSibling retorna o nó irmão seguinte ao elemento atual.

- previousSibling retorna o nó irmão anterior ao elemento atual.

```js
let element = document.getElementById("meuElemento");
let proximoIrmao = element.nextSibling;
let irmaoAnterior = element.previousSibling;

console.log(proximoIrmao);
console.log(irmaoAnterior);
```

| **Propriedade**         | **Descrição**                                                                            |
| ----------------------- | ---------------------------------------------------------------------------------------- |
| **`lastChild`**         | Retorna o último nó filho (pode ser texto, comentário, ou elemento).                     |
| **`firstChild`**        | Retorna o primeiro nó filho (pode ser texto, comentário, ou elemento).                   |
| **`childNodes`**        | Retorna todos os filhos, incluindo nós de texto e comentários.                           |
| **`children`**          | Retorna apenas os elementos filhos (exclui texto e comentários).                         |
| **`lastElementChild`**  | Retorna o último **elemento** filho (não inclui texto ou comentários).                   |
| **`firstElementChild`** | Retorna o primeiro **elemento** filho (não inclui texto ou comentários).                 |
| **`parentNode`**        | Retorna o nó pai de um elemento (pode ser qualquer tipo de nó).                          |
| **`parentElement`**     | Retorna o nó pai, mas especificamente um **elemento** (não inclui texto ou comentários). |
| **`nextSibling`**       | Retorna o próximo **nó irmão** (pode ser texto, comentário ou elemento).                 |
| **`previousSibling`**   | Retorna o anterior **nó irmão** (pode ser texto, comentário ou elemento).                |



