# 🔘 Tutorial de Uso do JButton no NetBeans

## 🪟 Passo 1: Abrir o NetBeans
Abra o **NetBeans IDE** no seu computador.

## 🧱 Passo 2: Criar um novo JFrame
1. Vá em **File → New Project**.  
2. Escolha **Java → Java Application** e clique em **Next**.  
3. Dê um nome ao projeto e finalize.  
4. Dentro do projeto, clique com o botão direito em **Source Packages → New → JFrame Form**.  
5. Dê um nome para o formulário e clique em **Finish**.

## 🖲️ Passo 3: Inserir o JButton
1. Abra o formulário (`.java` com design).  
2. Na aba **Palette**, procure por **Button** (ou `JButton`).  
3. Arraste o componente para dentro do JFrame.

## ⚙️ Passo 4: Configurar Propriedades
1. Clique no **JButton**.  
2. Vá até a aba **Properties**.  
3. Altere:
   - **text:** texto do botão (ex: `Clique Aqui`)  
   - **font:** fonte e tamanho  
   - **foreground / background:** cores  
   - **toolTipText:** dica ao passar o mouse  

## 💡 Passo 5: Criar Ação do Botão
1. Dê **duplo clique** no botão no modo Design.  
2. O NetBeans criará automaticamente um método de evento, por exemplo:
```java
private void btnCliqueAquiActionPerformed(java.awt.event.ActionEvent evt) {
    System.out.println("Botão clicado!");
}
