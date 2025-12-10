# 🧩 Chipsets e Arquitetura de Placas-mãe

O **chipset** é o conjunto de controladores que gerencia a comunicação entre a CPU, memória, armazenamento, portas e demais componentes do computador.

---

## 🧠 1. O que é o chipset?

O chipset funciona como o “centro de controle” da placa-mãe.

Ele coordena:
- Comunicação entre CPU e memória RAM;
- Controladores SATA, NVMe, USB, PCIe;
- Rede, áudio, e outros periféricos integrados.

---

## ⚙️ 2. Arquitetura moderna

Desde a 8ª geração Intel e os Ryzen AM4, a arquitetura usa **PCH (Platform Controller Hub)**:


🔹 **CPU**: acessa diretamente a memória RAM e PCIe principais.  
🔹 **PCH (chipset)**: gerencia as conexões secundárias (USB, SATA, etc).

---

## 💡 3. Funções do chipset

| Função | Descrição |
|---------|------------|
| **PCI Express Lanes** | Determina quantos dispositivos PCIe podem ser usados. |
| **SATA / NVMe** | Controla interfaces de armazenamento. |
| **USB** | Define o número e versão das portas disponíveis. |
| **Overclocking** | Alguns chipsets permitem alterar multiplicadores da CPU/RAM. |
| **Suporte a RAM** | Define frequências máximas e compatibilidade. |

---

## 🧩 4. Tipos de chipsets (exemplos)

### Intel (séries recentes)
| Série | Perfil | Recursos principais |
|--------|---------|----------------------|
| **Z** (Z690, Z790) | Entusiasta | Overclock, mais PCIe, mais USB |
| **B** (B660, B760) | Intermediário | Sem OC, boa conectividade |
| **H** (H610) | Básico | Restrito, sem OC, menos portas |
| **X** (X299) | Workstation | Suporte a CPUs HEDT |

### AMD (AM4/AM5)
| Série | Perfil | Recursos principais |
|--------|---------|----------------------|
| **X** (X570, X670) | Alta performance, PCIe 4.0/5.0, overclock |
| **B** (B550, B650) | Equilíbrio entre custo e desempenho |
| **A** (A520) | Básico, sem overclock |
| **WRX / TRX** | Workstation / Threadripper |

---

## 🔌 5. Conexão entre CPU e Chipset

- **DMI (Intel)**: ligação direta entre CPU e PCH.
- **Infinity Fabric (AMD)**: barramento que interliga CPU, chipset e memória.

---

## 🚀 6. Chipsets modernos e NVMe

Chipsets UEFI modernos possuem **drivers nativos para NVMe**, permitindo boot direto em SSDs PCIe, sem necessidade de módulos adicionais.

💬 *Exemplo:*  
Uma placa com chipset **B550** reconhece SSDs NVMe automaticamente via UEFI.

---

## 🧱 7. Resumo

| Item | Função |
|-------|--------|
| **CPU** | Processamento e controle principal |
| **Chipset (PCH)** | Gerencia
