# 📘 Tutorial de Instalação do NetBeans:

***NetBeans é uma IDE (Ambiente de Desenvolvimento Integrado) utilizada principalmente para desenvolvimento em Java e JavaFX.***

- Dowload do Netbents: https://netbeans.apache.org/front/main/download/


## 🛠️ Etapas de Instalação

Baixe o instalador do NetBeans a partir do link acima.

Execute o instalador e siga as instruções padrão de instalação.

Após a instalação, abra o NetBeans.

## 🚀 Criando um Projeto no NetBeans

Com o NetBeans aberto, clique em "File" > "New Project".

Escolha o tipo de projeto:

Java Application (aplicação comum)

JavaFX Application (interface gráfica com JavaFX)

![CriandoProjeto](https://github.com/SidneiAJr/Documentacao_Linguagens/blob/main/prints/8.png)

## 🎨 Trabalhando com JavaFX

Se você escolheu um projeto JavaFX, verá a seguinte interface:

![Tools](https://github.com/SidneiAJr/Documentacao_Linguagens/blob/main/prints/9.png)

- ***Tools NetBeans***

![Lista_tools](https://github.com/SidneiAJr/Documentacao_Linguagens/blob/main/prints/10.PNG)

 # 🧰 Ferramentas Visuais no NetBeans (GUI Builder)

Aqui estão os principais **componentes (tools)** disponíveis no **NetBeans** ao criar interfaces gráficas com JavaFX ou Swing. Esses elementos são utilizados para construir janelas, formulários e menus em aplicações visuais.

---

## 🎯 Componentes de Interface Gráfica

| Componente        | Função                                                                 |
|-------------------|------------------------------------------------------------------------|
| **Label**         | Rótulo usado para exibir texto fixo (ex: "Nome:", "Senha:")            |
| **TextField**     | Campo de texto de uma linha para entrada de dados                      |
| **TextArea**      | Área de texto com várias linhas (ex: para comentários ou mensagens)     |
| **PasswordField** | Campo de texto que esconde os caracteres digitados (senha)             |
| **Button**        | Botão que executa uma ação quando clicado                              |
| **CheckBox**      | Caixa de seleção que pode ser marcada ou desmarcada (sim/não, on/off)  |
| **RadioButton**   | Botão de opção; usado em grupo para selecionar apenas uma alternativa  |
| **ComboBox**      | Caixa de seleção com uma lista suspensa (tipo drop-down menu)          |
| **List**          | Lista de itens onde você pode selecionar um ou mais                    |
| **Table**         | Tabela para exibir dados organizados em linhas e colunas               |
| **Slider**        | Controle deslizante para selecionar um valor num intervalo             |
| **Spinner**       | Campo com setas para aumentar/diminuir valores numéricos               |
| **ProgressBar**   | Barra de progresso visual para indicar carregamentos                   |
| **ToolTip**       | Dica que aparece ao passar o mouse sobre um componente (texto flutuante)|
| **Panel**         | Contêiner usado para agrupar outros componentes                        |
| **TabbedPane**    | Abas de navegação (como as de navegadores)                             |
| **ScrollPane**    | Permite rolar o conteúdo se ele for maior que a área visível           |
| **MenuBar**       | Barra de menus (no topo da janela)                                     |
| **Menu**          | Menu individual (ex: Arquivo, Editar)                                  |
| **MenuItem**      | Opções dentro de um menu (ex: Salvar, Sair)                            |
| **Separator**     | Linha visual usada para separar seções ou grupos de botões             |
| **ImageIcon**     | Componente para exibir imagens                                          |

---

## 🧩 Exemplo de Uso Comum em Formulários

Um formulário simples pode conter os seguintes elementos:

- `Label` → "Nome", "Email", "Senha"
- `TextField` → entrada do nome e e-mail
- `PasswordField` → entrada da senha
- `Button` → botão "Cadastrar"
- `CheckBox` → opção "Aceito os termos"
- `ComboBox` → seleção de país ou estado
- `TextArea` → campo para observações
- `MenuBar` com `Menu` e `MenuItem` → Arquivo > Salvar, Sair, etc.

---

## 📌 Dica

Você pode acessar essas ferramentas no **GUI Builder** do NetBeans, arrastando os componentes para o painel de design. Cada componente pode ser configurado visualmente (tamanho, cor, ação, etc.) ou diretamente pelo código Java.

---




## 🧩 Explorando a Aba "Source"

Dentro da aba Source, você encontrará o menu de opções relacionadas ao código:
Dentro da Opção Source:


- Menu de Opções(Source->Codigo)

![source](https://github.com/SidneiAJr/Documentacao_Linguagens/blob/main/prints/11.PNG)

- Dentro de Source -> Codigo

![codigo](https://github.com/SidneiAJr/Documentacao_Linguagens/blob/main/prints/12.PNG)


## ⌨️ Atalhos de Teclado Úteis

| Ação                     | Atalho (Windows/Linux) | Atalho (macOS)      |
|--------------------------|------------------------|----------------------|
| Executar o Projeto       | `F6`                   | `Cmd + F6`           |
| Compilar Arquivo Atual   | `Shift + F11`          | `Shift + Cmd + F11`  |
| Executar Arquivo Atual   | `Shift + F6`           | `Shift + Cmd + F6`   |
| Comentar/Descomentar     | `Ctrl + Shift + C`     | `Cmd + Shift + C`    |
| Formatar Código          | `Alt + Shift + F`      | `Cmd + Shift + F`    |

## Exemplo de codigo:

```JAVA
 private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:
    String nome = it_nome.getText();
    String turma = tj_Turma.getText();
    String idade = it_idade.getText();
    
    int idadeuser = Integer.parseInt(idade);
    
    if(idadeuser<=18){
    
    }else{
        
    }
    
    // monta a mensagem completa
    String mensagem = "Nome: " + nome + ", Turma: " + turma + "Idade Meliante" + idadeuser;
    
    // coloca a mensagem no JLabel
    jLabel4.setText(mensagem);
         
    }              
```

## Exemplo de codigo 2:
```Java
String valorIni = txtvalor.getText();
        String tempo = txttmp.getText();
        String juro = txtjuros.getText();

        double valorInicial = Double.parseDouble(valorIni);
        int tempo2 = Integer.parseInt(tempo);
        double jurostotal = Double.parseDouble(juro);
        double jurosdiv = jurostotal/100;
        double vf = valorInicial * Math.pow(1 + jurosdiv, tempo2);
        DecimalFormat df = new DecimalFormat("#.##");
        String vfFormatado = df.format(vf);
        
        
        if(tempo2<=1){
            double ir = vf*0.22;
            double liquido = vf - ir;
            String irFormatado = df.format(ir);
            String liquidoFormatado = df.format(liquido);
            lbimp.setText ("Valor dos impostos R$: " +irFormatado);
            lbfinal.setText("O total futuro será R$ " + liquidoFormatado);
            String brutototal = df.format(vf);
            lbbruto.setText("O Valor Bruto R$"+brutototal);
        }else if(tempo2>2){
            double ir = vf*0.175;
            double liquido = vf - ir;
            String irFormatado = df.format(ir);
            String liquidoFormatado = df.format(liquido);
            lbimp.setText ("Valor dos impostos R$: " +irFormatado);
            lbfinal.setText("O total futuro será R$ " + liquidoFormatado);
            String brutototal = df.format(vf);
            lbbruto.setText("O Valor Bruto R$"+brutototal);
        }else{
            double ir = vf*0.15;
            double liquido = vf - ir;            
            String irFormatado = df.format(ir);
            String liquidoFormatado = df.format(liquido);
            lbimp.setText ("Valor dos impostos R$: " +irFormatado);
            lbfinal.setText("O total futuro será R$ " + liquidoFormatado);
            String brutototal = df.format(vf);
            lbbruto.setText("O Valor Bruto R$"+brutototal);
```

## ⚔️ JavaFX: NetBeans vs IntelliJ IDEA
🟦 NetBeans

***Suporte nativo para JavaFX***

GUI Builder integrado (arrasta e solta)

Gera código automaticamente com FXML e Controller

🟥 IntelliJ IDEA

***Não possui GUI Builder nativo para JavaFX***

Precisa configurar JavaFX SDK manualmente

Ideal para projetos maiores e profissionais

Mais trabalho para iniciantes que querem criar GUI rapidamente

## Exemplo de Telas em JavaFX 1:

![Tela1](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20163242.png)

## Exemplo de Telas em JavaFX 2:

![Tela2](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20163348.png)

## Exemplo de Telas em JavaFX 3:
![tela3](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20163608.png)

## Tools de Menu NetBeans:

![Menus](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20163620.png)

## Alterar cor do texto e Fonte Texto:
![CorTexti](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20164126.png)

## Sistema com ComboxBox | Lancheria:
![Sistema](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-23%20164839.png)
