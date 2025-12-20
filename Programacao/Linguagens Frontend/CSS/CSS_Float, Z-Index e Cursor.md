# 🌊 CSS – `float`, `z-index` e `cursor`

Essas propriedades controlam **posicionamento, empilhamento** e **interação visual** dos elementos na página.  
São recursos simples, mas muito úteis em layouts e interfaces interativas.

---

## 🧭 `float`

A propriedade `float` move um elemento para o **lado esquerdo ou direito** dentro do seu container,  
permitindo que o texto ou outros elementos **“flutuem” ao redor** dele.

| 💡 **Propriedade** | 📝 **Descrição** | 💻 **Exemplo** |
| ------------------ | ---------------- | -------------- |
| `float` | Alinha o elemento à **esquerda** ou **direita** | `float: left;` / `float: right;` |

📘 **Dica:**  
O `float` era muito usado para montar layouts antes do **Flexbox** e do **Grid**.  
Hoje, ele é mais usado para **imagens e pequenos alinhamentos laterais**.

> ⚠️ Quando usar `float`, é comum precisar limpar o fluxo depois com `clear: both;`  
> Isso evita que outros elementos “invadam” o espaço flutuante.

---

## 🧱 `z-index`

Define a **ordem de empilhamento** dos elementos na tela — quem fica **por cima** de quem.

| 💡 **Propriedade** | 📝 **Descrição** | 💻 **Exemplo** |
| ------------------ | ---------------- | -------------- |
| `z-index` | Determina a **posição em camadas (eixo Z)**; elementos com valor maior aparecem **acima** dos menores. | `z-index: 10;` |

📘 **Importante:**  
O `z-index` **só funciona** em elementos com `position` diferente de `static` (`relative`, `absolute`, `fixed` ou `sticky`).

💡 **Exemplo prático:**  
Um modal ou menu suspenso usa `z-index` alto pra ficar acima do conteúdo principal.

---

## 🖱️ `cursor`

Controla **o tipo de ponteiro do mouse** ao passar sobre o elemento — ótimo para botões, links e áreas interativas.

| 💡 **Propriedade** | 📝 **Descrição** | 💻 **Exemplo** |
| ------------------ | ---------------- | -------------- |
| `cursor` | Define o estilo do cursor do mouse: `pointer`, `text`, `move`, `wait`, `not-allowed`, etc. | `cursor: pointer;` |

📘 **Dicas comuns:**
- `cursor: pointer;` → Indica algo clicável (botões, links).  
- `cursor: text;` → Indica campo de texto editável.  
- `cursor: move;` → Indica item arrastável.  
- `cursor: not-allowed;` → Indica ação bloqueada.

---

## ✅ Resumo Rápido

| Propriedade | Função Principal | Uso Comum |
|--------------|------------------|------------|
| **float** | Move o elemento lateralmente dentro do container | Imagens e textos alinhados |
| **z-index** | Define qual elemento fica por cima | Modais, menus, pop-ups |
| **cursor** | Controla o tipo de ponteiro do mouse | Botões e interações |

---

💬 **Conclusão:**  
Essas três propriedades são fundamentais pra dar **profundidade, organização e interação visual** ao layout.  
Mesmo com Flexbox e Grid, `float`, `z-index` e `cursor` continuam sendo **parte essencial do arsenal CSS**.
