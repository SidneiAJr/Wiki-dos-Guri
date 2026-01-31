# 📦 Arrays em PHP – Exemplos Práticos

## 🔹 1. Array Indexado
Lista simples com índices numéricos.

```php
$frutas = ["Maçã", "Banana", "Laranja"];

echo $frutas[1]; // Banana
```

## 2. Array Associativo

```php
$usuario = [
    "nome" => "Carlos",
    "idade" => 23,
    "cidade" => "Curitiba"
];

echo $usuario["nome"];
```

## 3. Array Multidimensional
```php
$produtos = [
    ["nome" => "Mouse", "preco" => 50],
    ["nome" => "Teclado", "preco" => 150]
];

echo $produtos[1]["nome"]; // Teclado
```

## 4. Manipulação com Funções de Arrays
```php
$itens = ["A", "B", "C"];
echo count($itens);
```

## Convertendo String ⇄ Array

```php
$texto = "a,b,c";
$lista = explode(",", $texto);
```

```php
$alunos = [
    [
        "nome" => "João",
        "notas" => [7, 8, 9]
    ],
    [
        "nome" => "Maria",
        "notas" => [10, 9, 8]
    ]
];

echo $alunos[0]["notas"][2]; // 9
```

## Exemplo de Array:
- Exemplo de Array Acessando valores:

````php
<?php

$ar = ["pedro",20,30]; // Array com 3 Valores


for($i=0; $i<count($ar); $i++){ // For para acessar o array e percorrer o tamanho
    echo "Indice $i: ".$ar[$i]." \n"; // Em PHP usa-se count() em vez de length() para arrays
}

?>
````
