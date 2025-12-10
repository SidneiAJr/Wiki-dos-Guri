# PHP | Trabalhando com Arquivos em PHP

## Leitura e Escrita de Arquivos
````php
$file = fopen("arquivo.txt", "w"); // Abre o arquivo para escrita
fwrite($file, "Conteúdo do arquivo!");
fclose($file); // Fecha o arquivo
$file = fopen("arquivo.txt", "r"); // Abre o arquivo para leitura
echo fread($file, filesize("arquivo.txt"));
fclose($file);

````
## Manipulação de Diretórios:

````php
if (is_dir("pasta")) {
    echo "O diretório existe!";
} else {
    echo "O diretório não existe!";
}
````

## Autenticação e Controle de Acesso

### Login e Logout
````php
- Criar sistemas de login utilizando sessões ou cookies para armazenar as informações do usuário.
session_start();
if ($_POST['usuario'] == 'admin' && $_POST['senha'] == 'senha') {
    $_SESSION['logado'] = true;
    header('Location: dashboard.php');
} else {
    echo "Usuário ou senha inválidos!";
}
````
