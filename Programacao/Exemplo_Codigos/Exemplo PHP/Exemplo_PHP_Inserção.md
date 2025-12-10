# PHP | Inserindo Informação 

## Inserindo Aluno | Arquivo: inserir_aluno.php

```php
<?php
session_start();
require "../atv3/conexao.php";

// --------------------------
// 1. RECEBE E VALIDA DADOS
// --------------------------
$nome  = trim($_POST["f_codigo"]);
$nivel = trim($_POST["f_nivel"]); 

$erro = false;

if(empty($nome)){
    echo "<b>Erro:</b> Nome não informado!<br>";
    $erro = true;
}

if(empty($nivel)){
    echo "<b>Erro:</b> Nível não informado!<br>";
    $erro = true;
}

if($erro){
    echo "<br><b>O formulário apresenta erros. Favor corrigir.</b>";
    exit;
}

// --------------------------
// 2. INSERIR NO BANCO (SEGURO)
// --------------------------

// Query usando prepared statement para evitar SQL Injection
$sql = $conexao->prepare(
    "INSERT INTO Alunos (nome, nivel) VALUES (?, ?)"
);

$sql->bind_param("ss", $nome, $nivel);  // s = string

if(!$sql->execute()){
    die("Erro ao inserir aluno no banco.");
}

echo "<b>Aluno inserido com sucesso!</b><br>";

// ID do aluno recem cadastrado
$ultimoID = $conexao->insert_id;


// --------------------------
// 3. TRATAMENTO DA FOTO
// --------------------------

if(isset($_FILES["f_foto"]) && !empty($_FILES["f_foto"]["name"])){

    $foto = $_FILES["f_foto"];

    // Verifica tipo
    if($foto["type"] !== "image/jpeg"){
        echo "<b>Formato inválido.</b> Apenas JPEG é permitido.<br>";
    } else {

        $caminho = "imagens/" . $ultimoID . ".jpg";

        // Se já existe, apaga
        if(file_exists($caminho)){
            unlink($caminho);
        }

        // Move arquivo
        if(move_uploaded_file($foto["tmp_name"], $caminho)){
            echo "<b>Foto enviada com sucesso!</b><br>";
        } else {
            echo "<b>Erro ao mover o arquivo!</b><br>";
        }
    }

} else {
    echo "<b>Nenhuma foto enviada.</b><br>";
}

?>
````

### Explicações:

### `📌 Cadastro de Alunos com Upload de Foto (PHP + MySQL + Upload Seguro)`

Este script permite:

- ✔ Receber informações enviadas por um formulário
- ✔ Validar campos obrigatórios
- ✔ Inserir dados na tabela Alunos usando Prepared Statements
- ✔ Obter o último ID cadastrado
- ✔ Fazer upload da foto do aluno
- ✔ Renomear a foto com base no ID do banco
- ✔ Garantir que apenas arquivos JPEG sejam aceitos
- ✔ Substituir a foto caso o aluno já possua uma
