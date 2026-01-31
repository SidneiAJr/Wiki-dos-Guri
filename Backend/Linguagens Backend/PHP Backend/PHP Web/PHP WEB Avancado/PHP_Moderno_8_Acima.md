# ⭐ SINTAXE MODERNA DO PHP 8 

## 1. Operador Nullsafe

Permite acessar propriedades e métodos de algo que pode ser nulo sem causar erro. Caso algum item da cadeia seja nulo, o resultado final vira nulo automaticamente.

## 2. Operador de Fusão Nula

Retorna o primeiro valor que não é nulo entre duas opções. Geralmente usado para valores padrão.

## 3. Atribuição com Fusão Nula

Atribui um valor a uma variável somente se ela for nula. Evita ifs desnecessários.

## 4. Match Expression

Substitui o switch com uma sintaxe mais compacta, segura, rápida e que exige correspondência exata. Pode retornar valores diretamente.

## 5. Tipos de União

Permite que um parâmetro ou retorno aceite dois ou mais tipos diferentes. Ajuda muito na tipagem forte do PHP moderno.

## 6. Argumentos Nomeados

Permite informar parâmetros pelo nome ao invés da ordem, deixando as chamadas mais claras e flexíveis.

## 7. Promoção de Propriedade no Construtor

Reduz o código repetitivo ao declarar propriedades e atribuí-las no construtor, fazendo isso direto na assinatura.

## 8. Tipo de Retorno “static”

Permite que métodos retornem uma instância da classe exata que chamou o método, útil em heranças.

## 9. Weak Maps

Estruturas especiais que armazenam objetos sem impedir que sejam removidos da memória. Usado para caches leves.

## 10. Atributos (Annotations Modernas)

Marcadores nativos embutidos no código, usados por frameworks para fornecer metadados de forma clara, substituindo comentários @annotation antigos.

## 11. Funções Arrow

Funções anônimas muito mais curtas, usadas especialmente em callbacks e transformações rápidas.

## 12. Novos Tipos (mixed, false, never)

O PHP ganhou tipos mais específicos:

“mixed”: qualquer tipo

“false”: literal

“never”: indica funções que nunca retornam normalmente

## 13. Melhoria em Exceptions Internas

Erros internos que antes eram “erros fatais” agora podem ser tratados como exceções.

## 14. Regex mais avançado e rápido

O PHP 8 incorporou melhorias no sistema de expressões regulares, tornando buscas e validações mais eficientes.

## 15. JIT (Just-In-Time Compiler)

Grande avanço de performance que torna cálculos e operações pesadas mais rápidas.

# Exemplo:

# ⚡ Exemplos de Sintaxe Moderna do PHP 8

## 1. Nullsafe Operator
```php
$resultado = $usuario?->endereco?->cidade;
```
## 2. Null Coalescing (??)
```php
$nome = $input ?? "Visitante";
```
## 3. Null Coalescing Assignment (??=)
```php
$config["tema"] ??= "escuro";
```
## 4. Match Expression
```php
$statusMsg = match ($status) {
    200 => "OK",
    404 => "Não encontrado",
    default => "Erro desconhecido",
};
```
## 5. Union Types
```php
function soma(int|float $n) {
    return $n + 10;
}
```
## 6. Named Arguments
```php
alerta(
    titulo: "Erro",
    mensagem: "Algo aconteceu",
    urgente: true
);
```
## 7. Constructor Property Promotion
```php
class Usuario {
    public function __construct(
        public string $nome,
        public int $idade
    ) {}
}
```
## 8. Static Return Type
```php
class A {
    public function criar(): static {
        return new static();
    }
}
```
## 9. WeakMap
```php
$map = new WeakMap();
$map[$objeto] = "dados";
```

## 10. Atributos (Attributes)
```php
#[Tabela("usuarios")]
class Usuario {}
```

## 11. Arrow Functions
```php
$dobro = fn($n) => $n * 2;
```

## 12. Tipo never
```php
function parar(): never {
    exit;
}
```





