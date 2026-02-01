# 🌅 Modo de Textura e Renderização no Blender

Nesta etapa, você aprenderá a configurar o **renderizador**, aplicar **texturas** e ajustar **iluminação** para criar uma cena mais realista no Blender.

---

## ⚙️ 1. Escolhendo o Motor de Renderização

1. Vá até a **aba de Renderização** (ícone de câmera no painel lateral direito).  
2. Em **Render Engine**, selecione **Cycles**.  
   - O **Cycles** é um motor de render mais **realista e completo**, ideal para iluminação, reflexos e sombras mais precisas.  
   - Se quiser uma pré-visualização rápida, use o **Eevee**, mas para render final prefira **Cycles**.

---

## 💡 2. Ajustando a Qualidade de Render

1. Em **Sampling → Render**, defina o número de **amostras (Samples)**.  
   - Para bons resultados sem demorar muito, use entre **128 e 1024** amostras.  
   - Menos amostras = render mais rápido, mas com mais ruído.  
   - Mais amostras = imagem mais limpa, porém mais lenta.

💡 **Dica:** Ative a opção **Denoise** para remover ruídos automaticamente e melhorar a qualidade final.

---

## 🌞 3. Configurando a Iluminação Global

1. Vá para o **World Properties** (ícone de globo).  
2. Em **Surface → Color**, clique no botão à direita e escolha **Environment Texture**.  
3. Selecione uma **imagem HDRI** (formato `.hdr` ou `.exr`) — ela simula iluminação natural e realista.  
4. Ajuste a **força (Strength)** conforme necessário para equilibrar a luz da cena.

💡 **Dica:** Use HDRIs de paisagem para criar ambientes externos realistas (como céu, sol e horizonte).

---

## 🧱 4. Aplicando Texturas aos Objetos

1. Selecione o objeto.  
2. Vá até **Material Properties → New**.  
3. No **Shader Editor**, conecte uma textura à entrada **Base Color** do **Principled BSDF**.  
4. Ajuste propriedades como:
   - **Roughness** → brilho da superfície  
   - **Metallic** → aparência metálica  
   - **Normal Map** → relevo e detalhes da textura  

---

## 🖼️ 5. Renderizando a Imagem

1. Configure a resolução em **Output Properties → Dimensions**.  
2. Escolha o formato de saída em **Output → File Format** (por exemplo: **JPEG**, **PNG** ou **EXR**).  
3. Clique em **Render → Render Image (F12)**.
***⚠️Observacao a Renderizar o processador e memoria****
5. Após o render terminar, vá em **Image → Save As** e salve sua imagem.

💾 **Dica:** Use formato **PNG** se quiser preservar transparência ou mais qualidade.

---

## ✅ Resultado

Agora você terá uma **imagem renderizada com texturas, iluminação realista e materiais configurados corretamente** — pronta para uso em portfólios, projetos ou integração com Unity/Unreal.

---

