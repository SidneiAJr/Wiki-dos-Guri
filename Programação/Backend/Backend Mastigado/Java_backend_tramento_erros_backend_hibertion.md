# ☕ Hibernate em Java — ERROS COMUNS + EXCEPTIONS + comparação com Entity Framework (C#)

Este canvas junta **tudo de uma vez**, do jeito que você pediu:

* erros reais de Hibernate
* exceptions do Java (SQL, conversão, runtime, etc.)
* tipos de `catch`
* comparação direta com C# / Entity Framework

---

## 🚨 Erros MAIS COMUNS em Hibernate (vida real)

### 1️⃣ LazyInitializationException

**Erro clássico de iniciante.**

Causa:

* Você tenta acessar um relacionamento `LAZY`
* Fora da sessão do Hibernate

```java
Usuario u = usuarioRepository.findById(1L).get();
u.getPedidos().size(); // 💥 erro aqui
```

Motivo:

* A sessão já fechou

Soluções reais:

* Usar `fetch join`
* Usar DTO
* Abrir transação corretamente

---

### 2️⃣ N+1 Problem

Sintoma:

* Uma query busca usuários
* Para cada usuário, outra query busca pedidos

Resultado:

* Performance horrível

Solução:

```java
@Query("SELECT u FROM Usuario u JOIN FETCH u.pedidos")
List<Usuario> buscarTudo();
```

---

### 3️⃣ ConstraintViolationException

Causa:

* Violação de regra do banco

Exemplos:

* `unique = true`
* `not null`
* chave estrangeira inválida

```java
email duplicado
```

---

### 4️⃣ TransactionRequiredException

Causa:

* Update/delete sem transação

```java
usuario.setNome("Novo Nome"); // sem @Transactional
```

---

### 5️⃣ MappingException

Causa:

* Relacionamento mal mapeado
* `mappedBy` errado

---

## ⚠️ Exceptions IMPORTANTES do Hibernate

| Exception                    | Motivo              |
| ---------------------------- | ------------------- |
| LazyInitializationException  | sessão fechada      |
| ConstraintViolationException | regra do banco      |
| MappingException             | erro de mapeamento  |
| ObjectNotFoundException      | registro não existe |
| StaleStateException          | concorrência        |

---

## 🧨 Exceptions IMPORTANTES do Java (backend)

### SQLException

Erro direto do banco:

```java
catch (SQLException e) {
    e.printStackTrace();
}
```

Causas:

* SQL inválido
* tabela não existe
* erro de conexão

---

### NumberFormatException

Conversão inválida:

```java
Integer.parseInt("abc"); // 💥
```

---

### NullPointerException

Objeto nulo:

```java
Usuario u = null;
u.getNome(); // 💥
```

---

### ClassCastException

Cast inválido:

```java
Object x = "texto";
Integer y = (Integer) x; // 💥
```

---

### IllegalArgumentException

Argumento inválido:

```java
Thread.sleep(-1);
```

---

### ArrayIndexOutOfBoundsException

```java
int[] x = new int[2];
x[5] = 10;
```

---

## 🧩 Tipos de catch (Java)

### Catch simples

```java
try {
   // código
} catch (Exception e) {
   e.printStackTrace();
}
```

---

### Catch específico (CORRETO)

```java
try {
   Integer.parseInt("abc");
} catch (NumberFormatException e) {
   System.out.println("Número inválido");
}
```

---

### Múltiplos catch

```java
try {
   // código
} catch (NumberFormatException e) {
} catch (SQLException e) {
} catch (Exception e) {
}
```

---

### Multi-catch

```java
catch (SQLException | IOException e) {
}
```

---

### Finally

```java
finally {
   // sempre executa
}
```

---

## 🧠 Checked vs Unchecked Exceptions

### Checked

* Obrigam tratamento
* Exemplo: `SQLException`

### Unchecked (RuntimeException)

* Não obrigam tratamento
* Exemplo: `NullPointerException`

Hibernate usa **MUITO RuntimeException**.

---

## 🔄 Hibernate (Java) x Entity Framework (C#)

### Conceito geral

| Java            | C#               |
| --------------- | ---------------- |
| Hibernate / JPA | Entity Framework |
| @Entity         | [Table]          |
| @Id             | [Key]            |
| JPQL            | LINQ             |
| Session         | DbContext        |

---

### Entidade Java (Hibernate)

```java
@Entity
public class Usuario {
   @Id
   @GeneratedValue
   private Long id;
}
```

### Entidade C# (Entity Framework)

```csharp
public class Usuario {
   [Key]
   public long Id { get; set; }
}
```

---

### Buscar dados

**Hibernate (JPQL)**

```java
SELECT u FROM Usuario u
```

**Entity Framework (LINQ)**

```csharp
context.Usuarios.ToList();
```

---

### Relacionamento

Hibernate:

```java
@OneToMany(mappedBy = "usuario")
```

Entity Framework:

```csharp
public List<Pedido> Pedidos { get; set; }
```

---

### Lazy Loading

* Hibernate: explícito
* EF: automático (ou proxy)

---

## 🎯 Mercado (realidade)

* Java + Hibernate → bancos, governo, ERP
* C# + EF → empresas Microsoft, jogos, sistemas internos

Quem domina Hibernate aprende EF rápido.

---

