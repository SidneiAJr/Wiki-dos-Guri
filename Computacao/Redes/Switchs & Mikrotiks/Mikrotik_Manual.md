# 📘 Manual Completo Mikrotik
Guia definitivo para iniciantes e profissionais configurarem e entenderem um roteador Mikrotik.  
Este manual cobre desde o básico até configurações de nível empresarial.

---

# 📌 Índice
1. [O que é Mikrotik](#-o-que-é-mikrotik)
2. [Para que serve](#-para-que-serve)
3. [Modelos e Categorias](#-modelos-e-categorias)
4. [Formas de Acesso](#-formas-de-acesso)
5. [Primeira Configuração](#-primeira-configuração)
6. [Configuração de Internet (WAN)](#-configuração-de-internet-wan)
7. [Configuração da Rede Interna (LAN)](#-configuração-da-rede-interna-lan)
8. [DHCP Server](#-dhcp-server)
9. [NAT / Masquerade](#-nat--masquerade)
10. [DNS](#-dns)
11. [Firewall Básico](#-firewall-básico)
12. [VLANs no Mikrotik](#-vlans-no-mikrotik)
13. [QoS / Controle de Banda](#-qos--controle-de-banda)
14. [VPN](#-vpn)
15. [Balanceamento de Links (PCC)](#-balanceamento-de-links-load-balance)
16. [Failover Automático](#-failover-automático)
17. [Hotspot](#-hotspot)
18. [Backup e Restore](#-backup-e-restore)
19. [Comandos Úteis](#-comandos-úteis)
20. [Boas Práticas de Segurança](#-boas-práticas-de-segurança)

---

# 🧠 O que é Mikrotik?
A **Mikrotik** fabrica equipamentos de rede e o sistema operacional **RouterOS**, usado como:

- roteador
- firewall
- switch
- balanceador
- servidor de VPN
- controlador de WiFi

É conhecido pelo custo-benefício e alto nível de configuração.

---

# 🎯 Para que serve?
O Mikrotik pode atuar como:

- Roteador corporativo
- Firewall avançado
- Load Balance
- Controle de banda (QoS)
- DHCP/DNS Server
- Hotspot
- PPPoE Server
- VPN
- Switch gerenciável

---

# 📦 Modelos e Categorias
| Categoria | Exemplos | Descrição |
|----------|----------|-----------|
| Home | hAP Lite, hAP ac2 | Uso doméstico |
| SMB | RB2011, RB3011 | Pequenas empresas |
| Enterprise | CCR1009, CCR2004 | Alta performance |
| Wireless | cAP, wAP | Ambientes Wi-Fi |
| Switches | CRS series | Switch gerenciável |

---

# 🔐 Formas de Acesso

### ✔ WinBox (mais recomendado)
Interface gráfica leve e funcional.

### ✔ WebFig
Acesso via navegador.

### ✔ SSH
Terminal avançado.

### ✔ MAC Winbox
Mesmo sem IP configurado.

### ✔ Console Serial
Resgate e manutenção.

---

# 🛠 Primeira Configuração

## 🔄 Reset para configuração limpa

Opções:
- **Keep Defaults** → mantém configuração de fábrica  
- **No Default Configuration** → limpa tudo

---

# 🌍 Configuração de Internet (WAN)

## 1. Definir IP da WAN (estático)

/ip address add address=100.100.50.2/30 interface=ether1


## 2. Configurar Gateway


/ip route add gateway=100.100.50.1


---

# 🏠 Configuração da Rede Interna (LAN)

## Definir o IP LAN


/ip address add address=192.168.1.1/24 interface=bridge


---

# 📡 DHCP Server
Iniciar o assistente:


/ip dhcp-server setup


O Mikrotik solicitará:
- Interface
- Gateway
- Range DHCP
- DNS
- Tempo de lease

---

# 🔥 NAT / Masquerade

## Regra essencial para navegar:


/ip firewall nat add chain=srcnat out-interface=ether1 action=masquerade


---

# 🌐 DNS
Configurar DNS público:


/ip dns set servers=8.8.8.8,1.1.1.1 allow-remote-requests=yes


---

# 🛡 Firewall Básico

## Bloquear conexões inválidas


/ip firewall filter add chain=forward connection-state=invalid action=drop


## Permitir tráfego já estabelecido


/ip firewall filter add chain=forward connection-state=established,related action=accept


## Bloquear acesso externo ao roteador


/ip firewall filter add chain=input in-interface=ether1 action=drop


---

# 🏷 VLANs no Mikrotik

## Criar VLAN na porta ether2


/interface vlan add name=vlan10 interface=ether2 vlan-id=10


## Atribuir IP à VLAN


/ip address add address=10.0.10.1/24 interface=vlan10


---

# 📊 QoS / Controle de Banda

## Limitar banda de um IP específico


/queue simple add target=192.168.1.50 max-limit=10M/5M


## Priorizar VoIP


/queue type add name=voip priority=1

/interface l2tp-server server set enabled=yes use-ipsec=yes ipsec-secret=SENHA_FORTE


---

# 🔀 Balanceamento de Links (Load Balance)

(Técnica PCC — Per Connection Classifier)

Exemplo simples:


/ip firewall mangle add chain=prerouting dst-address-type=!local in-interface=bridge per-connection-classifier=both-addresses:2/0 action=mark-connection new-connection-mark=wan1_conn


(Posso montar o PCC completo se quiser.)

---

# ⚡ Failover Automático


/ip route add gateway=100.100.1.1 distance=1
/ip route add gateway=200.200.1.1 distance=2


---

# 📢 Hotspot
Iniciar assistente:


/ip hotspot setup


---

# 💾 Backup e Restore

### Criar backup binário


/system backup save name=config


### Restaurar


/system backup load name=config


### Exportar em texto


/export file=config_text


---

# 💻 Comandos Úteis


/ip address print
/ip route print
/system resource print
/log print
/interface print


---

# 🔐 Boas Práticas de Segurança
- Trocar usuário *admin*
- Usar senha forte
- Desabilitar serviços não usados (telnet, ftp, api)
- Bloquear acesso externo ao winbox/ssh
- Usar firewall mínimo
- Backup periódico
