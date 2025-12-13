# Simulador de Cadastro e Consulta de Abrigos - JavaScript 

## Feito para o 3000TI

```js
// ==============================
// Variáveis de entrada
// ==============================
let opcao = prompt(
  "1-Cadastrar Abrigo\n2-Listar Abrigo\n3-Procurar Abrigo\n4-Sair\nEscolha uma opção:"
);
let listabrigo = []; // Lista para armazenar os abrigos cadastrados

// ==============================
// Menu de ações
// ==============================
while(opcao !== '4'){ // Enquanto não escolher sair
    switch(opcao){
        case '1':
            cadfun();       // Chama função para cadastrar abrigo
            break;
        case '2':
            infoabrigo();   // Chama função para listar abrigos
            break;
        case '3':
            procurabrigo(); // Chama função para procurar abrigo por cidade
            break;
        case '4':
            alert('Sair');  // Opção de sair
            break;
        default:
            alert('Opção Inválida!!!!'); // Se a opção não for válida
            break;
    }
    // Reexibe menu após cada ação
    opcao = prompt(
        "1-Cadastrar Abrigo\n2-Listar Abrigo\n3-Procurar Abrigo\n4-Sair\nEscolha uma opção:"
    );
}

// ==============================
// Função de Cadastro de Abrigo
// ==============================
function cadfun(){
    // Recebe informações do usuário
    let nomecid = prompt("Qual é o nome da cidade que gostaria de cadastrar?");
    let enderecocid = prompt("Qual é o endereço do abrigo?");
    let telefone = Number(prompt("Qual é o telefone do abrigo?"));
    let lotacao = Number(prompt("Qual é a lotação do abrigo em pessoas?"));

    // Cria objeto do abrigo
    let listeste = {
        Cidade: nomecid,
        Endereco: enderecocid,
        Telefone: telefone,
        Capacidade: lotacao
    };

    // Adiciona abrigo à lista
    listabrigo.push(listeste);
}

// ==============================
// Função de Listar Abrigos
// ==============================
function infoabrigo(){
    for(let i = 0; i < listabrigo.length; i++){
        alert(`== Lista de Abrigos Cadastrados ==\n` +
              `Nome da Cidade: ${listabrigo[i].Cidade}\n` +
              `Endereço: ${listabrigo[i].Endereco}\n` +
              `Telefone do Abrigo: ${listabrigo[i].Telefone}\n` +
              `Capacidade do Abrigo: ${listabrigo[i].Capacidade}\n=======`);
    }
}

// ==============================
// Função de Procurar Abrigo por Cidade
// ==============================
function procurabrigo(){
    const cidcadastrada = prompt("Por favor, insira a cidade que quer procurar:");
    const resultado = []; // Armazena resultados encontrados

    // Percorre a lista de abrigos e verifica cidade
    for(let i = 0; i < listabrigo.length; i++){
        if(cidcadastrada === listabrigo[i].Cidade){
            resultado.push(listabrigo[i]);
        }
    }

    // Verifica se encontrou algum abrigo
    if(resultado.length === 0){
        alert("Cidade não cadastrada.");
    } else {
        // Mostra os abrigos encontrados
        for(let i = 0; i < resultado.length; i++){
            alert(`== Lista de Abrigos Cadastrados ==\n` +
                  `Nome da Cidade: ${resultado[i].Cidade}\n` +
                  `Endereço: ${resultado[i].Endereco}\n` +
                  `Telefone do Abrigo: ${resultado[i].Telefone}\n` +
                  `Capacidade do Abrigo: ${resultado[i].Capacidade}\n=======`);
        }
    }
}
