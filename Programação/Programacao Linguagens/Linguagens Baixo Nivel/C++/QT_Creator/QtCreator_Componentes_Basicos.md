# 🧩 Componentes Básicos do Qt Creator (Qt Widgets)

Este guia apresenta os **principais componentes visuais** disponíveis no **Qt Creator**, com equivalentes ao Java Swing (NetBeans) e exemplos práticos em C++.

---

## 🧱 1️⃣ Comparativo: NetBeans (Swing) × Qt Creator (Qt Widgets)

| Função / Componente | NetBeans (Swing) | Qt Creator (Qt Widgets) | Descrição |
|----------------------|------------------|--------------------------|------------|
| Campo de texto (1 linha) | `JTextField` | `QLineEdit` | Entrada de texto simples (nome, e-mail, etc). |
| Área de texto (multi-linha) | `JTextArea` | `QTextEdit` / `QPlainTextEdit` | Texto extenso; `QTextEdit` aceita HTML e formatação. |
| Rótulo (texto fixo) | `JLabel` | `QLabel` | Exibe texto, ícones e HTML simples. |
| Botão | `JButton` | `QPushButton` | Dispara ações ao clicar. |
| Caixa de seleção | `JCheckBox` | `QCheckBox` | Valor booleano (ligado/desligado). |
| Botão de opção | `JRadioButton` | `QRadioButton` | Escolha exclusiva dentro de um grupo. |
| Lista suspensa | `JComboBox` | `QComboBox` | Escolha de opções pré-definidas. |
| Lista de itens | `JList` | `QListWidget` | Exibe uma lista simples de itens. |
| Tabela | `JTable` | `QTableWidget` | Exibe dados tabulares; suporta edição. |
| Barra de progresso | `JProgressBar` | `QProgressBar` | Mostra progresso de uma tarefa. |
| Slider (controle deslizante) | `JSlider` | `QSlider` | Ajuste numérico visual (volume, brilho). |
| Container / painel | `JPanel` | `QWidget`, `QFrame`, `QGroupBox` | Agrupa outros widgets. |
| Janela principal | `JFrame` | `QMainWindow` | Estrutura principal da interface. |
| Caixa de mensagem | `JOptionPane` | `QMessageBox` | Exibe alertas, avisos e confirmações. |
| Layout | `GridLayout`, `GroupLayout`, etc. | `QVBoxLayout`, `QHBoxLayout`, `QGridLayout`, `QFormLayout` | Gerencia o posicionamento automático dos widgets. |

---

## ⚙️ 2️⃣ Exemplos Práticos

### 🧾 Campo de Texto — `QLineEdit`
```cpp
QLineEdit *campo = new QLineEdit(this);
campo->setPlaceholderText("Digite seu nome...");
```

| Widget            | Função                                   |
| :---------------- | :--------------------------------------- |
| `QTabWidget`      | Cria abas (tipo navegador).              |
| `QStackedWidget`  | Alterna entre páginas diferentes.        |
| `QToolBox`        | Painéis dobráveis.                       |
| `QCalendarWidget` | Calendário interativo.                   |
| `QLCDNumber`      | Mostra números em estilo LCD.            |
| `QDial`           | Controle circular (ex: volume).          |
| `QSplitter`       | Divide a tela em áreas redimensionáveis. |
| `QGraphicsView`   | Renderização 2D e cenas gráficas.        |


| Layout        | Descrição                       | Uso comum                   |
| :------------ | :------------------------------ | :-------------------------- |
| `QHBoxLayout` | Organiza widgets na horizontal. | Botões lado a lado.         |
| `QVBoxLayout` | Organiza widgets na vertical.   | Campos empilhados.          |
| `QGridLayout` | Grelha (linha x coluna).        | Formulários mais complexos. |
| `QFormLayout` | Duas colunas (rótulo + campo).  | Telas de cadastro.          |

