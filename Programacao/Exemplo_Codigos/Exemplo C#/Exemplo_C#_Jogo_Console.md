# Exemplo C# – POO (Personagem / Inimigo / Jogo)

## `📌 Descrição`

Pequeno exemplo de um sistema simples de jogo utilizando Programação Orientada a Objetos (POO) em C#.

- `Ele demonstra:`

- `Criação de classes`

- `Construtores`

- `Atributos`

- `Métodos`

- `Interação entre objetos`

## Classe Personagem

```C#
using System;

class Personagem
{
    // Atributos: variáveis que caracterizam o objeto
    public string nome;
    public int forca;
    public double rouboVida;
    public int vida;
    public double velAtaque;

    // Método que representa uma ação do personagem
    public void Atacar()
    {
        Console.WriteLine($"Personagem {nome} ataca com força {forca}, " +
        $"velocidade de ataque {velAtaque}, e roubo de vida {rouboVida}");
    }

    public void Andar()
    {
        Console.WriteLine($"{nome} está andando em direção ao monstro");
    }

    // Construtor: define como o objeto é criado
    public Personagem(string nomePersonagem, int forcaInicial, int vidaInicial, double velAtaque2, double roubo)
    {
        nome = nomePersonagem;
        forca = forcaInicial;
        vida = vidaInicial;
        velAtaque = velAtaque2;
        rouboVida = roubo;
    }
}

```

## Classe Inimigo

```java
class Inimigo
{
    public string nome;
    public int forca;
    public int vida;
    public string tipo;

    public void Atacar(Personagem meuPersonagem)
    {
        meuPersonagem.vida -= forca;
        Console.WriteLine($"O inimigo do tipo {tipo} ataca o personagem {meuPersonagem.nome}, " +
        $"reduzindo sua vida para {meuPersonagem.vida} pontos");
    }

    public void Andar()
    {
        Console.WriteLine($"{nome} está se movendo...");
    }

    public Inimigo(string nomeInimigo, int forcaInicial, int vidaIni)
    {
        tipo = "Monstro";
        nome = nomeInimigo;
        forca = forcaInicial;
        vida = vidaIni; // Corrigi o bug: antes estava invertido
    }
}
```

## Classe Jogo

```java
class Jogo
{
    static void Main(string[] arg)
    {
        // Criar um personagem
        Personagem personagem1 = new Personagem("Dama Vermelha", 5, 100, 0.45, 0.75);
        personagem1.Atacar();
        personagem1.Andar();

        // Criar um inimigo
        Inimigo inimigo1 = new Inimigo("Monstro", 5, 400);
        inimigo1.Atacar(personagem1);
        inimigo1.Andar();
    }
}
```

## Diferença entre Classe, Interface e Classe Abstrata (C#)

| Tipo                | Pode ter implementação? | Pode instanciar? | Pode ter atributos?               | Pode ter métodos abstratos?             | Pode herdar de mais de um?       |
| ------------------- | ----------------------- | ---------------- | --------------------------------- | --------------------------------------- | -------------------------------- |
| **Classe**          | ✔️ Sim                  | ✔️ Sim           | ✔️ Sim                            | ❌ Não (exceto virtual/override)         | ❌ Não                            |
| **Classe Abstrata** | ✔️ Sim                  | ❌ Não            | ✔️ Sim                            | ✔️ Sim                                  | ❌ Não                            |
| **Interface**       | ❌ Não (só assinatura)   | ❌ Não            | ❌ Não (só propriedades sem corpo) | ✔️ Sim (todos são abstratos por padrão) | ✔️ Sim (pode implementar várias) |
