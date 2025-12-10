# 🔄 Pipeline MakeHuman + Blender

## 🎯 Objetivo
Aprender o **fluxo completo de criação, exportação e importação** de personagens entre **MakeHuman** e **Blender**, mantendo **texturas, rig e animações**.

---

## 🧍 Etapa 1 — Criar o Personagem no MakeHuman

1. Abra o **MakeHuman**.  
2. Ajuste:
   - Gênero, idade, altura e peso em **Modeling → Main**.  
   - Traços faciais em **Modeling → Face**.  
   - Roupas e cabelo em **Geometries**.  
3. Vá em **Pose/Animate → Skeleton** e selecione:
   - `Game Engine` (para jogos)
   - `Default` (para animações detalhadas)
   - `Blender Rig (MHX2)` (para animação no Blender)
4. Clique em **Apply**.

💡 *Dica:* salve o projeto com `File → Save` antes de exportar.

---

## 📤 Etapa 2 — Exportar para Blender

1. Vá em **File → Export**.  
2. Escolha o formato **MHX2 (.mhx2)** ou **FBX (.fbx)**.  
3. Configure:
   - **Scale:** 1.00  
   - **Triangulate mesh:** ✔️ (evita erros de deformação)  
   - **Include skeleton:** ✔️  
4. Clique em **Export** e salve o arquivo na pasta desejada.

📁 Exemplo:


---

## 🧩 Etapa 3 — Instalar o Plugin no Blender

### 🔹 Instalar o *MakeHuman Importer (MHX2)*

1. Baixe o plugin em:  
   🔗 [https://www.makehumancommunity.org/content/mhx2_plugin.html](https://www.makehumancommunity.org/content/mhx2_plugin.html)
2. No Blender:
   - Vá em **Edit → Preferences → Add-ons**.  
   - Clique em **Install…**  
   - Selecione o arquivo `.zip` do MHX2.  
   - Ative o plugin: **MakeHuman: Importer for MHX2** ✔️

---

## 📥 Etapa 4 — Importar no Blender

1. Vá em **File → Import → MakeHuman (.mhx2)**.  
2. Selecione o arquivo exportado (`personagem.mhx2`).  
3. O modelo será importado com:
   - **Texturas de pele, olhos e cabelo**  
   - **Esqueleto (rig)**  
   - **Roupas e acessórios**

💡 *Dica:* se o personagem vier muito grande, use `S` para escalar no Blender.

---

## 🎨 Etapa 5 — Ajustar no Blender

- Use **Material Preview (Z → Material)** para visualizar texturas.  
- Se necessário, aplique **Shade Smooth**.  
- Ajuste **Rigs e Weights** no modo **Pose** e **Weight Paint**.

---

## 🏃 Etapa 6 — Animação

1. Se o rig for MHX2, você pode:
   - Adicionar **Keyframes** normalmente.  
   - Importar arquivos `.bvh` (captura de movimento).  
2. Também é possível usar **Auto-Rig Pro** ou **Rigify** para controle avançado.

---

## ⚙️ Etapa 7 — Exportar de Volta (para Jogos ou Render)

Para usar em **Unity**, **Unreal** ou outros motores:

1. Selecione o personagem no Blender.  
2. Vá em **File → Export → FBX (.fbx)**.  
3. Configure:
   - **Apply Transform:** ✔️  
   - **Mesh + Armature:** ✔️  
   - **Bake Animation:** opcional  
4. Exporte para o diretório do seu projeto.

---



