# ☕Java — Tipos de Arrays e Coleções

## Array Simples (fixo)

- Estrutura básica com tamanho fixo, não cresce.

- ✔ Características

- Índices numéricos

- Tamanho definido ao criar

- Armazena valores do mesmo tipo

## Comandos principais

| Comando        | Função           |
| -------------- | ---------------- |
| `array.length` | tamanho do array |
| `array[i]`     | acessar elemento |
| `array[i] = x` | alterar valor    |

## ArrayList (Lista)

Lista dinâmica que pode crescer e reduzir.

- Características

- Permite elementos repetidos

- Mantém ordem

- Cresce automaticamente

| Comando      | Função                   |
| ------------ | ------------------------ |
| `add()`      | adiciona elemento        |
| `get()`      | pega elemento por índice |
| `set()`      | altera elemento          |
| `remove()`   | remove por índice/objeto |
| `size()`     | tamanho da lista         |
| `contains()` | verifica se existe       |
| `clear()`    | limpa tudo               |
| `isEmpty()`  | verifica se está vazia   |

## Set (HashSet)

Coleção sem elementos repetidos e sem índice.

- Características

- Sem repetição

- Não garante ordem

- Muito rápido para buscar

| Comando      | Função              |
| ------------ | ------------------- |
| `add()`      | adiciona            |
| `remove()`   | remove elemento     |
| `contains()` | verifica existência |
| `size()`     | tamanho             |
| `clear()`    | limpa               |
| `isEmpty()`  | está vazio?         |

## Map (HashMap)

Armazena pares chave → valor.

- Busca extremamente rápida

- Sem repetição de chave

- Valor pode repetir

| Comando                | Função                   |
| ---------------------- | ------------------------ |
| `put(chave, valor)`    | adiciona ou substitui    |
| `get(chave)`           | obtém valor              |
| `remove(chave)`        | remove um par            |
| `containsKey(chave)`   | verifica chave           |
| `containsValue(valor)` | verifica valor           |
| `keySet()`             | retorna todas as chaves  |
| `values()`             | retorna todos os valores |
| `size()`               | tamanho                  |
| `clear()`              | limpa tudo               |
| `isEmpty()`            | verifica se está vazio   |

## Set + Map (keySet + values)

Combinação muito usada com HashMap:

| Método           | Função                              |
| ---------------- | ----------------------------------- |
| `map.keySet()`   | retorna um *Set* de chaves          |
| `map.values()`   | retorna uma *Collection* de valores |
| `map.entrySet()` | retorna pares chave→valor           |


## Resumo Final

| Estrutura     | Repetição   | Ordem | Índice        | Cresce Dinamicamente | Uso Comum      |
| ------------- | ----------- | ----- | ------------- | -------------------- | -------------- |
| **Array**     | ✔           | ✔     | ✔             | ❌                    | dados fixos    |
| **ArrayList** | ✔           | ✔     | ✔             | ✔                    | listas gerais  |
| **Set**       | ❌           | ❌     | ❌             | ✔                    | valores únicos |
| **Map**       | chave única | ✔     | chave → valor | ✔                    | dicionários    |




