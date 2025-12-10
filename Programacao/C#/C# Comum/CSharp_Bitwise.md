# BitWise - C#

```C#
using System;  // Importa o namespace System, que contém classes essenciais como Console.

class progdobra {  // Declara a classe 'progdobra'.
    static void Main(){  // Inicia o método Main, que é o ponto de entrada de um programa C#.

        int num = 10;  // Declara a variável 'num' do tipo inteiro e a inicializa com o valor 10.
        
        num = num << 1;  // O operador '<<' realiza um deslocamento de bits à esquerda. 
                         // Isso equivale a multiplicar o valor de 'num' por 2 (10 * 2 = 20).
                         // Agora, 'num' é igual a 20.

        int num2 = 20;  // Declara outra variável 'num2' e a inicializa com o valor 20.

        num = num2 << 2;  // Realiza outro deslocamento de bits à esquerda, mas agora usando 'num2'.
                          // O operador '<<' desloca os bits de 'num2' (20) para a esquerda por 2 posições.
                          // Isso equivale a multiplicar 20 por 4 (20 * 4 = 80).
                          // Agora, 'num' será igual a 80.

        Console.WriteLine(num);  // Imprime o valor de 'num' na tela, que neste ponto é 80.

    }
}
```
