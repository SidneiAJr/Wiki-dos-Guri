# C# – Expressões Lambda

## 1. O que é uma Lambda?
Uma expressão lambda é uma forma curta de escrever funções anônimas.  
É muito usada em LINQ, delegados, eventos e processamento funcional.


---

## 2. Por que usar Lambdas?

- Código mais limpo e direto  
- Fácil integração com LINQ  
- Ideal para filtros, validações e operações rápidas  
- Utilizado em Actions, Funcs e Predicates  

---

## 3. Tipos de Lambdas

### ✔ Lambda de expressão  
Possui apenas uma instrução.  
Retorna valor implicitamente.

### ✔ Lambda de bloco  
Usa `{ }` e permite múltiplas instruções.  
Requer `return` quando houver retorno.

---

## 4. Uso com Delegados

### ✔ Func
Representa funções que **retornam valor**.

### ✔ Action
Representa funções **sem retorno**.

### ✔ Predicate
Retorna booleano (`bool`).

---

## 5. Lambdas em LINQ
Lambdas são a base de:
- Where  
- Select  
- OrderBy  
- Any  
- FirstOrDefault  
- GroupBy  

---

## 6. Escopo e captura de variáveis
Lambdas podem capturar valores da variável externa no momento da criação.

---

## 7. Lambdas e métodos anônimos
Lambdas substituem métodos anônimos pois são mais curtas e mais flexíveis.

---

## 8. Lambdas com async/await
Possível criar lambdas assíncronas:
- async () => ...  
- async value => ...  

---

## 9. Boas práticas

- Use lambdas curtas  
- Use lambdas nomeadas (com métodos) quando ficar grande demais  
- Evite lógica complexa dentro de lambdas  
- Prefira expressões ao invés de blocos quando possível  

---

