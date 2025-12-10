# 🎨 CSS: Cor e Fundo

As propriedades de cor e fundo permitem personalizar o visual dos elementos, controlando tanto a cor do texto quanto o fundo (sólido, com imagem ou transparente).

# 🖋️ Cor do Texto (color)

Define a cor do texto de um elemento.

```CSS
color: #333;
```

# 🎨 Você pode usar nomes de cores, valores hexadecimais, RGB, HSL ou variáveis CSS:

```CSS
color: red;

color: #ff5733;

color: rgb(255, 87, 51);

color: hsl(10, 100%, 60%);
```

# 🟦 Cor de Fundo (background-color)

Define a cor de fundo do elemento.

```CSS
background-color: lightblue;
```
💡 Dica: use rgba() para aplicar transparência no fundo:
```CSS
background-color: rgba(0, 0, 255, 0.3);
```
# 🖼️ Imagem de Fundo (background-image)

Adiciona uma imagem de fundo ao elemento.
```CSS
background-image: url('fundo.jpg');
```
# 🧠 Use com background-size, background-position e background-repeat para ajustar o comportamento da imagem.

# 📏 Tamanho da Imagem (background-size)

Define o tamanho da imagem de fundo.
```CSS
background-size: cover;
```

cover → cobre todo o elemento, cortando partes da imagem se necessário.

contain → redimensiona para caber completamente dentro do elemento.

Também aceita valores fixos (100px 200px) ou percentuais (50% 100%).

# 🎯 Posição da Imagem (background-position)

Controla a posição inicial da imagem de fundo.

background-position: center top;


# 📌 Outros exemplos:

```CSS
left top

right bottom

center center

50% 50%
```
# 🔁 Repetição da Imagem (background-repeat)

Define se a imagem de fundo deve se repetir.

background-repeat: no-repeat;


# 🔄 Valores comuns:

```CSS
repeat (padrão)

no-repeat

repeat-x

repeat-y
```
# 🌫️ Transparência (opacity)

Controla a transparência total do elemento, de 0 (invisível) a 1 (opaco).
```CSS
opacity: 0.8;
```
# ⚠️ Cuidado: o opacity afeta todo o conteúdo interno.
Para deixar só o fundo translúcido, use rgba() no background-color.

| 💡 **Propriedade**        | 📝 **Descrição**                                                                 | 💻 **Exemplo de Uso**                 |
| ------------------------- | -------------------------------------------------------------------------------- | ------------------------------------- |
| **`color`**               | Define a **cor do texto**.                                                       | `color: #333;`                        |
| **`background-color`**    | Define a **cor de fundo** do elemento.                                           | `background-color: lightblue;`        |
| **`background-image`**    | Define uma **imagem de fundo**.                                                  | `background-image: url('fundo.jpg');` |
| **`background-size`**     | Define o **tamanho** da imagem de fundo (`cover`, `contain`, ou valores em px/%) | `background-size: cover;`             |
| **`background-position`** | Define a **posição** da imagem de fundo.                                         | `background-position: center top;`    |
| **`background-repeat`**   | Define se a imagem de fundo **se repete** (`repeat`, `no-repeat`, etc.).         | `background-repeat: no-repeat;`       |
| **`opacity`**             | Controla a **transparência** do elemento (de `0` a `1`).                         | `opacity: 0.8;`                       |
