# 🏷️ Tutorial de Uso do JLabel no NetBeans

## 🪟 Passo 1: Abrir o NetBeans
Abra o **NetBeans IDE** no seu computador.

## 🧱 Passo 2: Criar um novo JFrame
1. Vá em **File → New Project**.  
2. Escolha **Java → Java Application** e clique em **Next**.  
3. Dê um nome ao projeto e finalize.  
4. Dentro do projeto, clique com o botão direito em **Source Packages → New → JFrame Form**.  
5. Dê um nome para o formulário e clique em **Finish**.

## 🖼️ Passo 3: Inserir o JLabel
1. Abra o formulário (`.java` com design).  
2. Na aba **Palette**, procure por **Label** (ou `JLabel`).  
3. Arraste o componente para dentro do seu JFrame.

## ⚙️ Passo 4: Configurar Propriedades
1. Clique no **JLabel**.  
2. Vá até a aba **Properties** (geralmente no canto direito).  
3. Aqui você pode alterar:
   - **text:** texto exibido no JLabel (ex: `Olá, Mundo!`)  
   - **font:** tipo e tamanho da fonte  
   - **foreground / background:** cores do texto e fundo  
   - **horizontalAlignment:** alinhamento (esquerda, centro, direita)  
   - **icon:** permite adicionar uma imagem ao JLabel  
   - **toolTipText:** dica que aparece ao passar o mouse  

## 🧩 Passo 5: Alterar o Texto via Código
Você também pode mudar o texto do JLabel pelo código:
```java
lblMensagem.setText("Bem-vindo ao sistema!");
