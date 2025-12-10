# ⚡ Atalhos de Código no NetBeans

Os atalhos de código no NetBeans agilizam a escrita de estruturas comuns no Java, poupando tempo e reduzindo erros.  
Abaixo estão os principais **snippets automáticos** disponíveis no editor.

---

## 🖥️ Impressão e Depuração

- **sou** → `System.out.println();`  
  **Explicação:** Gera um comando de impressão no console para depuração ou exibição de mensagens.

- **soutv** → `System.out.println("variável: " + variavel);`  
  **Explicação:** Exibe o valor de uma variável junto com uma mensagem de log.

- **sysout** → `System.out.println();`  
  **Explicação:** Mesma função de `sou`; imprime saídas no console.

---

## 🚀 Estruturas Principais

- **psvm** → `public static void main(String[] args) { }`  
  **Explicação:** Cria automaticamente o método principal de execução do programa.

- **main** → `public static void main(String[] args) { }`  
  **Explicação:** Outro atalho para gerar o método `main`.

- **ctor** → `public NomeClasse() { }`  
  **Explicação:** Cria o construtor padrão da classe.

- **class** → `class NomeClasse { }`  
  **Explicação:** Gera a estrutura de uma nova classe Java.

- **interface** → `interface NomeInterface { }`  
  **Explicação:** Cria a estrutura de uma interface Java.

- **package** → `package nome.do.pacote;`  
  **Explicação:** Define o pacote onde a classe está localizada.

- **import** → `import nome.do.pacote;`  
  **Explicação:** Importa classes ou bibliotecas externas para uso no código.

---

## 🔁 Estruturas de Controle

- **fori** → `for (int i = 0; i < ; i++) { }`  
  **Explicação:** Cria um laço `for` com variável de controle `i`.

- **foreach** → `for (Tipo variavel : colecao) { }`  
  **Explicação:** Itera sobre uma coleção sem precisar controlar índices manualmente.

- **if** → `if () { }`  
  **Explicação:** Estrutura condicional básica.

- **else** → `else { }`  
  **Explicação:** Define o bloco a ser executado se a condição do `if` for falsa.

- **elseif** → `else if () { }`  
  **Explicação:** Adiciona uma nova condição após um `if`.

- **while** → `while () { }`  
  **Explicação:** Executa o bloco enquanto a condição for verdadeira.

- **do** → `do { } while ();`  
  **Explicação:** Executa o bloco pelo menos uma vez antes de testar a condição.

- **switch** →  
  ```java
  switch () {
      case :
          break;
  }
  ```
  
| Categoria    | Atalho                                             | Geração                | Uso                   |
| ------------ | -------------------------------------------------- | ---------------------- | --------------------- |
| Impressão    | `sou`, `sysout`, `soutv`                           | `System.out.println()` | Saídas e logs         |
| Estruturas   | `psvm`, `main`, `ctor`, `class`, `interface`       | Métodos e classes      | Código base           |
| Controle     | `fori`, `foreach`, `if`, `else`, `while`, `switch` | Laços e condicionais   | Lógica de fluxo       |
| Exceções     | `try`, `tryf`, `throw`, `throws`                   | Blocos de tratamento   | Erros e segurança     |
| Entrada      | `sysin`                                            | `Scanner`              | Leitura de dados      |
| Documentação | `javadoc`                                          | `/** ... */`           | Comentários e Javadoc |

