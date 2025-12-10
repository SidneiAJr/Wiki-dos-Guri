# 🧾 Entradas e Saídas no Qt Creator (C++ / Qt Widgets)

## 📖 Introdução

Em aplicações gráficas feitas no **Qt Creator (C++)**, as **entradas e saídas** são fundamentais para a interação entre o usuário e o sistema.  
- **Entradas**: são os dados que o usuário fornece (digitando, selecionando, clicando).  
- **Saídas**: são as informações que o programa exibe (resultados, mensagens, imagens, etc.).  

O Qt fornece uma ampla variedade de **widgets** (componentes de interface) que tornam essa comunicação simples e poderosa.

---

## 🚪 Entradas — Recebendo Dados do Usuário

Os componentes de **entrada** são usados para capturar informações que o usuário fornece à aplicação.

### 🟩 QLineEdit
É o campo de texto padrão para digitação.  
Usado para inserir **nomes, números, endereços ou valores**.

**Características:**
- Permite texto de uma linha.  
- Possui validações e máscaras integradas.  
- Pode ter texto de placeholder (dica ao usuário).  

**Propriedades úteis:**
- `setText()` → define o texto.  
- `text()` → obtém o texto digitado.  
- `setPlaceholderText()` → mostra uma dica antes da digitação.  

---

### 🟦 QTextEdit
Permite inserir **várias linhas de texto**, ideal para descrições longas ou campos de observação.

**Usos comuns:**
- Mensagens, relatórios, comentários.  
- Texto formatado (HTML simples).  

**Propriedades:**
- `toPlainText()` → obtém o texto puro.  
- `setPlainText()` → define o conteúdo.  
- `setReadOnly(true)` → transforma em saída somente leitura.  

---

### 🟨 QSpinBox / QDoubleSpinBox
Campos numéricos que permitem **incrementar ou decrementar valores** com botões laterais.  

**Usos comuns:**
- Selecionar quantidades, idade, preços, porcentagens.  

**Propriedades:**
- `value()` → obtém o valor atual.  
- `setValue()` → define o valor.  
- `setRange(min, max)` → limita o intervalo.  

---

### 🟧 QComboBox
Permite **selecionar opções de uma lista suspensa**.

**Usos comuns:**
- Escolha de categorias, cidades, modos de operação.  

**Propriedades:**
- `addItem()` → adiciona item.  
- `currentText()` → obtém o item selecionado.  
- `setCurrentIndex()` → muda o item ativo.  

---

### 🟪 QCheckBox
Caixa de marcação simples (ligado/desligado).  
Ideal para configurações booleanas.

**Propriedades:**
- `isChecked()` → retorna se está marcado.  
- `setChecked(true)` → marca automaticamente.  

---

### 🟫 QRadioButton
Permite **selecionar apenas uma opção** entre várias disponíveis.  
Usado em grupos (por exemplo, gênero ou modo de operação).

**Propriedade:**
- `isChecked()` → verifica se o botão está ativo.  

---

### 🟦 QPushButton
O **botão de ação** da interface.  
Ele **não é uma entrada de dado**, mas **dispara eventos** que processam as informações de entrada.

**Evento principal:**
- `clicked()` → executa uma função quando pressionado.  

---

### 🟨 QFileDialog
Permite ao usuário **abrir ou salvar arquivos**.

**Usos comuns:**
- Escolher imagens, documentos, planilhas.  

**Métodos:**
- `getOpenFileName()` → abre seletor de arquivo.  
- `getSaveFileName()` → salva arquivo.  

---

## 💡 Boas Práticas de Entrada

- Use **placeholders** e **tooltips** para orientar o usuário.  
- Valide dados antes de processar (ex: se o campo está vazio).  
- Converta os tipos de dados com cuidado (`toInt()`, `toDouble()`).  
- Agrupe opções relacionadas em **QGroupBox**.  
- Evite depender de dados sem validação.  

---

## 💻 Saídas — Exibindo Resultados ao Usuário

As **saídas** são os meios pelos quais o programa apresenta informações ao usuário.

### 🟩 QLabel
Componente básico de exibição de texto.  
É a forma mais comum de mostrar resultados.

**Propriedades:**
- `setText()` → define o texto mostrado.  
- `text()` → lê o conteúdo atual.  
- `setStyleSheet()` → permite alterar cor, tamanho e estilo.  

---

### 🟦 QTextBrowser
Semelhante ao `QTextEdit`, mas ideal para **exibir texto formatado ou HTML**.  

**Usos comuns:**
- Mostrar relatórios, logs ou textos formatados.  

---

### 🟨 QMessageBox
Cria **janelas de diálogo** para mensagens, alertas e confirmações.  
É a forma mais direta de apresentar informações rápidas.

**Tipos principais:**
- `information()` → mensagem informativa.  
- `warning()` → alerta de atenção.  
- `critical()` → erro.  
- `question()` → confirmação (Sim/Não).  

---

### 🟧 QProgressBar
Mostra **progresso de tarefas** (ex: carregamento, download, cálculo).  

**Propriedades:**
- `setValue()` → define o progresso atual.  
- `setRange(min, max)` → define os limites.  

---

### 🟪 QListWidget / QTableWidget
Permitem exibir **listas** ou **tabelas de dados** na tela.  
São ideais para mostrar múltiplos resultados, registros ou relatórios.  

**Propriedades:**
- `addItem()` → adiciona item na lista.  
- `setItem()` → insere valor em uma célula da tabela.  

---

### 🟫 QPixmap / QLabel
Permite exibir **imagens**.  
Combinando `QLabel` com `QPixmap`, é possível mostrar fotos, gráficos e ícones.

**Exemplo de uso típico:**
- `label->setPixmap(QPixmap(":/images/logo.png"));`

---

## 🔄 Ciclo de Entrada e Saída

1. Usuário fornece dados nos campos (entrada).  
2. O sistema processa a informação (lógica no código C++).  
3. O resultado é exibido em um widget (saída).  

**Exemplo de fluxo visual:**
- O usuário digita → clica no botão → o texto aparece no label.

---

## ⚙️ Boas Práticas de Saída

- Use **QMessageBox** para erros e confirmações.  
- Mantenha **LabeIs claros e curtos**.  
- Destaque resultados importantes com **cores ou negrito**.  
- Atualize dinamicamente os widgets para manter o usuário informado.  
- Evite poluir a interface com muitas mensagens.  

---

## 🧠 Integração com Conversões

Muitos dados de entrada vêm em formato **string**, mas o programa pode precisar de **valores numéricos** para cálculos.  
O Qt facilita essa conversão com métodos diretos:

| Conversão | Método | Retorno |
|------------|--------|----------|
| Texto → Inteiro | `text().toInt()` | `int` |
| Texto → Double | `text().toDouble()` | `double` |
| Número → Texto | `QString::number(valor)` | `QString` |

Essas funções são essenciais para o ciclo **entrada → processamento → saída**.

---



