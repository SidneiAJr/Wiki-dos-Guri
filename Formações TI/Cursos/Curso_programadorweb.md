# Curso de Programador Web

## Introdução ao HTML e CSS

Durante o curso, adquiri conhecimentos fundamentais sobre a construção de páginas web utilizando **HTML** (HyperText Markup Language) e **CSS** (Cascading Style Sheets). Aprendi a estruturar o conteúdo de uma página web com HTML, utilizando tags como `<div>`, `<header>`, `<footer>`, `<section>`, entre outras. No CSS, estudei como estilizar esses elementos, incluindo manipulação de cores, fontes, layouts e posicionamento.

## Introdução ao JavaScript

Após dominar as bases do HTML e CSS, foi a vez de aprender **JavaScript**, uma linguagem fundamental para tornar as páginas web interativas e dinâmicas. No início, estudei os conceitos básicos de JavaScript, como a manipulação de elementos DOM, eventos e interações com o usuário.

### Revisão Geral de JavaScript

Para reforçar o aprendizado, realizamos uma revisão geral dos principais conceitos da linguagem, como:

- **Tipos de Dados:** String, Number, Boolean, Object, Array, etc.
- **Operadores:** Aritméticos, lógicos e de comparação.
- **Estruturas Condicionais:** `if`, `else`, `switch`.
- **Laços de Repetição:** `for`, `while`, `do while`.
- **Funções:** Declaração e invocação de funções.
- **Objetos e Arrays:** Manipulação de dados estruturados.

## Como Funciona uma Variável em JavaScript

Em **JavaScript**, uma variável é um espaço de memória nomeado que armazena um valor. As variáveis podem ser declaradas utilizando as palavras-chave `var`, `let` e `const`, cada uma com escopos e comportamentos diferentes:

- **`var`**: Declara uma variável com escopo global ou de função, dependendo de onde é declarada. Não tem boa prática de uso devido ao seu escopo flexível e o comportamento de "hoisting".
- **`let`**: Declara uma variável com escopo de bloco, mais restrito que o `var`. É o recomendado para a maioria das situações, pois oferece maior controle sobre o escopo.
- **`const`**: Usada para declarar uma constante, ou seja, uma variável cujo valor não pode ser alterado depois de atribuído. Também tem escopo de bloco.

Exemplo:

```javascript
let nome = "João";
const idade = 30;
nome = "Maria";  // Reatribuindo o valor da variável 'nome'
