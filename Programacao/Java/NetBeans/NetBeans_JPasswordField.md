# 🔒 Tutorial de Uso do JPasswordField no NetBeans

## 🪟 Passo 1: Abrir o NetBeans
Abra o **NetBeans IDE**.

## 🧱 Passo 2: Criar o JFrame
Siga o mesmo processo de criação dos tutoriais anteriores.

## 🔑 Passo 3: Inserir o JPasswordField
1. Na aba **Palette**, escolha **Password Field** (`JPasswordField`).  
2. Arraste para o JFrame.

## ⚙️ Passo 4: Configurar Propriedades
1. Altere:
   - **name:** `txtSenha`  
   - **echoChar:** símbolo que oculta a senha (ex: `*`)  

## 💡 Passo 5: Obter o Valor Digitado
```java
char[] senha = txtSenha.getPassword();
String senhaTexto = new String(senha);
System.out.println("Senha digitada: " + senhaTexto);
