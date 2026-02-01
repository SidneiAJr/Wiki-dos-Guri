# 🔐 PHP | Sessões Avançadas

As sessões permitem identificar e armazenar dados do usuário durante a navegação.
Mas, para aplicações profissionais, é necessário usar sessões com segurança, validação, regeneração e proteção contra hijacking.

Este guia cobre tudo isso em um único documento.

## 🧱 `Iniciando uma Sessão da Forma Correta`

O PHP permite iniciar sessões com session_start(), porém existem configurações adicionais que aumentam a segurança.

```php
<?php
session_start([
    'cookie_httponly' => true,
    'cookie_secure'   => true,    // Exige HTTPS
    'cookie_samesite' => 'Strict'
]);
?>
```

## 🔐 `Criando Variáveis de Sessão`
```php
<?php
session_start();

$_SESSION['usuario'] = "S";
$_SESSION['nivel'] = "admin";
?>
```

## `Regenerando ID de Sessão (Proteção Anti-Hijack)`
```php
session_start();
session_regenerate_id(true); // Gera um ID totalmente novo
```

## `Encerrando Sessão com Segurança`
```php
<?php
session_start();

// Apaga todas as variáveis
session_unset();

// Destrói sessão
session_destroy();

// Remove o cookie
setcookie(session_name(), "", time() - 3600);
?>
```

## `Proteção Contra Session Hijacking`
```php
if (!isset($_SESSION['agente'])) {
    $_SESSION['agente'] = $_SERVER['HTTP_USER_AGENT'];
} elseif ($_SESSION['agente'] !== $_SERVER['HTTP_USER_AGENT']) {
    session_destroy();
    die("Sessão suspeita!");
}
```

## `Bloqueio por IP`
```php
if (!isset($_SESSION['ip'])) {
    $_SESSION['ip'] = $_SERVER['REMOTE_ADDR'];
} elseif ($_SESSION['ip'] !== $_SERVER['REMOTE_ADDR']) {
    session_destroy();
    die("Mudança de IP detectada!");
}
```

## `Definindo Tempo de Expiração da Sessão`
```php
session_start();

$tempoMaximo = 600; // 10 minutos

if (!isset($_SESSION['ultimo_acesso'])) {
    $_SESSION['ultimo_acesso'] = time();
} else {
    if (time() - $_SESSION['ultimo_acesso'] > $tempoMaximo) {
        session_unset();
        session_destroy();
        die("Sessão expirada!");
    }

    $_SESSION['ultimo_acesso'] = time();
}
```

## `Bloqueando ataques de Session Fixation`
```php
session_start();
session_regenerate_id(true); // Antes de criar sessão do usuário
$_SESSION['logado'] = true;
```

## `Configurações de Segurança no php.ini`
```php
session.cookie_httponly = 1
session.cookie_secure = 1
session.use_strict_mode = 1
session.sid_length = 64
session.sid_bits_per_character = 6
```

| Técnica             | Protege Contra       |
| ------------------- | -------------------- |
| `httponly`          | XSS                  |
| `secure`            | sniffing em HTTP     |
| validar IP          | session hijacking    |
| validar User-Agent  | roubo de cookie      |
| timeout             | sessões abandonadas  |
| regenerar ID        | fixation e hijacking |
| SameSite            | CSRF                 |
| handler customizado | escalabilidade       |
