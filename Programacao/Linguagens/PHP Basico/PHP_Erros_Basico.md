# PHP – Tratamento de Erros (Básico)

O PHP possui diferentes níveis de erro e formas de lidar com eles.  
Este arquivo explica **como entender, exibir e tratar erros corretamente**.

---

## 🧩 Tipos de Erros Comuns

| Tipo | Descrição |
|------|-----------|
| **Notice** | Avisos de algo que pode dar errado, mas não quebra o código |
| **Warning** | Erros mais sérios, mas o script continua executando |
| **Fatal Error** | Interrompe completamente a execução |
| **Parse Error** | Erro de sintaxe (faltou ;, chave, etc.) |

---

## 🛠️ Exibir Erros no Ambiente de Desenvolvimento

```php
ini_set('display_errors', 1);
ini_set('display_startup_errors', 1);
error_reporting(E_ALL);

error_reporting(E_ERROR);          // Apenas erros fatais
error_reporting(E_ALL);            // Todos os erros
error_reporting(E_ALL & ~E_NOTICE); // Todos exceto notices

//🎯 Try / Catch (Tratamento de Exceções)
try {
    $con = new PDO("mysql:host=localhost;dbname=test", "root", "");
} catch (Exception $e) {
    echo "Erro ao conectar: " . $e->getMessage();
}

//🚫 Lançando seu próprio erro
function dividir($a, $b) {
    if ($b == 0) {
        throw new Exception("Divisão por zero não permitida!");
    }
    return $a / $b;
}

try {
    dividir(10, 0);
} catch (Exception $e) {
    echo $e->getMessage();
}

```

