# 🌀 Overflow no CSS

A propriedade `overflow` controla **como o conteúdo que ultrapassa o tamanho de um elemento** é exibido (ou escondido).  
Ela é frequentemente usada em layouts fixos, caixas com texto, ou quando precisamos de rolagem em um container.

---

## 🔹 Propriedade: `overflow`

```css
overflow: visible | hidden | scroll | auto;
```

| **Valor** | **Descrição**                                                                              | **Exemplo Visual**                |
| --------- | ------------------------------------------------------------------------------------------ | --------------------------------- |
| `visible` | O conteúdo **ultrapassa** o limite do elemento e é visível. Não faz nada, é o **padrão**.  | 🟦 🟦 🟦 (conteúdo transbordando) |
| `hidden`  | O conteúdo que ultrapassar o tamanho do container **será ocultado**. Não é possível rolar. | 🟦⬛ (conteúdo cortado)            |
| `scroll`  | Sempre exibe as **barras de rolagem** (independente de o conteúdo ultrapassar ou não).     | 🟦⬜⬛ (sempre rolagem)             |
| `auto`    | Exibe as **barras de rolagem** apenas quando o conteúdo ultrapassa o limite do container.  | 🟦⬜⬛ (só quando necessário)       |
