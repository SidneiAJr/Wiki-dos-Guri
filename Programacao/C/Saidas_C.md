# Tutorial de Saídas em C

| Format Specifier | Tipo de dado                       | Exemplo de uso                           | Observação                          |
| ---------------- | ---------------------------------- | ---------------------------------------- | ----------------------------------- |
| `%d`             | Inteiro (`int`)                    | `int x = 10; printf("%d", x);`           | Para valores inteiros               |
| `%f`             | Ponto flutuante (`float`/`double`) | `double pi = 3.14159; printf("%f", pi);` | Por padrão imprime 6 casas decimais |
| `%.2f`           | Ponto flutuante com 2 casas        | `printf("%.2f", pi);`                    | Arredonda e mostra 2 casas decimais |
| `%.3f`           | Ponto flutuante com 3 casas        | `printf("%.3f", pi);`                    | Arredonda e mostra 3 casas decimais |
| `%c`             | Caractere (`char`)                 | `char letra = 'A'; printf("%c", letra);` | Um único caractere                  |
| `%s`             | String (`char[]`)                  | `char str[] = "Olá"; printf("%s", str);` | Para arrays de caracteres           |
| `%p`             | Ponteiro / endereço                | `int *ptr = &x; printf("%p", ptr);`      | Mostra o endereço de memória        |

```C
#include <stdio.h>

int main() {
    int idade = 25;
    double pi = 3.14159;
    char letra = 'A';
    char nome[] = "Maria";

    printf("Idade: %d anos\n", idade);           // Inteiro
    printf("Valor de pi: %f\n", pi);             // Float/Double
    printf("Valor de pi (2 casas): %.2f\n", pi); // Float com 2 casas
    printf("Valor de pi (3 casas): %.3f\n", pi); // Float com 3 casas
    printf("Letra: %c\n", letra);                // Caractere
    printf("Nome: %s\n", nome);                  // String
    printf("Endereço de idade: %p\n", &idade);   // Endereço de memória

    return 0;
}
```
