# JavaScript | Comandos front end JavaScript:

## 1. **Função `esconder()`**
A função `esconder()` tem a tarefa de alternar entre esconder e mostrar um elemento na página. 
- Ela verifica se o estilo de exibição (`display`) do elemento com o `id="colorBox"` está configurado como `none` (escondido).
- Se o elemento estiver escondido, ele é mostrado (`display = block`).
- Se o elemento estiver visível, ele é escondido (`display = none`).

## 2. **Eventos de Mouse no `colorBox`**

### - **Evento `mouseover`**
- Este evento é acionado quando o mouse passa sobre o elemento com o `id="colorBox"`.
- Ao ser acionado, ele muda a cor de fundo do elemento para **azul**.

### - **Evento `mouseout`**
- Este evento é acionado quando o mouse sai do elemento com o `id="colorBox"`.
- Ao ser acionado, ele retorna a cor de fundo do elemento para **cinza**.

## 3. **Sincronização entre o `inputTexto` e `textoMostrar`**
- A função associada a este comportamento é um evento `keyup` no campo de input de texto.
- Toda vez que o usuário digitar algo, o conteúdo digitado é automaticamente copiado para o parágrafo com o `id="textoMostrar"`.
- O texto no parágrafo será atualizado em tempo real conforme o usuário digita no campo de input.

## 4. **Função `adicionar()` - Adicionar uma Tarefa à Lista**
- A função `adicionar()` permite adicionar uma tarefa à lista de tarefas.
- O valor digitado no campo de texto (com o `id="tarefa"`) é verificado.
  - Se o campo de texto não estiver vazio, o valor digitado é usado para criar um novo item (`<li>`) e este item é adicionado a uma lista (`<ul>` com o `id="listaTarefas"`).
  - Se o campo estiver vazio, um alerta é exibido, pedindo para digitar uma tarefa válida.
- Após adicionar a tarefa, o campo de texto é limpo.

## 5. **Função `mudartema()` - Alternar entre Modo Claro e Escuro**
- A função `mudartema()` é usada para alternar entre o modo claro e o modo escuro na página.
- Ela faz isso alterando as classes CSS do elemento `<body>`.
  - A função alterna entre as classes `claro` e `escuro`, aplicando o estilo correspondente a cada modo.
  - O modo claro define o fundo como branco e o texto como preto, enquanto o modo escuro define o fundo como preto e o texto como branco.
