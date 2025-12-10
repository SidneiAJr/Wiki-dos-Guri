# ⚠️ Problemas Comuns em PCs e Possíveis Soluções

Este guia lista alguns dos problemas mais frequentes encontrados em computadores, suas causas prováveis e possíveis soluções.

---

## 💡 1. PC não liga

### Possíveis causas:
- Fonte de alimentação desligada ou com chave de tensão incorreta (110V/220V).
- Cabo de energia desconectado ou danificado.
- Botão de energia com mau contato.
- Fonte queimada por uso incorreto da tensão.

### Solução:
- Verifique se o cabo de energia está firmemente conectado.
- Confira se a chave da fonte está na posição correta:
  - **110V (127V)** → para redes elétricas de baixa tensão.
  - **220V** → para redes de alta tensão.
- Se a fonte foi ligada em 220V estando ajustada para 110V → **pode queimar imediatamente**.
- Teste a fonte com outro cabo ou use um testador.

---


## 💻 2. Tela Azul (BSOD - Blue Screen of Death)

### Possíveis causas:
- Falhas em memória RAM.
- Drivers corrompidos ou incompatíveis.
- Problemas no sistema operacional.
- Superaquecimento da CPU ou GPU.

### Solução:
- Execute o **diagnóstico de memória** do Windows (`mdsched.exe`).
- Atualize drivers da placa-mãe e GPU.
- Verifique temperaturas com HWInfo ou similar.
- Reinstale o sistema se erros persistirem.

---

## 🧱 3. Travamentos e lentidão constantes

### Possíveis causas:
- Disco rígido danificado (bad sectors).
- Vírus ou malware.
- Fragmentação excessiva (em HDDs).
- Superaquecimento ou fonte instável.

### Solução:
- Execute o comando `chkdsk /f /r` ou use o **CrystalDiskInfo**.
- Faça uma varredura com antivírus confiável.
- **Desfragmente** apenas HDDs (nunca SSDs).
- Se for SSD lento, verifique se o modo **AHCI** está ativado na BIOS.
- Substitua a unidade de armazenamento se houver falhas físicas.

---

## 🔊 4. Sem som

### Possíveis causas:
- Drivers de áudio desatualizados.
- Dispositivo de reprodução errado selecionado.
- Cabo de áudio desconectado ou fone com defeito.

### Solução:
- Atualize o driver de áudio (Realtek, AMD, NVIDIA, etc).
- Clique no ícone de som → “Dispositivos de reprodução”.
- Teste outro cabo, fone ou saída.

---

## 🌐 5. Sem internet / Rede instável

### Possíveis causas:
- Driver de rede corrompido.
- Cabo Ethernet com mau contato.
- Conflito de IP ou DNS.
- Roteador com falhas ou IP bloqueado.

### Solução:
- Execute no terminal:
  ```bash
  ipconfig /release
  ipconfig /renew
  ipconfig /flushdns
  ```

## 🖥️ 7. Imagem com listas, artefatos ou sem vídeo
Possíveis causas:
- Cabo de vídeo (HDMI/VGA/DP) com mau contato.
- Placa de vídeo mal encaixada.
- Driver gráfico corrompido.
- GPU superaquecendo ou com defeito.
- Desligue o PC e reconecte o cabo de vídeo.
- Teste outro cabo e outra porta (HDMI/DisplayPort).
- Atualize ou reinstale o driver de vídeo.
- Se for placa dedicada:
- ***Teste o vídeo onboard (se disponível) para isolar o problema, Se o Processador Tiver.***
