# 🧠 Introdução ao C++

C++ é uma linguagem poderosa, de alto desempenho e controle total sobre memória — essencial no desenvolvimento de **jogos, sistemas embarcados e engines**.

| Tipo | Descrição | Exemplo de Valor | Tamanho Aproximado |
|------|------------|------------------|--------------------|
| `int` | Números inteiros | `10`, `-5`, `2000` | 4 bytes |
| `float` | Números decimais de precisão simples | `3.14`, `-0.5` | 4 bytes |
| `double` | Números decimais de precisão dupla | `2.718281828` | 8 bytes |
| `char` | Um único caractere | `'A'`, `'z'`, `'1'` | 1 byte |
| `bool` | Verdadeiro ou falso | `true`, `false` | 1 byte |
| `string` | Conjunto de caracteres (texto) | `"Olá mundo"` | variável |
| `long` | Inteiro longo (valores grandes) | `1234567890` | 8 bytes |
| `short` | Inteiro curto (valores pequenos) | `-100`, `250` | 2 bytes |

---

## 📦 Estrutura básica de um programa C++

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Olá, C++!" << endl;
    return 0;
}
```

## 🧩 Explicação:

#include <iostream> → adiciona a biblioteca de entrada/saída

- using namespace std; → permite usar cout, cin, endl sem prefixo

- int main() → ponto de entrada do programa

- cout → saída (exibe informações no console)

- endl → quebra de linha

- return 0 → encerra o programa com sucesso

```cpp
int a = 10, b = 5;
cout << a + b << endl; // soma
cout << a - b << endl; // subtração
cout << a * b << endl; // multiplicação
cout << a / b << endl; // divisão
cout << a % b << endl; // resto
```

## IF/Else
```cpp
if (a > b) {
    cout << "A é maior que B" << endl;
} else {
    cout << "B é maior ou igual a A" << endl;
}
```
## 🔹 `for` — Contador com início e fim definidos

```cpp
for (int i = 0; i < 5; i++) {
    cout << "Valor de i: " << i << endl;
}
```
## 🔹 while — Executa enquanto a condição for verdadeira

int contador = 0;
```cpp
while (contador < 3) {
    cout << "Contador: " << contador << endl;
    contador++;
}
```

## 🔹 Estrutura de uma Função
```cpp
tipo_retorno nome_da_funcao(parâmetros) {
    // código
    return valor; // opcional
}
```


