# PHP | Capturando Informações do Form:

### `Captura de Formulário + Login Seguro em PHP (mysqli + password_verify)`

### `Este exemplo demonstra como capturar dados de um formulário via POST, consultar o banco de dados com Prepared Statements e validar senha utilizando password_verify(), seguindo as práticas modernas de segurança no PHP.`

### Arquivo: Login.php

```php
<?php
session_start();
require "conexao.php";

// Sanitiza e recebe
$usuario = trim($_POST["f_usuario"]);
$senha   = trim($_POST["f_senha"]);

// Prepara query (DIFERENÇA: aqui é protegido contra SQL Injection)
$sql = $con->prepare("SELECT usu_senha FROM tab_usuario WHERE usu_login = ?");
$sql->bind_param("s", $usuario);
$sql->execute();
$result = $sql->get_result();

// Se não encontrou usuário
if($result->num_rows === 0) {
    header("Location: erro.html");
    exit;
}

// Pega o registro
$linha = $result->fetch_assoc();

// Verifica senha com password_verify
if(password_verify($senha, $linha["usu_senha"])){

    $_SESSION['loginok'] = 'ok';
    header("Location: menuadm.php");
    exit;

} else {

    header("Location: erro.html");
    exit;
}
?>
```

## Conexção de PHP

### Arquivo: conexao.php

```php
<?php
$host = "localhost";
$user = "root";
$pass = "";
$db   = "meubanco";

$con = new mysqli($host, $user, $pass, $db);

if($con->connect_error){
    die("Erro de conexão: " . $con->connect_error);
}

$con->set_charset("utf8mb4");
?>
```

| Parte                     | O que faz                       | Importância                             |
| ------------------------- | ------------------------------- | --------------------------------------- |
| `session_start()`         | Inicia sessão para autenticação | Necessário para login persistente       |
| `trim()`                  | Remove espaços extras           | Evita erro de digitação / SQL Injection |
| `prepare()`               | Prepara consulta segura         | Protege contra injeção SQL              |
| `bind_param()`            | Liga os valores à query         | Segurança + tipagem                     |
| `get_result()`            | Obtém resultado da consulta     | Permite verificar usuário               |
| `password_verify()`       | Compara senha com o hash        | Método correto e seguro no PHP          |
| `header("Location: ...")` | Redireciona usuário             | Navegação pós-login                     |
| `$con->set_charset()`     | Define UTF-8                    | Evita problemas com acentos             |


