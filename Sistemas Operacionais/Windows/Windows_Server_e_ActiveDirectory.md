# 🪟 Windows Server e Active Directory

O **Windows Server** é o sistema operacional da Microsoft voltado para servidores.  
Uma das suas principais funções é o **Active Directory (AD)** — um serviço que gerencia usuários, grupos, computadores e permissões em redes corporativas.

---

## 🧱 O que é o Active Directory?

O **Active Directory (AD)** é um **banco de dados centralizado** que armazena informações sobre:
- Usuários  
- Grupos  
- Computadores  
- Políticas de segurança  

Ele permite que **todos os dispositivos da rede** sejam autenticados e administrados de forma centralizada.

---

## ⚙️ Funções Principais do Active Directory

| Função | Descrição |
|--------|------------|
| **Domain Services (AD DS)** | Controla autenticação e políticas dentro do domínio. |
| **DNS** | Responsável por traduzir nomes de rede (ex: servidor.local → IP). |
| **Group Policy (GPO)** | Define regras e permissões aplicadas aos usuários e computadores. |
| **Active Directory Users and Computers (ADUC)** | Ferramenta para gerenciar usuários, grupos e máquinas. |

---

## 🧩 Estrutura do AD

O AD é dividido em **unidades lógicas**:

| Nível | Descrição |
|-------|------------|
| **Floresta (Forest)** | Conjunto de domínios que compartilham a mesma estrutura. |
| **Domínio (Domain)** | Conjunto principal de usuários e recursos (ex: empresa.local). |
| **OU (Organizational Unit)** | Subdivisão usada para organizar usuários e computadores. |

---

## 🧰 Instalando o Active Directory

1. **Instale o Windows Server (2022, 2019 ou 2016)**.  
2. No *Server Manager*, clique em:  
   - *Add Roles and Features* → *Active Directory Domain Services (AD DS)*.  
3. Após a instalação, promova o servidor a **Controlador de Domínio**.  
4. Crie o nome do domínio (ex: `empresa.local`).  
5. Reinicie o servidor.

---

## 👥 Criando Usuários e Grupos

Abra o **Active Directory Users and Computers (ADUC)**:
1. Vá até a OU desejada.  
2. Clique com o botão direito → *New → User*.  
3. Defina o nome, login e senha.  
4. Para grupos: *New → Group* → defina o nome e tipo (*Security / Distribution*).

---

## 🔐 Políticas de Grupo (GPO)

As **Group Policies (GPOs)** permitem aplicar regras a todos os usuários ou PCs do domínio.  
Exemplo: bloquear o Painel de Controle, definir papel de parede, scripts de login, etc.

Acesse via:
