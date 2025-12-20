# 🧩 Visual Studio | Componentes de Interface (C#)

Este documento descreve os principais **componentes visuais** usados no Visual Studio para aplicações **Desktop em C#**, principalmente em **WinForms** e **WPF**.

A ideia é a mesma do NetBeans:  
👉 cada componente tem uma função clara na interface.

---

## 🪟 Form / Window

### O que é:
É a **janela principal** da aplicação.

### Função:
- Serve como contêiner dos outros componentes
- Representa a tela do programa

### Equivalente no NetBeans:
`JFrame`

---

## 🔘 Button

### O que é:
Um botão clicável.

### Função:
- Executar ações
- Disparar eventos ao clicar

### Exemplos de uso:
- Salvar
- Enviar
- Confirmar
- Cancelar

### Equivalente no NetBeans:
`JButton`

---

## 📝 TextBox

### O que é:
Campo de texto para entrada de dados.

### Função:
- Receber texto digitado pelo usuário
- Pode ser simples ou multilinha

### Exemplos de uso:
- Nome
- Email
- Senha
- Comentários

### Equivalente no NetBeans:
`JTextField` / `JTextArea`

---

## 🔐 PasswordBox (WPF) / TextBox com senha (WinForms)

### O que é:
Campo para senhas.

### Função:
- Ocultar caracteres digitados
- Garantir privacidade

### Equivalente no NetBeans:
`JPasswordField`

---

## 🏷️ Label

### O que é:
Texto fixo exibido na tela.

### Função:
- Identificar campos
- Mostrar mensagens estáticas

### Exemplos:
- "Nome:"
- "Senha:"
- "Resultado:"

### Equivalente no NetBeans:
`JLabel`

---

## ☑️ CheckBox

### O que é:
Campo de seleção múltipla.

### Função:
- Marcar ou desmarcar opções
- Pode ter várias selecionadas ao mesmo tempo

### Exemplos:
- Aceitar termos
- Ativar opção

### Equivalente no NetBeans:
`JCheckBox`

---

## 🔘 RadioButton

### O que é:
Botão de seleção exclusiva.

### Função:
- Permitir escolher **apenas uma opção** entre várias

### Exemplos:
- Sexo
- Tipo de pagamento

### Equivalente no NetBeans:
`JRadioButton`

---

## 📋 ComboBox

### O que é:
Lista suspensa de opções.

### Função:
- Selecionar um item de uma lista
- Economiza espaço na tela

### Exemplos:
- Estados
- Cidades
- Categorias

### Equivalente no NetBeans:
`JComboBox`

---

## 📜 ListBox

### O que é:
Lista visível de itens.

### Função:
- Exibir várias opções
- Pode permitir múltipla seleção

### Equivalente no NetBeans:
`JList`

---

## 📊 DataGridView (WinForms) / DataGrid (WPF)

### O que é:
Tabela de dados.

### Função:
- Mostrar dados tabulares
- Ideal para listas vindas do banco

### Exemplos:
- Usuários
- Produtos
- Relatórios

### Equivalente no NetBeans:
`JTable`

---

## 🧭 MenuStrip

### O que é:
Menu superior da aplicação.

### Função:
- Organizar ações em menus
- Criar menus como "Arquivo", "Editar", "Ajuda"

### Equivalente no NetBeans:
`JMenuBar`

---

## 🧰 ToolStrip

### O que é:
Barra de ferramentas com ícones.

### Função:
- Acesso rápido a ações comuns
- Botões visuais com ícones

### Equivalente no NetBeans:
`JToolBar`

---

## 🖼️ PictureBox (WinForms) / Image (WPF)

### O que é:
Exibe imagens.

### Função:
- Mostrar logos
- Ícones
- Fotos

### Equivalente no NetBeans:
`ImageIcon`

---

## ⏱️ ProgressBar

### O que é:
Barra de progresso.

### Função:
- Indicar carregamento
- Mostrar progresso de tarefas longas

### Equivalente no NetBeans:
`JProgressBar`

---

## 📦 Panel

### O que é:
Contêiner de componentes.

### Função:
- Organizar layout
- Agrupar componentes relacionados

### Equivalente no NetBeans:
`JPanel`

---

## 🧱 GroupBox

### O que é:
Agrupador com título.

### Função:
- Organizar campos relacionados
- Melhorar visual e semântica

### Equivalente no NetBeans:
`JPanel` com borda/título

---

## 🧠 Resumo rápido

| Componente | Função |
|-----------|-------|
| Form / Window | Janela principal |
| Button | Executar ações |
| TextBox | Entrada de texto |
| Label | Texto fixo |
| CheckBox | Seleção múltipla |
| RadioButton | Seleção única |
| ComboBox | Lista suspensa |
| ListBox | Lista visível |
| DataGrid | Tabela |
| MenuStrip | Menu superior |
| ToolStrip | Barra de ferramentas |
| PictureBox | Imagem |
| ProgressBar | Progresso |
| Panel | Organização |
| GroupBox | Agrupamento |

---

📌 **Observação final**  
Esses componentes existem tanto em **WinForms** quanto em **WPF**, mas no WPF eles são mais poderosos e geralmente usados junto com **MVVM**.
