## 📐 CSS Flexbox – Justify Content & Align Items

Essas duas propriedades controlam o **alinhamento interno** dos itens em um container Flexbox:  
- `justify-content` → controla o **alinhamento horizontal** (eixo principal).  
- `align-items` → controla o **alinhamento vertical** (eixo cruzado).  

> 💡 Lembre-se: o eixo principal muda conforme o `flex-direction`.  
> - Se `flex-direction: row` → eixo principal é **horizontal**.  
> - Se `flex-direction: column` → eixo principal é **vertical**.

---

## ⚖️ `justify-content`

Controla **como os itens são distribuídos ao longo do eixo principal**.  

| 💡 **Valor** | 📝 **Descrição** |
| ------------- | ---------------- |
| `flex-start` | Itens alinhados **no início** do container. *(padrão)* |
| `flex-end` | Itens alinhados **no final** do container. |
| `center` | Itens **centralizados** na linha. |
| `space-between` | Itens distribuídos com **espaço igual entre eles**, **sem espaço nas bordas**. |
| `space-around` | Itens distribuídos com **espaço igual ao redor**, com **metade do espaço nas extremidades**. |
| `space-evenly` | Itens com **espaços totalmente iguais**, inclusive nas bordas. |

📘 **Dica:**  
`space-between` é ótimo pra distribuir elementos como botões ou colunas sem usar margens manuais.

---

## 🧭 `align-items`

Controla **como os itens se alinham no eixo cruzado**, perpendicular ao principal.  

| 💡 **Valor** | 📝 **Descrição** |
| ------------- | ---------------- |
| `flex-start` | Alinha os itens **no início** do eixo cruzado. |
| `flex-end` | Alinha os itens **no final** do eixo cruzado. |
| `center` | Centraliza os itens verticalmente. |
| `baseline` | Alinha os itens pela **linha de base** do texto. |
| `stretch` | Faz os itens **preencherem todo o espaço disponível** (padrão). |

📘 **Dica:**  
`align-items: center` é a forma mais simples de centralizar conteúdo verticalmente dentro de um container.

---

## 🧠 Resumo Rápido

| Propriedade | Controla | Eixo | Exemplo |
| ------------ | -------- | ---- | -------- |
| `justify-content` | Alinhamento **horizontal** | Principal | `justify-content: space-between;` |
| `align-items` | Alinhamento **vertical** | Cruzado | `align-items: center;` |

---

💬 **Conclusão:**  
Essas duas propriedades são a **base do alinhamento no Flexbox**.  
Dominar `justify-content` e `align-items` é essencial pra criar layouts **responsivos, simétricos e bem distribuídos** sem precisar usar `margin` manualmente.
