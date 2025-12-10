# 🍽️ Tutorial – Menus no NetBeans Swing

## 🎯 Objetivo
Aprender a criar **menus interativos no Java Swing** usando o **NetBeans**, com `JMenuBar`, `JMenu`, `JMenuItem` e `JCheckBoxMenuItem`.  
O menu é um dos componentes mais usados em interfaces desktop — ele organiza ações e opções de forma profissional.

---

## 🧰 Pré-requisitos
- NetBeans IDE (8.2 ou superior)
- JDK 8+ instalado
- Conhecimento básico de JFrame e eventos Swing

---

## 🪟 1. Criando o Projeto

1. Abra o **NetBeans**
2. Vá em **File → New Project → Java with Ant → Java Application**
3. Nomeie como `SwingMenuDemo`
4. Desmarque “Create Main Class”
5. Clique em **Finish**

---

## ⚙️ 2. Criando o JFrame

1. Clique com o botão direito no projeto → **New → JFrame Form**
2. Nomeie como `MenuPrincipal`
3. Clique em **Finish**

Isso abrirá o **GUI Builder**, onde você pode adicionar componentes graficamente.

---

## 🧩 3. Adicionando a Barra de Menu

### Opção 1 – Usando o GUI Builder

1. No painel **Palette**, arraste um **Menu Bar** (`JMenuBar`) para o topo do JFrame.  
2. Automaticamente aparecerá um menu padrão “File”.  
3. Clique no menu e altere o nome (por exemplo, “Arquivo”).  
4. Clique com o botão direito → **Add From Palette → Menu Item** e adicione os itens desejados:
   - “Novo”
   - “Abrir”
   - “Salvar”
   - “Sair”

### Opção 2 – Criando pelo Código

Se quiser fazer manualmente:

```java
import javax.swing.*;

public class MenuPrincipal extends JFrame {
    public MenuPrincipal() {
        setTitle("Exemplo de Menu Swing");
        setSize(400, 300);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setLocationRelativeTo(null);

        // Criação da barra de menu
        JMenuBar barraMenu = new JMenuBar();

        // Menu Arquivo
        JMenu menuArquivo = new JMenu("Arquivo");
        JMenuItem itemNovo = new JMenuItem("Novo");
        JMenuItem itemAbrir = new JMenuItem("Abrir");
        JMenuItem itemSalvar = new JMenuItem("Salvar");
        JMenuItem itemSair = new JMenuItem("Sair");

        // Adiciona itens ao menu
        menuArquivo.add(itemNovo);
        menuArquivo.add(itemAbrir);
        menuArquivo.add(itemSalvar);
        menuArquivo.addSeparator(); // linha divisória
        menuArquivo.add(itemSair);

        // Adiciona o menu à barra
        barraMenu.add(menuArquivo);

        // Define a barra no JFrame
        setJMenuBar(barraMenu);

        // Evento para o item "Sair"
        itemSair.addActionListener(e -> System.exit(0));
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(() -> new MenuPrincipal().setVisible(true));
    }
}
```
| Tipo            | Classe                          | Descrição                     |
| --------------- | ------------------------------- | ----------------------------- |
| Item comum      | `JMenuItem`                     | Executa uma ação simples      |
| Item de seleção | `JCheckBoxMenuItem`             | Pode ser marcado/desmarcado   |
| Item de opção   | `JRadioButtonMenuItem`          | Pertence a um grupo de opções |
| Submenu         | `JMenu` dentro de outro `JMenu` | Cria menus hierárquicos       |
