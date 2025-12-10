# ⚛️ O que é React?

**React** é uma biblioteca JavaScript criada pelo **Facebook (Meta)** em 2013 para o desenvolvimento de **interfaces de usuário (UI)**.  
Ele é usado principalmente para construir **aplicações web dinâmicas e modernas**, com alto desempenho e facilidade de manutenção.

Diferente de frameworks completos como Angular ou Vue, o React foca exclusivamente na **camada de visualização** da aplicação (a parte que o usuário vê e interage).

---

## 🧠 Conceito Principal

O React é baseado em **componentes** — pequenos blocos de código que representam partes independentes da interface, como botões, formulários ou menus.  
Esses componentes podem ser **reutilizados** em várias partes da aplicação, o que torna o código mais organizado e eficiente.

Exemplo de um componente React simples:

```jsx
function OlaMundo() {
  return <h1>Olá, Mundo!</h1>;
}
```

⚙️ Como o React Funciona

O React trabalha com algo chamado DOM Virtual (Virtual DOM).
Em vez de atualizar diretamente a página inteira no navegador, ele mantém uma cópia virtual da interface na memória.

Quando algo muda (por exemplo, o usuário digita em um campo), o React compara o novo estado com o anterior e atualiza apenas o que realmente mudou — deixando a aplicação mais rápida e eficiente.

## 🧩 Componentes e Estado
🔹 Componentes

São funções ou classes que retornam elementos visuais (HTML dentro do JavaScript).
Cada componente pode ter seu próprio comportamento e aparência.

🔹 Estado (State)

O estado representa dados dinâmicos do componente — valores que mudam com o tempo, como um contador, input de usuário ou resultado de API.
