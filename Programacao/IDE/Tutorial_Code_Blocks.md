# 🧱 Tutorial Code::Blocks — IDE para C e C++

O **Code::Blocks** é uma IDE gratuita, leve e multiplataforma feita especialmente para **linguagens C e C++**.  
Ele vem com editor, depurador, compilador (GCC/MinGW) e ferramentas integradas.

---

## 🧩 1. Instalação

### 🪟 **Windows**
1. Acesse o site oficial: [https://www.codeblocks.org/downloads](https://www.codeblocks.org/downloads)
2. Baixe o instalador **"codeblocks-XXmingw-setup.exe"** (vem com o compilador MinGW incluso)
3. Execute o instalador e siga os passos padrão (`Next → Next → Finish`)

### 🐧 **Linux**
```bash
sudo apt update
sudo apt install codeblocks
sudo apt install g++   # compilador
```

## ⚙️ 2. Primeiros Passos
Criar um novo projeto:

Abra o Code::Blocks

Vá em File → New → Project

Escolha Console Application → Clique em Go

Escolha C ou C++

Dê um nome ao projeto e escolha onde salvar

Clique em Finish

A IDE criará automaticamente um arquivo main.c ou main.cpp.

## 🚀 4. Compilar e Executar

Clique no botão Build and Run (ícone com engrenagem verde)
ou pressione F9.

💡 O Code::Blocks automaticamente compila e executa o programa no terminal interno.

## 5. Depuração (Debug)

Vá em Debug → Start / Continue (F8)

Clique na margem esquerda do código para adicionar breakpoints

Use:

▶️ Continue (F8) — executa até o próximo breakpoint

🔁 Step Into (F7) — entra em funções linha a linha

🔼 Step Over (Shift + F7) — pula funções

Veja as variáveis no painel Watches

## Atalhos Importantes

| Ação                   | Atalho             |
| ---------------------- | ------------------ |
| 🧱 Compilar            | `Ctrl + F9`        |
| 🚀 Compilar e Executar | `F9`               |
| 🐞 Iniciar Depuração   | `F8`               |
| 💾 Salvar              | `Ctrl + S`         |
| ➕ Novo Projeto         | `Ctrl + Shift + N` |
| 🔎 Buscar no código    | `Ctrl + F`         |


## 7. Configurações Úteis

Alterar Tema (Editor → Syntax Highlighting)
→ Escolha entre temas escuros e claros

Definir compilador manualmente
→ Settings → Compiler → Selected Compiler

Ativar número de linhas
→ Settings → Editor → Display line numbers
