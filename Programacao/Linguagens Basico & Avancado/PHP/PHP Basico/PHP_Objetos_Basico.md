# PHP – Programação Orientada a Objetos (Básico)

A POO no PHP permite organizar o código em classes e objetos.  
Aqui estão os fundamentos principais.

---

## 🧱 Criando uma Classe e Objeto

```php
class Pessoa {
    public $nome;
    public $idade;

    public function apresentar() {
        return "Olá, eu sou $this->nome e tenho $this->idade anos.";
    }
}

$p = new Pessoa();
$p->nome = "Ana";
$p->idade = 22;

echo $p->apresentar();

````

| Tipo          | Acesso                       |
| ------------- | ---------------------------- |
| **public**    | acessível em qualquer lugar  |
| **protected** | apenas na classe e herdeiros |
| **private**   | apenas na própria classe     |


