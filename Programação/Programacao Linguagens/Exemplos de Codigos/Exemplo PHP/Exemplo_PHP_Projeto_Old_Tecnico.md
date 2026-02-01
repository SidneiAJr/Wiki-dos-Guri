# 🐘PHP | Projeto Completo Tecnico | OLD HTML 4


## Banco de dados | Recriado porem Não se sabe o original:

### `SQL |Tabela de usuários`

```sql
CREATE TABLE tab_usuario (
    id INT AUTO_INCREMENT PRIMARY KEY,
    usu_login VARCHAR(50) NOT NULL,
    usu_senha VARCHAR(255) NOT NULL
);
INSERT INTO tab_usuario (usu_login, usu_senha)
VALUES ('admin', '123');
````

### `SQL |Tabela Livros`
```sql
CREATE TABLE livros (
    codigo INT AUTO_INCREMENT PRIMARY KEY,
    titulo VARCHAR(150) NOT NULL,
    preco DECIMAL(10,2) NOT NULL,
    categoria INT NOT NULL,
    descricao TEXT
INSERT INTO livros (titulo, preco, categoria, descricao)
VALUES
('Banco de Dados Relacional', 59.90, 1, 'Livro sobre SQL e bancos de dados.'),
('HTML e CSS para iniciantes', 39.90, 5, 'Introdução ao HTML clássico.'),
('Javascript Moderno', 49.90, 6, 'Curso completo de JS.');
);
```

### `SQL |Tabela Alunos`
```sql
CREATE TABLE alunos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(150) NOT NULL,
    nivel INT NOT NULL
);
```

### `SQl | Tabela tab_usuario`
```sql
CREATE TABLE tab_usuario (
    usu_login VARCHAR(40) NOT NULL PRIMARY KEY,
    usu_senha VARCHAR(40) NOT NULL
);
INSERT INTO tab_usuario (usu_login, usu_senha)
VALUES ('admin', '123');
````

---

### PHP | Conexção com Banco: 

```php
<?php
$host = "localhost";
$user = "root";
$pass = "";
$db   = "projeto_old";

// cria a conexão
$conexao = mysqli_connect($host, $user, $pass, $db);

// verifica erros
if (!$conexao) {
    die("Erro ao conectar ao banco de dados: " . mysqli_connect_error());
}

// define charset (importante pra acentuação)
mysqli_set_charset($conexao, "utf8");
?>
````

### HTML | Formulario:

````html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Livraria Paluminio</title>
</head>

<body>

<table width="712" border="2">
    <tr>
        <td width="182" rowspan="2">
            <img src="images/9.jpg" alt="" width="176" height="140" />
        </td>
        <td width="512">
            <strong>Livraria Paluminio</strong>
        </td>
    </tr>

    <!-- LOGIN -->
    <tr>
        <td>
            <form id="form_login" name="form_login" method="post" action="login.php">
                <p><strong>Usuário:
                    <input type="text" name="f_usuario" id="f_usuario" />
                </strong></p>
                <p><strong>Senha:
                    <input type="password" name="f_senha" id="f_senha" />
                </strong>
                <input type="submit" value="OK" />
                </p>
            </form>
        </td>
    </tr>

    <!-- BUSCA -->
    <tr>
        <td colspan="2">
            <form id="form_busca" name="form_busca" method="post" action="listagem.php">
                <strong>Busca:
                    <input type="text" name="f_prod" id="f_prod" />
                </strong>
                <input type="submit" value="OK" />
            </form>
        </td>
    </tr>
</table>

</body>
</html>
````

### PHP | Login - Recriado

````php
<?php
// Inicia a sessão
session_start();

// Verifica se o formulário foi enviado
if (!isset($_POST["f_usuario"]) || !isset($_POST["f_senha"])) {
    header("location:erro.html");
    exit();
}

// Recebe dados do formulário
$usuario = trim($_POST["f_usuario"]);
$senha   = trim($_POST["f_senha"]);

// Verifica campos vazios
if ($usuario == "" || $senha == "") {
    header("location:erro.html");
    exit();
}

// Conexão com o banco
include "conexao.php";

// Consulta preparada
$sql = "SELECT usu_login, usu_senha FROM tab_usuario WHERE usu_login = ?";
$stmt = mysqli_prepare($conexao, $sql);
mysqli_stmt_bind_param($stmt, "s", $usuario);
mysqli_stmt_execute($stmt);
$res = mysqli_stmt_get_result($stmt);

// Verifica se o usuário existe
if (mysqli_num_rows($res) == 0) {
    header("location:erro.html");
    exit();
}

$linha = mysqli_fetch_assoc($res);

// Aqui estamos comparando a senha diretamente (modelo antigo)
if ($senha === $linha["usu_senha"]) {

    // Login OK
    $_SESSION["loginok"] = "ok";
    $_SESSION["usuario"] = $linha["usu_login"];

    header("location:menuadm.php");
    exit();

} else {
    // Senha incorreta
    header("location:erro.html");
    exit();
}

?>
````

### PHP | HTML Listagem

```php
<?php
// Inicia a sessão
session_start();

