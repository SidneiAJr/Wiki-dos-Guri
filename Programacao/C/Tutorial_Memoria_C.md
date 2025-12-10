# 🧠 Tutorial de Memória em C

## 🎯 Objetivo

Aprender como a memória funciona em C, incluindo variáveis, ponteiros e alocação dinâmica, conceitos essenciais para programação avançada e sistemas operacionais.

## Tipos de Variáveis e Memória

C organiza a memória em 3 partes principais:

***Stack (pilha) – para variáveis locais.***

***Heap (monte) – para memória alocada dinamicamente.***

***Data segment – para variáveis globais e estáticas.***

```C
#include <stdio.h>

int global = 100; // Data segment

int main() {
    int local = 50; // Stack
    printf("Global: %d, Local: %d\n", global, local);
    return 0;
}

```

Ponteiros (o coração da memória em C)

Um ponteiro é uma variável que guarda o endereço de memória de outra variável.
```C
#include <stdio.h>

int main() {
    int x = 10;
    int *ptr = &x;  // &x é o endereço de x
    printf("Valor de x: %d\n", *ptr); // *ptr acessa o valor
    printf("Endereço de x: %p\n", ptr);
    return 0;
}
```

*ptr → valor no endereço.

&x → endereço de x.

## Alocação Dinâmica (Heap)
```C
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr = (int*)malloc(sizeof(int)); // aloca memória para 1 int
    if(ptr == NULL) {
        printf("Falha na alocação de memória!\n");
        return 1;
    }

    *ptr = 42; // armazena valor
    printf("Valor alocado: %d\n", *ptr);

    free(ptr); // libera memória
    return 0;
}
```

## Arrays e Ponteiros

Arrays e ponteiros estão intimamente ligados:
```C
#include <stdio.h>

int main() {
    int arr[3] = {1, 2, 3};
    int *ptr = arr; // arr é o endereço do primeiro elemento

    for(int i = 0; i < 3; i++) {
        printf("%d ", *(ptr + i)); // acesso via ponteiro
    }
    return 0;
}
```
