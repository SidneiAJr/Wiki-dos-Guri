# JavaScript | Capturando Valores

## `getElementById`

O método `getElementById` retorna o primeiro elemento do documento que corresponde ao ID especificado. Esse método é usado para capturar um único elemento com base no atributo `id` do HTML.

### Exemplos:

```javascript
const element = document.getElementById('meuElemento');
console.log(element); // Exibe o elemento com o ID 'meuElemento'
```

### `getElementsByClassName`
````js
const elements = document.getElementsByClassName('minhaClasse');
console.log(elements); // Exibe todos os elementos com a classe 'minhaClasse'
````
- O método getElementsByClassName retorna uma coleção de elementos com a classe especificada. Essa coleção é "ao vivo", ou seja, é automaticamente atualizada quando a estrutura do DOM muda.

### `getElementsByClassName`
````js
const parent = document.getElementById('meuElementoPai');
const elements = parent.getElementsByClassName('minhaClasse');
console.log(elements); // Exibe os elementos com a classe 'minhaClasse' dentro de 'meuElementoPai'
````
- Esse método combina o uso do getElementsByClassName com um ID específico, permitindo capturar elementos com uma classe específica dentro de um determinado elemento.

### `querySelector`
````js
const element = document.querySelector('#meuElemento');
console.log(element); // Exibe o primeiro elemento com o ID 'meuElemento'
````
- O método querySelector retorna o primeiro elemento que corresponde a um seletor CSS especificado. É mais flexível do que getElementById ou getElementsByClassName, permitindo o uso de qualquer seletor CSS válido.

### `querySelectorAll`
````js
const elements = document.querySelectorAll('.minhaClasse');
console.log(elements); // Exibe todos os elementos com a classe 'minhaClasse'
````
- O método querySelectorAll retorna todos os elementos que correspondem ao seletor CSS especificado. A diferença principal em relação ao querySelector é que ele retorna uma NodeList com todos os elementos que atendem ao critério, enquanto querySelector retorna apenas o primeiro.
