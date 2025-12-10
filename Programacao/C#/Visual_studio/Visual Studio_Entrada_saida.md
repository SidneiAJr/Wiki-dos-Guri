# 🧾 Entradas e Saídas no C# (Windows Forms)

## 📖 Introdução

Em aplicações **C# com Windows Forms**, o conceito de **entradas e saídas** define como o **usuário interage** com o sistema.  
- As **entradas** são os dados que o usuário fornece (digitando, selecionando ou clicando).  
- As **saídas** são as respostas que o programa mostra (resultados, mensagens, textos, etc.).  

Essas operações são a base de qualquer interface gráfica interativa, permitindo que o sistema receba informações, processe e retorne algo visível ao usuário.

---

## 🚪 Entradas — Recebendo Dados do Usuário

As **entradas** são os meios pelos quais o usuário envia informações ao programa.  
No **Windows Forms**, isso é feito com **componentes de formulário**, como campos de texto, botões e seleções.

### 🟩 TextBox
Usado para digitar **textos, números ou palavras**.  
É o componente mais comum de entrada.

**Usos típicos:**
- Digitar nomes, valores, senhas, endereços, etc.  
- Inserir dados para cálculos ou cadastros.  

**Propriedades importantes:**
- `Text` → obtém ou define o conteúdo digitado.  
- `MaxLength` → define o número máximo de caracteres.  
- `Multiline` → permite mais de uma linha.  

---

### 🟦 MaskedTextBox
Semelhante ao TextBox, mas permite **máscaras de entrada**, garantindo que o usuário siga um formato específico.

**Usos comuns:**
- CPF, CNPJ, telefone, datas, CEP, horários.  

**Vantagem:**  
Controla o padrão de entrada e evita erros de digitação.

---

### 🟨 ComboBox
Cria uma **lista suspensa** com opções predefinidas.  
O usuário escolhe uma delas, e o valor selecionado é tratado como entrada.

**Usos comuns:**
- Selecionar cidade, estado, categoria ou tipo de operação.  

**Propriedades úteis:**
- `Items` → define os itens da lista.  
- `SelectedIndex` → indica o item selecionado.  
- `Text` → obtém o valor escolhido.  

---

### 🟧 CheckBox
Permite ao usuário **marcar ou desmarcar** uma opção.  
Pode ser usado isoladamente ou em grupo.

**Usos comuns:**
- Selecionar preferências, permissões, configurações.  

**Propriedade principal:**
- `Checked` → indica se o item está marcado (`true` ou `false`).

---

### 🟪 RadioButton
Permite **escolher apenas uma opção entre várias**.  
Geralmente é usado dentro de um **GroupBox**.

**Usos comuns:**
- Selecionar sexo, forma de pagamento, ou modo de operação.  

**Propriedade principal:**
- `Checked` → retorna `true` se o botão estiver selecionado.  

---

### 🟫 Button
O **botão** é o ponto de ação da interface.  
Ele **não recebe dados**, mas é a **entrada de evento** que aciona o processamento.  

**Usos comuns:**
- Confirmar informações.  
- Calcular resultados.  
- Salvar ou limpar dados.  

**Evento principal:**
- `Click` → executa uma ação quando pressionado.  

---

### 🟦 OpenFileDialog / FolderBrowserDialog
Permitem **selecionar arquivos ou pastas** no sistema operacional.

**Usos comuns:**
- Importar documentos, imagens, planilhas.  
- Escolher diretórios de destino.  

---

## 💡 Boas Práticas de Entrada

- Sempre **valide** o que o usuário digita antes de processar.  
- Use **máscaras** quando o formato for fixo (como CPF).  
- Evite depender de dados “crus” — converta e trate o valor antes de usar.  
- Utilize mensagens claras quando o usuário inserir algo incorreto.  
- Use **TryParse()** para conversões numéricas seguras (sem erros).  

---

## 💻 Saídas — Mostrando Resultados ao Usuário

As **saídas** são as respostas visuais que o sistema apresenta.  
Elas podem ser textos, números, imagens ou mensagens.

### 🟩 Label
Componente básico para **exibir textos** fixos ou resultados processados.  
É o principal meio de mostrar saídas na tela.

**Usos comuns:**
- Mostrar mensagens, resultados ou títulos.  

**Propriedades:**
- `Text` → conteúdo exibido.  
- `ForeColor` → cor do texto.  
- `Font` → tipo e tamanho da fonte.  

---

### 🟦 MessageBox
Exibe **caixas de diálogo** com mensagens, avisos ou confirmações.  
É uma saída direta e simples.

**Usos comuns:**
- Mostrar erros, avisos ou resultados de operações.  
- Confirmar exclusões, salvamentos, etc.  

**Tipos comuns de janelas:**
- Informação (`Information`)  
- Erro (`Error`)  
- Alerta (`Warning`)  
- Confirmação (`Question`)  

---

### 🟨 TextBox (ReadOnly)
Um **TextBox configurado como somente leitura** também pode servir como área de saída.  

**Usos comuns:**
- Mostrar logs, resultados longos ou relatórios.  

**Propriedade:**
- `ReadOnly = true` → impede que o usuário edite o conteúdo.  

---

### 🟧 RichTextBox
Permite **formatar o texto** de saída (negrito, cor, tamanho).  
Ideal para exibir relatórios ou textos grandes com destaque.  

---

### 🟪 ListBox
Exibe **listas de resultados** — útil para mostrar múltiplas saídas.  

**Usos comuns:**
- Mostrar registros processados, histórico ou listas de dados.  

---

### 🟫 DataGridView
Apresenta **dados em formato de tabela**.  
É a principal saída para exibir consultas de banco de dados, relatórios e cadastros.

**Usos comuns:**
- Mostrar listas de clientes, produtos, pedidos, etc.  

---

### 🟦 PictureBox
Mostra **imagens** na tela.  
Usado para saídas gráficas, fotos ou logotipos.

**Propriedades:**
- `Image` → define a imagem exibida.  
- `SizeMode` → ajusta a exibição (Zoom, Stretch, Center).  

---

### 🟨 ProgressBar
Indica **progresso de uma tarefa**.  
Útil para informar que algo está sendo processado.

**Propriedades:**
- `Value` → nível atual de progresso.  
- `Maximum` → valor máximo.  
- `Minimum` → valor inicial.  

---

## 🔄 Ciclo de Entrada e Saída

1. O usuário fornece dados (entrada).  
2. O sistema processa as informações internamente.  
3. O resultado é exibido na tela (saída).  

Exemplo de fluxo visual:

- O usuário digita algo → clica no botão → o resultado aparece no label.

---

## ⚙️ Boas Práticas de Saída

- Dê **feedback imediato** após ações (mensagens, labels, progresso).  
- Use **cores e ícones** para diferenciar erros e sucessos.  
- Evite poluição visual: mostre apenas informações úteis.  
- Centralize as mensagens mais importantes.  
- Prefira **MessageBox** para alertas e confirmações.  

---

## 🧠 Integração com Conversões

Muitas vezes, entradas e saídas envolvem **conversão de tipos**, especialmente quando o usuário digita texto que precisa virar número.  

**Ciclo comum:**
1. Entrada (TextBox → texto).  
2. Conversão (`ToInt32`, `TryParse`, `ToDouble`).  
3. Processamento lógico.  
4. Saída (Label, MessageBox, RichTextBox).  

---



