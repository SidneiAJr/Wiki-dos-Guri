# 📦 CSS Flexbox – Gap & Order

No **Flexbox**, as propriedades `gap` e `order` controlam o **espaçamento** e a **ordem dos itens** dentro do container, sem precisar alterar o HTML diretamente.  
Essas propriedades são muito úteis para manter o código mais limpo e organizado.

---

## 🧩 `gap`

Define o **espaço entre os itens** dentro de um container flexível (ou grid).  
Substitui o uso de `margin` individual em cada item, simplificando o layout.

| 💡 **Propriedade** | 📝 **Descrição** | 💻 **Exemplo de Uso** |
| ------------------ | ---------------- | --------------------- |
| `gap` | Define o **espaço horizontal e vertical** entre os elementos. | `gap: 20px;` |
| `row-gap` | Espaço **vertical** entre linhas (quando há várias linhas). | `row-gap: 10px;` |
| `column-gap` | Espaço **horizontal** entre colunas. | `column-gap: 15px;` |

📘 **Dica:**  
`gap` funciona tanto em **Flexbox** quanto em **CSS Grid**, e é mais limpo que usar `margin` em cada item.

---

## 🔢 `order`

A propriedade `order` controla a **posição visual dos elementos** dentro do container flex.  
O item com o **menor valor de order** aparece primeiro.

| 💡 **Propriedade** | 📝 **Descrição** | 💻 **Exemplo de Uso** |
| ------------------ | ---------------- | --------------------- |
| `order` | Define a **posição do item**. O padrão é `0`. | `order: 2;` |

📌 **Exemplo:**  
Se um item tiver `order: -1`, ele será exibido **antes** dos outros, mesmo que apareça depois no HTML.

---

## 🧠 Resumo Rápido

| Propriedade | Função | Exemplo |
| ------------ | ------- | -------- |
| `gap` | Define o **espaçamento** entre itens | `gap: 20px;` |
| `row-gap` | Espaçamento **vertical** | `row-gap: 10px;` |
| `column-gap` | Espaçamento **horizontal** | `column-gap: 15px;` |
| `order` | Define a **ordem de exibição** | `order: -1;` |

---

💬 **Conclusão:**  
Essas propriedades tornam o layout **mais previsível e flexível**.  
Usar `gap` e `order` corretamente evita o uso excessivo de `margin` e facilita o controle visual dos elementos sem alterar o HTML.
