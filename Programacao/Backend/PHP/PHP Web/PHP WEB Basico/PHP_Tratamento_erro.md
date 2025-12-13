# ⚠️ Tratamento de Erros e Exceções em PHP (Completo)

PHP possui dois sistemas de erros:

1. **Erros tradicionais (warning, notice, fatal)**  
2. **Exceções com try/catch**

Aqui estão os dois, do básico ao avançado.

---

# ⭐ 1. Tipos de Erros em PHP

- **Notice** → aviso leve  
- **Warning** → problema mais sério  
- **Fatal error** → interrompe o script  
- **Parse error** → erro de sintaxe  
- **Exception** → erro controlado via try/catch

---

# ⭐ 2. Tratamento com Try/Catch

```php
try {
    if (!file_exists("dados.txt")) {
        throw new Exception("Arquivo não encontrado!");
    }
} catch (Exception $erro) {
    echo "Erro: " . $erro->getMessage();
}
```
# 3. Bloco Finally

```php
try {
    echo "Processando...";
} catch (Exception $e) {
    echo $e->getMessage();
} finally {
    echo "Finalizado!";
}
```

# 4. Criando Exceções Personalizadas
```php
class MeuErro extends Exception {}

try {
    throw new MeuErro("Erro personalizado");
} catch (MeuErro $e) {
    echo $e->getMessage();
}
```

# 5. set_error_handler() – Capturar erros tradicionais

```php
function tratarErros($nivel, $mensagem) {
    echo "Erro capturado: $mensagem";
}

set_error_handler("tratarErros");

echo $x; // Notice capturado
```

# 6. trigger_error() – Criar erros manuais
```php
trigger_error("Algo deu errado!", E_USER_WARNING);
```

# 7. Convertendo Erros em Exceções
```php
set_error_handler(function($n, $m){
    throw new Exception($m);
});
```

# 8. Exceções com PDO (Banco de Dados)
```php
$pdo = new PDO("mysql:host=x;dbname=y","root","senha",[
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION
]);
```

# 9. try/catch Aninhado
```php
try {
    // nível 1
    try {
        throw new Exception("Erro interno");
    } catch (Exception $e) {
        throw new Exception("Erro externo");
    }
} catch (Exception $e) {
    echo $e->getMessage();
}
```




