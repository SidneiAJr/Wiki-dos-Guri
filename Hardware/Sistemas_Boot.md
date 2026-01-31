# 🧩 Sistemas de Boot (UEFI, BIOS, CSM e Legacy)

Eles não são tipos de armazenamento — e sim **modos de inicialização (boot)**, ou seja, a forma como o computador conversa com o hardware e inicia o sistema operacional.

---

## 🧠 1. O que é BIOS, UEFI, CSM e Legacy

| Termo | Significado | O que é na prática |
|--------|--------------|--------------------|
| **BIOS** | *Basic Input/Output System* | O sistema antigo de inicialização dos PCs (anos 80–2010) |
| **UEFI** | *Unified Extensible Firmware Interface* | O “sucessor” moderno do BIOS — mais rápido, seguro e compatível com NVMe |
| **CSM** | *Compatibility Support Module* | Um modo dentro do UEFI que **emula o BIOS antigo** |
| **Legacy** | — | Outro nome para o modo BIOS antigo (sem UEFI) |

---

## ⚙️ 2. Diferenças principais

| Modo | Tipo de Partição | Boot via | Suporte a NVMe |
|------|------------------|-----------|----------------|
| **Legacy (BIOS)** | MBR | Setor de boot (MBR) | ❌ Não suporta boot em NVMe |
| **UEFI** | GPT | Arquivo EFI (bootloader) | ✅ Suporte nativo |
| **UEFI + CSM** | MBR ou GPT | Emulação do BIOS | ⚠️ Pode causar conflitos |

---

## 🚀 3. Benefícios do UEFI

| Recurso | Explicação |
|----------|------------|
| **Suporte a NVMe** | Permite inicializar sistemas diretamente em SSDs NVMe |
| **Inicialização mais rápida** | Boot mais veloz que o BIOS tradicional |
| **Discos > 2 TB (GPT)** | Elimina o limite de 2 TB do MBR |
| **Interface moderna** | Setup com mouse e gráficos |
| **Secure Boot** | Protege contra bootkits e malware |
| **Drivers embutidos** | Reconhece hardware como NVMe e rede direto no firmware |

---

## ⚠️ 4. Quando usar Legacy ou CSM

| Situação | Recomendado |
|-----------|--------------|
| Instalar sistemas antigos (Windows 7, XP, Linux antigos) | ✅ Legacy/CSM |
| Hardware moderno (NVMe, Windows 10/11, Linux novos) | ✅ UEFI |
| Placa-mãe muito antiga (sem suporte UEFI) | ⚠️ Legacy obrigatório |

---

## 🧩 5. Resumo rápido

| Questão | UEFI | Legacy / CSM |
|----------|------|---------------|
| Suporte a NVMe | ✅ Sim | ❌ Não |
| Suporte a GPT | ✅ Sim | ❌ Não |
| Boot mais rápido | ✅ | ❌ |
| Compatível com Windows 11 | ✅ | ❌ |
| Compatível com sistemas antigos | ⚠️ Parcial | ✅ Sim |
| Segurança (Secure Boot) | ✅ | ❌ |

---

> 💬 **Em resumo:**  
> O UEFI é o sucessor do BIOS. Ele é necessário para dar boot em discos NVMe e sistemas modernos (Windows 10/11, Linux atual).  
> O Legacy/CSM serve apenas para compatibilidade com sistemas ou hardware antigos.


> ⚠️ **Importante:**  
> Na placa-mãe *Mancer 520DB (AM4)*, o modo **Legacy/CSM** impede o boot em SSDs **NVMe**.  
> É obrigatório instalar o sistema com a BIOS configurada em **UEFI Only** e o pendrive de instalação formatado como **GPT/UEFI**.  
> O modo “Dual” não reconhece corretamente o NVMe como dispositivo de boot.

---

> 💬 **Resumo:**  
> - **IDE →** obsoleto, compatibilidade com sistemas antigos.  
> - **AHCI →** padrão atual para discos SATA.  
> - **NVMe →** protocolo moderno para SSDs via PCIe, muito mais rápido.

## ⚙️ O que é AHCI

AHCI = Advanced Host Controller Interface

É um padrão de comunicação entre o sistema operacional e controladores SATA.

Ele define como os dados são enviados e recebidos entre o SSD/HDD e o processador/chipset.

👉 Em outras palavras:

O AHCI é o “intérprete” que o sistema usa pra falar com um SSD ou HD ligado via SATA.

## 🧩 1. IDE (modo legado)

Criado para HDs mecânicos com interface PATA (Parallel ATA).

Limitado em velocidade (~133 MB/s).

Usa comandos muito simples, não suporta recursos modernos.

Ainda aparece em BIOS modernas apenas por compatibilidade.

💬 Resumo: extremamente obsoleto.
Hoje, só serve pra instalar sistemas muito antigos (como Windows XP).

## ⚙️ 2. AHCI (modo moderno para SATA)

Substituiu o IDE.

Projetado para discos SATA, incluindo SSDs SATA.

Permite recursos modernos como:

NCQ (Native Command Queuing) → otimiza a ordem de leitura/gravação;

Hot Swap → permite conectar/desconectar sem desligar;

TRIM → melhora desempenho e vida útil de SSDs.

## 🚀 3. NVMe (modo atual para PCIe)

Criado especificamente para SSDs (não HDs).

Usa interface PCI Express (PCIe) — muito mais rápida que SATA.

Elimina as limitações do AHCI:

Suporta milhares de filas e comandos simultâneos;

Latência extremamente baixa;

Aproveita melhor CPUs multicore.
