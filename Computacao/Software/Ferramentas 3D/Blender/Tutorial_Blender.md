# 🧱 Introdução ao Blender — Guia Básico para Modelagem 3D

> 💡 **Objetivo:** Entender o essencial do Blender, desde criar objetos, editar malhas e aplicar materiais até exportar modelos para Unity.

---

## 🧭 1. O que é o Blender?

O **Blender** é um software **gratuito e open-source** para:
- Modelagem 3D  
- Escultura digital  
- Texturização e materiais  
- Rigging e animação  
- Simulações físicas  
- Renderização (Eevee e Cycles)  
- E integração com **Unity**, **Unreal**, entre outros.

---

## ⚙️ 2. Instalando o Blender

- Acesse [https://www.blender.org](https://www.blender.org)
- Clique em **Download Blender**
- Instale normalmente (Windows, macOS ou Linux)

---

## 🧰 3. Interface Básica

| Área | Descrição |
|------|------------|
| **3D Viewport** | Onde você modela e visualiza objetos |
| **Outliner** | Mostra todos os objetos da cena |
| **Properties Panel** | Controla materiais, modificadores, renderização etc. |
| **Timeline** | Usada para animações |
| **Tool Shelf (T)** | Ferramentas rápidas de modelagem |

## Interface Inicial:
![Interface Inicial](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20212859.png)

### 🧭 Navegação:

| Ação | Atalho |
|------|--------|
| Girar visão | **Botão do meio (MMB)** |
| Mover câmera | **Shift + MMB** |
| Zoom | **Scroll do mouse** |
| Centralizar objeto | **Numpad .** |
| Perspectiva/Ortográfica | **Numpad 5** |

## Navegação:
![Menu](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20212909.png)

## Preferencias:
![Preferencias](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20212940.png)

## Renderizador:
![Renderizado](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20212955.png)

---

## 🧱 4. Criando e Manipulando Objetos

| Ação | Atalho |
|------|--------|
| Adicionar objeto | **Shift + A** |
| Mover | **G** |
| Rotacionar | **R** |
| Escalar | **S** |
| Duplicar | **Shift + D** |
| Excluir | **X** |
| Aplicar transformações | **Ctrl + A** → “All Transforms” |

> 💡 Dica: combine **G**, **R**, **S** com eixos — ex: `G + Z` move apenas no eixo Z.

---

## ✂️ 5. Edit Mode — Modelagem

Entre no modo de edição com **Tab**.

| Ação | Atalho |
|------|--------|
| Selecionar vértice/aresta/face | **1 / 2 / 3** |
| Extrudir (criar novas faces) | **E** |
| Inserir loop cut | **Ctrl + R** |
| Cortar faces (Knife) | **K** |
| Apagar faces | **X** |
| Mesclar vértices | **M** |
| Duplicar | **Shift + D** |
| Espelhar | **Ctrl + M** |

---

## 🧩 6. Modificadores Importantes

| Modificador | Função |
|--------------|--------|
| **Mirror** | Espelha o modelo em um eixo (simetria) |
| **Subdivision Surface** | Suaviza e adiciona polígonos |
| **Solidify** | Dá espessura a superfícies |
| **Bevel** | Arredonda bordas |
| **Array** | Duplica objetos em sequência |
| **Boolean** | Une ou corta objetos |

> 🧠 Sempre aplique modificadores com **Ctrl + A → Apply All Transforms** antes de exportar.

---

## 🎨 7. Materiais e Texturas

1. Vá em **Properties → Material (ícone de esfera)**  
2. Clique em **New**  
3. Ajuste cores e brilho no **Shader Editor**  
4. Troque para o **modo Material Preview (Z → Material Preview)** para visualizar  

### Shader básico:
- **Principled BSDF** → O shader padrão  
- **Base Color** → Cor do material  
- **Roughness** → Controle de brilho (0 = espelhado, 1 = fosco)  
- **Metallic** → Define se o material parece metal  

---

## 🌄 8. Luzes e Câmera

| Ação | Atalho |
|------|--------|
| Adicionar luz | **Shift + A → Light → Point/Sun/Area** |
| Mover câmera | **G + Z / G + Y / G + X** |
| Entrar na visão da câmera | **Numpad 0** |
| Travar câmera à visão | **N → View → Lock Camera to View** |

---

## 🧍 9. Exportando para Unity

1. Selecione o objeto (ou todos com **A**)  
2. Vá em **File → Export → FBX (.fbx)**  
3. No painel da direita:
   - **Scale = 1.0**
   - **Apply Transform**
   - **Forward = -Z Forward**
   - **Up = Y Up**
   - Marque **Selected Objects**  
4. Salve em uma pasta dentro do seu projeto Unity (`Assets/Models`)  
5. O Unity importará automaticamente!

---

## 🔄 10. Ciclo de Trabalho Blender + Unity

```mermaid
graph LR
A[Modelar no Blender] --> B[Aplicar Modificadores]
B --> C[Aplicar Materiais / Texturas]
C --> D[Exportar .FBX]
D --> E[Importar no Unity]
E --> F[Aplicar Scripts e Física]
F --> G[Testar no Jogo 🎮]
