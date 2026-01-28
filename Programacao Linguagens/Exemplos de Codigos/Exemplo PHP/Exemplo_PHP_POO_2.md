# PHP | Exemplo de codigo:

- `POO - Programação Orientada a Objeto em PHP`
- Exemplo com uma interface uma classe abstrata e class normal

```php
<?php

interface verificar1{
   public function verificar();
}

abstract class teste implements verificar1{
   protected int $valor;
   protected string $info;

   public function __construct(int $valor, String $info){
    $this->valor = $valor;  
    $this->info = $info;
   }

   public function verificar(){}

}

class teste2 implements verificar1{ 

   protected int $valor;    
   protected string $info;

   public function __construct(int $valor, String $info){
    $this->valor = $valor;
    $this->info = $info;
    }

    public function verificar(){}

}

?>
```
