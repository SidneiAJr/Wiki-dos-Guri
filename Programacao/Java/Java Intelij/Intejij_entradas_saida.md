# 🧾 Tutorial de Entradas e Saídas no IntelliJ IDEA (Swing)

## 📖 Introdução
Em aplicações Java com Swing, os conceitos de **entrada** e **saída** representam a forma como o usuário **interage** com a interface.  
- **Entradas** são os dados fornecidos pelo usuário (como textos, seleções ou cliques).  
- **Saídas** são as informações exibidas pela aplicação (como mensagens, resultados ou alertas).  

No **IntelliJ IDEA**, essas interações podem ser criadas de forma visual, utilizando o **Swing UI Designer**, ou configuradas manualmente no código.

---

## 🧩 Componentes de Entrada

Os principais componentes de **entrada de dados** no Swing são:

### 🟦 JTextField
Usado para digitar textos simples, como nomes, números ou senhas.  
No IntelliJ IDEA, você pode arrastar o componente **Text Field** da paleta e configurar:
- O nome da variável (em *variable name*).  
- O tamanho do campo.  
- O texto inicial, se desejar.  

---

### 🟩 JPasswordField
Semelhante ao JTextField, mas oculta os caracteres digitados.  
Ideal para campos de senha.  
Pode ser inserido a partir da **Palette** em *Swing Controls → Password Field*.

---

### 🟨 JTextArea
Permite múltiplas linhas de texto, indicada para descrições ou observações.  
No painel de propriedades é possível definir:
- Quantidade de linhas e colunas.  
- Se o texto será editável.  
- Quebras automáticas de linha (*line wrap*).

---

### 🟧 JComboBox
Usado para criar **listas suspensas** de opções.  
O usuário escolhe um item entre várias alternativas pré-definidas.  
No IntelliJ, o conteúdo da lista pode ser configurado diretamente na propriedade **model**.

---

### 🟪 JCheckBox
Representa uma **caixa de seleção**.  
Pode estar marcada (true) ou desmarcada (false).  
É ideal para permitir que o usuário escolha **mais de uma opção** ao mesmo tempo.

---

### 🟫 JRadioButton
Permite criar **opções exclusivas**, onde o usuário escolhe apenas uma entre várias.  
No IntelliJ, basta agrupar os botões de rádio dentro de um **ButtonGroup**.

---

### ⬜ JButton
Embora seja um botão, ele também faz parte das “entradas”, pois é o **gatilho** de ações.  
Normalmente, os botões são usados para:
- Confirmar ou enviar informações.  
- Limpar campos.  
- Abrir janelas ou diálogos.  

---

### 🔵 JFileChooser (Entrada de Arquivos)
Usado para permitir que o usuário **escolha arquivos ou diretórios** do sistema.  
No modo visual, pode ser adicionado através da categoria **Swing Windows → File Chooser**.  

---

## 📤 Componentes de Saída

Os componentes de **saída de dados** são responsáveis por **mostrar informações** para o usuário.  
Eles podem exibir textos, resultados, ícones ou mensagens de confirmação.

---

### 🟩 JLabel
Exibe **mensagens ou descrições** fixas na tela.  
Também pode ser usado para mostrar resultados de cálculos, avisos ou feedbacks após ações do usuário.  

---

### 🟦 JTextArea (como saída)
Além de entrada, também é muito usada para **exibir logs, textos e relatórios**.  
Basta definir a propriedade **editable = false**, para evitar que o usuário modifique o conteúdo.

---

### 🟨 JOptionPane
Usado para **exibir mensagens rápidas**, confirmações e alertas.  
É uma das formas mais simples de mostrar saídas visuais no Swing.  
Pode ser utilizada para informar o sucesso de uma ação, avisar sobre erros ou pedir confirmação de decisões.

---

### 🟧 JTable
Permite exibir **tabelas de dados**, como listas, registros ou relatórios.  
Ideal para aplicações que mostram informações estruturadas (como cadastros ou resultados de consultas).

---

### 🟪 JList
Exibe uma lista de elementos.  
Pode ser usada tanto para mostrar informações quanto para permitir seleção simples ou múltipla.

---

### 🔵 JProgressBar
Mostra o **progresso de uma operação**, útil em processos que levam tempo, como carregamentos ou gravações de arquivo.

---

## 🧮 Fluxo de Entrada e Saída

O processo típico de uma aplicação Swing segue esta lógica:

1. O usuário **digita informações** (em campos de texto, caixas de seleção, etc.).  
2. Clica em um **botão** para enviar ou processar os dados.  
3. O programa **interpreta a entrada** e realiza as operações necessárias.  
4. O resultado é **exibido na interface**, por meio de labels, áreas de texto ou janelas de mensagem.  

Esse ciclo de entrada → processamento → saída é a base de qualquer sistema interativo.

---

## 🎨 Configurando Entradas e Saídas no IntelliJ IDEA

No **IntelliJ GUI Designer**, você pode configurar isso de forma visual:

1. Crie um **JFrame Form**.  
2. Arraste componentes da **Palette** para o formulário.  
3. Nomeie cada componente no campo **variable name**.  
4. Ajuste as propriedades, como texto, tamanho e alinhamento.  
5. Organize os componentes com **Layouts** (FlowLayout, GridLayout, etc.).  

Depois disso, basta definir o que cada botão ou ação deve fazer, conectando as entradas às saídas.

---

## ⚙️ Boas Práticas

- Use nomes claros e coerentes para os componentes (por exemplo: `campoNome`, `botaoSalvar`, `labelResultado`).  
- Deixe as áreas de saída bem visíveis e com destaque.  
- Utilize labels para identificar claramente cada campo de entrada.  
- Evite sobrecarregar a tela com muitos elementos.  
- Teste o comportamento da interface com diferentes tamanhos de janela.  
- Sempre valide as entradas antes de processá-las (ex: verificar se um campo não está vazio).

---

## 💡 Dicas Visuais no IntelliJ

- O painel **Inspector** mostra a hierarquia de componentes, facilitando a organização das entradas e saídas.  
- As **propriedades dinâmicas** permitem alterar cor, texto e fonte diretamente.  
- A opção **Preview Design** permite visualizar a aparência da janela antes de executar.  
- Você pode usar **GroupLayout** ou **BoxLayout** para manter o alinhamento limpo entre campos de entrada e labels.

---



