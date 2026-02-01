# C# – Coleções e Generics

## 1. Por que usar Generics?
Generics permitem criar classes e métodos que funcionam com qualquer tipo, garantindo:
- Segurança de tipo  
- Melhor desempenho  
- Reutilização de código  

Exemplo de uso:
- List<T>  
- Dictionary<TKey, TValue>  
- Queue<T>  
- Stack<T>  

---

## 2. Coleções Genéricas Principais

### ✔ List<T>
Lista dinâmica que permite adicionar, remover e acessar itens por índice.

---

### ✔ Dictionary<TKey, TValue>
Estrutura de chave–valor.  
Chaves não podem se repetir.

---

### ✔ HashSet<T>
Coleção que não permite valores duplicados.

---

### ✔ Queue<T>
Fila (FIFO — primeiro a entrar, primeiro a sair).

---

### ✔ Stack<T>
Pilha (LIFO — último a entrar, primeiro a sair).

---

## 3. Interfaces Importantes

### ✔ IEnumerable<T>
Permite iteração (foreach).  
Base para LINQ.

---

### ✔ ICollection<T>
Fornece métodos como Add(), Remove(), Count.

---

### ✔ IList<T>
Adiciona acesso por índice.

---

## 4. Quando usar cada coleção

- **List<T>** → lista geral, acessos por índice  
- **Dictionary<TKey,TValue>** → buscas rápidas por chave  
- **HashSet<T>** → garantir unicidade  
- **Queue<T>** → processamento em fila  
- **Stack<T>** → histórico, undo/redo  
- **IEnumerable<T>** → leitura sequencial  

---

## 5. Collections vs Generics

As coleções antigas (ArrayList, Hashtable):
- Não são seguras quanto ao tipo  
- Exigem casting  
- São menos performáticas  

Por isso, sempre preferir:
- List  
- Dictionary  
- Queue  
- Stack  
- HashSet  

---

## 6. Coleções Imutáveis
Disponíveis em System.Collections.Immutable.

Permitem:
- Segurança em concorrência  
- Imutabilidade funcional  

---

## 7. Generics Avançado

### ✔ Constraints (restrições)
Limitam os tipos aceitos por um método/classe genérica:
- where T : class  
- where T : struct  
- where T : new()  
- where T : BaseClass  

---

### ✔ Delegates genéricos
- Func<T>  
- Action<T>  
- Predicate<T>  

---

### ✔ Métodos Genéricos
Funções que aceitam qualquer tipo T.

---
