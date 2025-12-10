# 💻 Introdução ao C#

C# (C-Sharp) é uma linguagem de programação moderna, orientada a objetos, criada pela Microsoft.  
Muito usada em aplicações .NET e também amplamente empregada no desenvolvimento de jogos com a engine Unity.

---

## 📁 Repositórios com C#

![Dev Jogos](https://github.com/SidneiAJr/Documentacao_Linguagens/blob/main/prints/1.PNG)

---

## 🧩 Exemplo de Código — Unity

![Exemplo de código](https://github.com/SidneiAJr/Documentacao_Linguagens/blob/main/prints/2.PNG)

---

## 📦 Tipos de Variáveis em C#

| Tipo      | Descrição                                 | Exemplo                  |
|-----------|-------------------------------------------|--------------------------|
| `int`     | Número inteiro                            | `int idade = 25;`        |
| `double`  | Número decimal (alta precisão)            | `double pi = 3.14;`      |
| `float`   | Número decimal (menos preciso, usa `f`)   | `float peso = 70.5f;`    |
| `decimal` | Número decimal (usado em finanças)        | `decimal valor = 10.5m;` |
| `char`    | Um único caractere (entre aspas simples)  | `char letra = 'A';`      |
| `string`  | Conjunto de caracteres (texto)            | `string nome = "Ana";`   |
| `bool`    | Verdadeiro ou falso (booleano)            | `bool ativo = true;`     |
| `var`     | Tipo inferido automaticamente             | `var idade = 30;`        |
| `object`  | Tipo genérico base de todos os tipos      | `object x = "texto";`    |

---

## ⚖️ Operadores de Comparação

```csharp
int n1 = 5;
int n2 = 10;

Console.WriteLine(n1 == n2); // Igualdade
Console.WriteLine(n1 != n2); // Diferente
Console.WriteLine(n1 > n2);  // Maior que
Console.WriteLine(n1 < n2);  // Menor que
Console.WriteLine(n1 >= n2); // Maior ou igual
Console.WriteLine(n1 <= n2); // Menor ou igual
```
## Array (Tamanho Fixo)

// Array de inteiros com 5 elementos
```C#
int[] arrayInt = new int[5] { 1, 2, 3, 4, 5 };  // Declaração e inicialização do array

// Array de doubles com 5 elementos
double[] arrayDouble = new double[5] { 1.1, 2.2, 3.3, 4.4, 5.5 };  // Declaração e inicialização do array

- int[,] matriz = new int[2, 3]  // Declara um array de 2 linhas e 3 colunas
{
    { 1, 2, 3 },
    { 4, 5, 6 }
};

Console.WriteLine(matriz[0, 0]);  // Saída: 1
Console.WriteLine(matriz[1, 2]);  // Saída: 6
```
# 📚 Comandos com Arrays e List<T> em C#

---

## 🧮 Arrays

| 🧩 Ação | 🧠 Comando / Exemplo |
|---------|----------------------|
| **Declarar e Inicializar** | `int[] numeros = new int[3] { 1, 2, 3 };` |
| **Acessar Elemento** | `numeros[0]; // 1` |
| **Modificar Elemento** | `numeros[1] = 10;` |
| **Tamanho do Array** | `numeros.Length;` |
| **Redimensionar Array** | `Array.Resize(ref numeros, 5);` |
| **Copiar Array** | `int[] copia = (int[])numeros.Clone();` |
| **Copiar com CopyTo** | `numeros.CopyTo(copia, 0);` |
| **Obter Índice Máximo** | `numeros.GetUpperBound(0);` |

---

## 🧩 List<T>

| 🧩 Ação | 🧠 Comando / Exemplo |
|---------|----------------------|
| **Criar e Inicializar Lista** | `List<int> lista = new List<int> { 1, 2, 3 };` |
| **Adicionar Elemento** | `lista.Add(4);` |
| **Inserir Elemento em Posição** | `lista.Insert(1, 99);` |
| **Remover Elemento (por valor)** | `lista.Remove(2);` |
| **Remover por Índice** | `lista.RemoveAt(0);` |
| **Limpar Lista** | `lista.Clear();` |
| **Verificar se Contém Item** | `lista.Contains(3);` |
| **Obter Índice de Item** | `lista.IndexOf(3);` |
| **Ordenar Lista** | `lista.Sort();` |
| **Inverter Lista** | `lista.Reverse();` |
| **Iterar com ForEach** | `lista.ForEach(x => Console.WriteLine(x));` |

---

💡 **Dica:**  
- Use **Array** quando o tamanho for fixo.  
- Use **List<T>** quando precisar adicionar/remover elementos dinamicamente.  


## Condicao:
```C#
if(n1===n2){
    console.log("Não e Igual")
}else{
    console.log("E igual")
}
```
## Loop: 
```C#
using System;

public class HelloWorld
{
    public static void Main(string[] args)
    {
        
for(int i=0; i<=10; i++){
    Console.WriteLine($"Incrementado {i}");
}
    }
}
```

## 📋 Comandos com List<T>
```C#
List<int> lista = new List<int> { 1, 2, 3 };

lista.Add(4);              // Adiciona no final
lista.Insert(1, 99);       // Insere na posição 1
lista.Remove(2);           // Remove o número 2 (valor)
lista.RemoveAt(0);         // Remove pelo índice
lista.Clear();             // Limpa a lista
bool tem = lista.Contains(99); // Verifica se contém
int pos = lista.IndexOf(3);    // Índice do valor 3
lista.Sort();              // Ordena
lista.Reverse();           // Inverte
lista.ForEach(Console.WriteLine); // Itera
```

## IF/ELSE
```C#
int n1 = 10;
int n2 = 20;

if (n1 == n2) {
    Console.WriteLine("São iguais");
} else {
    Console.WriteLine("Não são iguais");
}
```
## LOOP FOR

```C#
for (int i = 0; i <= 10; i++) {
    Console.WriteLine($"Incrementando: {i}");
}
```

## LOOP While

```C#
int i = 0;
while (i < 5) {
    Console.WriteLine(i);
    i++;
}
```
## Array
```C#
int[] numeros = { 1, 2, 3 };
foreach (int n in numeros) {
    Console.WriteLine(n);
}
```

```C#
static int Soma(int a, int b) {
    return a + b;
}


static void Main() {
    int resultado = Soma(5, 3);
    Console.WriteLine($"Resultado: {resultado}");
}
```

## Converter Tipos

- Tipos de Dados e Conversões

- ***Explique casting implícito e explícito, Convert.ToInt32(), ToString()***.

- Mostre exemplos de conversão entre int, double, string.

## 6. Tratamento de Erros e Exceções

Uso de try, catch, finally

Criação de exceções personalizadas

Exemplo:
```C#
try {
    int x = 10 / 0;
} catch (DivideByZeroException e) {
    Console.WriteLine("Erro: divisão por zero!");
}
```

## 🧰 7. Manipulação de Arquivos

File.WriteAllText(), File.ReadAllText()

StreamReader, StreamWriter

Exemplo:
```C#
File.WriteAllText("dados.txt", "Olá, C#!");
string texto = File.ReadAllText("dados.txt");
Console.WriteLine(texto);
## Observações Importantes
```
## 🔄 8. Namespaces e Organização

Explicar como organizar classes e usar namespaces:
```C#
namespace MeuProjeto.Modelos {
    public class Produto { }
}
```
***C# é case-sensitive, ou seja, diferencia maiúsculas de minúsculas (Console ≠ console)***.

== é o operador de comparação; não use === como em JavaScript.

Para imprimir no console, use sempre Console.WriteLine().

Métodos e classes em C# usam PascalCase por convenção.

