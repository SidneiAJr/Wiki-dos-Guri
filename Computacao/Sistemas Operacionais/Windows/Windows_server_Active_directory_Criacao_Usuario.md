# 👤 Tutorial: Criando um Usuário no Active Directory

O **Active Directory (AD)** permite criar e gerenciar contas de usuários para acesso à rede, sistemas e arquivos compartilhados.

---

## 🧭 Passo a Passo

### 1. Acessar o Active Directory
1. Abra o **Server Manager**.  
2. Vá em:  
   **Tools → Active Directory Users and Computers (ADUC)**  
3. O ícone é um **livro amarelo** 📒 (representa o console do AD).

---

### 2. Escolher a Unidade Organizacional (OU)
- No painel à esquerda, selecione a **OU (Organizational Unit)** onde o usuário será criado.  
  > Exemplo: `Empresa.local → Usuarios → Administrativo`

---

### 3. Criar o Novo Usuário
1. Clique com o botão direito na OU → **New → User**  
2. Preencha as informações:
   - **First name:** Nome  
   - **Last name:** Sobrenome  
   - **User logon name (UPN):** login do usuário (ex: joao.silva)

3. Clique em **Next**.

---

### 4. Definir Senha e Políticas
1. Crie uma senha temporária ou definitiva.  
2. Marque as opções desejadas:
   - ✅ **User must change password at next logon** (recomendado)  
   - ❌ **User cannot change password** (opcional)  
   - ❌ **Password never expires** (evite em produção)

---

### 5. Adicionar o Usuário a um Grupo
Após criar:
1. Clique com o botão direito no novo usuário → **Properties**.  
2. Vá até a aba **Member Of** → **Add...**  
3. Selecione o grupo apropriado (ex: *Administrativo*, *TI*, *Financeiro*).  

> Grupos definem **permissões e acessos** na rede (pastas, impressoras, políticas, etc).

---

### 6. Definir Permissões em Pastas Compartilhadas
1. No servidor de arquivos, vá até a pasta compartilhada.  
2. Clique com o botão direito → **Propriedades → Segurança**.  
3. Adicione o **usuário ou grupo** criado.  
4. Configure as permissões necessárias:
   - **Leitura (Read)**
   - **Gravação (Write)**
   - **Controle total (Full Control)**  

---

### 🧠 Dica: Automatização com PowerShell
Você também pode criar usuários por script:
```powershell
New-ADUser -Name "João Silva" -GivenName "João" -Surname "Silva" -SamAccountName "joao.silva" -UserPrincipalName "joao.silva@empresa.local" -Path "OU=Usuarios,DC=empresa,DC=local" -AccountPassword (ConvertTo-SecureString "Senha123@" -AsPlainText -Force) -Enabled $true
