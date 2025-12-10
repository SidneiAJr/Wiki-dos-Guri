# 📌 HTML - Imagens (`img`)

O elemento `img` é utilizado para **exibir imagens** em uma página HTML.  
Ele é um elemento **auto-contido** (não necessita de tag de fechamento).

---

## **1) `src` — Local da Imagem**
Define o **caminho** da imagem.  
Pode ser:
- Caminho interno no projeto
- URL externa

---

## **2) `alt` — Texto Alternativo**
Descreve a imagem quando ela **não pode ser exibida**.  
É essencial para:
- Acessibilidade
- Leitores de tela
- Motores de busca (SEO)

Regra de ouro:
> O `alt` deve descrever o que a imagem representa, e não o nome do arquivo.

---

## **3) Formatos Comuns de Imagem**

| Formato | Característica | Indicação |
|--------|----------------|-----------|
| `.jpg` ou `.jpeg` | Compacto, bom para fotos | Sites, imagens grandes |
| `.png` | Suporta transparência, mais nítido | Ícones e gráficos |
| `.gif` | Animações simples | Ilustrações animadas |
| `.svg` | Vetorial, não perde qualidade | Logos e imagens escaláveis |

---

## **4) Dimensões e Controle de Exibição**
O tamanho da imagem não deve ser controlado diretamente no HTML.  
A recomendação correta é ajustar **pelo CSS** ou via **Bootstrap** quando estilizando.

---

## **5) Quando Não Usar Imagem**
Evite usar imagem quando:
- É apenas um fundo decorativo (use background no CSS)
- Representa algo textual (use texto real para SEO)

---

## 🏁 Resumo

| Atributo | Função |
|---------|--------|
| `src` | Caminho da imagem |
| `alt` | Descrição da imagem (essencial para acessibilidade) |

