# PHP | Exemplo de codigo:

## `POO — Soma com readline() (funciona apenas no terminal/compilador web)`

## Aqui temos 4 valores mais a soma, mais redline e uma interface com dois metodos.

```php
<?php

interface Ver {
    public function somar();
    public function subtracao();
}

class Numeros implements Ver {

    protected float $n1;
    protected float $n2;
    protected float $n3;
    protected float $n4;
    protected float $soma;

    public function __construct(float $n1 = 0, float $n2 = 0, float $n3 = 0, float $n4 = 0) { 
        $this->n1 = $n1;  
        $this->n2 = $n2;
        $this->n3 = $n3;
        $this->n4 = $n4;
        $this->soma = 0;
    }

    public function somar() {
        // Primeiro recebe os números do usuário
        $this->n1 = (float)readline("Insira o 1º número: ");
        $this->n2 = (float)readline("Insira o 2º número: ");
        $this->n3 = (float)readline("Insira o 3º número: ");
        $this->n4 = (float)readline("Insira o 4º número: ");

        // Calcula a soma
        $this->soma = $this->n1 + $this->n2 + $this->n3 + $this->n4;

        echo "Soma: " . $this->soma . PHP_EOL;
    }

    public function subtracao() {
        // Lê os valores do usuário
        $this->n1 = (float)readline("Insira o 1º número: ");
        $this->n2 = (float)readline("Insira o 2º número: ");
        $this->n3 = (float)readline("Insira o 3º número: ");
        $this->n4 = (float)readline("Insira o 4º número: ");

        // Calcula a subtração sequencial
        $resultado = $this->n1 - $this->n2 - $this->n3 - $this->n4;
        echo "Subtração: " . $resultado . PHP_EOL;
    }
}

// Teste
$calc = new Numeros();
$calc->somar();
$calc->subtracao();

?>
````
