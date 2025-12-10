# ⌨️ Componentes de Entrada — WinAPI32 no Code::Blocks (C)

## 📖 Introdução

Em um aplicativo **WinAPI32**, os **componentes de entrada (input)** são todos os elementos que permitem ao usuário **interagir e enviar informações** ao programa.

Eles são a base para criar interfaces interativas no Windows, controlando tudo — desde botões e caixas de texto até seletores e menus.  
Mesmo sendo uma API de baixo nível, a WinAPI32 oferece um conjunto poderoso de **controles padrão** para entrada de dados, sem precisar de bibliotecas externas.

No **Code::Blocks**, esses componentes funcionam perfeitamente através do **compilador MinGW**, usando a biblioteca padrão `windows.h`.

---

## 🧩 O que é um Componente de Entrada

Um **componente de entrada** é qualquer controle de janela (window control) que:
- Recebe ações do usuário (cliques, digitação, seleção).
- Envia mensagens (events) para o programa através do sistema de mensagens da WinAPI.
- Permite capturar e processar os dados fornecidos pelo usuário.

Cada componente de entrada é criado dentro de uma janela principal, e identificado por um **ID numérico** no arquivo de recursos (`.rc`).

---

## 🎛️ Principais Componentes de Entrada

| Componente | Descrição | Uso Comum |
|-------------|------------|------------|
| **Button** | Botão de ação. | Executar comandos ou confirmar ações. |
| **Edit Control** | Campo de texto editável. | Receber texto, números e nomes. |
| **CheckBox** | Caixa de marcação (ligar/desligar). | Ativar ou desativar opções. |
| **RadioButton** | Botões de escolha exclusiva. | Selecionar apenas uma opção. |
| **ComboBox** | Caixa de seleção com lista. | Escolher um item entre várias opções. |
| **ListBox (interativa)** | Lista clicável de elementos. | Selecionar ou visualizar múltiplos itens. |
| **Menu / Accelerator** | Entrada de comandos via menu ou teclado. | Ações rápidas e atalhos. |

---

## 🔘 1. Button (Botão)

O botão é o controle mais básico e comum da WinAPI.  
Ele é usado para **disparar eventos** quando o usuário clica sobre ele.

**Características principais:**
- Pode conter texto ou imagem.  
- Envia mensagens `WM_COMMAND` ao ser clicado.  
- É criado como controle filho da janela principal.  

**Usos comuns:**
- Confirmar ações (Salvar, Enviar, Sair).  
- Executar funções dentro do aplicativo.  
- Interagir com outros campos da interface.

**Eventos principais:**
- `BN_CLICKED` — ocorre quando o botão é pressionado.

---

## 📝 2. Edit Control (Campo de Texto)

O **Edit Control** é usado para **entrada direta de texto** pelo usuário.

**Características:**
- Pode ser de uma ou várias linhas.  
- Suporta rolagem e edição dinâmica.  
- Pode ser configurado como:
  - Entrada livre.
  - Numérica (restrita por lógica).
  - Somente leitura.

**Funções associadas:**
- `GetWindowText()` — lê o texto digitado.  
- `SetWindowText()` — define um texto padrão.

**Usos comuns:**
- Receber nomes, números, senhas e descrições.  
- Ler dados de entrada para cálculos.  
- Entrada de comandos e consultas.

---

## ☑️ 3. CheckBox (Caixa de Seleção)

O **CheckBox** é um componente binário — pode estar **marcado** ou **desmarcado**.

**Características:**
- Permite múltiplas seleções independentes.  
- Usado para opções que podem coexistir.  
- Envia mensagens `WM_COMMAND` com estado atual.

**Usos comuns:**
- Ativar/desativar recursos.  
- Marcar preferências.  
- Criar grupos de configurações.

**Estados possíveis:**
- Marcado ✅  
- Desmarcado ⬜  
- (Opcional) Indeterminado ▢

---

## ⚪ 4. RadioButton (Botão de Opção)

Os **RadioButtons** permitem **escolher uma única opção** dentro de um grupo.

**Características:**
- Cada grupo contém múltiplos botões de opção.  
- Apenas um pode estar ativo por vez.  
- Envia mensagem `WM_COMMAND` quando o estado muda.

**Usos comuns:**
- Selecionar modos de operação.  
- Escolher entre opções exclusivas (ex: Masculino / Feminino).  
- Trocar parâmetros de exibição ou cálculo.

---

## 🔽 5. ComboBox (Caixa de Seleção)

O **ComboBox** combina um **campo de texto** com uma **lista suspensa** de opções.

**Características:**
- Pode ser somente leitura (seleção fixa) ou editável.  
- Ideal para escolher entre valores predefinidos.  
- Envia mensagens `CBN_SELCHANGE` quando a seleção muda.

**Usos comuns:**
- Selecionar cidades, cores, tipos, categorias.  
- Escolher modos de configuração.  
- Exibir listas curtas de opções.

---

## 📋 6. ListBox (Interativo)

A **ListBox** permite selecionar um ou mais itens de uma lista.

**Características:**
- Mostra várias linhas de texto.  
- Pode ser configurada como seleção simples ou múltipla.  
- Usa mensagens `LB_GETCURSEL`, `LB_ADDSTRING`, `LB_DELETESTRING`.

**Usos comuns:**
- Exibir logs, histórico ou dados do usuário.  
- Permitir seleção de múltiplos itens.  
- Criar listas dinâmicas de conteúdo.

---

## 🧭 7. Menu e Aceleradores

Menus e aceleradores (atalhos de teclado) também são considerados **entradas**, pois permitem interação via comandos.

**Características:**
- Criados no arquivo de recursos (`.rc`).  
- Associados a IDs específicos.  
- Enviam mensagens `WM_COMMAND` para o programa.  

**Usos comuns:**
- Criar menus de aplicação (Arquivo, Editar, Ajuda).  
- Adicionar atalhos como `Ctrl + S`, `Ctrl + Q`.  
- Fornecer navegação avançada na interface.

---

## 💬 Sistema de Mensagens (Input Events)

Todos os componentes de entrada comunicam suas ações ao sistema por **mensagens**.  
Essas mensagens são recebidas na função **WindowProc**, e o programa decide o que fazer com cada uma.

**Mensagens de entrada mais comuns:**

| Mensagem | Origem | Descrição |
|-----------|--------|-----------|
| `WM_COMMAND` | Botões, menus, checkboxes | Ação executada. |
| `WM_CHAR` | Teclado | Captura de caractere digitado. |
| `WM_KEYDOWN` | Teclado | Pressionamento de tecla. |
| `WM_LBUTTONDOWN` | Mouse | Clique do botão esquerdo. |
| `WM_RBUTTONDOWN` | Mouse | Clique do botão direito. |
| `WM_MOUSEMOVE` | Mouse | Movimento sobre a janela. |

---

## 🧠 Boas Práticas

- Sempre defina **IDs únicos** para cada controle de entrada.  
- Organize eventos de input na função principal (`WindowProc`).  
- Use `GetWindowText()` para capturar texto de entrada com segurança.  
- Trate o evento `WM_COMMAND` de forma clara e estruturada.  
- Combine **entradas (input)** e **saídas (output)** para criar fluxos completos.  
- Atualize a interface com feedback visual após ações do usuário.  

---

## 📁 Estrutura Recomendada do Projeto (Code::Blocks)

