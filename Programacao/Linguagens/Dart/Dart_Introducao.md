# Introdução ao Dart

## O que é o Dart?

O **Dart** é uma linguagem de programação criada pelo **Google**, projetada para ser rápida, produtiva e fácil de aprender. O Dart é a linguagem principal usada no desenvolvimento de apps com o **Flutter**, mas também pode ser usado em aplicações de servidor, aplicativos web e até em sistemas de backend.

### Principais Características do Dart:
- **Desempenho**: O Dart é compilado Just-in-Time (JIT) durante o desenvolvimento, o que permite **hot reload**. Quando compilado para produção, o Dart utiliza **compilação Ahead-of-Time (AOT)**, garantindo performance nativa.
- **Sintaxe simples**: O Dart tem uma sintaxe fácil de aprender e lembra outras linguagens como **JavaScript**, **Java** e **C#**.
- **Segurança de tipo**: O Dart é uma linguagem **tipada**, o que ajuda a evitar erros de execução e melhora a qualidade do código.
- **Versatilidade**: O Dart pode ser usado para desenvolver **apps móveis** (com Flutter), **aplicações web**, **back-end** e até mesmo **scripts** e **ferramentas** de linha de comando.

---

## Sintaxe Básica do Dart

### 1. **Variáveis e Tipos**
Dart é uma linguagem **tipada**, o que significa que você pode definir tipos para suas variáveis. Aqui estão alguns exemplos:

```dart
// Tipos básicos
int numero = 10;
double pi = 3.14;
String nome = 'Flutter';

// Variáveis dinâmicas (sem tipo explícito)
var idade = 25; // O tipo será inferido como 'int'

// Constantes
final double altura = 1.75;
const int diasPorSemana = 7;
```

### Funções
```dart
// Função simples
void saudacao() {
  print("Olá, Mundo!");
}

// Função com retorno
String saudacaoComNome(String nome) {
  return "Olá, $nome!";
}

void main() {
  saudacao(); // Chama a função sem retorno
  print(saudacaoComNome("Flutter")); // Chama a função com retorno
}
```

### Controle de Fluxo
```dart
// if/else
int numero = 10;
if (numero > 0) {
  print("Positivo");
} else {
  print("Negativo");
}

// for
for (int i = 0; i < 5; i++) {
  print(i);
}

// while
int contador = 0;
while (contador < 5) {
  print(contador);
  contador++;
}
```

### Classes e Objetos
```dart
class Carro {
  String modelo;
  int ano;

  // Construtor
  Carro(this.modelo, this.ano);

  // Método
  void descricao() {
    print("Modelo: $modelo, Ano: $ano");
  }
}

void main() {
  var meuCarro = Carro('Fusca', 1965);
  meuCarro.descricao();
}
```

### Coleções
```dart
// List (Lista)
List<int> numeros = [1, 2, 3, 4];

// Set (Conjunto)
Set<String> frutas = {'maçã', 'banana', 'laranja'};

// Map (Dicionário)
Map<String, String> contatos = {'João': '1234-5678', 'Maria': '9876-5432'};
```

### Manipulação de Strings
```dart
String saudacao = "Olá, Flutter!";
print(saudacao.toUpperCase()); // "OLÁ, FLUTTER!"
print(saudacao.substring(0, 3)); // "Olá"
print(saudacao.contains("Flutter")); // true
print(saudacao.replaceAll("Flutter", "Dart")); // "Olá, Dart!"
```

### Null Safety
```dart
int? numeroNullable = null; // O tipo pode ser null
String nome = "Dart";

// Verificando valores nulos
if (numeroNullable != null) {
  print(numeroNullable + 10);
}

int numero = 10; // Não pode ser nulo
```

### Operadores Avançados
```dart
var carro = Carro('Fusca', 1965)
  ..descricao()
  ..ano = 1966;
````





