
# 💻 Tutorial Básico de C

🎯 Objetivo

Aprender a criar programas em C, entender tipos de variáveis, operadores, controle de fluxo e funções.

```C
#include <stdio.h>  // Biblioteca padrão de entrada/saída

int main() {
    printf("Olá, mundo!\n");  // Exibe mensagem na tela
    return 0;                  // Indica que o programa terminou corretamente
}
```

## Tipos de Variáveis

| Tipo                  | Descrição              | Exemplo de Valor        | Tamanho Aproximado |
| --------------------- | ---------------------- | ----------------------- | ------------------ |
| `int`                 | Número inteiro         | `10`, `-5`              | 4 bytes            |
| `float`               | Número decimal simples | `3.14`, `-0.5`          | 4 bytes            |
| `double`              | Número decimal duplo   | `2.71828`               | 8 bytes            |
| `char`                | Um caractere           | `'A'`, `'z'`            | 1 byte             |
| `bool` (C99: `_Bool`) | Verdadeiro ou falso    | `1` (true), `0` (false) | 1 byte             |

## Entrada e Saída

```C
#include <stdio.h>
int main() {
    int idade;
    printf("Digite sua idade: ");
    scanf("%d", &idade);  // & indica o endereço da variável
    printf("Você tem %d anos\n", idade);
    return 0;
}
```

## If / Else

```C
int x = 10;
if (x > 5) {
    printf("Maior que 5\n");
} else {
    printf("Menor ou igual a 5\n");
}
```

## LOOP

```C
for(int i = 0; i < 5; i++) {
    printf("%d\n", i);
}
```

## Funções

```C
#include <stdio.h>

int soma(int a, int b) {
    return a + b;
}

int main() {
    int resultado = soma(5, 3);
    printf("Resultado: %d\n", resultado);
    return 0;
}
```
