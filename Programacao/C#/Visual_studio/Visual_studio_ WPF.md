# 🪟 Tutorial — Introdução ao WPF (Windows Presentation Foundation)

## 🎯 Objetivo
Aprender a criar uma **interface gráfica moderna e estilizada** no **Visual Studio** usando o **WPF** (Windows Presentation Foundation) com **C#**.

O WPF é uma tecnologia da Microsoft que usa **XAML** (uma linguagem parecida com HTML) para definir a interface, e **C#** para a lógica do programa.

---

## 🧩 O que é o WPF?

O **WPF** é uma evolução do **Windows Forms**, e serve para criar **interfaces modernas** em aplicativos desktop do Windows.  
Ele permite:
- Criar **layouts responsivos e bonitos**.
- Usar **CSS-like styles** (chamados de *Styles* e *Templates*).
- Trabalhar com **imagens, gradientes, ícones e animações**.
- Conectar **dados** facilmente (Data Binding e MVVM).

---

## ⚙️ 1️⃣ Criando um Projeto WPF

1. Abra o **Visual Studio** (a versão roxa 🟣).
2. Vá em **Arquivo > Novo > Projeto**.
3. Escolha **"Aplicativo WPF (.NET)"**.
4. Dê um nome, por exemplo: `PrimeiroProjetoWPF`.
5. Clique em **Criar**.

O Visual Studio vai gerar dois arquivos principais:
- `MainWindow.xaml` → Define a interface (parte visual).
- `MainWindow.xaml.cs` → Define a lógica (parte de código C#).

---

## 🎨 2️⃣ Estrutura básica do XAML

```xml
<Window x:Class="PrimeiroProjetoWPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Janela Principal" Height="300" Width="400">
    
    <Grid Background="#F0F0F0">
        <Button x:Name="btnClique" 
                Content="Clique Aqui" 
                Width="120" Height="40" 
                HorizontalAlignment="Center" 
                VerticalAlignment="Center"
                Click="btnClique_Click"
                Background="#6A5ACD"
                Foreground="White"
                FontWeight="Bold"/>
    </Grid>
</Window>
```
