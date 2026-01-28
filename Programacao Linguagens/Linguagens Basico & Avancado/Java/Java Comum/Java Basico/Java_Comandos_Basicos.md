# Java Comandos Básicos:

## Comandos Básicos de String em Java:

- **`length()`**  
  Retorna o **tamanho** da string (quantidade de caracteres).

- **`charAt(int index)`**  
  Retorna o **caractere** na posição especificada pela variável `index`.

- **`substring(int beginIndex, int endIndex)`**  
  Retorna uma **subsequência** da string, começando no índice `beginIndex` e indo até `endIndex` (não inclusivo).

- **`equals(String anotherString)`**  
  Verifica se a string atual é **igual** a outra string, retornando um valor **booleano**.

- **`equalsIgnoreCase(String anotherString)`**  
  Verifica se a string atual é **igual** a outra string, ignorando diferenças de **maiúsculas e minúsculas**.

- **`toLowerCase()`**  
  Converte todos os caracteres da string para **minúsculas**.

- **`toUpperCase()`**  
  Converte todos os caracteres da string para **maiúsculas**.

- **`trim()`**  
  **Remove os espaços em branco** no início e no final da string.

- **`replace(char oldChar, char newChar)`**  
  **Substitui** todas as ocorrências do caractere `oldChar` por `newChar` na string.

- **`contains(CharSequence sequence)`**  
  Verifica se a string contém a sequência de caracteres `sequence`, retornando `true` ou `false`.

- **`startsWith(String prefix)`**  
  Verifica se a string começa com o prefixo especificado.

- **`endsWith(String suffix)`**  
  Verifica se a string termina com o sufixo especificado.

- **`indexOf(String str)`**  
  Retorna o **índice** da primeira ocorrência da string `str` dentro da string atual, ou `-1` se não encontrar.

- **`split(String regex)`**  
  **Divide a string** em um array de substrings com base no delimitador `regex`.

- **`isEmpty()`**  
  Verifica se a string está **vazia** (tamanho igual a zero).

- **`valueOf(int x)`**  
  Converte um valor numérico (como `int`, `double`) para uma **string**.

- **`isBlank()`**  
  Verifica se a string está **em branco** (ou seja, contém apenas espaços em branco). Retorna `true` se a string estiver vazia ou contiver apenas espaços. 

---

## Comandos Básicos de Arrays em Java:

- **`length`**  
  Retorna o **tamanho** do array (quantidade de elementos no array).

- **`Arrays.toString()`**  
  Converte o array em uma **string** que pode ser impressa. Útil para visualizar o conteúdo de um array.

- **`Arrays.copyOf()`**  
  **Cria uma cópia** do array, com ou sem alteração no tamanho.

- **`Arrays.copyOfRange()`**  
  **Copia uma parte específica** do array, definida pelos índices `from` e `to`.

- **`Arrays.sort()`**  
  **Ordena o array** em ordem crescente.

- **`Arrays.fill()`**  
  **Preenche todos os elementos** do array com o valor fornecido.

- **`Arrays.equals()`**  
  Verifica se **dois arrays são iguais**, comparando seus elementos.

- **`Arrays.binarySearch()`**  
  Realiza uma **busca binária** em um array (precisa que o array esteja ordenado).

- **`Arrays.stream()`**  
  Converte um array em um **stream**, o que permite aplicar operações de stream (como `filter`, `map`, etc.).

---

# Java — Comandos Básicos

---

## 📌 Strings — Métodos Essenciais

| Método | Descrição | Exemplo |
|--------|-----------|---------|
| `length()` | Retorna o tamanho da string | `"Java".length()` → `4` |
| `charAt(int index)` | Retorna o caractere na posição indicada | `"Java".charAt(1)` → `'a'` |
| `substring(int a, int b)` | Retorna parte da string entre os índices | `"Java".substring(1,3)` → `"av"` |
| `equals(String s)` | Compara strings exatamente | `"a".equals("A")` → `false` |
| `equalsIgnoreCase(String s)` | Compara ignorando maiúsculas | `"a".equalsIgnoreCase("A")` → `true` |
| `toLowerCase()` | Converte para minúsculas | `"JAVA".toLowerCase()` |
| `toUpperCase()` | Converte para maiúsculas | `"java".toUpperCase()` |
| `trim()` | Remove espaços no início e fim | `"  oi  ".trim()` → `"oi"` |
| `replace(char old, char new)` | Substitui caracteres | `"Java".replace('a','o')` → `"Jovo"` |
| `contains(CharSequence s)` | Verifica se contém trecho | `"Java".contains("av")` |
| `startsWith(String s)` | Verifica se começa com | `"Java".startsWith("Ja")` |
| `endsWith(String s)` | Verifica se termina com | `"Java".endsWith("va")` |
| `indexOf(String s)` | Retorna índice da primeira ocorrência | `"Java".indexOf("a")` → `1` |
| `split(String regex)` | Divide string em partes | `"a,b,c".split(",")` |
| `isEmpty()` | Verifica se está vazia | `"".isEmpty()` |
| `isBlank()` | Verifica se contém apenas espaços | `"   ".isBlank()` |
| `String.valueOf(x)` | Converte valores para string | `String.valueOf(10)` → `"10"` |

---

## 📌 Arrays — Métodos e Funções Comuns

| Método | Descrição | Exemplo |
|--------|-----------|---------|
| `array.length` | Tamanho do array | `int[] a = {1,2}; a.length` |
| `Arrays.toString()` | Converte array para string legível | `Arrays.toString(a)` |
| `Arrays.copyOf()` | Copia array | `Arrays.copyOf(a, 5)` |
| `Arrays.copyOfRange()` | Copia intervalo específico | `Arrays.copyOfRange(a,0,2)` |
| `Arrays.sort()` | Ordena array | `Arrays.sort(a)` |
| `Arrays.fill()` | Preenche array com valor | `Arrays.fill(a, 0)` |
| `Arrays.equals()` | Compara arrays | `Arrays.equals(a,b)` |
| `Arrays.binarySearch()` | Busca binária (array ordenado) | `Arrays.binarySearch(a,5)` |
| `Arrays.stream()` | Converte para Stream | `Arrays.stream(a)` |

---

## Exemplos rápidos

### 🔹 Dividir string
```java
String[] partes = "a-b-c".split("-");



