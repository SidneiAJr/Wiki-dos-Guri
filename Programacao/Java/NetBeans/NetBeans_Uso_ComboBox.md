# 🧭 Tutorial de Uso do ComboBox no NetBeans

## 🪟 Passo 1: Abrir o NetBeans
Abra o **NetBeans IDE** no seu computador.

## 🧱 Passo 2: Criar um novo JFrame
1. Vá em **File → New Project**.  
2. Escolha **Java → Java Application** e clique em **Next**.  
3. Dê um nome ao projeto e finalize.  
4. Dentro do projeto, clique com o botão direito em **Source Packages → New → JFrame Form**.  
5. Dê um nome para o formulário e clique em **Finish**.

## 🎛️ Passo 3: Inserir o ComboBox
1. Abra o formulário (`.java` com design).  
2. Na aba **Palette**, procure por **Combo Box** (ou `JComboBox`).  
3. Arraste o componente para dentro do seu JFrame.

## ⚙️ Passo 4: Configurar Propriedades
1. Clique no **ComboBox**.  
2. Vá até a aba **Properties** (geralmente no canto direito).  
3. Aqui você pode alterar:
   - **Name:** nome interno (ex: `cbOpcoes`)  
   - **Model:** lista de itens do ComboBox  
   - **Font:** tipo e tamanho da fonte  
   - **Foreground / Background:** cores  
   - **ToolTipText:** dica que aparece ao passar o mouse  

## 💡 Passo 5: Adicionar Itens no ComboBox
Você pode adicionar itens de duas formas:

### 🔹 Pelo **Design**:
1. Selecione o ComboBox.  
2. Em **Properties → model**, clique no `...` e adicione os itens manualmente.  
   Exemplo:  
