# Formatação de Números com `F2` em C#

No C#, para formatar números de ponto flutuante (como `double` ou `float`) e exibi-los com um número fixo de casas decimais, usamos a **formatação de números** com o **especificador `F2`**. O `F2` indica que o número deve ser formatado com **2 casas decimais**.

### Como funciona o `F2`:

- **`F`**: Especifica que o número deve ser formatado como um número de ponto fixo (ou seja, com um número específico de casas decimais).
- **`2`**: Indica o número de casas decimais que o número será arredondado ou exibido.

### Exemplos de uso:

#### 1. **Usando `String.Format`**

Com o método `String.Format`, você pode formatar o número de forma simples:

```csharp
double soma = 10.2567;
Console.WriteLine(String.Format("Soma {0:F2}", soma));  // Resultado: Soma 10.26
```

```csharp
double soma = 10.2567;
Console.WriteLine($"Soma {soma:F2}");  // Resultado: Soma 10.26
```
