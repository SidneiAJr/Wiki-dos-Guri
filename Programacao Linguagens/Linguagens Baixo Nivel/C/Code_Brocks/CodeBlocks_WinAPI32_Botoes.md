# 🔘 Botões — WinAPI32 no Code::Blocks (C)

## 📖 Introdução

Os **botões (Buttons)** são um dos elementos mais fundamentais da interface gráfica no **WinAPI32**.  
Eles permitem que o usuário **execute ações**, **confirme escolhas** e **interaja** com a aplicação de forma direta.

Na API do Windows, os botões são tratados como **controles de janela** — ou seja, são janelas filhas criadas dentro da janela principal.  
Cada botão tem um tipo, um estilo e responde a mensagens enviadas pelo sistema operacional.

---

## 🧩 1. Estrutura do Controle de Botão

Todo botão WinAPI é um **componente visual** que herda da classe padrão `"BUTTON"`.  
Ele é gerenciado pelo sistema, mas o programa é responsável por **tratar seus eventos** através de mensagens (`WM_COMMAND`).

Um botão tem:
- **Texto** (rótulo visível).  
- **Identificador (ID)** para associar a ações específicas.  
- **Posição e tamanho** dentro da janela principal.  
- **Estilo** (tipo visual e comportamento).  

---

## 🎨 2. Tipos de Botões

A API fornece diferentes estilos de botões para usos variados:

| Tipo de Botão | Estilo | Descrição |
|----------------|---------|------------|
| **Push Button** | `BS_PUSHBUTTON` | Botão comum, executa uma ação ao ser clicado. |
| **Default Button** | `BS_DEFPUSHBUTTON` | Botão padrão da janela (acionado por Enter). |
| **Check Box** | `BS_CHECKBOX` | Marcações independentes de “sim/não”. |
| **Radio Button** | `BS_RADIOBUTTON` | Seleção única em um grupo de opções. |
| **Group Box** | `BS_GROUPBOX` | Moldura que agrupa botões relacionados. |
| **Auto CheckBox** | `BS_AUTOCHECKBOX` | Marca e desmarca automaticamente. |
| **Auto RadioButton** | `BS_AUTORADIOBUTTON` | Seleção automática de uma única opção. |
| **Owner Draw** | `BS_OWNERDRAW` | Botão personalizado desenhado pelo programador. |

---

## ⚙️ 3. Estilos Visuais

Além do tipo, o botão também pode ter **estilos adicionais** que controlam sua aparência e comportamento.

| Estilo | Descrição |
|---------|------------|
| `WS_VISIBLE` | Torna o botão visível. |
| `WS_CHILD` | Define como controle filho da janela principal. |
| `BS_FLAT` | Botão com aparência mais moderna e sem relevo. |
| `BS_ICON` | Exibe um ícone em vez de texto. |
| `BS_BITMAP` | Exibe uma imagem (bitmap). |
| `BS_MULTILINE` | Permite múltiplas linhas de texto. |

Esses estilos podem ser combinados conforme a necessidade da interface.

---

## 🧠 4. Eventos e Mensagens

Os botões enviam **mensagens** para a janela principal quando são clicados.  
Essas mensagens chegam através de `WM_COMMAND` e podem ser identificadas pelo **ID do botão**.

Os eventos mais comuns são:

| Evento | Mensagem | Descrição |
|---------|------------|-----------|
| Clique | `BN_CLICKED` | Dispara quando o botão é pressionado. |
| Foco | `BN_SETFOCUS` | O botão recebeu foco. |
| Perda de foco | `BN_KILLFOCUS` | O botão perdeu o foco. |
| Check | `BN_DOUBLECLICKED` | Clique duplo no botão. |

Essas mensagens são tratadas dentro da função de janela (WindowProc).

---

## 🖼️ 5. Ícones e Imagens

Um botão também pode exibir **ícones** ou **imagens (bitmaps)**, tornando a interface mais visual.  
Para isso, o botão deve ser criado com o estilo adequado (`BS_ICON` ou `BS_BITMAP`) e o recurso precisa ser carregado previamente no programa.

Os ícones são gerenciados como recursos (`HICON`, `HBITMAP`) definidos no arquivo `.rc` da aplicação.

---

## 🪄 6. Botões Customizados

A WinAPI permite criar botões totalmente personalizados com o estilo `BS_OWNERDRAW`.  
Nesse modo, o sistema **não desenha o botão automaticamente** — em vez disso, o programador controla o desenho e os efeitos de clique, foco e estado.

Esse tipo de botão é usado quando se deseja:
- Estilo visual próprio (cores, fontes, imagens).  
- Botões com ícones dinâmicos.  
- Interações complexas.  

---

## ⚡ 7. Boas Práticas

- Sempre use **IDs únicos** para cada botão.  
- Centralize o tratamento de eventos `WM_COMMAND`.  
- Use textos curtos e diretos nos rótulos.  
- Prefira botões padrão para manter a consistência visual.  
- Evite excesso de botões — agrupe funções semelhantes em menus.  
- Utilize atalhos de teclado (`Alt + letra`) com `&` no texto, ex: `&Salvar`.

---

## 📂 Estrutura Recomendada

