# PHP | Exemplo de Conexão de Banco

### Usando `mysqli` sem POO + Sanitização

Este exemplo mostra como verificar credenciais, conectar ao banco MySQL usando **mysqli**, configurar charset e tratar erros de forma segura.

---

## 📌 Código

```php
<?php

# Configurações
$host   = "localhost";
$banco  = "nome_banco";
$porta  = "3306";  # Porta padrão do MySQL
$user   = "nome_usuario";
$senha  = "senha_banco";

# Verificação simples das variáveis
if ($banco && $user && $senha) {
    echo "Verificação de credenciais: OK" . PHP_EOL;
} else {
    die("Erro: informações incompletas.");
}

# Conexão com mysqli
$con = new mysqli($host, $user, $senha, $banco, $porta);

# Verifica erro de conexão
if ($con->connect_error) {
    error_log("Erro de conexão: " . $con->connect_error);
    http_response_code(500);
    die("Erro interno. Tente novamente mais tarde.");
}

# Define charset
$con->set_charset("utf8mb4");

echo "Conectado ao banco com sucesso!";

# Função de sanitização
function limparEntrada($valor) {
    return htmlspecialchars(trim($valor), ENT_QUOTES, 'UTF-8');
}

?>
```

---

## ✔ O que esse exemplo traz:

* mysqli sem POO
* Verificação inicial de variáveis
* Log de erros privados (`error_log`)
* Resposta HTTP 500
* Charset seguro (`utf8mb4`)
* Função de sanitização de entrada

---


