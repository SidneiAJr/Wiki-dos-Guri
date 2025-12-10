# Diferença entre JavaScript, Java e C#

### Java (Javão da Massa)
- **Tipo de tipagem**: Fortemente tipada (estática)
- **Comportamento**: Qualquer tipo de dado incorreto gera erros de compilação, o que exige mais atenção aos tipos de dados.
- **Exemplos de tipos**:
  - `double`
  - `int`
  - `String`
  - `float`
  
Java é uma linguagem que exige que você defina os tipos de variáveis explicitamente e não permite fazer conversões implícitas entre tipos diferentes. Isso pode ser um pouco "chato" às vezes, mas ajuda a evitar erros em tempo de execução.

---

### JavaScript
- **Tipo de tipagem**: Dinâmica e fraca
- **Comportamento**: O JavaScript permite que você altere o tipo de uma variável sem a necessidade de declarar explicitamente o tipo, o que pode ser confuso para quem está começando.
- **Exemplos de tipos**:
  - `Number`
  - `String`
  - `Boolean`

JavaScript tem tipagem fraca, ou seja, as variáveis podem mudar de tipo durante a execução do programa. Isso pode gerar menos erros de compilação, mas também pode resultar em comportamentos inesperados se não for bem controlado.

---

### C#
- **Tipo de tipagem**: Fortemente tipada (estática)
- **Comportamento**: Semelhante ao Java, o C# exige uma definição explícita de tipos de dados e também realiza checagem de tipos em tempo de compilação.
- **Exemplos de tipos**:
  - `double`
  - `int`
  - `String`
  - `float`

Embora o C# compartilhe muitas semelhanças com Java, ele tem algumas características próprias, como o uso de tipos de referência e tipos de valor, além de outras funcionalidades que aumentam a robustez da tipagem estática.

---

### Resumo

- **Java e C#** são fortemente tipadas e exigem mais controle do desenvolvedor em relação aos tipos de dados. Eles podem parecer "chatos" ou "rigorosos" porque exigem que o tipo de cada variável seja definido explicitamente.
- **JavaScript**, por outro lado, tem uma tipagem mais flexível, permitindo maior liberdade, mas também deixando espaço para possíveis erros de execução que só serão detectados em tempo de execução.


Exemplo de codigo:

## Subtração em JS:
```js
console.log("1"-1);
resultado 0? porque??
```

## Soma em Java:
```java
class Main {
    public static void main(String[] args) {
        double n1 = 5;
        double n2 = 5;
        double n3 = 5;
        double soma = (n1+n2+n3)/3;
        System.out.printf(String.format("Soma Total %.2f",soma));
        
    }
}
```
## Soma em C#:

```C#
using System;

public class HelloWorld
{
    public static void Main(string[] args)
    {
        double n1 = 5.5;
        double n2 = 5;
        double n3 = 5;
        double soma = (n1+n2+n3)/3;
        Console.WriteLine ($"Soma {soma:F2} ",soma);
        
    }
}
```


