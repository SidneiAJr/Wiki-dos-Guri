# Geração de Código no IntelliJ IDEA

O IntelliJ IDEA oferece diversas ferramentas de **geração automática de código**, permitindo agilizar o desenvolvimento e reduzir a necessidade de digitação manual.  
Essas opções são acessadas principalmente através do atalho **Alt + Insert** (no Windows/Linux) ou **Cmd + N** (no macOS).

---

## 📌 Menu de Geração de Código (Alt + Insert)

Dentro de uma classe, pressionar **Alt + Insert** abre o menu de geração de código.  
As principais opções são:

### 🏗️ **Constructor**
- Gera automaticamente **construtores** para a classe.  
- Pode incluir todos ou apenas alguns atributos.
- Útil para inicializar variáveis de instância rapidamente.

### ⚙️ **Getter e Setter**
- Cria os métodos de acesso (**getters**) e modificação (**setters**) para atributos privados.
- Essencial para o princípio de encapsulamento em Java.

### 🧱 **toString()**
- Gera o método `toString()`, que retorna uma representação textual do objeto.
- Pode ser personalizado para incluir apenas certos atributos.

### 🔁 **equals() e hashCode()**
- Cria automaticamente métodos de comparação (`equals`) e identificação (`hashCode`).
- Muito usado em coleções como `HashMap` e `HashSet`.

### 🔄 **Override Methods**
- Lista todos os métodos herdados de superclasses ou interfaces.
- Permite sobrescrever (override) métodos existentes de forma rápida.

### 🔧 **Implement Methods**
- Mostra os métodos obrigatórios de interfaces ou classes abstratas ainda não implementados.
- Permite adicioná-los automaticamente.

### 🔗 **Delegate Methods**
- Cria métodos que **delegam** chamadas para outro objeto interno.
- Útil em padrões de design como *composition*.

### 🪪 **Generate Serializable UID**
- Gera automaticamente o campo `serialVersionUID` para classes que implementam `Serializable`.

---

## 🧩 Outras Funcionalidades Relacionadas

### 📝 **Generate Comments / Javadoc**
- Gera blocos de comentário Javadoc padrão para classes, métodos e variáveis.
- Atalho: **Alt + Enter** sobre o elemento → *Add Javadoc*.

### 🧱 **Add Field from Constructor**
- Permite criar campos automaticamente a partir de parâmetros do construtor.

### 💡 **Surround With (Ctrl + Alt + T)**
- Envolve o código selecionado com estruturas como `if`, `try/catch`, `for`, etc.
- Exemplo: seleciona um bloco → `Ctrl + Alt + T` → escolhe `try/catch`.

### 🧠 **Live Templates**
- Modelos de código pré-definidos (como `sout`, `psvm`, `fori`, `ifn`).
- Atalho: **Ctrl + J** → abre a lista de templates disponíveis.
- Exemplo: digite `sout` → pressione `Tab` → gera `System.out.println();`.

---

## 🚀 Dica de Produtividade

- **Ctrl + O** → Override Methods  
- **Ctrl + I** → Implement Methods  
- **Alt + Insert** → Menu de geração  
- **Ctrl + Alt + T** → Surround With  
- **Ctrl + J** → Live Templates  
- **Alt + Enter** → Sugestões contextuais de geração/refatoração  

---

## 💡 Dica Extra: Plugins Úteis
- **Lombok Plugin** → Gera getters, setters e construtores automaticamente via anotações (`@Getter`, `@Setter`, `@AllArgsConstructor`, etc).  
- **CodeGlance Pro** → Minimapa de código (como no VS Code).  
- **String Manipulation** → Ferramentas rápidas para formatação e transformação de strings.

---

## 🧩 Conclusão

A geração de código no IntelliJ IDEA é uma das funções mais poderosas da IDE.  
Dominar **Alt + Insert** e os **atalhos relacionados** reduz drasticamente o tempo de escrita e melhora a consistência do código.

> 💬 *Dica do dev*: combine o menu de geração com refatorações automáticas (`Shift + F6`, `Ctrl + Alt + M`, etc.) para produtividade máxima.
