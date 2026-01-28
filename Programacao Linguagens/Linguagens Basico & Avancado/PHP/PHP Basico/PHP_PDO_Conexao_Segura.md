# 🔒 Conexão Segura com Banco de Dados usando PDO

O **PDO (PHP Data Objects)** é uma interface mais moderna e segura para se conectar a bancos de dados no PHP.  
Diferente do `mysqli`, ele suporta múltiplos bancos (MySQL, PostgreSQL, SQLite etc.) e permite **prepared statements**, evitando ataques de **SQL Injection**.

---

## 🚀 Criando uma Conexão Básica

```php
<?php
$host = 'localhost';
$db   = 'meu_banco';
$user = 'root';
$pass = 'minha_senha';
$charset = 'utf8mb4';

$dsn = "mysql:host=$host;dbname=$db;charset=$charset";

try {
    $pdo = new PDO($dsn, $user, $pass);
    // Define modo de erro para exceção
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    echo "✅ Conectado com sucesso!";
} catch (PDOException $e) {
    echo "❌ Erro de conexão: " . $e->getMessage();
}
?>

<?php
$sql = "INSERT INTO usuarios (nome, email) VALUES (:nome, :email)";
$stmt = $pdo->prepare($sql);
$stmt->bindParam(':nome', $nome);
$stmt->bindParam(':email', $email);

$nome = "Sidnei";
$email = "sidnei@example.com";
$stmt->execute();
?>

<?php
$stmt = $pdo->prepare("SELECT * FROM usuarios WHERE email = :email");
$stmt->execute(['email' => 'sidnei@example.com']);
$user = $stmt->fetch(PDO::FETCH_ASSOC);

if ($user) {
    echo "Usuário: " . $user['nome'];
}
?>
```
