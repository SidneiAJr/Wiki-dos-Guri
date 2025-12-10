# 🪟 Tutorial — Personalizar Janelas no Java (Swing e JavaFX)

## 🎯 Objetivo
Aprender a **personalizar janelas** em aplicações Java, controlando:
- O **tamanho** da janela  
- A **centralização** na tela  
- O **redimensionamento (resize)**  
- E outros ajustes visuais úteis no Swing e JavaFX.

---

## ☕ 1️⃣ Personalizando Janelas no **Java Swing**

O Swing permite controlar facilmente o comportamento da janela principal (`JFrame`).

### 🧩 Exemplo Completo
```java
import javax.swing.*;

public class JanelaPersonalizadaSwing {
    public static void main(String[] args) {
        JFrame janela = new JFrame("Minha Janela Personalizada 🪟");

        // Define o tamanho fixo
        janela.setSize(500, 400);

        // Impede o redimensionamento da janela
        janela.setResizable(false);

        // Centraliza a janela na tela
        janela.setLocationRelativeTo(null);

        // Define o comportamento ao fechar
        janela.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Torna a janela visível
        janela.setVisible(true);
    }
}
