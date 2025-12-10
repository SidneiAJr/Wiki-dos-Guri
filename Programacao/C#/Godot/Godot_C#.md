# ⚙️ Godot com C# (.NET)

> Documentação e exemplos sobre o uso do **C#** dentro da **Godot Engine (.NET build)**.  
> A Godot suporta C# através da integração com o **.NET SDK (Mono)**, permitindo tipagem estática, LINQ, e o ecossistema completo do C# dentro da engine.

---

## 🧠 O que é o “Godot .NET” (Mono)

- É a **versão da Godot** que vem com o **runtime do .NET (Mono)** embutido.  
- Permite escrever scripts em **C#** no lugar de GDScript.  
- O funcionamento interno da engine é o mesmo — só muda a linguagem usada nos scripts.  
- Precisa do **.NET SDK 6.0 ou superior** instalado no sistema.

📦 **Download oficial:**  
👉 [https://godotengine.org/download](https://godotengine.org/download)

Seleciona a versão **“Godot .NET”** (tem esse nome no site).

---

## 🧰 Requisitos

| Requisito | Versão mínima |
|:--|:--|
| .NET SDK | 6.0+ |
| Godot .NET (Mono) | 4.x |
| Editor C# (Visual Studio / VSCode) | qualquer |
| Sistema | Windows, Linux ou macOS |

---

## 🧩 Estrutura de Projeto (C#)

Quando cria um projeto Godot .NET, a estrutura é parecida com:

## 🧱 Exemplo básico em C#

```csharp
using Godot;
using System;

public partial class Player : Node2D
{
    public override void _Ready()
    {
        GD.Print("Olá, mundo da Godot em C#!");
    }

    public override void _Process(double delta)
    {
        Position += new Vector2(100 * (float)delta, 0);
    }
}
```
