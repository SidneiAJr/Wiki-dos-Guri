# 🔥 Renderização Avançada no Blender

Depois de dominar a modelagem e os materiais, é hora de criar **renders profissionais**.  
O Blender oferece dois principais motores: **Eevee** (tempo real) e **Cycles** (realista).

---

## ⚙️ 1. Escolhendo o Motor de Renderização

- Vá até **Render Properties → Render Engine**.  
- Selecione **Cycles** para renderização realista com **ray tracing**.  
- Use **Eevee** para pré-visualizações rápidas e cenas em tempo real.

💡 **Dica:** No Cycles, escolha **GPU Compute** (em *Preferences → System*) para acelerar o render.

---

## 💡 2. Configurações Principais (Cycles)

| Opção | Função |
|-------|---------|
| **Samples** | Quantidade de amostras (qualidade da imagem) |
| **Denoise** | Remove ruídos do render final |
| **Light Paths** | Controla quantos reflexos/refrações são calculados |
| **Clamp Direct/Indirect** | Reduz ruído de luzes intensas |
| **Film → Transparent** | Remove fundo (para compor em outro software) |

🔧 **Recomendado:**  
- Viewport Samples: 128  
- Render Samples: 512–1024  
- Ative **Adaptive Sampling** para otimizar o tempo.

---

## 🌞 3. Iluminação Avançada

- Use **Environment Texture (HDRI)** para luz global realista.  
- Combine com luzes **Area** e **Point** para controle de sombras.  
- Ative **Contact Shadows** no Eevee para maior profundidade.  
- Ajuste o **Color Management → Look = Medium High Contrast** para mais impacto visual.

---

## 🎬 4. Render Passes e Compositor

1. Vá em **View Layer Properties → Passes** e ative *Diffuse, Glossy, AO, Z, Mist*, etc.  
2. No **Compositor**, ative **Use Nodes**.  
3. Conecte os passes ao **Composite** e **Viewer** para pós-produção.  

💡 Assim você pode controlar brilho, contraste, foco e efeitos diretamente no Blender.

---

## 🖼️ 5. Exportando o Render

1. Vá em **Output Properties → Output → File Format**.  
2. Escolha **PNG** (com transparência) ou **JPEG** (leve).  
3. Clique em **Render → Render Image (F12)**.  
4. Salve com **Image → Save As**.

---

## 🧠 Conclusão

A renderização avançada transforma sua cena em uma **imagem cinematográfica**.  
Ajuste luzes, materiais e amostras até encontrar o equilíbrio entre **qualidade e desempenho**.

🚨 **Lembre-se:** sempre salve antes de renderizar cenas pesadas!

---
