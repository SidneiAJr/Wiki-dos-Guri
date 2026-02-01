# Entrada de Dados em C
| Função    | Uso                                      | Exemplo                                  |
| --------- | ---------------------------------------- | ---------------------------------------- |
| `scanf`   | Lê números ou strings sem espaços        | `int idade; scanf("%d", &idade);`        |
| `fgets`   | Lê uma linha inteira (inclusive espaços) | `char nome[50]; fgets(nome, 50, stdin);` |
| `getchar` | Lê um único caractere                    | `char letra = getchar();`                |

```C
#include <stdio.h>

int main() {
    int idade;
    char nome[50];

    printf("Digite sua idade: ");
    scanf("%d", &idade);  // leitura de inteiro

    getchar(); // limpa o '\n' que ficou no buffer

    printf("Digite seu nome: ");
    fgets(nome, 50, stdin); // leitura de string com espaços

    printf("Olá %sVocê tem %d anos.\n", nome, idade);

    return 0;
}
```
## 📌 Evitando erros de entrada

Sempre especifique o tamanho do buffer em fgets para evitar buffer overflow.

Use getchar() para limpar o caractere de nova linha deixado por scanf.

Nunca use gets() — é inseguro e causa overflow.

