# 🐘 Tutorial sobre PHP 🐘

PHP é uma linguagem de **script do lado do servidor**, usada principalmente para desenvolvimento web dinâmico.  
É **interpretada**, **multiparadigma** e **fracamente tipada**, o que significa que o tipo de variável é definido automaticamente em tempo de execução.

---

## 🤔 Características do PHP

- É **fracamente tipada**, ou seja, não é necessário declarar o tipo da variável.  
- Sempre termina comandos com **`;`**.  
- Pode ser embutida dentro do **HTML**.  
- É executada no **servidor** e retorna **HTML** para o navegador.

---

## 👋 Exemplo de “Hello World”

```php
<?php
echo "Hello World!";
?>
```

## 💡 Tipos de Variáveis

| Tipo | Descrição | Exemplo |
|------|------------|----------|
| `string` | Texto | `"Maria"` |
| `int` | Número inteiro | `25` |
| `float` / `double` | Número decimal | `1.75` |
| `bool` | Verdadeiro ou falso | `true` / `false` |
| `array` | Conjunto de valores | `$arr = [1, 2, 3];` |
| `object` | Objeto (usado em POO) | `new Pessoa();` |
| `null` | Variável sem valor | `NULL` |

## Concatenação: 
```php
echo $nome . " " . $sobrenome; // Ana Silva
```
## Funções em PHP:
```php
function saudacao() {
    
    echo "Olá!";

}
```
## Condições:
```php
$idade = 18;
if ($idade >= 18) {
    echo "Você é maior de idade.";
} else {
    echo "Você é menor de idade.";
}
```
## Switch
```php
$cor = "vermelho";

switch ($cor) {
    case "azul":
        echo "Você escolheu azul!";
        break;
    case "vermelho":
        echo "Você escolheu vermelho!";
        break;
    default:
        echo "Cor não reconhecida.";
}
```

## Array 
```php
$frutas = ["maçã", "banana", "laranja"];
echo $frutas[1]; // Imprime "banana"
```

## Array Associativo( Objeto JS)
```php
$pessoa = [
    "nome" => "Maria",
    "idade" => 25,
    "cidade" => "São Paulo"
];
echo $pessoa["nome"]; // Imprime "Maria"
```

## Comandos Array
```php
// Contar o número de elementos
echo count($frutas);

// Adicionar elemento no final
array_push($frutas, "manga");

// Remover elemento do final
array_pop($frutas);

// Verificar se um valor existe no array
if (in_array("banana", $frutas)) {
    echo "Banana está na lista!";
}
```

## GET e POST
```php
// Exemplo: script.php?nome=Maria
echo $_GET['nome']; // Imprime "Maria"
// Exemplo de um formulário HTML com método POST
<form method="POST" action="script.php">
    <input type="text" name="nome">
    <input type="submit">
</form>

// No script.php
echo $_POST['nome']; // Imprime o nome enviado pelo formulário
```

## Operações Matematicas
```php
$soma = 5 + 3; // 8
$subtracao = 5 - 3; // 2
$multiplicacao = 5 * 3; // 15
$divisao = 5 / 3; // 1.666...
$resto = 5 % 3; // 2 (resto da divisão)
```

