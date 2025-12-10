# 🧩 Instalação do Guest Additions no VirtualBox

O **Guest Additions** é um pacote adicional do VirtualBox que melhora a integração entre o sistema real (host) e o sistema virtual (guest).  
Ele adiciona recursos como:
- Melhoria no desempenho gráfico.  
- Suporte a tela cheia e redimensionamento automático.  
- Copiar/colar entre host e VM.  
- Pastas compartilhadas.  
- Melhor suporte a mouse e teclado.

---

## 💻 Instalação no Windows (Máquina Virtual)

1. Inicie sua máquina virtual com Windows.  
2. No menu superior do VirtualBox, clique em:  
   **Dispositivos → Inserir imagem de CD dos Additions...**  
3. O Windows vai montar automaticamente o disco de instalação.  
4. Abra o **Meu Computador** (ou “Este PC”) e clique duas vezes no ícone do **CD do VirtualBox Guest Additions**.  
5. Siga o instalador normalmente e, ao final, **reinicie a máquina virtual**.

> ⚠️ **Dica:** se o instalador pedir permissão do Windows ou driver, aceite — são necessários para os recursos funcionarem corretamente.

---

## 🐧 Instalação no Linux (Máquina Virtual)

Em distribuições Linux, o processo é um pouco diferente.  
Siga os passos:

1. Inicie sua VM Linux.  
2. No menu superior, clique em:  
   **Dispositivos → Inserir imagem de CD dos Additions...**  
3. O CD será montado automaticamente (geralmente em `/media/usuario/VBox_GAs_x.x.x`).  
4. Abra o terminal dentro dessa pasta e execute:

   ```bash
   sudo ./VBoxLinuxAdditions.run
