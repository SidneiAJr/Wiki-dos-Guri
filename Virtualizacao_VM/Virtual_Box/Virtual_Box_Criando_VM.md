# 🧩 Como Criar uma Máquina Virtual no VirtualBox

Criar uma máquina virtual no **VirtualBox** é um processo simples e rápido.  
Siga o passo a passo abaixo 👇

---

## ⚙️ Passo a Passo

1. **Baixe e instale o VirtualBox**  
   Disponível gratuitamente no site oficial: [https://www.virtualbox.org](https://www.virtualbox.org)

2. **Abra o VirtualBox** e clique em **"Novo"** ou **"Criar"**.

3. **Escolha o sistema operacional (SO)**  
   - Dê um nome à máquina.  
   - Selecione o tipo (Windows, Linux, BSD, etc.).  
   - Escolha a versão (ex: Ubuntu 64-bit, Windows 10, etc.).

4. **Defina a quantidade de memória RAM**  
   - Recomenda-se pelo menos **2 GB** para Linux leves e **4 GB ou mais** para Windows.  
   - Evite usar mais da metade da RAM total do seu computador.

5. **Configure os núcleos de processador (CPU)**  
   - Selecione quantos núcleos o sistema virtual poderá usar.  
   - Para bom desempenho, 2 núcleos é o ideal mínimo.

6. **Defina o armazenamento (HD virtual)**  
   - Crie um novo disco virtual ou use um existente.  
   - Escolha o tipo: **VDI** (recomendado) e o modo **dinamicamente alocado**.  
   - Ajuste o tamanho (mínimo 20 GB para Windows, 10 GB para Linux).

7. **Selecione o tipo de controlador e aceleração gráfica**  
   - Ative a opção **Aceleração 3D** se o sistema operacional oferecer suporte.  
   - Configure até **128 MB de vídeo** (o máximo permitido é 256 MB).

8. **Verifique o tipo de sistema operacional**  
   - Confirme se as opções correspondem ao SO que você vai instalar.

---

## ▶️ Inicialização

Após concluir a configuração, clique em **“Iniciar”** para ligar a máquina virtual.

A inicialização pode ser feita de duas formas:

- **Inicialização normal:** inicia o sistema normalmente a partir do ISO.  
- **Inicialização em modo headless:** executa a máquina virtual **sem interface gráfica**, ideal para servidores Linux com **XRDP** ou acesso remoto via terminal.

---

## 💡 Dica Extra

Para melhorar a experiência:
- Instale o **Guest Additions** dentro do sistema virtualizado (melhora vídeo, áudio e integração de pastas).  
- Use **snapshots** para salvar o estado da máquina e restaurar depois.  
- Evite usar 3D em sistemas que não precisam — melhora a estabilidade.

---


