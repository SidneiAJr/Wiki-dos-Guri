# 🧩 JavaScript — Eventos e Interatividade

Os **eventos** em JavaScript são ações que ocorrem no navegador, como cliques, movimentos do mouse, teclas pressionadas ou o carregamento de uma página.  
Com eles, o JavaScript consegue **reagir às interações do usuário** e tornar as páginas **dinâmicas**.

---

## 🎯 Tipos de Eventos Comuns

| Tipo de Evento | Descrição | Exemplo |
|----------------|------------|----------|
| `onclick` | Quando o elemento é clicado | Botão, link, imagem |
| `onmouseover` | Quando o mouse passa sobre o elemento | Destaque visual |
| `onmouseout` | Quando o mouse sai do elemento | Restaurar estilo |
| `onkeydown` | Quando uma tecla é pressionada | Captura de entrada |
| `onkeyup` | Quando uma tecla é liberada | Detectar digitação |
| `onchange` | Quando valor de input muda | Formulários |
| `onsubmit` | Quando formulário é enviado | Validação |
| `onload` | Quando a página ou elemento termina de carregar | Inicialização |

---

## 🧠 Formas de Usar Eventos

### 1. **Inline (no HTML)**
Adiciona o evento diretamente no elemento.

```html
<button onclick="alert('Olá!')">Clique aqui</button>
```

## Por atributo no DOM

```html
<button id="botao">Clique em mim</button>
<script>
const btn = document.getElementById("botao");
btn.onclick = function() {
  alert("Botão clicado!");
};
</script>
```

## Usando addEventListener() (forma moderna)
```html
<button id="botao">Clique</button>

<script>
const botao = document.getElementById("botao");

botao.addEventListener("click", () => {
  console.log("Evento via addEventListener");
});
</script>
```

## Remover Eventos
```js
function ola() {
  console.log("Oi!");
}

botao.addEventListener("click", ola);
botao.removeEventListener("click", ola);
```


