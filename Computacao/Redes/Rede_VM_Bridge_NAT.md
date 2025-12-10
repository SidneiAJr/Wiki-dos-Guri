# 🌐 Tipos de Rede em Máquinas Virtuais (Bridge, NAT, Host-Only)

Máquinas virtuais podem se conectar à rede física de diferentes formas.  
No VirtualBox ou VMware, essas opções definem **como a VM se comunica** com a Internet e com o host.

---

## 🌉 Modo Bridge
- A VM se comporta como **um computador físico na rede**.  
- Recebe um IP da mesma rede que o host.  
- Pode ser acessada de outros dispositivos da rede.

**Vantagens:**
- Comunicação direta com outros PCs.  
- Ideal para testes de servidores, DHCP, SSH, etc.

**Desvantagens:**
- Depende da rede física.  
- Pode gerar conflitos de IP.

---

## 🛰️ Modo NAT (Network Address Translation)
- A VM usa a **conexão do host** pra acessar a Internet.  
- Fica **invisível** para outros dispositivos da rede.  
- O VirtualBox faz o “roteamento” dos pacotes.

**Vantagens:**
- Fácil de configurar.  
- Mais seguro (a VM não é acessível externamente).

**Desvantagens:**
- Não dá pra acessar a VM diretamente da rede.

---

## 🧱 Host-Only
- Cria uma rede **somente entre o host e a VM**.  
- Não tem acesso à Internet.  
- Usado pra laboratórios internos e testes locais.

---

## 💡 Resumo

| Tipo | Acesso à Internet | Visível na Rede | Ideal Para |
|:--|:--:|:--:|:--|
| **Bridge** | ✅ | ✅ | Servidores e testes reais |
| **NAT** | ✅ | ❌ | Uso comum e navegação |
| **Host-Only** | ❌ | ❌ (só host↔VM) | Testes internos |

---

## ⚙️ Dica
No VirtualBox:
> Configurações → Rede → Adaptador → Modo de Rede  
Escolha **Bridge**, **NAT** ou **Host-Only** conforme sua necessidade.
