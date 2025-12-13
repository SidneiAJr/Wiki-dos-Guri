# PHP | Conceitos Essenciais (Operadores, Tipagem, Constantes Mágicas e Métodos Mágicos)

Este módulo explica alguns dos recursos mais importantes do PHP moderno:  
operadores especiais, como o `::` e `->`, funcionamento da tipagem fraca,  
constantes mágicas e métodos mágicos da linguagem.

---

## 🔹 Operador `::` (Operador de Escopo Estático / Scope Resolution)

Usado para acessar **membros estáticos**, **constantes**, **métodos da classe**,  
e elementos herdados, sem precisar instanciar o objeto.

### Exemplos:

### ✔ Acessando constante de classe
```php
class Produto {
    const TAXA = 0.12;
}

echo Produto::TAXA;

class Utils {
    public static function gerarId() {
        return rand(1, 1000);
    }
}

$id = Utils::gerarId();
echo Produto::class; 

```
###🔹 Operador -> (Acesso a Objetos)

Usado para acessar métodos e propriedades de uma instância.

```php
class Carro {
    public $modelo;

    public function ligar() {
        echo "Ligando...";
    }
}

$uno = new Carro();
$uno->modelo = "Uno Turbo";
$uno->ligar();
```

### 🔹 Tipagem Fraca do PHP

O PHP é fracamente tipado, ou seja:

converte tipos automaticamente

permite atribuir qualquer tipo a uma variável

compara valores de forma "flexível"

Exemplo de conversão automática:
```php
$x = "10";
$y = 2;

echo $x + $y;  // resultado: 12

Cuidado com comparação fraca:
var_dump("10" == 10);   // true
var_dump("10" === 10);  // false (estrito)

Tipagem recomendada (PHP moderno):
function somar(int $a, int $b): int {
    return $a + $b;
}
```

## Constantes Mágicas do PHP

| Constante      | O que retorna                     |
| -------------- | --------------------------------- |
| `__FILE__`     | Caminho COMPLETO do arquivo atual |
| `__DIR__`      | Diretório do arquivo atual        |
| `__LINE__`     | Número da linha atual             |
| `__FUNCTION__` | Nome da função                    |
| `__CLASS__`    | Nome da classe                    |
| `__METHOD__`   | Classe + método                   |

## Métodos Mágicos do PHP

| Método          | Quando é chamado                          |
| --------------- | ----------------------------------------- |
| `__construct()` | Ao criar um objeto                        |
| `__destruct()`  | Ao destruir um objeto                     |
| `__toString()`  | Quando o objeto é convertido para string  |
| `__get()`       | Ao tentar acessar propriedade inexistente |
| `__set()`       | Ao tentar definir propriedade inexistente |
| `__call()`      | Ao chamar método inexistente              |
| `__clone()`     | Quando o objeto é clonado                 |



