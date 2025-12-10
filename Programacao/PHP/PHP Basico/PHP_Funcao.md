# PHP | Tutorial de Função:

# 🧩 Tipos de Funções em PHP

Em PHP, as funções podem ser definidas de várias maneiras, dependendo do contexto e do comportamento desejado. Abaixo, veremos os principais tipos de funções em PHP.

---

## 📥 `Função Simples`

Uma **função simples** é aquela que é definida para executar uma tarefa específica e não recebe parâmetros ou retorna valores, ou então pode retornar um valor simples.

### Exemplo:

```php
function saudacao() {
    echo "Olá, mundo!";
}
saudacao(); // Chama a função e exibe "Olá, mundo!"
```

### `Função com Parâmetros`:
- Funções com parâmetros são aquelas que recebem valores externos para serem processados dentro delas.

```php
function somar($a, $b) {
    return $a + $b;
}

$resultado = somar(5, 3); // Chama a função com os parâmetros 5 e 3
echo $resultado; // Exibe "8"
```
---

### `Função com Valor Padrão`:

- Você pode definir um valor padrão para os parâmetros de uma função. Isso significa que, se o parâmetro não for passado ao chamar a função, o valor padrão será utilizado.

Exemplo:

```php
function saudacao($nome = "Visitante") {
    echo "Olá, $nome!";
}

saudacao("João");  // Exibe "Olá, João!"
saudacao();        // Exibe "Olá, Visitante!" (valor padrão)
```
---

### `Função Anônima (Função Lambda)`
- Funções anônimas, também conhecidas como funções lambda, são funções sem nome. Elas podem ser atribuídas a variáveis e passadas como parâmetros para outras funções.
```php
$soma = function($a, $b) {
    return $a + $b;
};

echo $soma(2, 3); // Exibe "5"
```

### `Função Recursiva`
- Funções recursivas são aquelas que se chamam a si mesmas. Elas são úteis para resolver problemas de repetição ou divisão, como cálculo de fatorial.
```php
function fatorial($n) {
    if ($n == 0) {
        return 1;
    }
    return $n * fatorial($n - 1);
}

echo fatorial(5); // Exibe "120" (5 * 4 * 3 * 2 * 1)
```

### `Função com Retorno`
- Funções podem retornar valores que podem ser utilizados em outras partes do código. O comando return é utilizado para enviar de volta um valor da função.
```php
  function multiplicar($a, $b) {
    return $a * $b;
}

$resultado = multiplicar(4, 5); // Chama a função e armazena o retorno
echo $resultado; // Exibe "20"
```

### `Função Variádica`
- Funções variádicas são aquelas que podem receber um número variável de argumentos. No PHP, isso é feito usando o operador ....
```php
function somarTodos(...$numeros) {
    return array_sum($numeros);
}

echo somarTodos(1, 2, 3, 4); // Exibe "10"
echo somarTodos(5, 10);      // Exibe "15"
```

### `Funções de Callback`
- Funções de callback são funções passadas como argumento para outras funções. São úteis para definir comportamentos personalizados em funções padrão.
```php
function executarCallback($funcao) {
    $funcao();  // Chama a função passada como argumento
}

executarCallback(function() {
    echo "Função de Callback!";
}); // Exibe "Função de Callback!"
```

| Tipo de Função            | Parâmetros                        | Retorno        | Exemplos de Uso                                  |
| ------------------------- | --------------------------------- | -------------- | ------------------------------------------------ |
| `Função Simples`          | ❌ Nenhum                          | ❌ Não retorna  | Função de exibição simples                       |
| `Função com Parâmetros`   | ✅ Recebe valores                  | ✅ Retorna algo | Cálculos ou processamento                        |
| `Função com Valor Padrão` | ✅ Com valor padrão                | ✅ Retorna algo | Funções com parâmetros opcionais                 |
| `Função Anônima`          | ✅ Recebe valores                  | ✅ Retorna algo | Funções rápidas e flexíveis                      |
| `Função Recursiva`        | ✅ Recebe valores                  | ✅ Retorna algo | Cálculos de estrutura repetitiva (como fatorial) |
| `Função com Retorno`      | ✅ Recebe valores                  | ✅ Retorna algo | Execução e processamento de valores              |
| `Função Variádica`        | ✅ Números variáveis de parâmetros | ✅ Retorna algo | Funções que recebem muitos parâmetros            |
| `Funções de Callback`     | ✅ Função passada como parâmetro   | ✅ Retorna algo | Definir comportamentos personalizados            |

