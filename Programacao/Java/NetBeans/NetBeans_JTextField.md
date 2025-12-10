# 📝 Tutorial de Uso do JTextField no NetBeans

## 🪟 Passo 1: Abrir o NetBeans
Abra o **NetBeans IDE** no seu computador.

## 🧱 Passo 2: Criar um novo JFrame
1. Vá em **File → New Project**.  
2. Escolha **Java → Java Application** e clique em **Next**.  
3. Crie o JFrame como nos tutoriais anteriores.

## 🔤 Passo 3: Inserir o JTextField
1. Vá até a aba **Palette**.  
2. Encontre **Text Field** (`JTextField`).  
3. Arraste-o para dentro do JFrame.

## ⚙️ Passo 4: Configurar Propriedades
1. Clique no campo de texto.  
2. Vá até **Properties** e altere:
   - **name:** `txtNome`  
   - **text:** valor inicial (ex: vazio)  
   - **font / colors:** estilo do texto  

## 💡 Passo 5: Obter o Texto Digitado
Para pegar o que o usuário digitou:
```java
String nome = txtNome.getText();
System.out.println("Nome digitado: " + nome);
