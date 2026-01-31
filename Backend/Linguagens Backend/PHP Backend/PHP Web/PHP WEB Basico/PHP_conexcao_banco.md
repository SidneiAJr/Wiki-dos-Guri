# Tutorial de conexção em banco em php:

## Exemplo de codigo:

```php

// Conexão segura
$host = 'localhost'; // Host do Banco de dados
$usuario = 'root'; // Usuario do Banco de dados
$senha = ''; // Senha do Banco de dados
$banco = ''; // Nome do Banco de dados

$con = new mysqli($host, $usuario, $senha, $banco);

// Tratamento de erro genérico
if ($con->connect_error) {
    error_log("Erro de conexão: " . $con->connect_error);
    http_response_code(500);
    die("Erro interno. Tente novamente mais tarde.");
}

// Força charset seguro para evitar problemas com dados especiais
$con->set_charset("utf8mb4");

// Protege contra SQL Injection em toda a aplicação
function limparEntrada($valor) {
    return htmlspecialchars(trim($valor), ENT_QUOTES, 'UTF-8');
}
?>
```

## 💡 Dicas importantes

- ***Sempre use senhas fortes para o banco de dados e evite deixar a senha vazia ou padrão.***

- ***Bloqueie o acesso a arquivos sensíveis usando .htaccess (exemplo: impedir acesso direto a arquivos PHP que contenham senhas ou configurações).***

- ***Use variáveis de ambiente ou arquivos fora da raiz pública para guardar suas credenciais de banco de dados, evitando expor no código fonte.***

- ***Considere usar PDO ao invés de mysqli para maior flexibilidade e recursos avançados.***

- ***Sempre valide e sanitize dados recebidos do usuário antes de usar em queries.***
