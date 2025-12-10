# Exemplo de Código PHP - Exclusão de Aluno com Parâmetro via URL

## Banco de dados | `Escola`:

```sql
CREATE TABLE alunos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    matricula VARCHAR(50),
    email VARCHAR(100),
    telefone VARCHAR(20)
);
```

```sql
CREATE TABLE livros (
    id INT AUTO_INCREMENT PRIMARY KEY,
    titulo VARCHAR(150) NOT NULL,
    autor VARCHAR(100),
    ano INT,
    editora VARCHAR(100)
);
```

```sql
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    usuario VARCHAR(50) NOT NULL UNIQUE,
    senha VARCHAR(255) NOT NULL
);
INSERT INTO usuarios (usuario, senha)
VALUES ('admin', MD5('123'));
```

## Descrição
Este código PHP recebe um **ID de aluno** passado via URL e realiza a **verificação** e **exclusão** do aluno na base de dados. Ele usa a função `$_GET` para receber o parâmetro `cod` e então executa as verificações de segurança antes de executar a consulta no banco de dados.

## Fluxo do Código
1. O código recebe o ID do aluno (`cod`) via parâmetro da URL.
2. Se o parâmetro não for fornecido, é exibida uma mensagem de erro.
3. O código verifica se o ID fornecido é numérico.
4. Se o parâmetro não for numérico, o código exibe um erro de "parâmetro inválido".
5. Se o parâmetro for válido, o código tenta encontrar o aluno no banco de dados.
6. Se o aluno não for encontrado, é exibida uma mensagem de erro.
7. Caso contrário, o código executa a exclusão do aluno no banco de dados.
8. Após a exclusão, é exibida uma mensagem confirmando a operação.

## Código PHP

```php
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Excluir Registro</title>
</head>

<body>
<?php
// RECEBE O PARÂMETRO
$idaluno = $_GET["cod"] ?? null;

// 1 — VERIFICA SE FOI PASSADO
if (!isset($idaluno)) {
    echo "Registro não informado!";
    exit;
}

// 2 — VERIFICA SE É NUMÉRICO
if (!is_numeric($idaluno)) {
    echo "Parâmetro inválido!";
    exit;
}

// CONEXÃO COM O BANCO
include "conexao.php";

// 3 — VERIFICA SE O ALUNO EXISTE
$sql = "SELECT * FROM alunos WHERE id = $idaluno";
$res = mysqli_query($conexao, $sql) or die("Erro ao selecionar aluno!");

if (mysqli_num_rows($res) == 0) {
    echo "Aluno não localizado!";
} else {

    // 4 — EXCLUI O ALUNO
    $sql = "DELETE FROM alunos WHERE id = $idaluno";
    mysqli_query($conexao, $sql) or die("Erro ao excluir aluno!");

    echo "Aluno excluído com sucesso!";
}

// FECHA A CONEXÃO
mysqli_close($conexao);
?>
</body>
</html>

````
