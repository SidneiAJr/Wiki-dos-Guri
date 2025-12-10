# 📚 Tutorial Detalhado — Swing Windows & Swing Fillers (para NetBeans)

**Arquivo sugerido:** `NetBeans_Swing_Windows_and_Fillers.md`  
**Objetivo:** explicar, com exemplos em código e instruções do NetBeans GUI Builder, como usar os componentes das seções *Swing Windows* e *Swing Fillers*.

---

## Sumário
- Swing Windows
  - Frame (`JFrame`)
  - Dialog (`JDialog`)
  - Option Pane (`JOptionPane`)
  - File Chooser (`JFileChooser`)
  - Color Chooser (`JColorChooser`)
- Swing Fillers (Box utilities)
  - Glue
  - Rigid Area
  - Horizontal/Vertical Strut
  - Exemplos com `Box` e `BoxLayout`
- Boas práticas e estrutura de projeto
- Exemplo completo (código)

---

# 🪟 Swing Windows

> Os componentes nessa seção servem para criar e exibir janelas, diálogos e seletores comuns em aplicações desktop.

---

## `JFrame` — Janela principal (Frame)

### Descrição
`JFrame` é a janela principal da aplicação — contém menu, barras, painéis e é normalmente a *entry point* da GUI.

### Usando no NetBeans (GUI Builder)
1. `File → New File → Swing GUI Forms → JFrame Form`
2. Nomeie (ex: `MainFrame`) — NetBeans cria `initComponents()` com o layout do form.
3. No inspetor, defina `defaultCloseOperation`, `resizable`, `size` e `location`.

### Exemplo (programático)
```java
import javax.swing.*;

public class MainFrame extends JFrame {
    public MainFrame() {
        setTitle("Aplicação - MainFrame");
        setSize(600, 400);
        setLocationRelativeTo(null); // centraliza
        setDefaultCloseOperation(EXIT_ON_CLOSE);

        // Conteúdo
        add(new JLabel("Janela Principal", SwingConstants.CENTER));
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(() -> new MainFrame().setVisible(true));
    }
}
