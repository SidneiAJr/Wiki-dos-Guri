# PHP | Soma Basico:

## `Exemplo de codigo PHP | Multiplicação com casa decimal`

```php
<?php

$n1 = (float)5.5;
$n2 = (float)5.5;
$n3 = (float)5.5;

$n4 = (double)5.75;
$n5 = (double)5.75;
$n6 = (double)2.55;


$soma2 = $n4 + $n3 + $n4 + $n5;

$soma = $n1 + $n2 + $n3;

$mult = $soma2 * $n4 + $n5;

$div = $n1 / $n2;

$sub = $soma2 - $n3 - $n4;

print "Soma: ".$soma."\n" ;
print "Soma: ".$soma2."\n" ;
echo sprintf("Multiplicação: %.2f\n",$mult);
print "Subtração: ".$sub."\n";

?>
````


