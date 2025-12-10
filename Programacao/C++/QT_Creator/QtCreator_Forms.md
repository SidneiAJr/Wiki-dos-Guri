# 🪟 Formulários (Forms) no Qt Creator — C++ / Qt Widgets

## 📖 Introdução

No **Qt Creator**, os **Forms** são a base da criação de interfaces gráficas (GUI) em C++.  
Eles representam **janelas visuais** — como as “Windows Forms” do C# ou os “Frames” do Java Swing.

Cada **Form** combina duas partes:
- O **layout visual**, definido no arquivo `.ui` (feito no editor gráfico).
- O **código de controle**, nos arquivos `.cpp` e `.h`, que definem a lógica do programa.

Essa separação permite criar aplicações elegantes e organizadas, misturando design visual com programação estruturada em C++.

---

## 🧱 Estrutura de um Form

Ao criar um novo formulário, o Qt gera automaticamente três arquivos principais:

| Arquivo | Função |
|----------|--------|
| `formulario.ui` | Layout visual da interface, criado no **Qt Designer**. |
| `formulario.h` | Cabeçalho da classe C++ (declara widgets e funções). |
| `formulario.cpp` | Implementação da lógica e eventos do formulário. |

Esses três arquivos trabalham juntos para formar uma janela funcional e interativa.

---

## 🪟 Tipos de Formulário no Qt Creator

O Qt fornece três tipos principais de formulários (Forms):

### 🟩 QMainWindow
- Janela principal da aplicação.  
- Suporta **menus**, **barras de ferramentas** e **status bar**.  
- Ideal para sistemas completos e interfaces com múltiplos painéis.  

**Exemplo de uso:**
- Sistema de cadastro.
- Editor de texto.
- Interface principal de aplicativo.

---

### 🟦 QDialog
- Janela **secundária** usada para tarefas específicas.  
- Pode ser **modal** (bloqueia a janela principal até ser fechada) ou **não modal** (permite interação simultânea).  
- Ideal para formulários de configuração, alertas ou confirmações.

**Exemplo de uso:**
- Caixa de login.
- Janela “Salvar como...”.
- Mensagens de aviso personalizadas.

---

### 🟨 QWidget
- Formulário básico e flexível, sem menus ou barras.  
- Pode ser usado como janela ou componente embutido.  
- Ideal para painéis simples, partes internas de janelas ou formulários customizados.

**Exemplo de uso:**
- Painel lateral.
- Tela de relatório.
- Componente de módulo.

---

## 🎨 Criando um Form no Qt Creator

### Etapa 1 — Criar o Form
1. No Qt Creator, vá até o menu:  
   **File → New File or Project → Qt → Qt Designer Form Class**
2. Escolha o tipo de formulário (Main Window, Dialog ou Widget).
3. Dê um nome à classe (ex: `MainWindow`).
4. O Qt criará automaticamente:


---

### Etapa 2 — Construir o Layout Visual
No **modo Design**, você pode:
- Arrastar componentes da paleta (botões, campos de texto, labels, etc.).
- Organizar os widgets usando **layouts automáticos** (vertical, horizontal, grid).
- Definir propriedades no **Inspector de Propriedades** (texto, cores, fontes, tamanhos).
- Nomear cada componente (`objectName`) para poder acessá-lo no código.

**Exemplo de nomes comuns:**
- `lineEditNome`
- `btnSalvar`
- `lblResultado`

---

### Etapa 3 — Ligar Interface ao Código (Sinais e Slots)
O Qt usa o mecanismo de **Sinais e Slots** para conectar **eventos** a **ações**.

- **Sinal**: algo que acontece (ex: clique de um botão).
- **Slot**: função que reage a esse evento.

**Forma automática:**
Se você nomear o slot no formato:
