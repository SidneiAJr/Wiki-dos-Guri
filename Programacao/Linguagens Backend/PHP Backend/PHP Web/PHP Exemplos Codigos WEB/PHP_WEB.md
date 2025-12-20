# Tutorial de PHP 2 - Web

```php
// Inclui o arquivo de conexão com o banco de dados
include "conexao.php";

// Recebe os valores do formulário enviados via POST
$usuario = $_POST["f_usuario"];
$senha   = $_POST["f_senha"]; 

// Monta a query SQL para selecionar o usuário pelo login
$sql = "select *FROM tab_usuario where usu_login ='$usuario'";

// Executa a query no banco de dados
$res = mysql_query(sql) or die ("erro ao tentar selecionar usuario"); 
// <- OBS: você está usando mysql_query com uma query sem o $ e com mysql_* functions obsoletas. Melhor usar mysqli ou PDO

// Verifica se a consulta retornou algum resultado
if(mysql_num_rows($res) == 0)
{
    // Se não encontrou usuário, redireciona para página de erro
    header('location:erro.html');
}
else
{
    // Pega a primeira linha do resultado da consulta
    $linha = mysqli_fetch_row($res); 
    // <- OBS: misturando mysql_* e mysqli_* aqui, o que pode quebrar o código

    // Compara a senha enviada com a senha do banco
    if($linha[0] == $senha) // <- Provavelmente a senha não está no índice 0, depende da ordem das colunas
    {
        // Inicia a sessão do usuário
        session_start();
        $_SESSION['loginok'] = 'ok';

        // Redireciona para a página de menu do administrador
        header('location:menuadm.php');
    }
    else
    {
        // Se a senha estiver incorreta, redireciona para página de erro
        header('location:erro.html');
    }
}
?>

