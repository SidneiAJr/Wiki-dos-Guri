# JavaScript | Contador de Botão

Neste tutorial, vamos criar um contador que aumenta a cada vez que o botão é clicado. O contador será exibido em um **H1** na tela, e o valor será atualizado a cada clique do usuário.

---

## 🛠️ Passo a Passo

### 1. **Criar os Arquivos**

Crie dois arquivos:

- **index.html**: Arquivo HTML onde vamos colocar o botão e o H1.
- **script.js**: Arquivo JavaScript onde a lógica do contador será feita.

---

### 2. **HTML: Criando o H1 e o Botão**

No arquivo `index.html`, vamos criar a estrutura básica com um **H1** para exibir o contador e um **botão** para que o usuário possa clicar e aumentar o valor.

```html
<h1 id="contador">Contando:</h1>
<button id="contar" onclick="cont()">Contar</button>
````
-  id="contador">Contando:</h1>: Cria um título com o ID "contador", onde o valor do contador será exibido.

- button id="contar" onclick="cont()">Contar</button>: Cria o botão que, ao ser clicado, chama a função cont() no JavaScript.

```JS
let contador = 0;  // Variável contador iniciada com valor 0

function cont(){
    // Manipula o botão, mas não é necessário usar o parseInt aqui, pois não estamos utilizando o valor do botão como numérico
    let texto = `Contando ${contador}`;  // Texto que mostra o valor do contador
    contador++;  // Incrementa o contador em 1 a cada clique
    document.getElementById("contador").innerHTML = `Contando: ${texto}`;  // Atualiza o conteúdo do H1 com o novo valor
}
```

### Explicação do Código JavaScript:

- let contador = 0;: A variável contador é inicializada com valor 0.

- Função cont():

- A função é chamada quando o botão é clicado.

- texto = Contando ${contador};: A variável texto recebe o valor atual de contador para ser exibido no H1.

- contador++;: A cada clique, o valor de contador é incrementado em 1.

- document.getElementById("contador").innerHTML = Contando: ${texto};: Atualiza o conteúdo do H1 com o novo valor de contador.


### 🧱 Passos Resumidos

- Criando o H1: Colocamos um para exibir a saída do contador.

- Criando o Botão: Criamos um botão com o ID contar, que ao ser clicado chama a função cont().

- JavaScript:

- Criamos a variável contador iniciada com 0.

- Criamos a função cont(), que incrementa o valor do contador e atualiza o conteúdo do H1.

- Usamos document.getElementById("contador").innerHTML para alterar o conteúdo do H1 com o novo valor de contador.
