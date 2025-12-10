# 🌍 Protocolos DNS, DHCP e HTTP

## 🧭 DNS (Domain Name System)
O **DNS** traduz nomes de domínio em endereços IP.

Exemplo:

**Funções principais:**
- Resolver nomes (hostname → IP)
- Armazenar cache de consultas
- Distribuir domínios hierarquicamente (.com, .org, .br)

---

## 🔌 DHCP (Dynamic Host Configuration Protocol)
O **DHCP** entrega automaticamente endereços IP e configurações de rede aos dispositivos.

**Etapas:**
1. **Discover:** o cliente procura um servidor DHCP.  
2. **Offer:** o servidor oferece um IP disponível.  
3. **Request:** o cliente aceita a oferta.  
4. **Acknowledge:** o servidor confirma e entrega as configs.

**DHCP fornece:**
- Endereço IP  
- Máscara de rede  
- Gateway padrão  
- DNS primário e secundário

---

## 🌐 HTTP (HyperText Transfer Protocol)
O **HTTP** é o protocolo de comunicação da web.

- Usa as portas **80 (HTTP)** e **443 (HTTPS)**  
- Baseado no modelo **cliente-servidor**  
- O navegador faz requisições (GET, POST, PUT, DELETE)

**Exemplo de requisição:**


**HTTP vs HTTPS:**
- HTTP → sem criptografia  
- HTTPS → usa SSL/TLS para segurança

---

## 💡 Resumo

| Protocolo | Função | Porta |
|:--|:--|:--:|
| **DNS** | Traduz nomes em IPs | 53 |
| **DHCP** | Entrega IPs automáticos | 67/68 |
| **HTTP/HTTPS** | Transfere páginas web | 80 / 443 |

