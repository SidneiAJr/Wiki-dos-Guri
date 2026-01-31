# 🖥️ JavaScript | getElementsByTagName()

## 🔹 getElementsByTagName()

O método getElementsByTagName() é utilizado para obter todos os elementos de um documento HTML que correspondem a uma tag específica. Ele retorna uma NodeList de todos os elementos que possuem a tag fornecida, e a busca é realizada de forma case-insensitive (não sensível a maiúsculas ou minúsculas).

```Javascript
let elements = document.getElementsByTagName(tagName);
````

````javascript
// Selecionando todos os elementos <p> no documento
let paragraphs = document.getElementsByTagName("p");

// Iterando sobre a NodeList retornada
for (let i = 0; i < paragraphs.length; i++) {
    console.log(paragraphs[i].innerText);
}
````

