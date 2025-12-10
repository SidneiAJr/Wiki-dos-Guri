# ⚙️ Programando com WinAPI 32 no Code::Blocks — Linguagem C

## 📖 Introdução

A **WinAPI 32 (Windows API)** é a interface oficial da Microsoft para desenvolver aplicativos nativos de desktop em **linguagem C** ou **C++**.  
Mesmo sendo uma tecnologia antiga, ela ainda é amplamente usada em aplicações de baixo nível, ferramentas de sistema e programas que exigem **alta performance e controle direto sobre o Windows**.

O **Code::Blocks** é um ambiente de desenvolvimento (IDE) compatível com **compiladores MinGW** e **MSVC**, o que permite criar, compilar e rodar aplicações WinAPI32 facilmente.

---

## 🧱 O que é a WinAPI 32

A **WinAPI (Windows Application Programming Interface)** é um conjunto de **funções, estruturas e definições** que permitem:
- Criar janelas e caixas de diálogo.
- Manipular botões, textos, menus e ícones.
- Controlar o teclado, o mouse e eventos do sistema.
- Acessar recursos do Windows como arquivos, processos e memória.

Diferente de frameworks como Qt ou .NET, a WinAPI32 não usa interface gráfica visual — tudo é definido **por código e funções C**, controlando diretamente os elementos da janela.

---

## 💻 Ambiente no Code::Blocks

Para trabalhar com WinAPI no Code::Blocks, você precisa apenas de:
- O **Code::Blocks** instalado (versão com MinGW).  
- O **compilador MinGW GCC** (vem incluso na maioria das versões).  
- O **SDK do Windows** (opcional, mas recomendado para suporte completo).  

O MinGW já inclui as bibliotecas essenciais (`windows.h`, `user32`, `gdi32`, etc.), então normalmente **nenhuma configuração adicional é necessária**.

---

## 🧩 Estrutura de um Projeto WinAPI no Code::Blocks

Quando você cria um projeto WinAPI no Code::Blocks, ele segue uma estrutura básica:

