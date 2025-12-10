# 🔐 Documento voltado para camadas de segurança em PHP

## 1. Blindagem contra SQL Injection
- Uso de **Prepared Statements** (parâmetros bindados) com **PDO** ou **mysqli**:
  ```php
  $stmt = $pdo->prepare("SELECT * FROM users WHERE email = ?");
  $stmt->execute([$email]);

## 2. Método POST (vs GET)
- ***Utilizar POST para envio de dados sensíveis como:***
- Senhas
- Dados pessoais
- Formulários de login, cadastro, alteração
- Evitar expor dados na URL (GET), principalmente em links compartilháveis.

## 3. Uso de password_hash() e password_verify()
- Funções nativas, seguras e atualizadas com algoritmos modernos como bcrypt e Argon2.
 ```php
$hash = password_hash($senha, PASSWORD_DEFAULT);
if (password_verify($senhaDigitada, $hash)) {
    // Senha válida
}
 ```

## 4. Validação e Sanitização de Dados

- Nunca confiar em dados do usuário.
- Funções úteis:
- filter_var() (ex: FILTER_VALIDATE_EMAIL, FILTER_SANITIZE_STRING)
- htmlspecialchars() (XSS)
- intval(), floatval() para forçar tipo
 ```php
$email = filter_var($_POST['email'], FILTER_VALIDATE_EMAIL);
$nome  = htmlspecialchars($_POST['nome'], ENT_QUOTES, 'UTF-8');
 ```

## 5.Proteção contra XSS (Cross-site Scripting)
- Escapar todas as saídas de dados dinâmicos no HTML:
 ```php
 <p><?= htmlspecialchars($usuario['nome']) ?></p>
 ```

## 6. Proteção contra CSRF (Cross-Site Request Forgery)
- Gerar token CSRF único por formulário e armazenar na sessão:
 ```php
$_SESSION['csrf_token'] = bin2hex(random_bytes(32));
 ```

## 6. Gerenciamento de Sessões Seguro
- Regenerar o ID de sessão após login:
 ```php
session_regenerate_id(true);
session_set_cookie_params([
    'lifetime' => 0,
    'path' => '/',
    'domain' => 'seudominio.com',
    'secure' => true,
    'httponly' => true,
    'samesite' => 'Strict'
]);
 ```

## 7.Limitação de Tentativas de Login (Brute Force Protection)
- Impedir ataques de força bruta:
- Implementar delay progressivo entre tentativas
- Lockout temporário após várias falhas
- Usar ReCaptcha
 ```php
if ($_SESSION['tentativas_login'] >= 5) {
    die("Muitas tentativas. Tente novamente em 15 minutos.");
}
 ```

## 8. Controle de Acesso e Autorização
- Verificar permissões de usuário antes de acessar rotas/páginas sensíveis:
 ```php
if ($_SESSION['tipo_usuario'] !== 'admin') {
    header("Location: sem_permissao.php");
    exit;
}
``` 

## 9. Headers de Segurança (via PHP ou .htaccess)
 ```php
header('X-Frame-Options: SAMEORIGIN');
header('X-Content-Type-Options: nosniff');
header('X-XSS-Protection: 1; mode=block');
header('Referrer-Policy: no-referrer-when-downgrade');
header('X-Frame-Options: SAMEORIGIN');
header('X-Content-Type-Options: nosniff');
header('X-XSS-Protection: 1; mode=block');
header('Referrer-Policy: no-referrer-when-downgrade');
 ```

## 10.Timeouts e Expiração de Sessões
```php
$tempo_inatividade = 900; // 15 minutos
if (isset($_SESSION['ultimo_acesso']) && time() - $_SESSION['ultimo_acesso'] > $tempo_inatividade) {
    session_destroy();
    header('Location: login.php');
    exit;
}
$_SESSION['ultimo_acesso'] = time();
 ```

## 11. Escape de comandos em Shell ou sistema
```php
// INCORRETO: pode permitir injeção de comandos
exec("ping " . $_GET['ip']);

// CORRETO: valida e escapa
$ip = escapeshellarg($_GET['ip']);
exec("ping $ip");
```

## 12. Proteção contra IDOR (Insecure Direct Object Reference)
- Nunca confiar em IDs na URL como prova de autorização:
```php
// Errado
arquivo.php?id=42

// Correto
if ($_SESSION['user_id'] !== $arquivo['dono_id']) {
    http_response_code(403);
    exit("Acesso negado.");
}
```

## 13. Proteção contra Uploads Maliciosos
````php
$arquivo = $_FILES['upload'];
$extensao = pathinfo($arquivo['name'], PATHINFO_EXTENSION);

// Verificar se a extensão é permitida
$extensoes_permitidas = ['jpg', 'jpeg', 'png', 'gif'];
if (!in_array($extensao, $extensoes_permitidas)) {
    die('Tipo de arquivo não permitido.');
}

// Renomear o arquivo para evitar conflitos
$novo_nome = uniqid() . '.' . $extensao;
move_uploaded_file($arquivo['tmp_name'], '/uploads/' . $novo_nome);
````

## 14. $ciphering = "AES-128-CTR";
````php
$iv_length = openssl_cipher_iv_length($ciphering);
$options = 0;
$encryption_iv = '1234567890123456';
$encryption_key = "key123";

// Criptografar
$encryption = openssl_encrypt($data, $ciphering, $encryption_key, $options, $encryption_iv);

// Descriptografar
$decryption = openssl_decrypt($encryption, $ciphering, $encryption_key, $options, $encryption_iv);
````


