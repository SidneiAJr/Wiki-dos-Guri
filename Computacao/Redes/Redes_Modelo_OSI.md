# 🌐 Modelo OSI (Open Systems Interconnection)

O modelo **OSI** é uma referência criada pela ISO para padronizar a comunicação entre sistemas de rede.

Ele divide a comunicação em **7 camadas**, cada uma com uma função específica:

| Camada | Nome | Função Principal | Exemplo |
|:--:|:--|:--|:--|
| 7 | **Aplicação** | Interface entre usuário e rede | HTTP, FTP, DNS |
| 6 | **Apresentação** | Converte formatos de dados | SSL/TLS, JPEG, ASCII |
| 5 | **Sessão** | Gerencia sessões de comunicação | RPC, NetBIOS |
| 4 | **Transporte** | Garante entrega e integridade | TCP, UDP |
| 3 | **Rede** | Roteia pacotes | IP, ICMP |
| 2 | **Enlace (Link)** | Transfere quadros dentro da rede local | Ethernet, Wi-Fi |
| 1 | **Física** | Transmissão de bits | Cabos, conectores, sinais elétricos |

---

## 🧠 Conceito-Chave
Cada camada **só se comunica com a camada imediatamente acima e abaixo**.  
Isso permite que protocolos mudem sem afetar o resto da rede.

---

## 📡 Exemplo prático
Quando tu abre um site:
1. A camada de aplicação (HTTP) faz o pedido.
2. A de transporte (TCP) divide os dados em segmentos.
3. A de rede (IP) envia os pacotes pelo melhor caminho.
4. A de enlace (Ethernet/Wi-Fi) entrega os quadros.
5. A de física converte em bits e sinais.

---

## 🔍 Dica
> Um jeito fácil de lembrar as camadas é:
> **"A Pega Sessão Toda Na Escola Física"**  
> (Aplicação → Apresentação → Sessão → Transporte → Rede → Enlace → Física)

