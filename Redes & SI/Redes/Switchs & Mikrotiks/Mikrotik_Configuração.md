# Mikrotik | Configuração Básica

A configuração de um Mikrotik pode ser feita de várias formas: **WinBox**, **WebFig**, **SSH** ou **Console físico**.  
O método mais simples e comum é usando o **WinBox**, que detecta automaticamente dispositivos Mikrotik na rede.

---

# 🧩 1. Acessando o Mikrotik

### ✔ Método recomendado: WinBox
1. Baixe o WinBox: https://mikrotik.com/download  
2. Abra o WinBox  
3. Vá em **Neighbors**  
4. O Mikrotik aparecerá mesmo sem IP configurado  
5. Clique e conecte usando:
   - **Usuário:** `admin`
   - **Senha:** *(em branco no primeiro acesso)*

---

# ⚠ Primeira coisa a fazer: Reset com configuração limpa (opcional)
Quando o Mikrotik vem com configuração padrão, ele ativa DHCP, NAT e firewall automaticamente.

Para começar *do zero*:

1. Acesse **System > Reset Configuration**
2. Marque **No Default Configuration**
3. Clique **Reset**

---

# 🌐 2. Configurar IP na porta LAN

Para acessar o Mikrotik diretamente:

1. Vá em **IP > Addresses**
2. Clique em **"+"**
3. Coloque um IP de gerenciamento:

Exemplo:


---

# 📡 3. Configurar DHCP Server

### Passo 1 — Crie um pool de IPs  
**IP > Pools > "+"**



### Passo 2 — Crie o DHCP  
**IP > DHCP Server > DHCP Setup**

Selecione a interface LAN (ex: `ether2`)

O Mikrotik vai perguntar em sequência:
- Gateway → `192.168.1.1`
- Range → usa o pool
- DNS → pode usar Google (8.8.8.8) ou próprio Mikrotik
- Lease Time → padrão 10 minutos

---

# 🌍 4. Configurar Internet (WAN)

No Mikrotik, a porta WAN geralmente é **ether1**.

### Configurar IP (quando fixo)
