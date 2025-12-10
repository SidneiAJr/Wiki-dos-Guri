# 🌐 PHP | Introdução à Web & Conexão Segura com Banco de Dados

Quando trabalhamos com PHP para páginas web, uma das tarefas mais comuns é receber dados de formulários e armazená-los no banco de dados.
Abaixo está um exemplo completo, seguro e padronizado de como fazer isso corretamente.

## 🧱 Exemplo Prático: Cadastro de Usuário (com Segurança)

Este exemplo mostra como:

✔ Receber dados via POST

✔ Validar informações

✔ Proteger contra SQL Injection

✔ Hash de senha (obrigatório!)

✔ Usar prepared statements do MySQLi

````php
<?php
// ============================
// 1) Conexão com o Banco
// ============================

// Arquivo conex.php deverá conter algo como:
// $conn = new mysqli("localhost", "usuario", "senha", "banco");
// if ($conn->connect_error) { die("Erro: " . $conn->connect_error); }

include('conex.php');


// ============================
// 2) Verifica se o formulário foi enviado
// ============================

if ($_SERVER["REQUEST_METHOD"] === "POST") {

    // ============================
    // 3) Coleta e valida os dados recebidos
    // ============================

    // Função para sanitizar input
    function limpar($dado) {
        return htmlspecialchars(trim($dado));
    }

    $nome      = limpar($_POST['nome']);
    $sobrenome = limpar($_POST['sobrenome']);
    $email     = filter_input(INPUT_POST, 'email', FILTER_VALIDATE_EMAIL);
    $telefone  = limpar($_POST['telefone']);
    $usuario   = limpar($_POST['usuario']);
    $senha     = $_POST['senha'];

    if (!$email) {
        die("E-mail inválido!");
    }

    // ============================
    // 4) Hash seguro da senha
    // ============================

    $senhaHash = password_hash($senha, PASSWORD_DEFAULT);


    // ============================
    // 5) Inserção no Banco com Prepared Statement
    // ============================

    $stmt = $conn->prepare("
        INSERT INTO usuarios 
        (nome, sobrenome, email, senha, telefone, usuario) 
        VALUES (?, ?, ?, ?, ?, ?)
    ");

    $stmt->bind_param(
        "ssssss",
        $nome,
        $sobrenome,
        $email,
        $senhaHash,
        $telefone,
        $usuario
    );

    // ============================
    // 6) Executa consulta
    // ============================

    if ($stmt->execute()) {
        echo "Cadastro realizado com sucesso!";
    } else {
        echo "Erro ao cadastrar usuário: " . $stmt->error;
    }

    $stmt->close();
}

$conn->close();
?>
````

| Boa Prática                                        | Por quê?                                                     |
| -------------------------------------------------- | ------------------------------------------------------------ |
| **Nunca salvar senha em texto puro**               | Se o banco vazar, todos os logins estão comprometidos.       |
| **Sempre usar password_hash()**                    | Usa bcrypt/argon2 automaticamente, extremamente mais seguro. |
| **Não usar método GET para formulários sensíveis** | Dados aparecem na URL.                                       |
| **Sanitizar inputs**                               | Remove XSS, espaços e caracteres maliciosos.                 |
| **Prepared Statements**                            | Evitam 100% SQL Injection quando usados corretamente.        |
| **Validar e-mail com filter_input**                | Evita dados inválidos ou maliciosos.                         |
