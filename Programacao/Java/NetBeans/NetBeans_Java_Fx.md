# ☕ Tutorial de JavaFX no NetBeans

Este guia explica, passo a passo, como criar e executar um projeto JavaFX utilizando o **NetBeans**.

---

## 🔧 Pré-requisitos

- Tenha o **NetBeans** instalado.  
- Certifique-se de ter o **Java JDK** compatível com JavaFX (versão 8 ou superior).

---

## 🚀 Passo a Passo

### 1. Abrir o NetBeans
Abra o software **NetBeans** no seu computador.

---

### 2. Criar um novo projeto
- Vá em **File → New Project**  
- Selecione **JavaFX Application** (ou **Java Application**, se for usar manualmente os módulos JavaFX)  
- Clique em **Next**, dê um nome ao projeto e finalize em **Finish**.

---

### 3. Criar o Formulário JavaFX
- No painel de projetos, clique com o botão direito sobre o pacote principal.  
- Selecione **New → Other → JavaFX → FXML Document** (ou Java Form, dependendo da versão).  
- Dê um nome ao arquivo, por exemplo: `TelaPrincipal.fxml`.

Imagem Tools | Netbeans

![Netbenas-tools](https://github.com/SidneiAJr/Documentacao/blob/main/prints/10.PNG)

---

### 4. Montar a Interface Gráfica
- Abra o arquivo `.fxml` no **Scene Builder** (ou diretamente no editor visual do NetBeans).  
- **Arraste** e **solte** os componentes que desejar, como:
  - `TextField` (campo de texto)
  - `Label` (rótulo)
  - `Button` (botão)

### Opções de Menu: 

![Menu](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20163620.png)

### Configurações:

![Configurações](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20164126.png)

### Exemplo de Menu JAVA: 

![Menu](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-21%20163608.png)
---

### 5. Fazer a Programação
- No arquivo **Controller** (gerado junto com o FXML), escreva o código Java que controla os eventos.  
  Exemplo simples:

  ```java
  @FXML
  private TextField inputNome;
  
  @FXML
  private Label lblSaida;
  
  @FXML
  private void exibirMensagem() {
      String nome = inputNome.getText();
      lblSaida.setText("Olá, " + nome + "!");
  }
  ```

### 🧠 Dica Extra — Criando Eventos Direto no Botão

Você pode criar o **evento de escuta (event handler)** diretamente no botão, sem precisar acessar o *Scene Builder*.

Basta clicar **com o botão direito** sobre o componente (ex: um `Button`) no editor do NetBeans e escolher **"Eventos → Ação → actionPerformed"** (ou similar).

Em seguida, o NetBeans vai criar automaticamente o método de evento dentro do código, onde você pode programar a lógica desejada, por exemplo:

```java
private void btnCalcularActionPerformed(java.awt.event.ActionEvent evt) {                                            
    // Exemplo de conversão de valores
    String valorStr = txtValor.getText();
    double valor = Double.parseDouble(valorStr);
    
    lblResultado.setText("O valor convertido é: " + valor);
}
```

## 6. Compilar e Testar

Pressione Shift + F6 para executar o projeto.

O JavaFX abrirá a janela da sua aplicação.


## 7. Gerar o Build

Clique no ícone de vassoura (Build Project) ou pressione F11.

Isso cria os arquivos necessários para distribuir o programa.

## 8. Ajustar o MANIFEST.MF

Vá até a pasta:
- Onde seu Projeto foi salvo aparecera em baixo
- Depois disso se tentar abrir o arquivo provavel que ele não abra
- Precisa fazer uma configuração no manifest.xml


```xml
Manifest-Version: 1.0
Created-By: Maven JAR Plugin 3.4.1
Build-Jdk-Spec: 24
Main-Class: com.mycompany.bc.menu
// Ali em Main-Class tem que colocar...
// Chamada de Menu
  new calcjr().setVisible(true);
```

### 9. Ajustar o MANIFEST.MF

Caso o aplicativo não abra ao clicar duas vezes no .jar, é necessário ajustar o arquivo MANIFEST.MF para apontar corretamente a classe principal.

Caminho do arquivo (geralmente):
```xml
dist/META-INF/MANIFEST.MF

Manifest-Version: 1.0
Created-By: Maven JAR Plugin 3.4.1
Build-Jdk-Spec: 24
Main-Class: com.mycompany.bc.menu
```

