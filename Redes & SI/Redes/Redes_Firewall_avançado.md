# 🧱 Guia de Firewall Avançado

Um **Firewall Avançado** é um sistema de segurança que vai além do simples bloqueio de portas, realizando **análise profunda de pacotes, inspeção de estado, controle de aplicações e prevenção de intrusões**.  
Ele é essencial em **redes corporativas, servidores e ambientes críticos**.

---

## ⚙️ 1. Conceito Avançado

Enquanto um firewall básico filtra apenas IPs, portas e protocolos, um firewall avançado **analisa o contexto e o conteúdo** do tráfego.

Ele entende:
- **Quem** está se comunicando;
- **O que** está sendo transmitido;
- **Qual aplicação** está envolvida;
- **Se o comportamento é normal ou malicioso**.

---

## 🔍 2. Tipos de Firewalls Avançados

| Tipo | Descrição | Exemplo |
|------|------------|----------|
| **Stateful Firewall** | Monitora o estado das conexões (TCP/UDP) e só permite tráfego relacionado. | pfSense, iptables com estado |
| **Proxy Firewall (Camada 7)** | Atua como intermediário, analisando requisições HTTP, FTP, etc. | Squid, Bluecoat |
| **Next-Generation Firewall (NGFW)** | Une inspeção profunda, controle de apps, IDS/IPS e antivírus. | FortiGate, Palo Alto, Sophos XG |
| **Firewall Cloud / WAF** | Protege aplicações web contra ataques como SQL Injection e XSS. | Cloudflare, AWS WAF |

---

## 🧠 3. Funções Avançadas

### 🔎 Inspeção Profunda de Pacotes (DPI)
Analisa o conteúdo real dos pacotes (camada de aplicação).  
Permite bloquear, por exemplo, streaming, redes P2P ou downloads de tipos de arquivo específicos.

### 🧩 Controle de Aplicações
Identifica e bloqueia aplicativos por assinatura (ex: WhatsApp, BitTorrent, TikTok, etc).

### 🚨 Integração IDS/IPS
- **IDS (Intrusion Detection System):** detecta atividades suspeitas.  
- **IPS (Intrusion Prevention System):** bloqueia automaticamente as ameaças detectadas.

### 🧱 Segmentação de Rede (Zone-Based)
Permite criar **zonas de segurança**:
- LAN → área interna confiável  
- DMZ → servidores públicos  
- WAN → internet externa  

Com regras específicas para cada direção (LAN → DMZ, DMZ → WAN, etc).

---

## 🧩 4. Exemplo de Estrutura de Regras

| Prioridade | Ação | Origem | Destino | Porta | Descrição |
|-------------|------|---------|----------|--------|------------|
| 1 | **Allow** | LAN | WAN | 80,443 | Acesso à web |
| 2 | **Deny** | LAN | WAN | 21,23,25 | Bloquear FTP/Telnet/SMTP |
| 3 | **Allow** | WAN | DMZ | 80 | Acesso público ao servidor web |
| 4 | **Deny** | Qualquer | Qualquer | * | Política padrão de negação |

---

## 🐧 5. Firewall Avançado no Linux (iptables / nftables)

### 🔹 iptables com estado:
```bash
# Limpar regras
sudo iptables -F

# Permitir conexões existentes
sudo iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT

# Permitir SSH
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT

# Bloquear tudo o resto
sudo iptables -P INPUT DROP
sudo iptables -P FORWARD DROP
