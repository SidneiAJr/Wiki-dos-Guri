# C# | Array:

## `Array C#`
```C#
using System;

public class HelloWorld
{
    public static void Main(string[] args)
    {
        int[] array = new int[5];

        for (int i = 0; i < array.Length; i++)
        {
            array[i] = i * 2;
            Console.WriteLine(array[i]);
        }
    }
}

```

##  `Imprimindo na Posição:`
````C#
using System;

class ArrayExemplo
{
    static void Main()
    {
        int[] array = new int[5];

        array[0] = 1;
        array[1] = 10;
        array[2] = 100;
        array[3] = 1000;
        array[4] = 10000;

        // Agora sim: capturar n1 depois de preencher
        int n1 = array[1];

        Console.WriteLine("Array completo:");

        // Imprime todas as posições
        for (int i = 0; i < array.Length; i++)
        {
            Console.WriteLine($"Posição {i}: {array[i]}");
        }

        Console.WriteLine();
        Console.WriteLine("Valor de n1: " + n1);
        Console.WriteLine("Valor da posição 3: " + array[3]);
    }
}

````

- ✔ O que esse exemplo ensina

- Criar arrays em C#

- Acessar valores por índice

- Preencher manualmente

- Imprimir usando for
