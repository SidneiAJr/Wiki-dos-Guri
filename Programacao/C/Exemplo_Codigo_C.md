# Exemplo de Codigo em C:

## Soma de Int com Int
```C
#include <stdio.h>

int main() {
    int a = 5;
    int b = 5;
    int soma = a+b;
    printf("Soma %d \n",soma);
}
```

## Comparação de Int com Double
```C

#include <stdio.h>

int main() {
    int a = 5;
    double b = 5.5;
    int comparador = a == b;
    printf("Comparação %d \n",comparador);
    
}
```

## Compração de Tipos:

```C

#include <stdio.h>
#include <stdbool.h>

int main() {
    double n1 = 5.;
    int n2 = 4;
    float n3 = 5.5;
    bool  n4 = true;
    
    bool comp = n1==n2;
    bool comp2 = n3==n4;
    
    printf("Comparação %d \n",comp);
    printf("Comparação %d \n",comp2);
    
    
}
```

## Loop Para verificar Idade:

```C


#include <stdio.h>
#include <stdbool.h>

int main() {
    char nome[5]= "pedro";
    int idade = 20;
    
    if(idade>=18){
        printf("Pode Entrar|Maior de Idade \n");
    }else{
        printf("Não Pode entrar|Menor de Idade \n");
    }
    
    printf("Olá %s",nome);
    
    
}
```
