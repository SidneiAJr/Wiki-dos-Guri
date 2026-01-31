# 🔥 Firewall | Regras (Guia Completo)

As regras de firewall determinam o que é permitido e o que é bloqueado dentro de uma rede.
Esse guia apresenta tudo que você precisa saber sobre regras, tipos, exemplos e boas práticas.

## O que é uma Regra de Firewall?

Uma regra define:

Ação — permitir ou bloquear

Protocolo — TCP, UDP, ICMP, etc.

Origem (Source)

Destino (Destination)

Porta (Port)

Interface — LAN, WAN, DMZ

Condições extras — horário, usuário, aplicação

## 🧱 Tipos de Ação
✔ ALLOW (Permitir)

Permite o tráfego.

❌ DENY (Negar)

Bloqueia e envia mensagem de volta.

🚫 DROP (Descartar)

Bloqueia silenciosamente.
Usado para segurança máxima.

↩️ REJECT (Rejeitar)

Bloqueia e informa ao cliente imediatamente.

## 🌐 Tipos de Tráfego que Podem Ser Filtrados

Entradas (Inbound)

Saídas (Outbound)

Local (Loopback)

VPN

DMZ

Inter-VLAN

Multicast / Broadcast

## Protocolo por Porta Comum

| Serviço    | Porta | Protocolo |
| ---------- | ----- | --------- |
| HTTP       | 80    | TCP       |
| HTTPS      | 443   | TCP       |
| DNS        | 53    | TCP/UDP   |
| FTP        | 20/21 | TCP       |
| SSH        | 22    | TCP       |
| RDP        | 3389  | TCP       |
| MySQL      | 3306  | TCP       |
| PostgreSQL | 5432  | TCP       |

## Tipos de Firewall e Suas Regras

Firewall de Camada 3 (Packet Filter)

Regras baseadas em:

IP origem

IP destino

Porta

Protocolo

## 2. Firewall de Camada 4 (Stateful)

Controla:

conexões ativas

estado da sessão

ALLOW TCP 80 IF connection_state == ESTABLISHED

## 3. Firewall de Camada 7 (Application Layer)

Filtra aplicações:

HTTP

DNS

WhatsApp

Netflix

YouTube

Ação | Protocolo | Porta | Origem | Destino | Interface | Observação

ALLOW TCP 443 FROM LAN TO ANY


Exemplos de Regras Usuais
🔹 Permitir navegação na web
ALLOW TCP 80,443 FROM LAN TO ANY

🔹 Bloquear SSH externo
DENY TCP 22 FROM WAN TO LAN

🔹 Bloquear todos os torrents
DENY ALL FROM LAN TO ANY WHERE traffic=p2p

🔹 Permitir apenas um IP acessar o servidor
ALLOW TCP 22 FROM 192.168.1.50 TO 192.168.1.10
DENY TCP 22 FROM ANY TO 192.168.1.10

🔹 Bloquear saída de redes sociais
DENY HTTP/HTTPS TO facebook.com, instagram.com, tiktok.com

⏲ Regras Baseadas em Horário
ALLOW TCP 80 FROM LAN TO ANY TIME 08:00-18:00
DENY TCP 80 FROM LAN TO ANY TIME 18:01-07:59


