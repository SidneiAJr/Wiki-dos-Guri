# 🧩 Atalho Alt + Insert no NetBeans

O atalho Alt + Insert no NetBeans abre o menu de geração automática de código, que facilita a criação de estruturas comuns em classes Java, poupando tempo e reduzindo erros manuais.

O atalho **Alt + Insert** no NetBeans abre o menu de **geração de código** dentro de uma classe. Ele é muito útil para criar rapidamente código repetitivo sem precisar digitar tudo manualmente.

# 🧩 Atalho **Alt + Insert** no NetBeans

O atalho **`Alt + Insert`** no NetBeans abre o menu de **geração automática de código**, que facilita a criação de estruturas comuns em classes Java, poupando tempo e reduzindo erros manuais.

---

## ⚙️ Funcionalidades Principais

### 🏗️ **Construtor (Constructor)**
- Gera automaticamente o construtor da classe, com todos ou alguns atributos.
- Permite inicializar campos rapidamente e garantir consistência na criação de objetos.

### 🧩 **Getters e Setters**
- Cria os métodos de acesso (`get`) e modificação (`set`) para os atributos da classe.
- Essencial para aplicar **encapsulamento**, mantendo atributos privados e acessos controlados.

### 🔁 **Override Methods**
- Lista os métodos herdados que podem ser sobrescritos.
- Facilita a personalização de comportamentos de superclasses ou interfaces implementadas.

### 🧠 **Implement Methods**
- Exibe métodos obrigatórios de interfaces ou classes abstratas ainda não implementados.
- Ajuda a manter a classe compatível com contratos de interface e abstrações.

### 🧾 **toString()**
- Gera automaticamente o método `toString()`, criando uma representação textual da classe (geralmente incluindo os atributos).
- Útil para depuração, logs e exibição de dados.

### 🔍 **hashCode() e equals()**
- Gera os métodos `hashCode()` e `equals()` com base em atributos selecionados.
- Importante para comparação de objetos e funcionamento correto em coleções (`HashSet`, `HashMap`, etc).

### 🧱 **Delegating Methods**
- Cria métodos que delegam chamadas para outro objeto interno da classe.
- Facilita a aplicação do **princípio de composição** em design orientado a objetos.

### ⚡ **Insert Code**
- A opção geral do menu, permitindo inserir rapidamente qualquer um dos elementos acima.

---

## 🧰 Funcionalidades Adicionais do **Alt + Insert**

Além das opções mais conhecidas, o NetBeans também oferece recursos extras através do mesmo menu:

### 🧩 **Override/Implement Abstract Methods**
- Mostra todos os métodos abstratos ou de interfaces que precisam ser implementados.
- Ideal para garantir que a classe cumpra os contratos exigidos.

### 📝 **Generate Comments / Javadoc**
- Cria automaticamente **Javadocs** para classes, métodos e atributos.
- Padroniza a documentação do código e facilita manutenção.

### 🔐 **Generate Serializable UID**
- Se a classe implementa `Serializable`, o NetBeans pode gerar o campo `serialVersionUID` automaticamente.
- Evita erros de serialização e mantém compatibilidade entre versões da classe.

### 🧱 **Add Field from Constructor**
- Permite gerar automaticamente atributos da classe com base nos parâmetros de um construtor.
- Útil para transformar parâmetros em propriedades da classe sem digitar manualmente.

### 🔄 **Delegate Methods**
- Gera métodos que chamam internamente outros objetos (delegação de comportamento).
- Facilita o uso do padrão **Delegation**.

### 🧩 **Insert Code Templates**
- Acessa **snippets** e **templates personalizados** de código (como `sout`, `fori`, `psvm`, etc.).
- Pode ser expandido via configurações ou plugins.

### ⚙️ **Custom Code Generation**
- Permite a inclusão de opções extras conforme os plugins instalados no NetBeans.
- Exemplo: geração de entidades JPA, controladores ou métodos específicos de frameworks.

### 🖱️ **Event Handlers (GUI)**
- Em projetos com **Swing** ou **JavaFX**, permite gerar métodos de tratamento de eventos automaticamente (`actionPerformed`, `mouseClicked`, etc.).
- Integração direta com os componentes visuais.

### 🚀 **Main Method**

- Gera rapidamente o método principal:
  ```java
  public static void main(String[] args) {
      // código principal aqui
  }
```
