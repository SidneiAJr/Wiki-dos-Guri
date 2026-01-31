# JavaScript | Mexendo no front end:

```js
// Função para esconder ou mostrar um elemento
function esconder() {
    // Seleciona o elemento com o id 'colorBox' (presumivelmente uma <div> ou algo similar)
    let documento = document.getElementById("colorBox");

    // Verifica se o elemento está oculto (display 'none')
    if (documento.style.display === "none") {
        // Se estiver oculto, torna o elemento visível (display 'block')
        documento.style.display = "block"; // Mostrar
    } else {
        // Se estiver visível, oculta o elemento (display 'none')
        documento.style.display = "none"; // Esconder
    }
}

// Seleciona a <div> com id 'colorBox' para fazer alterações nela mais tarde
let colorBox = document.getElementById("colorBox");

// Adiciona um evento 'mouseover' à 'colorBox' para mudar a cor do fundo quando o mouse passar por cima
colorBox.addEventListener("mouseover", function() {
    // Muda a cor de fundo para azul quando o mouse passa sobre a 'colorBox'
    colorBox.style.backgroundColor = "blue";
});

// Adiciona um evento 'mouseout' à 'colorBox' para voltar para a cor cinza quando o mouse sai de cima
colorBox.addEventListener("mouseout", function() {
    // Muda a cor de fundo de volta para cinza quando o mouse sai da 'colorBox'
    colorBox.style.backgroundColor = "gray";
});

// Seleciona o campo de input com id 'inputTexto' e o parágrafo com id 'textoMostrar' para manipulação posterior
let inputTexto = document.getElementById('inputTexto');
let textoMostrar = document.getElementById('textoMostrar');

// Adiciona um evento 'keyup' no input, ou seja, toda vez que o usuário digitar algo
inputTexto.addEventListener('keyup', function() {
    // Atualiza o conteúdo do parágrafo 'textoMostrar' com o texto digitado no campo de input
    textoMostrar.textContent = inputTexto.value;
});

// Função para adicionar tarefas à lista
function adicionar() {
    // Pega o valor digitado no campo de texto com id 'tarefa'
    var tarefa = document.getElementById('tarefa').value;

    // Verifica se o campo não está vazio (se a tarefa não é apenas espaços em branco)
    if (tarefa.trim() !== '') {
        // Cria um novo item de lista (<li>) para a tarefa
        let li = document.createElement('li');
        // Atribui o texto da tarefa ao item da lista
        li.textContent = tarefa;

        // Adiciona o item da lista (li) à lista de tarefas (<ul>) com id 'listaTarefas'
        document.getElementById('listaTarefas').appendChild(li);

        // Limpa o campo de texto após adicionar a tarefa à lista
        document.getElementById('tarefa').value = '';
    } else {
        // Se o campo estiver vazio, exibe um alerta pedindo para digitar uma tarefa válida
        alert("Digite uma tarefa válida!");
    }
}

// Função para mudar o tema da página (modo claro/escuro)
function mudartema() {
    // Alterna entre as classes "escuro" e "claro" no elemento <body>
    // A classe "escuro" aplica o estilo do modo escuro e a classe "claro" aplica o estilo do modo claro
    document.body.classList.toggle('escuro');
    document.body.classList.toggle('claro');
}
```
