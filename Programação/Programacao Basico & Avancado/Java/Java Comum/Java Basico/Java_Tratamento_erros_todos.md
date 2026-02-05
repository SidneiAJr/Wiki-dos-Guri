# ☕ Java Backend — MAPA COMPLETO de Exceptions (bem mastigado)

Este canvas é um **guia definitivo** de exceptions para **Java backend profissional**.
Aqui está **tudo organizado**, por categoria, com explicação simples e uso real.

---

## 🧨 O que são Exceptions (recap rápido)

* Erros que acontecem **em tempo de execução**
* Podem quebrar API, serviço ou aplicação
* No backend, **saber tratar é obrigatório**

---

## 🧱 1️⃣ Exceptions de BANCO DE DADOS

### JDBC (baixo nível)

#### SQLException (CHECKED)

* Erro direto do banco
* SQL inválido, tabela inexistente, conexão falhou

```java
throw new SQLException("Erro de banco");
```

---

### JPA / Hibernate

* `PersistenceException`
  → erro genérico de persistência

* `DataIntegrityViolationException`
  → violação de constraint (unique, FK, not null)

* `EntityNotFoundException`
  → entidade não encontrada

* `TransactionRequiredException`
  → operação sem transação

* `OptimisticLockException`
  → conflito de concorrência

* `LazyInitializationException`
  → LAZY fora da sessão

---

## 🔢 2️⃣ Exceptions de CONVERSÃO / DADOS

* `NumberFormatException`
  → texto convertido para número inválido

* `DateTimeParseException`
  → data inválida

* `ConversionFailedException` (Spring)
  → falha de conversão automática

* `InputMismatchException`
  → input incompatível

---

## ☠️ 3️⃣ Exceptions de OBJETO / LÓGICA

* `NullPointerException`
  → objeto nulo

* `IllegalArgumentException`
  → argumento inválido

* `IllegalStateException`
  → estado inválido do objeto

* `ClassCastException`
  → cast inválido

* `IndexOutOfBoundsException`
  → índice fora do limite

* `ConcurrentModificationException`
  → modificação durante iteração

---

## 🌐 4️⃣ Exceptions de API / WEB (Spring Boot)

* `HttpMessageNotReadableException`
  → JSON inválido

* `MethodArgumentNotValidException`
  → validação de DTO falhou

* `MissingServletRequestParameterException`
  → parâmetro obrigatório ausente

* `HttpRequestMethodNotSupportedException`
  → método HTTP errado

* `ResponseStatusException`
  → erro HTTP manual

---

## 🔐 5️⃣ Exceptions de SEGURANÇA

(Spring Security)

* `AuthenticationException`
  → falha de autenticação

* `BadCredentialsException`
  → login inválido

* `AccessDeniedException`
  → sem permissão

---

## ⚙️ 6️⃣ Exceptions de I/O e SISTEMA

* `IOException`
* `FileNotFoundException`
* `EOFException`
* `InterruptedException`

---

## 🧠 7️⃣ Checked vs Unchecked (ESSENCIAL)

### Checked Exceptions

* Obrigam try/catch
* Exemplo: `SQLException`, `IOException`

### Unchecked Exceptions

* Estendem `RuntimeException`
* Exemplo: `NullPointerException`, `IllegalArgumentException`

Hibernate e Spring usam **principalmente Unchecked**.

---

## 💥 8️⃣ Errors (NÃO são Exceptions)

Esses **não se tratam com catch**:

* `OutOfMemoryError`
* `StackOverflowError`
* `VirtualMachineError`

São erros da JVM.

---

## 🧩 9️⃣ Onde tratar cada erro (arquitetura)

* **Controller**
  → nunca lógica pesada

* **Service**
  → lança exceptions

* **Handler Global** (`@ControllerAdvice`)
  → trata TODAS

---

## 🛡️ 1️⃣0️⃣ Boas práticas de backend

* Nunca retornar stacktrace
* Sempre logar erro
* Mensagem limpa para cliente
* Código HTTP correto

---

