# 🔢 Tutorial de Uso do JSpinner no NetBeans

![Painel](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-28%20193012.png)

## 🪟 Passo 1: Abrir o NetBeans
Abra o **NetBeans IDE** no seu computador.

## 🧱 Passo 2: Criar um novo JFrame
1. Vá em **File → New Project**.  
2. Escolha **Java → Java Application** e clique em **Next**.  
3. Dê um nome ao projeto e finalize.  
4. Dentro do projeto, clique com o botão direito em **Source Packages → New → JFrame Form**.  
5. Dê um nome para o formulário e clique em **Finish**.

## 🔘 Passo 3: Inserir o JSpinner
1. Abra o formulário (`.java` com design).  
2. Na aba **Palette**, procure por **Spinner** (ou `JSpinner`).  
3. Arraste o componente para dentro do seu JFrame.

## ⚙️ Passo 4: Configurar Propriedades
1. Clique no **JSpinner**.  
2. Vá até a aba **Properties** (geralmente no canto direito).  
3. Aqui você pode alterar:
   - **name:** nome interno do componente (ex: `spnIdade`)  
   - **font:** tipo e tamanho da fonte  
   - **model:** define os valores possíveis  
   - **enabled:** habilita/desabilita o componente  
   - **toolTipText:** dica que aparece ao passar o mouse  

## 🔧 Passo 5: Definir o Modelo do Spinner
Você pode configurar o **modelo** do JSpinner para diferentes tipos de valores:

### 🔹 Números
Defina o modelo no código:
```java
SpinnerNumberModel modelo = new SpinnerNumberModel(18, 0, 100, 1);
spnIdade.setModel(modelo);
```

## Exemplo de Tela:

- ***Quantidade e Um Spinner***

![Tela](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-23%20164839.png)
