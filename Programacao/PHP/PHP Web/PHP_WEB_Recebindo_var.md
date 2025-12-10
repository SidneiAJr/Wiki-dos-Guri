# PHP | Recebendo de variaives pelo PHP

No PHP, podemos receber variáveis de diferentes fontes, como formulários GET, POST, ou até variáveis de sessão. Vamos entender os diferentes métodos de como o PHP lida com essas variáveis.

Recebendo Dados com $_POST

O $_POST é utilizado para enviar dados via formulário, geralmente usado quando você está lidando com informações sensíveis como senhas, ou para enviar grandes quantidades de dados.

````php
$nome = $_POST['nome'];  // Recebendo o nome do formulário
$senha = $_POST['senha'];  // Recebendo a senha do formulário
echo "Nome: " . $nome;
````

Recebendo Dados com $_SESSION

O $_SESSION é utilizado para armazenar dados temporários durante a navegação de um usuário no site. Essas informações podem ser usadas para armazenar variáveis de login, controle de acesso, ou dados persistentes entre várias páginas.

Exemplo:

````php
// Inicia a sessão
session_start();

// Recebendo dados em uma página e armazenando na sessão
$_SESSION['usuario'] = 'S';  // Armazena o nome do usuário

// Em outra página, você pode acessar o valor assim
session_start();
echo $_SESSION['usuario'];  // Exibe: S
````

### `Formulário HTML`:

````html
<form method="POST" action="processa.php">
  Nome: <input type="text" name="nome"><br>
  Idade: <input type="text" name="idade"><br>
  <input type="submit" value="Enviar">
</form>
````

### `Recebendo e Processando no PHP`
````php
// Recebendo dados via POST
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $nome = $_POST['nome'];
    $idade = $_POST['idade'];

    echo "Nome: " . $nome . "<br>";
    echo "Idade: " . $idade . "<br>";
}
````

| Método      | Uso Principal                             | Dados Visíveis | Segurança | Exemplo                        |
| ----------- | ----------------------------------------- | -------------- | --------- | ------------------------------ |
| `$_GET`     | Receber dados da URL (parâmetros)         | Sim            | Baixa     | exemplo.com?nome=S       |
| `$_POST`    | Enviar dados de formulários (sensíveis)   | Não            | Alta      | Formulários de login, cadastro |
| `$_SESSION` | Armazenar dados temporários entre páginas | Não            | Alta      | Armazenar status de login      |






