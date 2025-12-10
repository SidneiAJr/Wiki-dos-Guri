# ☑️ Optional em Java

`Optional<T>` é uma classe introduzida no Java 8 para **evitar NullPointerException** e representar valores **que podem ou não estar presentes**.

---

## 🔹 Criando Optionals

```java
Optional<String> nome = Optional.of("Maria");
Optional<String> vazio = Optional.empty();
Optional<String> talvez = Optional.ofNullable(null);
```
