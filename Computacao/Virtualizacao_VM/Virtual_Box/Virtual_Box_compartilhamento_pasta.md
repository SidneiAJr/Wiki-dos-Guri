# 📁 Compartilhando Pastas no VirtualBox (Windows)

Para compartilhar pastas entre o **sistema host (Windows)** e a **máquina virtual**, é necessário ter o **Guest Additions** instalado.  
Esse recurso permite trocar arquivos facilmente entre o seu computador e o sistema dentro da VM.

---

## ⚙️ Pré-requisitos

- Guest Additions instalado dentro da máquina virtual.  
- Máquina virtual desligada antes de configurar o compartilhamento.

---

## 🧩 Passo a Passo

1. Selecione a máquina virtual no VirtualBox (sem iniciá-la).  
2. Clique em **Configurações → Pastas Compartilhadas**.  
3. Clique no **ícone de “+” (Adicionar nova pasta)**.  
4. Escolha a pasta do seu sistema **host (Windows)** que deseja compartilhar.  
5. Marque as opções conforme sua necessidade:
   - **Montar automaticamente:** a pasta será montada toda vez que a VM iniciar.  
   - **Tornar permanente:** mantém o compartilhamento mesmo após reiniciar.  
   - **Somente leitura:** impede que o sistema convidado altere arquivos.

---

## 💻 Dentro da Máquina Virtual

- No **Windows Guest:**  
  A pasta aparecerá como uma **unidade de rede** dentro do “Este PC” (geralmente com o nome `\\vboxsrv\<nome_da_pasta>`).  

- No **Linux Guest:**  
  A pasta será montada em `/media/sf_<nome_da_pasta>` automaticamente.

Se a pasta não aparecer, você pode montar manualmente (em Linux):
```bash
sudo mount -t vboxsf <nome_da_pasta> /pasta/destino
