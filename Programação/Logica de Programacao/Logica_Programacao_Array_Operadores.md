# 🧠 Arrays, Vetores, Matrizes e Operadores Lógicos

Este documento explica os conceitos de **arrays**, **vetores**, **matrizes** e **operadores lógicos**, fundamentais para a construção de soluções eficientes em programação.

---

## 1) **Arrays** (ou Vetores)

Arrays são estruturas que permitem **armazenar múltiplos valores** em uma única variável.  
Em vez de criar várias variáveis para armazenar valores semelhantes, você usa um array.

### Conceitos Importantes

- **Indexação**: Arrays começam a ser indexados de 0. Ou seja, o primeiro valor está no índice 0, o segundo no 1 e assim por diante.
- **Tamanho fixo**: O tamanho de um array é definido no momento da sua criação. Depois disso, o tamanho não pode ser alterado (em algumas linguagens).

---

### Vantagens dos Arrays
- **Armazenamento de dados de forma compacta**.
- **Acesso rápido aos elementos**, pois é possível acessar qualquer valor pelo índice.

---

### Tipos de Arrays

| Tipo | Descrição |
|------|-----------|
| **Unidimensionais** | Armazenam valores em uma única linha (ex.: uma lista de números). |
| **Multidimensionais** | Armazenam dados em mais de uma dimensão (ex.: uma tabela de valores). |

---

## 2) **Vetores**

Na maioria das linguagens, **vetores são o mesmo que arrays**.  
O termo **vetor** é mais comum em **matemática e física**.

A principal diferença é semântica — ambos armazenam dados de maneira sequencial.  
A única diferença pode ser no nome dependendo da linguagem (em C, C++, e Java por exemplo, “vetor” e “array” são intercambiáveis).

---

## 3) **Matrizes**

Matrizes são **arrays multidimensionais**.  
Elas são **arrays dentro de arrays**, permitindo armazenar dados de forma bidimensional (ou mais dimensões, dependendo da aplicação).

Exemplo mental: pense em uma **tabela**, onde cada linha é um array, e a tabela toda é uma matriz.

### Exemplo de matriz (2D)
- Matrizes são usadas para representar dados estruturados em **linhas e colunas**.

---

| Índice | Coluna 1 | Coluna 2 | Coluna 3 |
|--------|----------|----------|----------|
| **Linha 1** | 1 | 2 | 3 |
| **Linha 2** | 4 | 5 | 6 |
| **Linha 3** | 7 | 8 | 9 |

- No exemplo acima, a matriz tem **3 linhas** e **3 colunas**. Você acessa o valor utilizando a combinação de índice de linha e coluna.

---

## 4) **Operadores Lógicos**

Operadores lógicos são usados para **tomar decisões** baseadas em **condições**. Eles são fundamentais quando você precisa fazer **comparações entre variáveis** ou decidir qual caminho o programa deve seguir.

### Tipos de Operadores Lógicos

| Operador | Descrição |
|----------|-----------|
| **AND (&&)** | Retorna `true` se ambas as condições forem verdadeiras. |
| **OR (||)**  | Retorna `true` se pelo menos uma condição for verdadeira. |
| **NOT (!)**  | Retorna `true` se a condição for falsa, e `false` se a condição for verdadeira. |

### Exemplos de uso

- **AND**: `(x > 5) && (y < 10)` — ambos precisam ser verdadeiros.
- **OR**: `(x > 5) || (y < 10)` — basta um ser verdadeiro.
- **NOT**: `!(x > 5)` — inverte o resultado da condição.

---

## 5) **Operadores Relacionais**

Os operadores **relacionais** são utilizados para comparar valores. Eles retornam `true` ou `false`.

| Operador | Significado | Exemplo |
|----------|-------------|---------|
| **==** | Igualdade | `x == y` (verifica se x é igual a y) |
| **!=** | Diferente | `x != y` (verifica se x é diferente de y) |
| **>** | Maior que | `x > y` |
| **<** | Menor que | `x < y` |
| **>=** | Maior ou igual | `x >= y` |
| **<=** | Menor ou igual | `x <= y` |

---

## 6) **Combinando Operadores**

Você pode combinar operadores lógicos e relacionais para **fazer comparações complexas**.

Exemplo:
