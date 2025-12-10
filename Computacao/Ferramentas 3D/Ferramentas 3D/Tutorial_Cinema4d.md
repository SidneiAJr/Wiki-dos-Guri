# 🎥 Introdução ao Cinema 4D

## 🎯 Objetivo
Aprender o básico do **Cinema 4D**, uma das ferramentas 3D mais usadas no cinema, motion design e publicidade,  
focando em **modelagem, texturização, iluminação e renderização**.

---

## 🧩 O que é o Cinema 4D?

O **Cinema 4D** é um software de modelagem, animação e renderização 3D desenvolvido pela **Maxon**.  
É conhecido pela sua **interface intuitiva**, **rapidez** e **integração com After Effects**.

---

## ⚙️ Etapa 1 — Interface e Navegação

| Função | Atalho | Descrição |
|---------|---------|-----------|
| Girar a visão | `Alt + Clique Esquerdo` | Rotaciona a câmera |
| Mover a visão | `Alt + Clique do Meio` | Move a câmera |
| Zoom | `Alt + Clique Direito` | Aproxima/Afasta |
| Resetar visão | `F1–F5` | Alterna entre vistas (Perspectiva, Top, Front, Right) |

💡 *Dica:* Use `Ctrl + Z` e `Ctrl + Y` para desfazer/refazer ações.

---

## 🧱 Etapa 2 — Modelagem Básica

1. Crie um **objeto primitivo**:  
   🧊 *Menu Object → Cube / Sphere / Cylinder / Plane*  
2. Clique no botão **Make Editable (C)** para transformar o objeto em polígonos editáveis.  
3. Use as ferramentas:
   - `Move (E)`
   - `Scale (T)`
   - `Rotate (R)`
   - `Knife (K)` — corta polígonos  
   - `Extrude (D)` — extruda faces  

💡 Combine primitivos e modificadores (deformers) como *Bend*, *Twist*, *FFD*.

---

## 🎨 Etapa 3 — Materiais e Texturas

1. Crie um novo material com **Create → New Material**.  
2. Ajuste:
   - **Color** — cor base ou textura  
   - **Reflectance** — brilho e reflexo  
   - **Bump / Normal** — detalhes de relevo  
   - **Alpha** — transparência  
3. Arraste o material para o objeto na viewport.

---

## 💡 Etapa 4 — Luzes e Iluminação

- **Light → Area Light** — iluminação realista e difusa  
- **Light → Infinite Light** — luz solar paralela  
- **Light → Spot Light** — foco de cena  

Use **Shadows: Area** para sombras suaves e realistas.  
💡 *Dica:* Posicione 3 luzes (key, fill, back) para o clássico setup de estúdio 3-pontos.

---

## 📷 Etapa 5 — Câmera e Enquadramento

1. Adicione uma **Câmera (Objects → Camera)**.  
2. Ative o ícone da câmera para “entrar nela”.  
3. Ajuste:
   - **Focal Length (mm)** — controla o zoom/ângulo  
   - **Depth of Field** — profundidade de campo  
   - **Target Tag** — para travar o foco em um objeto  

---

## 🎞️ Etapa 6 — Animação

1. Selecione um objeto.  
2. Clique no **botão vermelho de gravação** 🔴 no timeline para criar *keyframes*.  
3. Altere a posição/rotação/escala e insira novos keyframes ao longo do tempo.  
4. Pressione **Play (F8)** para visualizar.

💡 *Motion Tags* e *Effectors* (em MoGraph) permitem animações de alto nível sem scripts.

---

## 🧠 Etapa 7 — Renderização

1. Vá em **Render Settings (Ctrl + B)**.  
2. Escolha:
   - **Renderer:** Physical ou Redshift (se instalado)  
   - **Output:** 1920×1080 px ou 4K  
   - **Format:** PNG / JPEG / AVI / MP4  
3. Clique em **Render to Picture Viewer (Shift + R)**.

💡 Use **Ambient Occlusion** e **Global Illumination** para resultados mais realistas.

---

## 🔗 Integrações

| Software | Uso |
|-----------|-----|
| **Adobe After Effects** | Motion Graphics (importa C4D diretamente) |
| **Unreal Engine / Unity** | Exportação via *FBX* para jogos |
| **ZBrush** | Esculpir e retopologar modelos orgânicos |
| **Blender** | Intercâmbio via *OBJ/FBX* |

---

## 📁 Estrutura Recomendada de Projeto

