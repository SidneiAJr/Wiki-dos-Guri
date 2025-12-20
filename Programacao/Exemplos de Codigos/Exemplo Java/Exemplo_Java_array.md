# 📦 Java – Arrays, ArrayList, Set e Map (bem mastigado)

Este documento explica **cada pedaço** dos exemplos de Arrays em Java, no estilo **wiki pessoal** para revisão rápida.

---

## 🔹 1) Array Comum

### O que é?

Um **Array** é uma estrutura **fixa**, com tamanho definido na criação.

```java
double array[] = new double[6];
```

* `double` → tipo dos dados
* `6` → tamanho fixo (não cresce, não diminui)

---

### Preenchendo o Array

```java
for(int i=0; i<array.length; i++){
    array[i] = entrada.nextDouble();
}
```

* `array.length` → tamanho do array
* `i` → índice (posição)
* `array[i]` → acesso direto à posição

👉 Sempre começa do **0**.

---

### Exibindo os valores

```java
for(int i=0; i<array.length; i++){
    System.out.println(array[i]);
}
```

👉 Percorre todas as posições e imprime os valores.

---

### Quando usar Array?

✔ Quando o tamanho é conhecido
✔ Quando performance importa
❌ Quando precisa crescer/diminuir

---

## 🔹 2) ArrayList (Lista)

### O que é?

Um **ArrayList** é uma lista **dinâmica**.

```java
List<String> lista = new ArrayList<>();
```

* Cresce automaticamente
* Trabalha com objetos (não tipos primitivos diretos)

---

### Adicionando elementos

```java
lista.add("Arthur");
lista.add("Jian");
```

* `add()` → adiciona no final da lista

---

### Removendo elementos

```java
lista.remove("Joao da massa");
```

* Remove pelo **valor** ou pelo **índice**

---

### Acessando elementos

```java
String p1 = lista.get(0);
```

* `get(index)` → acesso por posição

---

### Alterando valor

```java
lista.set(2, "Lukao o brabo");
```

* Substitui o valor da posição informada

---

### Tamanho da lista

```java
int tamanho = lista.size();
```

---

### Quando usar ArrayList?

✔ Lista dinâmica
✔ Ordem importa
✔ Acesso por índice

---

## 🔹 3) Set (HashSet)

### O que é?

Um **Set** armazena **valores únicos**.

```java
Set<String> tecnologia = new HashSet<>();
```

---

### Adicionando elementos

```java
tecnologia.add("Java");
tecnologia.add("Java");
```

👉 Valor duplicado **não entra**.

---

### Tamanho

```java
int tamanho = tecnologia.size();
```

---

### Percorrendo o Set

```java
for(String tech : tecnologia){
    System.out.println(tech);
}
```

* Não usa índice
* Ordem **não garantida** (HashSet)

---

### Quando usar Set?

✔ Evitar duplicados
✔ Listas únicas
❌ Quando precisa de índice

---

## 🔹 4) Map (HashMap)

### O que é?

Um **Map** funciona como **chave → valor**.

```java
Map<String, Double> poderes = new HashMap<>();
```

* Cada chave é única
* Valores podem repetir

---

### Inserindo dados

```java
poderes.put("Eldrin", 750.0);
```

---

### Atualizando valor

```java
double antigo = poderes.put("Eldrin", 800.0);
```

* Retorna o valor antigo

---

### Buscando valor

```java
double poder = poderes.get("Mira");
```

---

### Percorrendo o Map

```java
for(Map.Entry<String, Double> entry : poderes.entrySet()){
    System.out.println(entry.getKey() + " - " + entry.getValue());
}
```

---

### Quando usar Map?

✔ Cadastros
✔ Dicionários
✔ Configurações

---

