# 🧩 Generics em Java

## 📘 Introdução
**Generics** permitem criar **classes, interfaces e métodos** que trabalham com **tipos parametrizados**, ou seja, o tipo de dado é definido no momento da utilização.  
Isso aumenta a **reutilização**, **segurança de tipo** e **clareza** do código.

Com Generics, o compilador pode detectar **erros de tipo em tempo de compilação**, evitando *casts* manuais e falhas em tempo de execução.

---

## 🧠 Conceito

Generics introduzem o conceito de **parâmetros de tipo**, geralmente representados por letras maiúsculas:

| Símbolo | Significado Comum |
|----------|------------------|
| T | Type (Tipo genérico) |
| E | Element (Elemento em coleções) |
| K | Key (Chave em mapas) |
| V | Value (Valor em mapas) |
| N | Number (Número) |

Esses parâmetros são substituídos por **tipos concretos** quando a classe ou método é instanciado.

---

## ⚙️ Como Funcionam

- Permitem que o **mesmo código** funcione para diferentes tipos de dados.  
- Eliminam a necessidade de **conversões explícitas (casts)**.  
- Melhoram a **segurança de tipo**, garantindo que apenas o tipo esperado seja usado.  
- São **verificados em tempo de compilação**, não em tempo de execução.

---

## 🧱 Estrutura Conceitual

Um tipo genérico define um **modelo de comportamento** para qualquer tipo que seja passado como parâmetro.  
Por exemplo:

- Uma classe genérica pode armazenar ou processar qualquer tipo de dado.  
- Um método genérico pode operar sobre listas de diferentes tipos, sem duplicar código.  
- Interfaces genéricas permitem padronizar comportamentos em estruturas como coleções.

---

## 🧩 Benefícios Principais

- **Reutilização:** um único código serve para múltiplos tipos.  
- **Segurança:** impede erros de tipo e elimina *casts*.  
- **Legibilidade:** o tipo fica explícito na declaração.  
- **Desempenho:** o tipo é resolvido em tempo de compilação, sem custo extra em runtime.

---

## 📦 Tipos de Uso Comum

### 1. Classes Genéricas
Permitem criar estruturas de dados ou utilitários que aceitam diferentes tipos de elementos.

Exemplo conceitual: uma "Caixa" que pode conter qualquer tipo de objeto (texto, número, etc).

---

### 2. Métodos Genéricos
Um método pode ser declarado com um **tipo genérico local**, tornando-o independente de tipos fixos.  
Isso é útil para algoritmos reutilizáveis, como busca, ordenação ou validação.

---

### 3. Interfaces Genéricas
Permitem definir **contratos flexíveis** aplicáveis a vários tipos, como coleções (`List<T>`, `Map<K,V>`) ou repositórios (`Repository<T>`).

---

## 🔒 Tipos Limitados (Bounded Types)

Generics permitem restringir o tipo aceito:

- **Upper Bound (`extends`)** → aceita apenas um tipo ou seus subtipos.  
  Exemplo conceitual: `T extends Number` → apenas tipos numéricos.

- **Lower Bound (`super`)** → aceita um tipo e seus supertipos.  
  Útil para manipular hierarquias de herança em coleções.

Esses limites permitem **controle de comportamento** e **flexibilidade segura**.

---

## 🌀 Wildcards (`?`)

O curinga `?` representa um tipo **desconhecido**, e é usado quando não importa o tipo exato, apenas que ele pertence a uma hierarquia.

Exemplos conceituais de uso:
- `? extends T` → lê dados de uma estrutura (somente leitura).  
- `? super T` → grava dados em uma estrutura (somente escrita).  
- `?` → tipo genérico totalmente desconhecido.

---

## 🧠 Boas Práticas

- Prefira **Generics** a tipos `Object` quando for necessário aceitar diferentes tipos.  
- Evite **usar tipos crus (raw types)** — sempre especifique o tipo genérico.  
- Use **nomes significativos** para os parâmetros de tipo quando forem complexos.  
- Combine Generics com **interfaces e coleções** para código mais limpo e seguro.

---

## 🧰 Aplicações Comuns

- Coleções (`List<T>`, `Set<T>`, `Map<K,V>`)  
- Classes utilitárias (`Comparator<T>`, `Optional<T>`)  
- Frameworks (Spring, JPA, etc.)  
- Padrões de projeto genéricos (Repository, Factory, Builder)

---

## 🧩 Limitações dos Generics

- Não é possível usar tipos primitivos diretamente (`int`, `double` etc.).  
- Não há **informação de tipo em runtime** devido ao *type erasure*.  
- Não é permitido criar **instâncias diretas** de parâmetros genéricos (`new T()` não é válido).  
- Arrays de tipos genéricos não são suportados diretamente (`new T[]` não é permitido).

---

## 🧭 Conclusão
**Generics** são um dos pilares da linguagem Java moderna.  
Eles trazem **segurança, reuso e clareza**, reduzindo erros e duplicações de código.

> Usar Generics corretamente é escrever **código elegante, seguro e escalável**.

---
