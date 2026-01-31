# 🔥 Firewall – Básico

O **Firewall** é uma ferramenta essencial de segurança de rede usada para **controlar o tráfego de entrada e saída** entre um computador (ou rede) e a Internet.  
Ele funciona como uma **barreira de proteção**, permitindo apenas o que é seguro e bloqueando acessos suspeitos.

---

## 🧱 1. O que é um Firewall?

Um **firewall** monitora e filtra os dados que entram e saem de um sistema, com base em **regras de segurança** pré-definidas.  
Seu principal objetivo é **impedir acessos não autorizados** e **bloquear ataques** vindos da rede.

Existem dois tipos principais:

| Tipo | Descrição |
|------|------------|
| **Firewall de Hardware** | Integrado em roteadores e dispositivos de rede. Protege toda a rede. |
| **Firewall de Software** | Instalado em sistemas operacionais (como o Windows Defender Firewall). Protege apenas o dispositivo local. |

---

## ⚙️ 2. Função Básica

O firewall trabalha com **portas** e **protocolos**.  
Ele analisa cada pacote de dados que tenta entrar ou sair, verificando se a conexão é **permitida, bloqueada ou monitorada**.

### Exemplo:
- Porta **80 (HTTP)** → tráfego web normal → **permitido**  
- Porta **23 (Telnet)** → protocolo inseguro → **bloqueado**  
- Porta **3389 (RDP)** → acesso remoto → **permitido apenas para IPs confiáveis**

---

## 🛡️ 3. Tipos de Filtro

| Tipo de Filtro | Descrição |
|----------------|------------|
| **Filtro de Pacotes** | Verifica IPs, portas e protocolos. É rápido, mas básico. |
| **Firewall de Aplicação** | Analisa o conteúdo do tráfego (ex: HTTP, FTP). Mais seguro. |
| **Stateful Inspection** | Mantém o estado das conexões ativas para detectar tráfego suspeito. |
| **Next-Generation Firewall (NGFW)** | Combina inspeção profunda, antivírus, IDS/IPS e controle de aplicativos. |

---

## 🔧 4. Exemplos Práticos

### 🪟 Windows:
- O **Windows Defender Firewall** vem ativado por padrão.  
