# Java | Streams API

## O que é a Streams API?

A **Streams API** (Java 8+) é uma forma moderna e funcional de **processar coleções de dados** (`List`, `Set`, `Map`) sem utilizar loops tradicionais como `for` ou `while`.

Ela funciona como um **pipeline de dados**:

> Coleção → Stream → Operações → Resultado

---

## Exemplo simples

### Forma tradicional

```java
List<Integer> numeros = List.of(1, 2, 3, 4, 5, 6);
List<Integer> pares = new ArrayList<>();

for (int n : numeros) {
    if (n % 2 == 0) {
        pares.add(n);
    }
}

System.out.println(pares);
```

### Usando Streams API

```java
List<Integer> numeros = List.of(1, 2, 3, 4, 5, 6);

List<Integer> pares = numeros.stream()
    .filter(n -> n % 2 == 0)
    .toList();

System.out.println(pares);
```

---

## Como um Stream funciona

Um Stream sempre possui três partes:

1️⃣ **Fonte**

```java
numeros.stream();
```

2️⃣ **Operações intermediárias** (retornam um novo stream)

* `filter()`
* `map()`
* `sorted()`

3️⃣ **Operação terminal** (executa o processamento)

* `toList()`
* `forEach()`
* `collect()`
* `reduce()`

Sem operação terminal, **nada é executado**.

---

## Principais operações da Streams API

### filter — filtrar dados

```java
.filter(n -> n > 10)
```

---

### map — transformar dados

```java
.map(n -> n * 2)
```

---

### forEach — percorrer dados

```java
.forEach(System.out::println);
```

---

### collect — coletar resultados

```java
.collect(Collectors.toList());
```

---

### reduce — reduzir tudo a um valor

```java
int soma = numeros.stream()
    .reduce(0, Integer::sum);
```

---

### sorted — ordenar

```java
.sorted();
```

---

## Exemplo real (backend)

```java
class Usuario {
    String nome;
    boolean ativo;
}
```

```java
List<Usuario> usuarios = ...;

List<String> nomesAtivos = usuarios.stream()
    .filter(u -> u.ativo)
    .map(u -> u.nome)
    .toList();
```

---

## Streams paralelos

```java
List<Integer> pares = numeros.parallelStream()
    .filter(n -> n % 2 == 0)
    .toList();
```

⚠️ Use apenas para grandes volumes de dados.

---

## Quando usar Streams

✅ Processamento de listas
✅ Código limpo e legível
✅ Regras de negócio simples

❌ Lógicas muito complexas
❌ Muitas condições encadeadas

---

## Resumo rápido

* Streams = pipeline de dados
* Não alteram a coleção original
* Código mais limpo
* Muito usado em backend Java moderno
