# 🎨 Tutorial de CSS — Estilo Moderno com Glass Effect e Gradient
### 🔧 Resetando o estilo global (para todos os navegadores)

### Antes de começar a estilizar, é importante “resetar” as propriedades padrão dos navegadores, garantindo que todos comecem do mesmo ponto.

## Resetando Globalmente para todos os navegadores
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    outline: none;
    text-decoration: none;
}
```

## Colocando Linear gradiente no corpo do html:

```css
body {
    background: linear-gradient(to left, #6a11cb, #2575fc);
}
```

## 🧱 Estilizando as divs .a e .b
Diferença entre classe e ID

No CSS, usamos ponto (.) para selecionar uma classe.
Exemplo: .a { ... }

E usamos cerquilha (#) para selecionar um ID.
Exemplo: #meuId { ... }

```css
.a {
    padding: 100px;
}

.b {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    justify-content: center;
    /* From https://css.glass */
    background: rgba(255, 255, 255, 0.1);
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    border: 1px solid rgba(255, 255, 255, 0.3);
}
```

## Estilizando o botão e colocando efeito:

```css
.btn {
    width: 100px;
    height: 50px;
    background-color: white;
    border: none;
    border-radius: 10px;
    font-size: 18px;
    font-weight: bolder;
}
.btn:hover{
    font-weight: bolder;
    font-size: 19px;
    cursor: pointer;
}
```

## Estilizando Texto H1 e P:

```css
h1,p{
    color: white;
    font-family:Arial, Helvetica, sans-serif;
}
```

