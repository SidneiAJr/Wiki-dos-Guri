# 📍 Ponteiros em C

Os **ponteiros** são uma das partes mais importantes (e poderosas) da linguagem C.  
Eles permitem acessar e manipular **endereços de memória diretamente**, tornando o código mais eficiente e flexível.

---

## 🔹 O que é um Ponteiro?

Um **ponteiro** é uma variável que **guarda o endereço de memória** de outra variável.

```c
int a = 10;
int *ptr = &a; // ptr guarda o endereço de a
```

🧠 Explicando:

a → armazena o valor 10.

&a → obtém o endereço de memória de a.

*ptr → acessa o valor armazenado nesse endereço.

```c
#include <stdio.h>

int main() {
    int x = 5;
    int *p;

    p = &x; // p aponta para x

    printf("Valor de x: %d\n", x);
    printf("Endereco de x: %p\n", &x);
    printf("Valor armazenado em p: %p\n", p);
    printf("Valor apontado por p: %d\n", *p);

    return 0;
}
```

## 🧱 Operadores Importantes

| 🔹 **Operador** | 📝 **Função**                          |
| --------------- | -------------------------------------- |
| `&`             | Retorna o endereço da variável.        |
| `*`             | Acessa o valor armazenado no endereço. |

```c
#include <stdio.h>

void dobrar(int *n) {
    *n = *n * 2;
}

int main() {
    int valor = 10;
    dobrar(&valor);
    printf("Valor dobrado: %d\n", valor);
    return 0;
}
```
| 💡 **Conceito** | 🧾 **Descrição**                              |
| --------------- | --------------------------------------------- |
| `int *p;`       | Declara um ponteiro para inteiro.             |
| `p = &x;`       | Armazena o endereço de `x` em `p`.            |
| `*p`            | Acessa o valor armazenado no endereço de `x`. |

