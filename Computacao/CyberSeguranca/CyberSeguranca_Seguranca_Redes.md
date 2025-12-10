# 🌐 Segurança em Redes

## 🎯 Objetivo
Aprender as principais práticas de **segurança em redes de computadores**, garantindo **confidencialidade, integridade e disponibilidade** das informações.

---

## 🧠 1️⃣ Conceitos Fundamentais

| 🔑 Termo | 📘 Significado |
|-----------|----------------|
| **Rede Segura** | Conjunto de dispositivos protegidos contra acessos indevidos. |
| **Firewall** | Sistema que filtra o tráfego de rede, bloqueando conexões suspeitas. |
| **VPN** | Cria um túnel criptografado entre o usuário e a internet. |
| **IDS/IPS** | Ferramentas que detectam e previnem intrusões. |
| **Proxy** | Servidor intermediário que ajuda a controlar e monitorar acessos. |

---

## 🔒 2️⃣ Firewall — Primeira Linha de Defesa

O **firewall** atua como uma barreira entre a rede interna e o mundo externo.

### 📋 Tipos de Firewall:
- **Baseado em software:** integrado ao sistema operacional (como o do Windows ou Linux).  
- **Baseado em hardware:** roteadores e equipamentos dedicados.  
- **De próxima geração (NGFW):** inclui inspeção profunda de pacotes e detecção de ameaças.

### 💡 Exemplo prático:
- Bloquear portas desnecessárias (como 21, 23, 445).  
- Permitir apenas o tráfego essencial (HTTP, HTTPS, DNS, etc.).

---

## 🧭 3️⃣ Segmentação de Rede

Separar a rede em **zonas menores (sub-redes)** reduz o impacto de invasões e facilita o controle.

| 🌐 Zona | ⚙️ Função |
|---------|-----------|
| **LAN (Local Area Network)** | Rede interna segura (usuários, impressoras, etc.) |
| **DMZ (Demilitarized Zone)** | Área intermediária onde ficam servidores acessíveis pela internet (como web servers). |
| **WAN (Wide Area Network)** | Conexão externa com a internet. |

> 💡 Exemplo: um servidor web pode ficar na DMZ, enquanto o banco de dados permanece isolado na LAN.

---

## 🔑 4️⃣ Criptografia de Dados

A **criptografia** transforma informações em códigos ilegíveis para quem não possui a chave correta.

### 🧩 Tipos:
- **Simétrica:** usa a mesma chave para criptografar e descriptografar.  
- **Assimétrica:** usa um par de chaves (pública e privada).  

### 📦 Aplicações comuns:
- HTTPS (SSL/TLS)  
- VPNs  
- E-mails seguros  
- Armazenamento de senhas

---

## 📡 5️⃣ Segurança em Redes Wi-Fi

Wi-Fi é uma das portas mais visadas por atacantes.  
Proteger a rede sem fio é essencial, tanto em casa quanto em empresas.

### 🔐 Boas práticas:
- Usar **WPA3** (ou pelo menos WPA2).  
- Desativar o **WPS**.  
- Alterar o **SSID padrão** e a senha do roteador.  
- Limitar o acesso por **MAC address**.  
- Desativar o broadcast do SSID se possível.  

> ⚠️ Nunca usar “admin / admin” como credenciais de roteador!

---

## 🧰 6️⃣ VPN — Rede Privada Virtual

A **VPN (Virtual Private Network)** cria um **túnel criptografado** entre o usuário e o servidor.  
Ela protege os dados transmitidos, especialmente em redes públicas.

### ✅ Benefícios:
- Protege comunicações em Wi-Fi público.  
- Oculta o endereço IP real.  
- Garante privacidade e anonimato online.  

> 💡 Exemplo: ao usar um café com Wi-Fi aberto, conectar-se via VPN impede que curiosos interceptem seus dados.

---

## 🧩 7️⃣ IDS e IPS — Monitoramento Ativo

Ferramentas que **detectam (IDS)** e **previnem (IPS)** intrusões na rede.

| 🧠 Tipo | ⚙️ Função |
|---------|-----------|
| **IDS (Intrusion Detection System)** | Apenas monitora e alerta sobre comportamentos suspeitos. |
| **IPS (Intrusion Prevention System)** | Além de detectar, bloqueia automaticamente o ataque. |

Exemplo de ferramentas conhecidas:
- **Snort**  
- **Suricata**  
- **OSSEC**

---

## 🧭 8️⃣ Políticas de Segurança de Rede

Um ambiente seguro depende de **regras bem definidas**.

### 📋 Itens importantes:
- Controle de acesso por função (mínimo necessário).  
- Bloqueio automático após tentativas de login falhas.  
- Logs de auditoria e monitoramento contínuo.  
- Senhas e certificados com prazo de expiração.  
- Documentação das mudanças na infraestrutura.

---

## 🧩 9️⃣ Boas Práticas de Administração de Rede

| 💡 Ação | 🧰 Benefício |
|---------|--------------|
| Atualizar firmwares de roteadores | Corrige vulnerabilidades. |
| Usar IPs fixos para servidores | Facilita controle e monitoramento. |
| Monitorar largura de banda | Identifica picos anormais de uso. |
| Revisar logs semanalmente | Detecta acessos indevidos. |

---

## 0️⃣ Conclusão

A segurança de rede é um **processo contínuo**, não uma configuração única.  
Com políticas bem definidas, atualizações regulares e boas práticas, é possível **manter o ambiente protegido** contra a maioria das ameaças digitais.

> 🔐 “Rede segura não é a que nunca é atacada, mas a que está sempre pronta para reagir.”
