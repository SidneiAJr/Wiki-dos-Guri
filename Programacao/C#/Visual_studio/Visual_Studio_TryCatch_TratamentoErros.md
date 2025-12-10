# ⚡ Tutorial — Tratamento de Erros com Try-Catch no Visual Studio (C#)

## 🎯 Objetivo
Aprender a usar o bloco **try-catch** para tratar erros e evitar que o programa feche de forma inesperada.

---

## 🧩 1️⃣ O que é o Try-Catch?

O `try-catch` serve para **testar um trecho de código** e **capturar erros (exceções)** que podem ocorrer durante a execução.

---

## 🧠 2️⃣ Estrutura Básica

```csharp
try
{
    // Código que pode causar erro
}
catch (Exception ex)
{
    // Tratamento do erro
    MessageBox.Show("Ocorreu um erro: " + ex.Message);
}
finally
{
    // (Opcional) Executa sempre, mesmo que haja erro
}
