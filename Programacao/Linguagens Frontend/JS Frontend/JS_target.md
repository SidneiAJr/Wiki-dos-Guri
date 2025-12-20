# JavaScript | Target

A propriedade target é comumente utilizada dentro de eventos em JavaScript para referenciar o elemento que acionou o evento. O target é frequentemente usado para manipulação de eventos, como cliques, para obter o elemento exato que gerou o evento.

```js
document.addEventListener("click", function(event) {
    console.log("Elemento clicado:", event.target);
});
```

🔹 Usando getElementsByTagName() com target

Você pode combinar getElementsByTagName() com target para criar interações mais complexas. Por exemplo, pode-se adicionar um event listener para todos os elementos de uma determinada tag e usar o target para manipular o elemento que foi clicado.

```js
// Adicionando um evento de clique para todos os <button> no documento
let buttons = document.getElementsByTagName("button");

for (let i = 0; i < buttons.length; i++) {
    buttons[i].addEventListener("click", function(event) {
        alert("Você clicou no botão: " + event.target.innerText);
    });
}
```

| **Método/Propriedade**       | **Descrição**                                                                    |
| ---------------------------- | -------------------------------------------------------------------------------- |
| **`getElementsByTagName()`** | Retorna todos os elementos com o nome da tag especificada no documento.          |
| **`target`**                 | Retorna o **elemento** que disparou o evento (útil em manipuladores de eventos). |
