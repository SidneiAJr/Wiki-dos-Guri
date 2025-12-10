# 🧠 Programação Orientada a Objetos em C++

A **Programação Orientada a Objetos (POO)** é um dos pilares do desenvolvimento moderno.  
Em C++, ela permite **organizar o código em classes e objetos**, tornando programas mais **modulares, reutilizáveis e fáceis de manter**.

---

## 🧩 1️⃣ O que é uma Classe e um Objeto?

- **Classe**: É um modelo ou molde que define atributos (variáveis) e comportamentos (métodos).  
- **Objeto**: É uma instância (exemplo real) de uma classe.

### Exemplo básico:

```cpp
#include <iostream>
using namespace std;

class Pessoa {
public:
    string nome;
    int idade;

    void apresentar() {
        cout << "Olá, meu nome é " << nome << " e tenho " << idade << " anos." << endl;
    }
};

int main() {
    Pessoa p1;
    p1.nome = "Ana";
    p1.idade = 25;
    p1.apresentar();

    return 0;
}
