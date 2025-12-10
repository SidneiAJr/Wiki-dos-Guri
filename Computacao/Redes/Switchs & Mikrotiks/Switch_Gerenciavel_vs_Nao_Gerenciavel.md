# 🌐 Switch Gerenciável vs Não Gerenciável

Este documento explica as diferenças entre **switches gerenciáveis e não gerenciáveis**, quando usar cada um, vantagens, desvantagens e exemplos reais de aplicação.

---

## 🔵 O que é um Switch Não Gerenciável?

Um switch **não gerenciável** é um dispositivo plug-and-play sem configurações.  
Ele apenas faz o básico: **receber pacotes e enviá-los para a porta correta**.

### ✔ Vantagens
- Muito barato  
- Fácil: plugou, funciona  
- Ideal para pequenas redes  
- Baixo consumo e pouca manutenção  

### ❌ Desvantagens
- Sem VLANs  
- Sem QoS  
- Sem monitoramento  
- Sem segurança avançada  
- Sem logs  
- Não permite criar redundância (STP, LACP)  

### 📌 Uso recomendado
- Casas  
- Pequenos escritórios  
- Redes que não precisam de segmentação  

---

## 🔵 O que é um Switch Gerenciável?

Um switch **gerenciável** permite configurar e controlar toda a rede:

- VLANs  
- QoS  
- STP (evitar loops)  
- Segurança (Port Security)  
- LACP (agregação de links)  
- Monitoramento SNMP  
- espelhamento de porta  
- DHCP Snooping / ARP Inspection  
- ACLs  
- Logs / estatísticas  

### ✔ Vantagens
- Segurança muito superior  
- Suporte para redes grandes  
- Segmentação por VLAN  
- Controle de tráfego  
- Diagnóstico e logs  
- Redundância avançada  

### ❌ Desvantagens
- Mais caro  
- Requer conhecimento técnico  
- Pode exigir manutenção  

### 📌 Uso recomendado
- Empresas  
- Instituições de ensino  
- Redes críticas (hospital, governo)  
- Datacenters  

---

## 🆚 Comparação Geral

| Característica | Não Gerenciável | Gerenciável |
|---------------|------------------|-------------|
| VLAN          | ❌               | ✔           |
| QoS           | ❌               | ✔           |
| STP           | ❌               | ✔           |
| Port Security | ❌               | ✔           |
| Monitoramento | ❌               | ✔ SNMP      |
| Configuração  | Zero             | Avançada    |
| Preço         | Baixo            | Médio/Alto  |

---

## 📌 Conclusão
- Para **casas e pequenos ambientes**, um switch não gerenciável basta.
- Para **empresas, escolas, servidores e redes segmentadas**, o gerenciável é indispensável.

