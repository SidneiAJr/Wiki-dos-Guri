# 🪟 Win32 API Básico em C

> Guia rápido e prático para criar **interfaces gráficas nativas do Windows** usando **C puro** e a **Win32 API**.  
> Ideal para quem quer sair do console e começar a trabalhar com **janelas, botões e eventos**.

---

## 🎯 Objetivo
Aprender a criar uma janela simples no Windows com a **Win32 API**, entender sua estrutura básica e saber como compilar e executar o projeto.

---

## ⚙️ 1️⃣ O que é a Win32 API

A **Win32 API** é o conjunto de funções nativas do Windows usadas para criar programas com interface gráfica (GUI) — janelas, menus, botões, caixas de mensagem, etc.  
Ela é escrita e utilizada em **C puro**, sem precisar de C++.

📁 Biblioteca principal:  
```c
#include <windows.h>
```

## Ferramentas necessárias

| IDE                      | Compilador  | Suporte Win32 | Observação                 |
| ------------------------ | ----------- | ------------- | -------------------------- |
| **Code::Blocks**         | MinGW (gcc) | ✅ Sim         | Leve e fácil de configurar |
| **Visual Studio (roxo)** | MSVC        | ✅ Sim         | Oficial da Microsoft       |
| **Dev-C++**              | MinGW       | ✅ Sim         | Ideal para iniciantes      |
| **VS Code + MinGW**      | gcc         | ✅ Sim         | Requer configuração manual |

## Estrutura básica explicada

| Parte            | Descrição                                                       |
| ---------------- | --------------------------------------------------------------- |
| **WinMain()**    | Função principal (equivalente ao `main()` tradicional)          |
| **WNDCLASS**     | Estrutura que registra o tipo de janela                         |
| **WindowProc()** | Função que recebe e trata eventos (ex: fechar, clicar, digitar) |
| **Message Loop** | Loop que mantém a janela viva até o usuário fechá-la            |
