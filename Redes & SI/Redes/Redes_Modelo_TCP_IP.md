# 🌍 Modelo TCP/IP

O modelo **TCP/IP** é o padrão da internet moderna, criado pelo Departamento de Defesa dos EUA.  
Ele é mais prático que o OSI e tem **4 camadas**:

| Camada | Função | Protocolos |
|:--:|:--|:--|
| 4 | **Aplicação** | Comunicação entre programas | HTTP, FTP, DNS, SMTP |
| 3 | **Transporte** | Controle de dados | TCP, UDP |
| 2 | **Internet** | Endereçamento e roteamento | IP, ICMP |
| 1 | **Acesso à Rede** | Envio físico e link de dados | Ethernet, Wi-Fi |

---

## ⚙️ Comparação OSI vs TCP/IP

| OSI | TCP/IP |
|-----|---------|
| 7 camadas | 4 camadas |
| Modelo teórico | Modelo prático |
| ISO | DoD (EUA) |
| Didático | Usado na Internet real |

---

## 📶 Fluxo de Comunicação
1. A aplicação envia dados (HTTP).  
2. O TCP divide e garante entrega.  
3. O IP define o destino (endereço).  
4. A camada de rede envia fisicamente os pacotes.

---

## 💡 Curiosidade
> O IP define o **endereço** do dispositivo, e o TCP garante que os **dados cheguem inteiros e na ordem certa**.

