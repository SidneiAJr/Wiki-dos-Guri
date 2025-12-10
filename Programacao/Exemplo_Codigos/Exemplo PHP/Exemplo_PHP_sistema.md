# PHP | Exemplo de Mini Sistema:

```php
<?php

function soma(){
    $n1 = (float)readline("Insira Um Numero: \n");
    $n2 = (float)readline("Insira Um Numero: \n");
    $soma = $n1 + $n2;
    echo sprintf("Soma: %.2f ", $soma);
}

function div(){
    $n1 = (float)readline("Insira Um Numero: \n");
    $n2 = (float)readline("Insira Um Numero: \n");
    $div = $n1 / $n2;
    echo sprintf("Divisão: %.2f", $div);
}

function menu(){
    $opcao = (int) readline("Selecione uma Opção: \n 1-Soma \n 2-Divição");
    switch($opcao){
       case 1;
       soma();
       break;
       case 2;
       div();
       break;
       default:
       echo sprintf("", $opcao);
    }
}
menu();

?>
```
