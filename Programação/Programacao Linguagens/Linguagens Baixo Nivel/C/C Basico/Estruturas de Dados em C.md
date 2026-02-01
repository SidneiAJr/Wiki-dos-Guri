# Estruturas de Dados em C

## Arrays

Vetores ou arrays são usados para armazenar coleções de dados do mesmo tipo.
```C
#include <stdio.h>

int main() {
    int numeros[] = {1, 2, 3, 4, 5};
    
    for(int i = 0; i < 5; i++) {
        printf("%d ", numeros[i]);
    }
    return 0;
}
```

```C
#include <stdio.h>

struct Pessoa {
    char nome[50];
    int idade;
};

int main() {
    struct Pessoa p1 = {"Pedro", 25};
    
    printf("Nome: %s, Idade: %d\n", p1.nome, p1.idade);
    return 0;
}
```

## enum (enumeration)

```C
#include <stdio.h>

enum Dias {Domingo, Segunda, Terca, Quarta, Quinta, Sexta, Sabado};

int main() {
    enum Dias hoje = Quarta;
    printf("Hoje é o dia número: %d\n", hoje);
    return 0;
}
```

## typedef

```C
#include <stdio.h>

typedef unsigned int uint;

int main() {
    uint x = 10;
    printf("Valor: %u\n", x);
    return 0;
}
```

