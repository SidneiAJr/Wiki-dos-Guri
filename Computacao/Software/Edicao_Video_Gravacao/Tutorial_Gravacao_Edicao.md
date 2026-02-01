# 🎥 Tutorial OBS Studio

O **OBS Studio (Open Broadcaster Software)** é um programa gratuito e de código aberto para **gravação e transmissão ao vivo**.  
Muito usado por criadores de conteúdo, streamers e professores — leve, poderoso e 100% personalizável.

---

## 🧭 Instalação

### 🔗 Download oficial:
[https://obsproject.com/pt-br](https://obsproject.com/pt-br)

> ⚠️ Nunca baixe OBS de outros sites — há versões falsas com malware.

### 💻 Requisitos básicos:
- Windows, macOS ou Linux  
- Placa de vídeo com suporte a DirectX 10 (ou superior)  
- Drivers atualizados (NVIDIA, AMD, Intel)

---

## 🧩 Primeiros passos

### 🆕 1. Criando uma **Cena**
As **cenas** são conjuntos de fontes (câmeras, imagens, telas, etc.).  
Cada cena pode ser um layout diferente.

1. Na parte inferior, clique em **“+” (Adicionar)** em *Cenas*.  
2. Dê um nome (ex: “Gameplay”, “Tutorial”, “Câmera”).  
3. Clique em **OK**.

---

### 🎛️ 2. Adicionando **Fontes**
Com a cena criada, adiciona os elementos visuais:

| Tipo de fonte | Uso comum |
|----------------|------------|
| **Captura de tela** | Gravar o monitor inteiro. |
| **Captura de janela** | Mostrar apenas um programa. |
| **Dispositivo de vídeo** | Webcam. |
| **Imagem / Texto** | Overlay, logo, título. |
| **Captura de jogo** | Games em tela cheia. |
| **Navegador** | Inserir widgets, alertas, chat. |

> 📌 As fontes ficam em camadas — arrasta pra cima ou pra baixo pra mudar a ordem (como no Photoshop).

---

### 🎤 3. Configurando **Áudio**

No painel *Mixer de Áudio*:
- 🎙️ **Mic/Aux** → microfone principal.  
- 🔈 **Áudio do Desktop** → som do PC (músicas, jogos).  

Clica no ⚙️ → *Propriedades* pra escolher os dispositivos certos.  
Use o **ícone de engrenagem → Filtro → Limite / Compressor** pra limpar o som.

---

## ⚙️ Configurações essenciais

### 🧾 **Geral**
- Tema → *Dark* (mais confortável)
- Idioma → Português (Brasil)

### 📹 **Vídeo**
| Configuração | Recomendada |
|---------------|--------------|
| Base (Canvas) | 1920x1080 |
| Saída (Scaled) | 1920x1080 ou 1280x720 |
| FPS | 30 ou 60 (dependendo do desempenho) |

### 💾 **Saída (Gravação)**
- **Tipo:** Padrão  
- **Caminho de gravação:** Escolha uma pasta  
- **Formato:** `mp4` ou `mkv`  
- **Encoder:**  
  - `x264` (CPU)  
  - `NVENC` (NVIDIA) ou `AMD` (GPU) — melhor desempenho  

> 💡 Se o vídeo travar, abaixa o bitrate ou muda o encoder.

### 🌐 **Transmissão (Live)**
- Serviço: YouTube / Twitch / Kick / etc  
- Cole tua **Stream Key** (pega na tua conta da plataforma)  
- Clica em **“Iniciar Transmissão”** pra começar

---

## 🎞️ Gravar a tela (modo offline)

1. Crie uma cena com:
   - **Captura de tela**
   - **Áudio do desktop**
   - **Microfone**
2. Clique em **“Iniciar Gravação”**
3. Quando terminar, **“Parar Gravação”**
4. O arquivo vai pra pasta configurada em *Saída → Caminho de gravação*

---

## 🎨 Layouts e personalização

- Adiciona **imagens PNG** pra overlay (bordas, webcam, logos).  
- Usa **transições** entre cenas: `Configurações → Transição de cena`.  
- Organiza as fontes em **grupos** pra facilitar.  
- Dá pra usar **atalhos de teclado**:
  - `Ctrl + Shift + S` → iniciar gravação  
  - `Ctrl + Shift + D` → parar gravação  
  - `Ctrl + Shift + M` → mutar microfone  

---

## 🚀 Dicas de desempenho

- Fecha apps que usam a GPU (navegadores, jogos abertos).  
- Usa **“Modo de Jogo”** no Windows pra otimizar.  
- Grava em `.mkv` (menos risco de corromper se travar).  
- Atualiza sempre o OBS e os drivers da placa de vídeo.

---

## 🔗 Links úteis

- [Site Oficial do OBS](https://obsproject.com/pt-br)  
- [Guia de Áudio no OBS](https://obsproject.com/wiki/Audio)  
- [Plugins Oficiais do OBS](https://obsproject.com/forum/resources/)  
- [OBS Studio GitHub](https://github.com/obsproject/obs-studio)
---
