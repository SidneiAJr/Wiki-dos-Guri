# 🎨 Efeitos de Hover em CSS

Os **efeitos de hover** são **animações ou mudanças visuais** aplicadas a elementos quando o usuário passa o cursor sobre eles.  
Eles são essenciais para:

- **Interatividade:** indicam que um elemento é clicável ou importante.  
- **Feedback visual:** melhora a experiência do usuário.  
- **Estética:** torna interfaces mais dinâmicas e modernas.  

---

## 🧩 Efeitos Comuns de Hover

### 1. Alteração de Cor
Mudar a **cor de fundo** ou do **texto** quando o cursor passa sobre o elemento.  

📘 **Uso comum:**  
- Botões  
- Links  
- Títulos ou cards interativos  

💡 **Boas práticas:**  
- Use cores consistentes com a identidade visual.  
- Mantenha contraste suficiente para acessibilidade.  
- Combine com **transições suaves** para melhor percepção.

```css
/* Exemplo de botão com hover */
.btn {
  background-color: #ff9933;
  color: #fff;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.btn:hover {
  background-color: #ff6600;
  color: #ffffff;
}
```

## 2. Transformações (Scale, Rotate)

Alterar tamanho, rotação ou posição do elemento ao passar o mouse.

📘 Uso comum:

Ícones interativos

Cards de produtos

Imagens de galeria

💡 Boas práticas:

Evite mudanças exageradas de escala.

Combine com transition para suavizar o efeito.

```
.card:hover {
  transform: scale(1.05); /* aumenta 5% */
  transition: transform 0.3s ease;
}
```
