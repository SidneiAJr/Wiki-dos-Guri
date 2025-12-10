# var_dump() – O que é e Para que Serve
## 📌 O que é var_dump()

var_dump() é uma função nativa do PHP utilizada para debug, exibindo informações detalhadas sobre variáveis.
Ela mostra:

Tipo do dado (string, int, array, object, bool, etc.)

Tamanho (quando aplicável)

Valor completo da variável

É muito mais detalhada que echo ou print_r().

## 📌 Para que Serve

Inspecionar variáveis em tempo de execução

Ver estrutura completa de arrays e objetos

Confirmar tipos corretamente

Descobrir falhas de lógica no código

Debugar APIs, formulários, dados de banco, sessões e muito mais

## 📌 Exemplo de Código
```php
<?php
$dados = [
    "nome" => "João",
    "idade" => 25,
    "ativo" => true,
    "skills" => ["PHP", "Laravel", "MySQL"]
];

var_dump($dados);
```
