# Tutorial PHP - Web3

```php
<?php 
// Recebe o parâmetro 'cod' da URL via GET
$idaluno = $_GET["cod"];


// VERIFICAÇÃO INCORRETA: a variável checada não existe ($idcod)
// Deveria ser $idaluno
if(!isset($idcod))
{
    echo "livros nao informado!";
}

// Verifica se o parâmetro passado é numérico
// Aqui você está checando $cod, mas a variável recebida é $idaluno
if(!is_numeric($cod))
{
    echo "parametro invalido";
}
else
{
    // Inclui arquivo de conexão com o banco de dados
    include "conexao.php";

    // Seleciona o registro do livro (ou aluno?) pelo id
    $sql = "select * from livros where id=$idaluno";

    // Executa a query e retorna o resultado
    $res = mysqli_query($conexao,$sql) or die("erro ao selecionar aluno!");

    // Conta quantos registros foram retornados
    $total = mysqli_num_rows($res);

    // Se não encontrou nenhum registro, exibe mensagem
    if($total == 0)
    {
        echo "livros nao localizado";
    }
    else
    {
        // Deleta o registro do aluno pelo id
        // <- ALERTA: você está usando $idaluno direto na query → risco de SQL injection
        $sql = "DELETE FROM alunos where id=$idaluno";

        // Executa a query de exclusão
        $res = mysqli_query($conexao,$sql) or die ("erro ao ecluir aluno"); // <- faltou ; no final

        // Mensagem de sucesso
        echo "aluno exlcuido com sucesso!";
    }
    
    // Fecha a conexão com o banco
    mysqli_close($close); // <- errado: variável de conexão é $conexao
?>
