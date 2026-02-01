# Exemplo de POO em C#

- Inclui:

- Interface

- Classe Abstrata

- Classe Comum

- Herança

- Polimorfismo

## Interface — IAtacante

```C#
public interface IAtacante
{
    void Atacar();
}
````

## Classe Abstrata — Personagem

```C#
public abstract class Personagem
{
    public string Nome { get; set; }
    public int Nivel { get; set; }

    public Personagem(string nome, int nivel)
    {
        Nome = nome;
        Nivel = nivel;
    }

    public void ExibirInfo()
    {
        Console.WriteLine($"{Nome} | Nível {Nivel}");
    }

    // Método obrigatório para todos os personagens
    public abstract void Especial();
}
````

## Classe Comum (concreta) — Mago

```C#
public class Mago : Personagem, IAtacante
{
    public double PoderMagico { get; set; }

    public Mago(string nome, int nivel, double poderMagico)
        : base(nome, nivel)
    {
        PoderMagico = poderMagico;
    }

    public void Atacar()
    {
        Console.WriteLine($"{Nome} lança uma bola de fogo!");
    }

    public override void Especial()
    {
        Console.WriteLine($"{Nome} usa sua magia suprema! Poder: {PoderMagico}");
    }
}
````

## Outra Classe Concreta — Guerreiro

```C#
public class Guerreiro : Personagem, IAtacante
{
    public int Forca { get; set; }

    public Guerreiro(string nome, int nivel, int forca)
        : base(nome, nivel)
    {
        Forca = forca;
    }

    public void Atacar()
    {
        Console.WriteLine($"{Nome} desfere um corte poderoso!");
    }

    public override void Especial()
    {
        Console.WriteLine($"{Nome} ativa FÚRIA GUERREIRA! Força: {Forca}");
    }
}
````

## Classe Program — Testando tudo

```C#
class Program
{
    static void Main(string[] args)
    {
        Mago mago = new Mago("Eldrin", 12, 850.5);
        Guerreiro g = new Guerreiro("Thorgar", 10, 120);

        // Exemplo de uso
        mago.ExibirInfo();
        mago.Atacar();
        mago.Especial();

        Console.WriteLine();

        g.ExibirInfo();
        g.Atacar();
        g.Especial();
    }
}
````

## Como entender isso ?

| Conceito            | Onde aparece             | Explicação                                |
| ------------------- | ------------------------ | ----------------------------------------- |
| **Interface**       | `IAtacante`              | Obriga classes a implementarem `Atacar()` |
| **Classe Abstrata** | `Personagem`             | Base que não pode ser instanciada         |
| **Classe Concreta** | `Mago`, `Guerreiro`      | Classes reais que podem ser criadas       |
| **Herança**         | `Mago : Personagem`      | Mago herda atributos e métodos            |
| **Polimorfismo**    | Override de `Especial()` | Cada classe faz o método do seu jeito     |





