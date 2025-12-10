# Switch | Guia Completo

Este é um guia completo para **entender e configurar switches** em redes. O objetivo deste documento é proporcionar uma visão geral das funcionalidades, tipos de switches, além de explicar como configurar e otimizar switches para redes corporativas e domésticas.

---

# 📌 Índice
1. [O que é um Switch?](#-o-que-é-um-switch)
2. [Tipos de Switches](#-tipos-de-switches)
3. [Configuração Básica de um Switch](#-configuração-básica-de-um-switch)
4. [VLAN em Switches](#-vlan-em-switches)
5. [Trunking e Uplink](#-trunking-e-uplink)
6. [Configuração de Portas](#-configuração-de-portas)
7. [STP - Spanning Tree Protocol](#-stp---spanning-tree-protocol)
8. [Switching Avançado: LACP e EtherChannel](#-switching-avançado-lacp-e-etherchannel)
9. [QoS e Controle de Banda](#-qos-e-controle-de-banda)
10. [Segurança em Switches](#-segurança-em-switches)
11. [Monitoramento e Diagnóstico](#-monitoramento-e-diagnóstico)
12. [Boas Práticas em Switches](#-boas-práticas-em-switches)

---

# 🧠 O que é um Switch?

Um **switch** é um dispositivo de rede que conecta diferentes dispositivos em uma rede local (LAN), como computadores, impressoras e servidores.  
Ele permite a comunicação entre esses dispositivos de forma rápida e eficiente, usando tabelas de endereços MAC para encaminhar pacotes entre as portas.

Ao contrário de um hub, que transmite os pacotes para todas as portas, um switch envia o pacote apenas para a **porta de destino**, o que melhora a **eficiência** e reduz **congestionamentos**.

---

# 🔄 Tipos de Switches

## ✔ Switch Não Gerenciável
- Plug-and-play, simples de configurar
- Não permite controle remoto
- Ideal para **ambientes domésticos** ou pequenas redes

## ✔ Switch Gerenciável
- Oferece controle e personalização
- Permite configurar VLANs, QoS, STP, etc.
- Ideal para **redes corporativas** e ambientes que exigem maior controle

## ✔ Switch Layer 2 (L2)
- Opera na camada de enlace de dados
- Responsável pelo **encaminhamento de pacotes** dentro da rede local
- Suporta VLANs, STP, port security

## ✔ Switch Layer 3 (L3)
- Operação de roteamento entre VLANs
- Ideal para **rede corporativa** e **roteamento inter-VLAN**

---

# 🔧 Configuração Básica de um Switch

## Passos Iniciais

### 1. Acesse o Switch
- Use **SSH**, **Telnet**, ou interface **Web (para switches gerenciáveis)**.
  
### 2. Defina o IP de gerenciamento
- Atribua um IP estático à interface de gerenciamento (geralmente **VLAN 1** ou **VLAN de gestão**).

Exemplo:


Switch> enable
Switch# configure terminal
Switch(config)# interface vlan1
Switch(config-if)# ip address 192.168.1.2 255.255.255.0
Switch(config-if)# no shutdown


---

# 🖧 VLAN em Switches

As **VLANs (Virtual Local Area Networks)** permitem segmentar fisicamente a rede, oferecendo maior segurança e desempenho.

## Criando uma VLAN no Switch

Exemplo de configuração de VLAN 10:


Switch(config)# vlan 10
Switch(config-vlan)# name SALES


## Atribuindo Portas à VLAN



Switch(config)# interface range fa0/1 - 24
Switch(config-if-range)# switchport mode access
Switch(config-if-range)# switchport access vlan 10


---

# 🔗 Trunking e Uplink

Trunking permite que múltiplas VLANs compartilhem o mesmo link entre switches.  
O **Uplink** é a porta usada para conectar o switch à rede maior (como o roteador ou outro switch).

## Configuração de Trunk


Switch(config)# interface fa0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 10,20,30


---

# 🌐 STP - Spanning Tree Protocol

O **STP** previne loops de rede, que podem causar quedas e congestionamentos.  
O STP permite que apenas um caminho seja usado para cada rede, desativando automaticamente os caminhos redundantes.

## Habilitando STP


Switch(config)# spanning-tree vlan 1 root primary


---

# 🔄 Switching Avançado: LACP e EtherChannel

### LACP (Link Aggregation Control Protocol)
LACP permite combinar múltiplos links em um **único canal de dados** para **aumentar a largura de banda** e garantir **redundância**.

Exemplo de configuração de LACP:


Switch(config)# interface range fa0/1 - 2
Switch(config-if-range)# channel-group 1 mode active


---

# 📊 QoS e Controle de Banda

### QoS (Quality of Service)
O **QoS** permite priorizar tráfego de alta importância, como VoIP ou aplicações críticas.

Exemplo:


Switch(config)# class-map match-any VOICE
Switch(config-cmap)# match ip dscp ef


### Limitar banda por porta:


Switch(config)# interface fa0/1
Switch(config-if)# bandwidth 10000


---

# 🔐 Segurança em Switches

## Bloqueio de Endereços MAC


Switch(config)# interface fa0/1
Switch(config-if)# switchport port-security mac-address sticky


## Autenticação 802.1X
Autenticação de usuários em cada porta.

---

# 🧰 Monitoramento e Diagnóstico

Utilize ferramentas de monitoramento para verificar o tráfego da rede e o estado das interfaces.

Exemplos:


Switch# show interfaces status
Switch# show spanning-tree
Switch# show vlan brief


---

# 📚 Boas Práticas em Switches

1. **Use VLANs para segmentar a rede.**
2. **Configure STP para evitar loops.**
3. **Habilite o port security** para limitar o acesso físico.
4. **Desative portas não utilizadas** para evitar acessos indesejados.
5. **Monitore constantemente** a saúde do switch e da rede.
6. **Realize backups frequentes** das configurações do switch.

---

# 📌 Conclusão

Os switches desempenham um papel fundamental na estrutura da rede, **conectando e gerenciando dispositivos**.  
Este manual cobre desde **configurações básicas** até tópicos avançados como **VLANs**, **STP**, **
