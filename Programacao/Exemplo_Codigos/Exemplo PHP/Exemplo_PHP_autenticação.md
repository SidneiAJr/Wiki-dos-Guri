# PHP | Autenticação | Projeto OLD

- Codigo de PHP com Mini sistema de Autenticação
- Cadastro com formulario
- Cadastro com Banco em PHP

## `Validação em PHP | Sem POO`

```php
<?php
// Recebe Variáveis de Login
$user = $_POST['f_nome'];
$senha = $_POST['f_senha'];

// Conecta ao Banco
$con = mysqli_connect('localhost', 'usuario', 'senha', 'banco_de_dados');
if (!$con) {
    die('Erro ao conectar ao banco de dados: ' . mysqli_connect_error());
}

// Previne SQL Injection usando Prepared Statements
$sql = "SELECT * FROM tb_cadastro WHERE username = ? AND senha = ?";
$stmt = mysqli_prepare($con, $sql);

// Vincula os parâmetros
mysqli_stmt_bind_param($stmt, "ss", $user, $senha);

// Executa a consulta
mysqli_stmt_execute($stmt);

// Verifica se o usuário e senha foram encontrados
$resultado = mysqli_stmt_get_result($stmt);
if (mysqli_num_rows($resultado) > 0) {
    echo "Login bem-sucedido!";
    // Redirecionar ou dar acesso ao sistema
} else {
    echo "Erro no login<br>";
    echo "<a href='login.php'>Voltar</a>";
}

// Fecha a conexão com o banco de dados
mysqli_close($con);
?>
````

## `Cadastro em PHP | Simples`:

### Aqui está um exemplo simples de cadastro, onde os dados são apenas recebidos e uma mensagem é exibida ao usuário. Ideal para situações de teste ou quando você só precisa dos dados na memória (sem persistência).

````php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // Receber os dados do formulário
    $nome = $_POST['nome'];
    $email = $_POST['email'];
    $senha = $_POST['senha'];

    echo "<h2>Cadastro Realizado com Sucesso!</h2>";
}
?>
````

## `Cadastro de cliente | Banco PHP`

````php
<?php
// Conexão com o banco de dados
include('conex.php'); // Verifique se o arquivo conex.php está configurado corretamente

// Verifica se o formulário foi enviado
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // Recebe os dados do formulário
    $nome = $_POST['nome'];
    $sobrenome = $_POST['sobrenome'];
    $email = $_POST['email'];
    $senha = $_POST['senha'];  // Senha sem hash - será convertida para hash
    $telefone = $_POST['telefone'];
    $usuario = $_POST['usuario'];

    // Hash da senha antes de armazenar
    $senhaHash = password_hash($senha, PASSWORD_DEFAULT);  // Utiliza bcrypt para gerar o hash da senha

    // Prepara a consulta SQL para inserir os dados no banco
    $stmt = $conn->prepare("INSERT INTO usuarios (nome, sobrenome, email, senha, telefone, usuario) VALUES (?, ?, ?, ?, ?, ?)");
    $stmt->bind_param("ssssss", $nome, $sobrenome, $email, $senhaHash, $telefone, $usuario);

    // Executa a consulta
    if ($stmt->execute()) {
        echo "Cadastro realizado com sucesso!";
    } else {
        echo "Erro ao cadastrar usuário: " . $stmt->error;
    }
}
?>
````

