# 📋 Tutorial de Uso do JTextArea no NetBeans

## 🪟 Passo 1: Abrir o NetBeans
Abra o **NetBeans IDE**.

## 🧱 Passo 2: Criar o JFrame
Crie o JFrame normalmente.

## 🗒️ Passo 3: Inserir o JTextArea
1. Na aba **Palette**, escolha **Text Area** (`JTextArea`).  
2. Arraste para o JFrame.  
3. Para barras de rolagem, adicione um **JScrollPane** e coloque o JTextArea dentro dele.

## ⚙️ Passo 4: Configurar Propriedades
1. **name:** `txtMensagem`  
2. **rows / columns:** tamanho do campo  
3. **lineWrap:** marque `true` para quebrar linha automaticamente  

## 💡 Passo 5: Obter o Texto
```java
String texto = txtMensagem.getText();
System.out.println("Texto digitado:\n" + texto);
