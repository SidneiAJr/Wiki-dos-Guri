# Exemplo Básico de POO em C#

## `Classe Pessoa com propriedades e métodos`

````C#
using System;

class Program
{
    static void Main(string[] args)
    {
        // Criando objetos
        Pessoa p1 = new Pessoa("Carlos", 25);
        Pessoa p2 = new Pessoa("Ana", 30);

        // Chamando métodos
        p1.Apresentar();
        p2.Apresentar();
    }
}

public class Pessoa
{
    // Propriedades (encapsulamento automático com get e set)
    public string Nome { get; set; }
    public int Idade { get; set; }

    // Construtor
    public Pessoa(string nome, int idade)
    {
        Nome = nome;
        Idade = idade;
    }

    // Método da classe
    public void Apresentar()
    {
        Console.WriteLine($"Olá! Meu nome é {Nome} e eu tenho {Idade} anos.");
    }
}
````

| Conceito     | Onde aparece                  | Explicação                 |
| ------------ | ----------------------------- | -------------------------- |
| Classe       | `public class Pessoa`         | Molde para criar objetos   |
| Propriedades | `Nome`, `Idade`               | Guardam dados do objeto    |
| Construtor   | `Pessoa(string nome...)`      | Executa ao criar o objeto  |
| Objeto       | `Pessoa p1 = new Pessoa(...)` | Instância da classe        |
| Método       | `Apresentar()`                | Ações que o objeto executa |
