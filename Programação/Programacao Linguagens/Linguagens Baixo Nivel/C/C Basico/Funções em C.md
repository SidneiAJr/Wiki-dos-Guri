# 📌 Definição e chamada de funções

Funções permitem modularizar o código. São blocos que podem ser reutilizados em várias partes do programa.

```C
#include <stdio.h>

void saudacao() {
    printf("Olá, Mundo!\n");
}

int main() {
    saudacao();  // Chama a função
    return 0;
}
```
