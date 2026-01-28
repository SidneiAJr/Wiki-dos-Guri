# Bibliotecas Úteis em C

## <stdio.h> – Entrada e Saída
Funções para trabalhar com entrada e saída de dados.
```C
#include <stdio.h>
int main() {
    printf("Hello, World!\n");  // Saída
    int idade;
    scanf("%d", &idade);  // Entrada
    return 0;
}
```
## <stdlib.h> – Funções gerais
```C
#include <stdio.h>
#include <stdlib.h>

int main() {
    int x = rand() % 10;  // Gera um número aleatório entre 0 e 9
    printf("Número aleatório: %d\n", x);
    return 0;
}
```

## <string.h> – Manipulação de Strings

Funções para manipulação de strings (como copiar, concatenar, comparar).
```C
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "Olá";
    char str2[] = " Mundo!";
    strcat(str1, str2);  // Concatena str2 a str1
    printf("%s\n", str1);  // Saída: Olá Mundo!
    return 0;
}
```
## <math.h> – Funções Matemáticas

Funções para cálculos matemáticos avançados.
```C
#include <stdio.h>
#include <math.h>

int main() {
    double x = sqrt(16);  // Raiz quadrada
    printf("Raiz quadrada de 16 é: %.2f\n", x);
    return 0;
}
```

## <time.h> – Manipulação de Tempo

Funções para manipulação de data e hora.
```C
#include <stdio.h>
#include <time.h>

int main() {
    time_t t;
    time(&t);  // Obtém o tempo atual
    printf("Data e hora atual: %s", ctime(&t));
    return 0;
}
```
