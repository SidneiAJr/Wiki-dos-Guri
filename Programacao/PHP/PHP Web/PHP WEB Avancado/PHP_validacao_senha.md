# 🔐 PHP | Validação de Senha

Este guia explica como **criar, armazenar e validar senhas de forma segura em PHP**, seguindo boas práticas usadas em aplicações reais.

> ❗ Nunca armazene senhas em texto puro (plain text).

---

## ❓ Por que validar senha corretamente?

Senhas mal armazenadas podem resultar em:
- Vazamento de dados
- Acesso indevido a contas
- Problemas legais (LGPD)

A validação correta envolve:
- Hash seguro
- Comparação correta
- Regras mínimas de força

---

## 🔑 Hash de Senha (Forma Correta)

O PHP fornece funções nativas seguras.

### ✅ Criando o hash da senha
```php
<?php
$senha = "MinhaSenha@123";

$hash = password_hash($senha, PASSWORD_DEFAULT);

echo $hash;
```

## Exemplo de Codigo
```php
<?php
$senhaDigitada = $_POST['senha'];
$hashBanco = $usuario['password']; // hash vindo do banco

if (password_verify($senhaDigitada, $hashBanco)) {
    echo "Login autorizado";
} else {
    echo "Senha inválida";
}
```

## Regras basisca de validação de Senha:

```php
<?php
$senha = $_POST['senha'];

if (strlen($senha) < 8) {
    echo "A senha deve ter no mínimo 8 caracteres.";
    exit;
}

if (!preg_match('/[A-Z]/', $senha)) {
    echo "A senha deve conter letra maiúscula.";
    exit;
}

if (!preg_match('/[a-z]/', $senha)) {
    echo "A senha deve conter letra minúscula.";
    exit;
}

if (!preg_match('/[0-9]/', $senha)) {
    echo "A senha deve conter número.";
    exit;
}

if (!preg_match('/[\W]/', $senha)) {
    echo "A senha deve conter caractere especial.";
    exit;
}

echo "Senha válida!";
```


