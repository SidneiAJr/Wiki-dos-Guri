# JavaScript | Alteração de Elementos

## `classList`

A propriedade `classList` retorna um objeto com todos os nomes de classe (classes CSS) de um elemento. Esse objeto possui métodos que permitem adicionar, remover e alternar classes sem afetar as outras classes do elemento.

### Exemplos:

```javascript
const element = document.querySelector('#meuElemento');
element.classList.add('novaClasse');       // Adiciona uma nova classe
element.classList.remove('classeAntiga'); // Remove a classe especificada
element.classList.toggle('classeAlternada'); // Alterna a classe (se existir, remove; se não, adiciona)
```

### textContent
````javascript
const element = document.querySelector('#meuElemento');
console.log(element.textContent); // Lê o texto
element.textContent = 'Texto alterado'; // Modifica o texto
````

### appendChild
````javascript
const parent = document.querySelector('#meuElementoPai');
const child = document.createElement('div');
child.textContent = 'Novo Elemento';
parent.appendChild(child); // Adiciona o novo nó como filho
````

### createElement
````javascript
const newElement = document.createElement('div');
newElement.textContent = 'Novo Elemento Criado';
document.body.appendChild(newElement); // Adiciona o novo elemento ao corpo do documento
````

### addEventListener
````javascript
const button = document.querySelector('#meuBotao');
button.addEventListener('click', function() {
    alert('Botão clicado!');
});
````

### lastElementChild
````javascript
const parent = document.querySelector('#meuElementoPai');
const lastChild = parent.lastElementChild;
console.log(lastChild); // Exibe o último elemento filho
````

### target.classList
````javascript
const button = document.querySelector('#meuBotao');
button.addEventListener('click', function(event) {
    event.target.classList.add('clicado'); // Adiciona a classe ao botão clicado
});
````

### toggle
````javascript
const element = document.querySelector('#meuElemento');
element.classList.toggle('classeAlternada'); // Alterna a classe
````
