# PHP | JSON (Básico)

JSON é um formato de dados muito usado para APIs e integrações.  
O PHP possui funções nativas para trabalhar com JSON facilmente.

---

## 🔄 Convertendo Array para JSON

```php
$dados = [
    "nome" => "João",
    "idade" => 25
];

$json = json_encode($dados);

echo $json;

{"nome":"João","idade":25}

```

## Convertendo JSON para Array

```php
$json = '{"nome":"Ana","idade":20}';

$array = json_decode($json, true);

print_r($array);

try {
    $dados = json_decode("{{erro}}", true, 512, JSON_THROW_ON_ERROR);
} catch (Exception $e) {
    echo "Erro ao decodificar JSON: " . $e->getMessage();
}


```

| Parâmetro             | Função                 |
| --------------------- | ---------------------- |
| `true`                | retorna array          |
| `false`               | retorna objeto         |
| `JSON_THROW_ON_ERROR` | lança exceções no erro |
