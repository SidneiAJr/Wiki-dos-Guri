# PHP | Programação Orientada a Objeto:

## Nesse codigo Vemos `Uma classe Abstrata | Uma Classe comum | e uma Interface`.

- ### `Dois Metodos ver e ver2`.

```php
<?php

interface verifica{
    public function ver();
    public function ver2();
}

abstract class informacao implements verifica{
     protected string $nomePersonagem;
     protected int $idadePersonagem;
     protected string $classe;

     protected float $velocidadeAtaque;

     protected int $vida;

     protected float $buff;
    
     public function ver()
     {
        echo "Classe: " . $this->classe . " | Vida: " . $this->vida . " HP\n";
     }

     public function ver2(){
        echo "Nome do personagem: " . $this->nomePersonagem . " | Idade: " . $this->idadePersonagem . "\n";
     }
}

class personagem extends informacao{
     public function __construct($nome, $idade, $classe, $vida) {
        $this->nomePersonagem = $nome;
        $this->idadePersonagem = $idade;
        $this->classe = $classe;
        $this->vida = $vida;
    }
}

$teste = new personagem("Albertao O Guerreiro",20,"Guerreiro",200);
$teste->ver();
$teste->ver2();

?>
```
