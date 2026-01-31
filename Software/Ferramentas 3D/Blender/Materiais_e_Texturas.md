# 🎨 Materiais e Texturas no Blender

Os **materiais** e **texturas** definem a aparência dos objetos: cores, brilho, reflexos e detalhes da superfície.  
Nesta seção, você vai aprender a criar e ajustar materiais realistas usando o **Shader Editor**.

---

## 🧱 1. Criando um Material

1. Selecione o objeto.  
2. Vá em **Properties → Material (ícone de esfera)**.  
3. Clique em **New**.  
4. O Blender cria automaticamente um **Principled BSDF**, o shader padrão.

---

## 🧩 2. Principais Propriedades do Principled BSDF

| Propriedade | Descrição |
|--------------|------------|
| **Base Color** | Cor principal do material |
| **Roughness** | Controle do brilho (0 = espelhado, 1 = fosco) |
| **Metallic** | Define se o material é metálico |
| **Specular** | Define a intensidade do reflexo |
| **Normal Map** | Adiciona relevo à superfície |
| **Emission** | Faz o objeto emitir luz |

💡 **Dica:** Use o atalho `Z → Material Preview` para visualizar o resultado em tempo real.

---

## 🧵 3. Aplicando Texturas

1. No **Shader Editor**, pressione `Shift + A → Texture → Image Texture`.  
2. Conecte a saída **Color** da textura na entrada **Base Color** do shader.  
3. Clique em **Open** e escolha sua imagem (JPEG, PNG, etc).  
4. Para ajustar a projeção da textura, vá em **UV Editing** e mapeie a malha.

---

## 🧶 4. Tipos de Textura

| Tipo | Descrição |
|------|------------|
| **Color Map (Albedo)** | Cor do material |
| **Roughness Map** | Define o brilho em áreas diferentes |
| **Normal Map** | Simula relevo sem adicionar polígonos |
| **Bump Map** | Relevo em escala de cinza |
| **Displacement Map** | Altera fisicamente a geometria |
| **Ambient Occlusion (AO)** | Sombra leve em áreas de contato |

---

## 🌄 5. Dicas de Realismo

- Combine texturas **PBR** (Physically Based Rendering).  
- Use **HDRIs** para iluminação realista.  
- Aplique **Denoise** para reduzir granulação.  
- Organize os nós no **Shader Editor** com `Frame` (`Ctrl + J`).

---

## 🎨 6. Exemplo de Setup PBR

