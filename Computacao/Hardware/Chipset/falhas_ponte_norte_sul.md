# 🧯 Falhas Mais Comuns — Ponte Norte e Ponte Sul

Este documento descreve os principais sintomas, causas e possíveis soluções para falhas relacionadas às pontes **Norte** e **Sul** em placas-mãe.

---

## ⚙️ Ponte Norte

A **Ponte Norte** é responsável pela comunicação entre a **CPU**, **RAM** e **GPU**.  
Falhas nesse componente costumam afetar o desempenho e a inicialização do sistema.

### 🔍 Sintomas Comuns
- O computador **não dá vídeo** na inicialização.  
- **Travamentos** ou **reboots aleatórios**.  
- O sistema **não reconhece a memória RAM**.  
- **Superaquecimento** anormal próximo ao processador.  
- **Beep codes** (códigos sonoros) indicando falha de memória ou CPU.

### 🧪 Causas Possíveis
- **Superaquecimento** devido à falta de dissipação adequada.  
- **Soldas frias** ou trincadas sob o chipset.  
- **Curto-circuito** causado por poeira ou oxidação.  
- **Fonte de alimentação instável**.  

### 🧰 Soluções / Diagnóstico
- Verificar se o **cooler do chipset** está funcionando.  
- Limpar a placa-mãe com **álcool isopropílico**.  
- Testar **outros módulos de RAM**.  
- **Reballing** ou **reflow** do chipset (realizado apenas por técnico qualificado).  

---

## ⚙️ Ponte Sul

A **Ponte Sul** gerencia dispositivos de **entrada e saída**, como **USB**, **SATA**, **áudio**, **rede** e **BIOS**.

### 🔍 Sintomas Comuns
- **Portas USB** não funcionam.  
- **HDs ou SSDs** não são reconhecidos.  
- Falha na **placa de rede** ou **áudio onboard**.  
- O computador **liga mas não inicializa o sistema operacional**.  
- **BIOS não acessa dispositivos de armazenamento**.

### 🧪 Causas Possíveis
- **Oxidação** nos conectores ou na ponte.  
- **Curto** em portas USB ou SATA.  
- **Falhas elétricas** na fonte ou no circuito de alimentação da ponte.  
- **Firmware corrompido** (BIOS).  

### 🧰 Soluções / Diagnóstico
- Testar a placa com **outros periféricos**.  
- Fazer **reset da BIOS** (remover a bateria CMOS por alguns minutos).  
- Inspecionar a região da Ponte Sul com **lupa e luz direta**.  
- Atualizar ou regravar a **BIOS**.  
- Em casos graves, realizar **reballing / substituição do chipset**.  

---

## 🧩 Tabela Resumo

| Tipo de Falha                 | Ponte Afetada | Sintoma Principal                   | Ação Recomendada                  |
|-------------------------------|----------------|------------------------------------|----------------------------------|
| Sem vídeo ao iniciar          | Norte          | Falha CPU/GPU                      | Testar RAM, vídeo e chipset      |
| USB não funciona              | Sul            | Falha de periféricos               | Testar portas e regravar BIOS    |
| HD não detectado              | Sul            | Falha SATA                         | Trocar cabo / testar outro HD    |
| Travamentos aleatórios        | Norte          | Comunicação CPU ↔ RAM              | Testar memória e temperatura     |
| Rede ou áudio onboard inativo | Sul            | Dispositivo não reconhecido        | Ver drivers ou regravar BIOS     |

---

# ***⚠️ **Atenção:** A substituição ou reballing de chipsets deve ser feita apenas por **técnicos especializados**, pois envolve risco de dano permanente à placa-mãe.***

