# Tutorial PHP - Inserção de Alunos com Foto

```php
<?php
// Recebe os dados do formulário via POST
$mnome = $_POST["f_codigo"];      // Nome do aluno
$mnivel = $_POST["f_"];           // Nível do aluno (campo vazio na hora do POST?)

// Inicializa variável de controle de erros
$erro = false;

// Verifica se o nome foi preenchido
if (empty($mnome))
{
    echo "<b>NOME</b> nao informado!";
    $erro = true;
}

// Se houver erro, exibe mensagem de correção
if($erro)
{
    echo "<br>O formulario apresenta erros, favor corrigir...";
}
else
{
    // Inclui arquivo de conexão com o banco
    include "../atv3/conexao.php";

    // Monta query de inserção
    // <- ALERTA: inserção direta com variáveis → risco de SQL Injection
    $sql = "INSERT INTO Alunos(nome, nivel) VALUES ('$mnome', $mnivel)";

    // Executa a query
    mysqli_query($conexao, $sql) or die("Erro na insercao de dados!");

    echo "<b>Alunos</b> inserido com sucesso!";
}

// Mensagem duplicada (pode ser removida)
echo "<b>ALUNO</b> inserido com sucesso!";

// Recebe arquivo enviado via formulário
$foto = $_FILES["f_foto"];

// Verifica se algum arquivo foi enviado
if(!empty($foto["name"]))
{
    // Verifica se o arquivo é JPEG
    if($foto["type"] != 'image/jpeg')
    {
        echo "<b>formato de arquivo invalido! Necessario .JPEG!</b><br>";
    }
    else
    {
        // Pega o último ID inserido no banco
        $ultimocod = mysqli_insert_id($conexao);

        // Define o caminho do arquivo
        $arquivo = "imagens/".$ultimocod.".jpg";

        // Se já existir, remove o arquivo antigo
        if(file_exists($arquivo))
        {
            unlink($arquivo);
        }

        // MOVE O ARQUIVO PARA O DIRETÓRIO (ERRO: função escrita incorretamente)
        move_uploaded_file($foto["tmp_name"], $arquivo); // <- Antes estava "move_uploade_file"

        echo "<b>foto inserida com sucesso!</b><br>";
    }
}
else
{
    echo "<b>nenhuma foto enviada!</b><br>";
}
?>
