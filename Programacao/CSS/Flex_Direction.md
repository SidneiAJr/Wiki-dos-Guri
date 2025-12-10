# 📦 CSS: Flexbox – `flex-direction`

A propriedade `flex-direction` define **a direção principal dos itens** dentro de um container com `display: flex`.  
Ela controla **como os elementos são distribuídos** — em linha, coluna ou em ordem invertida.

---

## 🎯 Função Principal
> Determina o **eixo principal (main axis)** do Flexbox: horizontal (linha) ou vertical (coluna).

---

## 💡 Valores Possíveis

| **Valor** | **Descrição** |
| ---------- | -------------- |
| `row` | Organiza os itens em **linha horizontal**, da **esquerda para a direita**. *(Padrão)* |
| `row-reverse` | Organiza os itens em linha, mas **inverte a ordem** — da **direita para a esquerda**. |
| `column` | Organiza os itens em **coluna vertical**, de **cima para baixo**. |
| `column-reverse` | Organiza os itens em coluna, mas **inverte a ordem** — de **baixo para cima**. |

---

## 🧩 Exemplo Visual

| `flex-direction` | Visualização |
| ---------------- | ------------- |
| `row` | 🟦 🟦 🟦 → *(horizontal normal)* |
| `row-reverse` | ← 🟦 🟦 🟦 *(horizontal invertido)* |
| `column` | 🟦<br>🟦<br>🟦 *(vertical normal)* |
| `column-reverse` | 🟦<br>🟦<br>🟦 *(vertical invertido)* |

---

## ⚙️ Dica Prática

Combine `flex-direction` com:
- `justify-content` → controla o **alinhamento no eixo principal**  
- `align-items` → controla o **alinhamento no eixo cruzado**

📘 Exemplo rápido:
```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
