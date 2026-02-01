# 🪟 Janelas (Windows) — WinAPI32 no Code::Blocks (C)

## 📖 Introdução

Em aplicações **WinAPI32**, a **janela** é o elemento principal da interface com o usuário.  
Tudo que aparece na tela — botões, menus, caixas de texto e mensagens — depende da criação de uma **janela principal (Main Window)** e, em alguns casos, de **sub-janelas (child windows)**.

A **WinAPI (Windows Application Programming Interface)** oferece funções diretas do sistema operacional para criar e gerenciar essas janelas, tornando possível construir interfaces gráficas em **C puro**, sem bibliotecas externas.

---

## ⚙️ Estrutura Básica de uma Janela

Toda janela WinAPI é composta por quatro elementos principais:

| Elemento | Descrição |
|-----------|------------|
| **Classe da Janela (Window Class)** | Estrutura que define as propriedades da janela (nome, estilo, ícone, cursor, etc.). |
| **Função de Callback (Window Procedure)** | Função que trata todas as mensagens enviadas à janela (cliques, teclas, redimensionamento, etc.). |
| **Criação da Janela (CreateWindow / CreateWindowEx)** | Comando que efetivamente cria a janela no sistema. |
| **Loop de Mensagens (Message Loop)** | Estrutura que mantém o programa executando e processando eventos do Windows. |

Esses quatro blocos formam o núcleo de qualquer aplicação WinAPI com interface gráfica.

---

## 🧱 1. Classe da Janela (Window Class)

Antes de criar uma janela, é necessário registrar uma **classe de janela** — uma estrutura que informa ao sistema como a janela se comporta e quais recursos visuais utiliza.

**A classe define:**
- Nome da janela e identificador.
- Ícone e cursor padrão.
- Cor de fundo.
- Ponteiro da função de tratamento de mensagens (WindowProc).
- Estilo de exibição (redimensionável, fixa, com bordas, etc.).

O registro é feito uma única vez, antes da criação da janela principal.

---

## 🧭 2. Criação da Janela Principal

Depois que a classe é registrada, o próximo passo é **criar a janela**.  
Isso é feito por funções da API como `CreateWindow()` ou `CreateWindowEx()`.

**Durante a criação, definem-se:**
- O tipo de janela (classe registrada).  
- O título exibido na barra superior.  
- A posição e o tamanho inicial.  
- O estilo visual (com ou sem borda, redimensionável, com título, etc.).  
- O identificador do programa.  

Ao ser criada, a janela ainda não aparece automaticamente — é preciso usar `ShowWindow()` para torná-la visível e `UpdateWindow()` para forçar a atualização do conteúdo.

---

## 🔁 3. Loop de Mensagens (Message Loop)

O **loop de mensagens** é o coração da aplicação WinAPI.  
Ele mantém o programa rodando, verificando continuamente se há eventos para processar (como cliques, teclas, redimensionamentos, etc.).

Sem esse loop, a janela seria criada e encerrada instantaneamente.

**O loop é responsável por:**
- Capturar mensagens do sistema.  
- Direcionar mensagens à função da janela (WindowProc).  
- Manter a aplicação ativa até o usuário encerrá-la.  

É ele que permite que a janela **responda dinamicamente** às ações do usuário.

---

## ⚡ 4. Função de Tratamento de Mensagens (WindowProc)

Toda janela precisa de uma função especial — a **Window Procedure (WndProc)** — responsável por **tratar os eventos** enviados pelo Windows.

Esses eventos (chamados de **mensagens**) incluem:
- `WM_CREATE` — janela sendo criada.  
- `WM_PAINT` — atualização visual.  
- `WM_SIZE` — redimensionamento.  
- `WM_COMMAND` — eventos de botões e menus.  
- `WM_CLOSE` e `WM_DESTROY` — encerramento da aplicação.  

Cada vez que o usuário interage com a janela, o sistema envia uma mensagem, e essa função decide o que fazer com ela.

---

## 🧩 5. Tipos de Janelas WinAPI

O Windows oferece diferentes categorias de janelas para usos específicos:

| Tipo | Descrição | Uso Comum |
|------|------------|-----------|
| **Janela Principal (Main Window)** | Janela principal da aplicação. | Ponto central do programa. |
| **Janela Filha (Child Window)** | Fica dentro da janela principal. | Contém controles como botões e caixas de texto. |
| **Janela de Diálogo (Dialog Box)** | Janela temporária de interação. | Exibir mensagens, perguntas ou configurações. |
| **Janela Pop-up** | Flutua sobre outras janelas. | Menus de contexto e notificações. |

---

## 🪟 6. Estilos de Janela

O comportamento e aparência da janela são definidos pelos **Window Styles**, conjuntos de flags que indicam como a janela deve se comportar.

### 🧰 Estilos comuns:
| Estilo | Descrição |
|---------|------------|
| `WS_OVERLAPPEDWINDOW` | Janela padrão com borda, título, menu e redimensionamento. |
| `WS_POPUP` | Janela sem borda (usada em menus e notificações). |
| `WS_CHILD` | Janela filha dentro de outra. |
| `WS_VISIBLE` | Torna a janela visível ao ser criada. |
| `WS_MINIMIZEBOX` / `WS_MAXIMIZEBOX` | Ativa botões de minimizar e maximizar. |
| `WS_SYSMENU` | Adiciona o menu padrão (ícone do sistema). |

Esses estilos podem ser combinados para criar interfaces personalizadas.

---

## 🎨 7. Elementos Visuais da Janela

Além da área principal, uma janela WinAPI pode conter:

- **Barra de Título:** mostra o nome e ícone da aplicação.  
- **Bordas:** permitem redimensionar.  
- **Área Cliente (Client Area):** região onde os controles (botões, labels, etc.) são exibidos.  
- **Menu de Sistema:** acessado pelo ícone do canto superior esquerdo.  
- **Status e Toolbars:** criadas manualmente ou via recursos (`.rc`).

Esses elementos seguem o padrão visual do próprio sistema Windows, mantendo a consistência da interface.

---

## 🧠 Boas Práticas

- Registre a **classe de janela** apenas uma vez no programa.  
- Sempre trate corretamente o evento `WM_DESTROY` para encerrar a aplicação.  
- Use `ShowWindow()` e `UpdateWindow()` após criar a janela.  
- Centralize a lógica de interface na função de mensagens (WindowProc).  
- Mantenha os identificadores (IDs) organizados em um arquivo `resource.h`.  
- Utilize estilos adequados para o tipo de janela (principal, filha, diálogo).

---

## 📁 Estrutura Recomendada (Code::Blocks)

