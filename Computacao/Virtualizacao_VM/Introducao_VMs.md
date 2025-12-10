# 🖥️ Tutorial de Uso de Máquina Virtual (VM)

## 📦 1. Instalação do Hypervisor
Antes de tudo, instale um gerenciador de máquinas virtuais (hypervisor):

- [VirtualBox (gratuito)](https://www.virtualbox.org)
- [VMware Workstation Player (gratuito para uso pessoal)](https://www.vmware.com)

Após o download, siga o instalador e finalize a instalação normalmente.

---

## ⚙️ 2. Configuração Inicial
1. Abra o VirtualBox ou VMware.
2. Clique em **"Nova"** para criar uma máquina virtual.
3. Defina:
   - **Nome da VM**  
   - **Tipo de sistema operacional** (ex: Linux, Windows, Debian)
   - **Versão** (32 ou 64 bits)

---

## 💾 3. Escolha da ISO
1. Baixe a **imagem ISO** do sistema operacional desejado (ex: Ubuntu, Windows, Kali Linux).  
2. No VirtualBox, selecione **“Usar arquivo ISO existente”** e escolha o arquivo.

---

## 🧠 4. Recursos de Hardware
Configure os recursos conforme sua máquina física:

| Recurso | Recomendado | Observação |
|----------|--------------|------------|
| **Memória RAM** | 2–4 GB | Use no máximo 40% da RAM total da sua máquina |
| **Processadores (CPU)** | 2 núcleos | Mais núcleos = mais desempenho |
| **Placa de vídeo** | Habilitar aceleração 3D | Melhora gráficos e responsividade |
| **Disco Rígido (HDD/SSD)** | 20–60 GB | Use o formato VDI e modo “Dinâmico” |
| **Controladora** | SATA (AHCI) | Melhor compatibilidade |

> ⚠️ Exemplo: se seu PC tem **8 GB de RAM**, use no máximo **2 a 3 GB** para a VM.  
> Exceder isso pode causar **crash** ou **tela azul** no sistema hospedeiro.

---

## ▶️ 5. Primeira Inicialização
1. Clique em **“Iniciar”**.
2. Selecione a ISO para inicializar o sistema.
3. Siga o instalador normalmente.

Dica: no VirtualBox, o **modo "Headless" (sem janela)** permite rodar a VM em segundo plano.

---

## 🌐 6. Acesso Remoto à VM
Para acessar a máquina virtual remotamente:

- **Linux (xrdp ou SSH)**  
  - Instale o `xrdp`:  
    ```bash
    sudo apt install xrdp
    ```
  - Anote o IP da VM:
    ```bash
    ip addr show
    ```
- **Windows (RDP)**
  - Use o cliente de acesso remoto (`mstsc`).
  - Configure no VirtualBox:  
    *Configurações → Exibir → Servidor Remoto (Habilitar RDP)*

---

## 🔁 7. Dicas Extras
- Faça **snapshots** (pontos de restauração) antes de testar algo arriscado.  
- Use **pastas compartilhadas** para trocar arquivos entre a VM e o sistema real.  
- Lembre de ativar o **suporte a virtualização (VT-x / AMD-V)** na BIOS.  
- Configure rede em **modo Bridge** se quiser que a VM tenha um IP na mesma rede do PC.

---

## ✅ 8. Finalizando
Pronto!  
Sua VM está configurada, segura e pronta para uso.  
Você pode instalar sistemas, testar programas, estudar redes e até programar sem arriscar o PC real.

> 💡 *Máquinas virtuais são o “laboratório” perfeito pra aprender sem medo!*
