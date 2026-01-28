# 🧱 Manipulação de DOM em JavaScript

O **DOM (Document Object Model)** é a forma como o JavaScript interage com o conteúdo de uma página HTML.  
Ele transforma cada parte da página (tags, textos, atributos) em **objetos manipuláveis**.

Em outras palavras:  
> O DOM é o mapa da tua página — e o JavaScript é o explorador.

---

## 📜 Comandos básicos

### 🔹 `document.getElementById("id")`
Busca **um elemento específico** pelo atributo `id`.

```js
const titulo = document.getElementById("titulo");
titulo.innerHTML = "Olá, Mundo!";
```

## 🔹document.getElementsByClassName("classe")
Busca vários elementos que compartilham a mesma classe.
Retorna uma coleção (HTMLCollection).
```js
const botoes = document.getElementsByClassName("btn");
botoes[0].style.backgroundColor = "blue";
```

## 🔹document.getElementsByTagName("tag")
Seleciona todos os elementos de uma tag HTML específica (ex: div, p, span).
```js
const paragrafos = document.getElementsByTagName("p");
paragrafos[1].innerHTML = "Texto atualizado via JS!";
```

## 🔹document.querySelector("seletor")
Seleciona o primeiro elemento que bate com o seletor (igual CSS).
```js
const titulo = document.querySelector(".titulo");
titulo.style.color = "red";
```

## 🔹document.querySelectorAll("seletor")
Seleciona todos os elementos que batem com o seletor (retorna uma NodeList).
```js
const itens = document.querySelectorAll(".item");
itens.forEach(el => el.style.color = "green");
```

| Comando                    | Retorna          | Tipo de busca |
| -------------------------- | ---------------- | ------------- |
| `getElementById()`         | 1 elemento       | ID único      |
| `getElementsByClassName()` | Vários elementos | Classe        |
| `getElementsByTagName()`   | Vários elementos | Tag HTML      |
| `querySelector()`          | 1 elemento       | Seletor CSS   |
| `querySelectorAll()`       | Vários elementos | Seletor CSS   |
