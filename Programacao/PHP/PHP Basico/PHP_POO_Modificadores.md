# PHP | Modificadores de Acesso (public, private, protected)

Controlam quem pode acessar métodos e propriedades.

### public

Acessível em qualquer lugar.
````php
class Teste {
    public public $x = 10;
}
````
### private

Só pode ser acessado dentro da própria classe.
````php
class Segredo {
    private $codigo = "123";

    private function mostrar() {
        return $this->codigo;
    }
}
````
### protected

Pode ser acessado:

dentro da classe

por classes filhas (herança)
````php
class Pai {
    protected $nome = "João";
}

class Filho extends Pai {
    public function mostrarNome() {
        return $this->nome;
    }
}
````
