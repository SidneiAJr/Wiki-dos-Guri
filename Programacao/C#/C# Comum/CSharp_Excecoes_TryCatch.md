# ⚠️ Exceções e Tratamento de Erros em C#

O C# oferece uma estrutura poderosa para capturar e tratar erros que podem ocorrer durante a execução do programa.  
Esses erros são chamados de **exceções** e são tratados com os blocos `try`, `catch`, `finally` e `throw`.

---

## 🧩 Estrutura Básica

```csharp
try
{
    // Código que pode gerar uma exceção
}
catch (Exception erro)
{
    // Código que trata a exceção
    Console.WriteLine("Ocorreu um erro: " + erro.Message);
}
finally
{
    // Código que sempre será executado
    Console.WriteLine("Fim da execução.");
}
```
```csharp
try
{
    int[] numeros = { 1, 2, 3 };
    Console.WriteLine(numeros[5]); // Erro: índice fora do limite
}
catch (IndexOutOfRangeException ex)
{
    Console.WriteLine("Erro: índice inválido!");
    Console.WriteLine("Detalhes: " + ex.Message);
}
finally
{
    Console.WriteLine("Finalizando o bloco try-catch...");
}
```