// Verifica se o usuário está logado
if (!isset($_SESSION['loginok']) || $_SESSION['loginok'] != 'ok') {
    header("location:erro.html");
    exit();
}

// Conexão com o banco
include "conexao.php";

// Consulta todos os alunos
$sql = "SELECT id, nome FROM alunos ORDER BY nome";
$res = mysqli_query($conexao, $sql) or die("Erro ao selecionar alunos!");

$total = mysqli_num_rows($res);
?>
```

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Listagem de Alunos</title>

<script type="text/javascript">
function confirmaExclusao() {
    return confirm("Deseja realmente excluir este aluno?");
}
</script>

</head>
<body>

<h2>Listagem de Alunos</h2>
```
```php
<?php
// Se não existirem alunos
if ($total == 0) {
    echo "<b>Nenhum aluno encontrado!</b>";
} else {

    // Lista os alunos
    while ($linha = mysqli_fetch_assoc($res)) {
?>
        <table width="600" border="1" cellpadding="5" cellspacing="0">
            <tr>
                <td width="400"><b><?php echo $linha['nome']; ?></b></td>

                <td width="100">
                    <a href="alt_aluno.php?cod=<?php echo $linha['id']; ?>">
                        Editar
                    </a>
                </td>

                <td width="100">
                    <a href="exc_aluno.php?cod=<?php echo $linha['id']; ?>" 
                       onclick="return confirmaExclusao();">
                        Excluir
                    </a>
                </td>
            </tr>
        </table>
        <br>
<?php
    }
}

mysqli_close($conexao);
?>

<br><br>
<a href="menuadm.php">Voltar ao Menu</a>
````
````html
</body>
</html>
````

### HTML | Menu

```html
<?php
session_start();

// Proteção da área restrita
if (!isset($_SESSION['loginok']) || $_SESSION['loginok'] !== 'ok') {
    header('location:erro.html');
    exit();
}
?>
<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="utf-8">
<title>Painel Administrativo</title>
</head>
<body>

<h2>Painel Administrativo</h2>

<ul>
    <li><a href="cadastro.php">Cadastrar aluno</a></li>
    <li><a href="listagem.php">Listar alunos</a></li>
    <li><a href="logout.php">Sair</a></li>
</ul>

</body>
</html>
````

### Html | Cadastro

```html
<?php
session_start();

if (!isset($_SESSION['loginok']) || $_SESSION['loginok'] != 'ok') {
    header("location:erro.html");
    exit();
}

include "conexao.php";
?>

<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="utf-8" />
<title>Cadastrar Aluno</title>
</head>
<body>

<h2>Cadastrar novo aluno</h2>

<form method="post" enctype="multipart/form-data">
    <p><strong>Nome:</strong><br>
        <input type="text" name="f_nome" required size="50">
    </p>

    <p><strong>Nível:</strong><br>
        <select name="f_nivel">
            <option value="1">Educação Infantil</option>
            <option value="2">Ensino Fundamental</option>
            <option value="3">Ensino Médio</option>
            <option value="4">Técnico</option>
        </select>
    </p>

    <p><strong>Foto (JPEG):</strong><br>
        <input type="file" name="f_foto" accept="image/jpeg">
    </p>

    <p>
        <input type="submit" value="Cadastrar">
        <input type="reset" value="Limpar">
    </p>
</form>
````
````php
<?php
// --- PROCESSA O FORMULÁRIO ---
if ($_SERVER["REQUEST_METHOD"] == "POST") {

    $nome  = $_POST["f_nome"];
    $nivel = $_POST["f_nivel"];

    // Insere aluno no banco
    $sql = "INSERT INTO alunos (nome, nivel) VALUES (?, ?)";
    $stmt = mysqli_prepare($conexao, $sql);
    mysqli_stmt_bind_param($stmt, "si", $nome, $nivel);

    if (mysqli_stmt_execute($stmt)) {
        echo "<b>Aluno cadastrado com sucesso!</b><br><br>";

        // ID do novo aluno
        $id = mysqli_insert_id($conexao);

        // FOTO
        if (!empty($_FILES["f_foto"]["name"])) {
            $foto = $_FILES["f_foto"];

            if ($foto["type"] != "image/jpeg") {
                echo "<b>Erro:</b> A foto deve ser JPEG!<br>";
            } else {
                $destino = "imagens/" . $id . ".jpg";

                move_uploaded_file($foto["tmp_name"], $destino);
                echo "Foto enviada com sucesso!<br>";
            }
        } else {
            echo "Nenhuma foto enviada.<br>";
        }

    } else {
        echo "Erro ao cadastrar aluno!";
    }
}
?>
````
````html
<br>
<a href="menuadm.php">Voltar ao Menu</a>

</body>
</html>
````




