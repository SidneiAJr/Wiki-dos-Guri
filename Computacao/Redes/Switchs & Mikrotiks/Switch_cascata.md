# 🔗 Portas de Switch e Cascateamento (Uplink)

Este documento explica como funcionam as portas de um switch, uplinks, portas tronco, e como fazer cascateamento da forma correta.

---

# 🔌 1. Tipos de Portas em Switches

## ✔ Portas Acesso (Access)
Usadas para **computadores, impressoras, câmeras, servidores**.

- Pertencem a **apenas uma VLAN**
- Enviam frames **não taggeados**

Exemplo de configuração:
```bash
switchport mode access
switchport access vlan 10
```

## Portas Trunk

Usadas entre switches, roteadores e virtualização.

Transportam várias VLANs ao mesmo tempo

Usam tag de VLAN (802.1Q)
```bash
switchport mode trunk
switchport trunk allowed vlan 10,20,30
```

## Porta Uplink

Porta dedicada (ou qualquer porta usada) para:

conectar um switch a outro

conectar switch → roteador

conectar switch → firewall

Normalmente tem mais velocidade (10Gbps em sws corporativos).

## Cascateamento de Switches (“Cascade”, “Daisy Chain”)

Cascatear = ligar um switch em outro.

Existem 3 formas:

Cascata Simples (padrão)

Switch A → Switch B


✔ Funciona

❌ Não escala para grandes redes

❌ Pode gerar gargalo

❌ Evitar grandes cadeias

Cascata com Trunk (correto)

Switch A ↔ Switch B usando trunk com VLANs.

✔ Ideal

✔ Suporta VLANs

✔ Correto para ambientes profissionais

2.3 Cascata em Corrente Grande (proibido)

A → B → C → D → E → F → G


❌ Latência alta

❌ Toda rede depende de um cabo

❌ risco de loop

❌ desastre em empresas

Loops e como evitar

Sem proteção, ligar dois switches por dois cabos causa loop de broadcast, derrubando toda rede.

STP evita:

loops

broadcast storm

travamento da rede

. Melhor forma de cascateamento

🔷 4.1 Estrela (topologia recomendada)

Um switch principal → todos os outros ligados nele.


✔ melhor latência

✔ mais rápido

✔ mais seguro

