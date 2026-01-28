# Controle de Fluxo em C

## 📌 Condicional: if, else if, else

O controle condicional permite executar um bloco de código com base em uma condição.

```C
#include <stdio.h>

int main() {
    int idade = 20;

    if (idade >= 18) {
        printf("Maior de idade\n");
    } else {
        printf("Menor de idade\n");
    }

    return 0;
}
```

## Múltipla escolha: switch

```C
#include <stdio.h>

int main() {
    int opcao = 2;

    switch(opcao) {
        case 1:
            printf("Opção 1\n");
            break;
        case 2:
            printf("Opção 2\n");
            break;
        default:
            printf("Opção inválida\n");
    }

    return 0;
}
```

## 📌 Loops: for, while, do while

```C
#include <stdio.h>

int main() {
    for (int i = 0; i < 5; i++) {
        printf("%d ", i);
    }
    return 0;
}
```

📌 Comandos Especiais

***break: Sai de um loop ou switch.***

***continue: Pula a iteração atual de um loop.***

***return: Retorna um valor de uma função.***
