# 🎨 Layouts e Views no Android Studio

## 🧩 Introdução

No Android, **Layouts** e **Views** são os elementos essenciais para criar a **interface do usuário (UI)**.  
Eles definem **como o app é exibido** e **como o usuário interage** com ele.

---

## 🏗️ Layouts — Estrutura da Tela

Os **Layouts** organizam os componentes visuais (**Views**) dentro da tela.  
Eles controlam **o posicionamento**, **o tamanho** e **a hierarquia** dos elementos.

📘 Em resumo:
- Cada **Activity** ou **Fragment** possui **um layout principal**.
- Dentro dele, você adiciona **views** (como botões, textos, imagens, etc.).
- Layouts podem conter **outros layouts** (estrutura hierárquica).

---

### ⚙️ Tipos Comuns de Layouts

#### 🟦 LinearLayout
Organiza os componentes **em linha ou coluna**, um após o outro.

- Direção: `horizontal` ou `vertical`.
- Permite definir pesos (`layout_weight`) para ajustar tamanhos proporcionais.

📌 Ideal para: interfaces simples e alinhadas.

---

#### 🟩 RelativeLayout *(menos usado atualmente)*
Posiciona cada elemento **em relação a outro componente** ou **à borda da tela**.

- Mais flexível que o `LinearLayout`, mas pode ficar confuso com muitos elementos.

📌 Ideal para: telas com posicionamento relativo (ex: “um botão abaixo do texto”).

---

#### 🟧 ConstraintLayout
O **layout mais moderno e recomendado** no Android.

- Permite criar interfaces complexas **sem aninhar layouts**.
- Utiliza **restrições (constraints)** entre os elementos para definir posições.
- Otimiza o desempenho da renderização.

📌 Ideal para: **qualquer tipo de interface**, simples ou complexa.

---

#### 🟥 FrameLayout
Exibe **um único componente** (ou sobrepõe vários, um em cima do outro).

📌 Ideal para:  
- Telas de carregamento.  
- Exibir uma única `View`.  
- Criar efeitos de sobreposição (imagens, botões flutuantes).

---

#### 🟨 GridLayout
Organiza os componentes em **linhas e colunas**.

📌 Ideal para:  
- Exibir elementos de forma tabular ou em grade (ex: galeria de imagens).

---

#### 🟪 TableLayout
Cria uma **tabela de linhas e células**.

📌 Ideal para:  
- Exibir informações estruturadas (ex: horários, dados financeiros).

---

## 🧱 Views — Elementos da Interface

As **Views** são os componentes que o usuário **vê e interage**.  
Cada `View` ocupa um espaço na tela e pode responder a toques, cliques ou gestos.

---

### ✨ Tipos Comuns de Views

| Tipo | Função | Exemplo de Uso |
|------|--------|----------------|
| **TextView** | Exibe texto fixo na tela | Mostrar títulos, mensagens ou rótulos |
| **EditText** | Permite entrada de texto | Campos de login, formulários |
| **Button** | Botão clicável | Ações como “Enviar”, “Salvar” |
| **ImageView** | Exibe uma imagem | Ícones, fotos, banners |
| **RecyclerView** | Lista de itens rolável e eficiente | Listas grandes (ex: contatos, produtos) |
| **CheckBox** | Caixa de seleção múltipla | Preferências, opções múltiplas |
| **RadioButton** | Botão de seleção única | Escolha de gênero, modo de envio |
| **Switch** | Interruptor (ligado/desligado) | Configurações booleanas |
| **ProgressBar** | Mostra progresso de tarefa | Downloads, carregamentos |
| **Spinner** | Menu suspenso (dropdown) | Escolha de opções (ex: país, idioma) |
| **SeekBar** | Controle deslizante de valor | Volume, brilho |
| **WebView** | Exibe conteúdo HTML ou páginas web | Visualizar sites dentro do app |

---

## 🧠 Hierarquia da Interface

O layout principal geralmente é o **container raiz**, e dentro dele ficam as **views filhas**.  
Exemplo de hierarquia visual:


