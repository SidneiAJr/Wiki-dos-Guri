# 📐 Diferença de `display` no CSS

O atributo `display` define **como um elemento HTML é exibido na página** — se ele ocupa uma linha inteira, se pode ficar lado a lado com outros, ou se seu conteúdo se ajusta automaticamente.

---

## 🧩 Tipos de Display

### **display: flex**
Torna o layout **flexível**, permitindo alinhar e distribuir elementos facilmente.  
Usado para criar **layouts modernos e responsivos**, com controle sobre direção, alinhamento e espaçamento.

---

### **display: block**
O elemento ocupa **toda a largura disponível** da linha.  
Cada novo elemento “block” começa **abaixo do anterior**.  
Exemplo comum: `<div>`, `<section>`, `<p>`.

---

### **display: inline-block**
Combina características de **block** e **inline**:  
- Mantém **altura e largura personalizadas**  
- Mas continua **na mesma linha** que outros elementos, se houver espaço.  
Muito usado em **botões e caixas pequenas** lado a lado.

---

### **display: inline**
O elemento fica **na mesma linha** dos outros, sem quebrar a estrutura.  
👉 Não aceita `height` nem `width`.  
Usado em textos e ícones — exemplos: `<span>`, `<a>`, `<strong>`.

---

## ⚙️ Tabela Comparativa

| Tipo de Display | Ocupa Linha Inteira | Aceita Height/Width | Pode Ficar Lado a Lado | Uso Comum |
|-----------------|---------------------|----------------------|-------------------------|------------|
| **block** | ✅ Sim | ✅ Sim | ❌ Não | Estruturas e containers |
| **inline** | ❌ Não | ❌ Não | ✅ Sim | Textos e ícones |
| **inline-block** | ❌ Não | ✅ Sim | ✅ Sim | Botões e cards pequenos |
| **flex** | ✅ Sim | ✅ Sim | ✅ Sim (via container) | Layouts modernos e responsivos |

---

💡 **Dica:**  
Combine `display: flex` com propriedades como `justify-content`, `align-items` e `flex-direction` para criar alinhamentos perfeitos sem precisar usar `float` ou `position`.
