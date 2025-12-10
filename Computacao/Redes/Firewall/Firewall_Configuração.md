# 🔥 Firewall | Configuração

Firewalls são sistemas responsáveis por **controlar o tráfego de rede**, permitindo ou bloqueando conexões conforme regras definidas.  
Entre os mais comuns no ambiente de estudo e trabalho estão:

- **Firewall do Windows**
- **iptables (Linux)**
- **pfSense (Firewall profissional / Open Source)**

---

# 🪟 1. Firewall do Windows

O Firewall do Windows é integrado ao sistema operacional e permite controlar:

- Programas permitidos ou bloqueados  
- Portas liberadas  
- Redes privadas e públicas  
- Regras de entrada e saída  

## ✔ Como abrir o Firewall

1. Abra o menu Iniciar  
2. Digite **Firewall do Windows**  
3. Clique em **Firewall do Windows Defender com Segurança Avançada**

## ✔ Criar uma regra de entrada (permitir porta)

1. Vá em **Regras de Entrada**  
2. Clique em **Nova Regra**  
3. Escolha **Porta**  
4. Escolha **TCP** ou **UDP**  
5. Digite a porta (ex: 80, 443, 3389)  
6. Selecione **Permitir a conexão**  
7. Aplique ao perfil desejado  
8. Dê um nome e finalize  

---

# 🐧 2. iptables (Linux)

O `iptables` é o firewall nativo do Linux (Camada 3/4).  
Permite controle profundo do tráfego:

- Bloquear IPs  
- Liberar portas  
- Redirecionar conexões (NAT)  
- Criar políticas de segurança  

## ✔ Comandos básicos

### Listar regras
```bash
sudo iptables -L -v

sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT

sudo iptables -A INPUT -p tcp --dport 23 -j DROP

sudo iptables -A INPUT -p tcp --dport 23 -j DROP

sudo netfilter-persistent save
```

## pfSense (Firewall Profissional)

O pfSense é um firewall completo e muito usado em empresas, escolas e provedores.

`Ele é acessado pelo navegador via Web GUI:`

http://192.168.1.1

usuário: admin

senha: pfsense

✔ Principais funções do pfSense

Criar VLANs

Regras de firewall detalhadas

NAT / Port Forward

VPN (OpenVPN, IPsec, WireGuard)

QoS / Traffic Shaping

DHCP server

Captive Portal (rede com autenticação)

Dashboard completo

## ✔ Criando regra de firewall no pfSense

Acesse Firewall > Rules

Escolha a interface (LAN, WAN, VLAN…)

Clique em Add (Adicionar)

Configure:

Action: Pass / Block / Reject

Source: IP/porta de origem

Destination: IP/porta destino

Protocol: TCP/UDP/ICMP

Clique em Save

Clique em Apply Changes

## Resumo Geral

| Firewall     | Complexidade | Uso Ideal                   |
| ------------ | ------------ | --------------------------- |
| **Windows**  | Fácil        | PCs, ambientes simples      |
| **iptables** | Médio/Alta   | Servidores Linux            |
| **pfSense**  | Médio        | Empresas, redes gerenciadas |

