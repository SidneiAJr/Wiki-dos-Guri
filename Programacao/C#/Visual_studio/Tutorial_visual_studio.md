![Visual Studio](https://img.shields.io/badge/Visual%20Studio-C%23-blueviolet?style=for-the-badge&logo=visualstudio)
![CSharp](https://img.shields.io/badge/Linguagem-C%23-%230078D7?style=for-the-badge&logo=csharp)
![Status](https://img.shields.io/badge/Projeto-Documentação%20Dev-green?style=for-the-badge)

# 📚 Guia de Visual Studio & Desenvolvimento C#

Bem-vindo(a)! Este documento é um **guia prático e direto ao ponto** para quem está iniciando com **Visual Studio, C# e ASP.NET**.  
Ideal para documentação, portfólio ou estudos.

---

## 📌 Sumário

- [⚙️ Instalação do Visual Studio](#️-instalação-do-visual-studio)
- [🚀 Criando o Primeiro Projeto (Console C#)](#-criando-o-primeiro-projeto-console-c)
- [▶️ Executando o Projeto](#️-executando-o-projeto)
- [🌐 Criando Projeto Web (ASP.NET Core)](#-criando-projeto-web-aspnet-core)
- [📄 Exemplo de PageModel (ASP.NET Razor)](#-exemplo-de-pagemodel-aspnet-razor)
- [🪟 Criando Interface com Windows Forms](#-criando-interface-com-windows-forms)
- [🧩 Código Gerado (Designer + Lógica)](#-código-gerado-designer--lógica)
- [⌨️ Atalhos Úteis no Visual Studio](#️-atalhos-úteis-no-visual-studio)
- [💡 Dicas Profissionais](#-dicas-profissionais)

---

## ⚙️ Instalação do Visual Studio

1. Acesse: **https://visualstudio.microsoft.com/**
2. Baixe a versão **Community (Gratuita)**
3. Durante a instalação, selecione:
   - ✅ **Desenvolvimento de Desktop .NET**
   - ✅ **ASP.NET e Desenvolvimento Web** *(opcional, para web)*
4. Clique em **Instalar** e aguarde a configuração.

> 💡 **Dica:** O Visual Studio gerencia **Soluções (.sln)** com vários projetos dentro. Ótimo para organizar sistemas reais.

---

## 🚀 Criando o Primeiro Projeto (Console C#)

1. Abra o Visual Studio → **Criar novo projeto**
2. Selecione **Aplicativo de Console (.NET)**
3. Nome do projeto: `MeuPrimeiroApp`
4. Clique em **Criar**

Exemplo de código inicial:

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Olá, Mundo!");
    }
}
```
## ▶️ Executando o Projeto

Pressione Ctrl + F5 → Executa sem depuração

Pressione F5 → Executa com debug

💬 Saída esperada no terminal:

## 🌐 Criando Projeto Web (ASP.NET Core)

Novo projeto → Aplicativo Web ASP.NET Core

Escolha o template:

✅ "Empty" (projeto limpo)

✅ Ou MVC caso queira Controllers e Views

Executar com Ctrl + F5

💡 ASP.NET Core utiliza arquitetura MVC (Model-View-Controller) ou Razor Pages.

## 📄 Exemplo de PageModel (ASP.NET Razor)

```csharp
using Microsoft.AspNetCore.Mvc.RazorPages; 
using Microsoft.AspNetCore.Mvc; 

public class calccotasModel : PageModel
{
    [BindProperty] public double valor_invest { get; set; }
    [BindProperty] public double preco_cota { get; set; }
    [BindProperty] public double provento { get; set; }

    public double? Total { get; set; }
    public double? Total_provento { get; set; }

    public void OnPost()
    {
        Total = valor_invest / preco_cota;
        Total_provento = Total * provento;
    }
}
```

## 🪟 Criando Interface com Windows Forms

Novo projeto → Aplicativo Windows Forms (.NET Framework)

A interface é criada visualmente, arrastando botões, textos e labels.

O Visual Studio gera automaticamente um arquivo Form1.Designer.cs

## ⚙ Lógica de Cálculo (Evento do Botão)

```csharp
private void btnCalcular_Click(object sender, EventArgs e)
{
    try
    {
        double valorInvestido = double.Parse(txtValorInvestido.Text);
        double taxaJuros = double.Parse(txtTaxaJuros.Text) / 100;
        int tempo = int.Parse(txtTempo.Text);
        double valorFuturo = valorInvestido * Math.Pow(1 + taxaJuros, tempo);
        lblResultado.Text = $"Valor Futuro: R$ {valorFuturo:0.00}";
    }
    catch
    {
        MessageBox.Show("Erro ao calcular. Verifique os valores.");
    }
}
```
