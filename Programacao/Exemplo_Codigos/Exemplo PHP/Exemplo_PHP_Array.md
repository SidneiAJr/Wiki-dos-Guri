# PHP | ARRAY(MAP,SET,MAP)

## `Array Comum`:

````php
$numeros = [10, 20, 30, 40];

foreach ($numeros as $i => $valor) {
    echo "Posição $i: $valor\n";
}
````

## `SET`

````php
$tecnologias = ["Java", "Python", "Java"]; 
$set = array_unique($tecnologias);

print_r($set);
````

## `MAP`

````php
Map<String, Double>
$magos = [
    "Eldrin" => 750.0,
    "Mira"   => 920.0,
    "Thalos" => 860.3
];

// Atualizando valor
$valorAntigo = $magos["Eldrin"];
$magos["Eldrin"] = 800.0;

// Acessando valor
$poderMira = $magos["Mira"];

foreach ($magos as $nome => $poder) {
    echo "Mago: $nome | Poder: $poder\n";
}

echo "Poder de Mira: $poderMira\n";
echo "Poder antigo de Eldrin: $valorAntigo\n";
echo "Poder atual de Eldrin: ".$magos["Eldrin"]."\n";
echo "Quantidade de magos: ".count($magos)."\n";

````

## `QUADRO COMPARATIVO — PHP vs Java`

| Estrutura        | Java                    | PHP                               | Observação                       |
| ---------------- | ----------------------- | --------------------------------- | -------------------------------- |
| **Array**        | Tamanho fixo            | Dinâmico                          | PHP é mais flexível              |
| **ArrayList**    | `ArrayList`             | Array normal                      | PHP não precisa de classe        |
| **Set**          | `HashSet`               | `array_unique()` ou extensão `ds` | PHP não possui Set nativo        |
| **Map**          | `HashMap`               | Array associativo                 | Chaves podem ser strings ou ints |
| **Map de Array** | `Map<String, double[]>` | Array dentro de array             | Igual                            |
| **Map de Lista** | `Map<String, List>`     | Array dentro de array             | Igual                            |

