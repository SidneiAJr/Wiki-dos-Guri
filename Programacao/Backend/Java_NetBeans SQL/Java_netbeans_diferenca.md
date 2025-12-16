# Java e Banco de Dados (estilo API / Backend)

Vamos direto ao ponto, no mesmo estilo que fizemos com **mysqli vs PDO**, só que agora em **Java** 😎☕

---

## ❓ Java tem `mysqli`?

**Não.**

* `mysqli` é **exclusivo do PHP**
* Java usa um padrão chamado **JDBC** (*Java Database Connectivity*)

👉 JDBC é a **base de tudo** em Java quando o assunto é banco de dados.

---

## 🧠 O que é JDBC?

**JDBC é uma API padrão do Java** que permite:

* Conectar ao banco (MySQL, PostgreSQL, Oracle, etc)
* Executar SQL
* Ler resultados
* Usar parâmetros (proteção contra SQL Injection)

📌 Ele funciona com **drivers** específicos de cada banco.

Exemplo:

* MySQL → `mysql-connector-j`
* PostgreSQL → `postgresql-driver`

---

## 🔌 Estrutura básica do JDBC

Sempre segue essa ordem:

1️⃣ Abrir conexão
2️⃣ Preparar SQL
3️⃣ Executar comando
4️⃣ Ler resultado (se houver)
5️⃣ Fechar tudo

---

## 🔗 Exemplo: Conexão com MySQL em Java

```java
Connection conn = DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/pokedex",
    "root",
    "root"
);
```

📌 Isso equivale ao `mysqli_connect()` ou `new PDO()` no PHP.

---

## 📝 Executando INSERT (igual teu Express)

```java
String sql = "INSERT INTO pokemons (nome_pokemon, tipo_pokemon, tem_evolucao) VALUES (?, ?, ?)";

PreparedStatement stmt = conn.prepareStatement(sql);
stmt.setString(1, nome);
stmt.setString(2, tipo);
stmt.setString(3, evolucao);

stmt.executeUpdate();
```

🛡️ `PreparedStatement` = **segurança total** contra SQL Injection

📌 Equivalente a:

* `mysqli_prepare()`
* `$pdo->prepare()`

---

## 📥 SELECT com ResultSet

```java
String sql = "SELECT * FROM pokemons";
Statement stmt = conn.createStatement();
ResultSet rs = stmt.executeQuery(sql);

while (rs.next()) {
    System.out.println(rs.getString("nome_pokemon"));
}
```

📌 `ResultSet` é tipo:

* `mysqli_fetch_assoc()`
* `$stmt->fetch()`

---

## 🔄 UPDATE em Java

```java
String sql = "UPDATE pokemons SET nome_pokemon=?, tipo_pokemon=?, tem_evolucao=? WHERE id=?";

PreparedStatement stmt = conn.prepareStatement(sql);
stmt.setString(1, nome);
stmt.setString(2, tipo);
stmt.setString(3, evolucao);
stmt.setInt(4, id);

stmt.executeUpdate();
```

---

## ❌ DELETE em Java

```java
String sql = "DELETE FROM pokemons WHERE id=?";
PreparedStatement stmt = conn.prepareStatement(sql);
stmt.setInt(1, id);
stmt.executeUpdate();
```

---

## 🧱 JDBC cru vs Frameworks

### JDBC puro (raiz)

✔ Mais controle
✔ Bom pra aprender
❌ Mais código
❌ Mais verboso

### Frameworks (vida mansa)

* **Spring JDBC**
* **Spring Data JPA / Hibernate**

Com isso você faz:

```java
pokemonRepository.save(pokemon);
```

😎 Sem SQL explícito

---

## ⚔️ Comparação rápida

| Linguagem | Tecnologia      | Observação                |
| --------- | --------------- | ------------------------- |
| PHP       | mysqli          | Simples, limitado         |
| PHP       | PDO             | Profissional, multi-banco |
| Java      | JDBC            | Base de tudo              |
| Java      | JPA / Hibernate | Mercado, enterprise       |

---

## 🧠 Resumo sincero

* Java **não tem mysqli**
* JDBC é o **equivalente real**
* Java é mais verboso
* Java é mais forte pra projetos grandes
* PHP é mais rápido pra API simples

👉 O que você fez em **Express + MySQL**, dá pra fazer:

* Em **PHP (PDO)**
* Em **Java (JDBC / Spring Boot)**

---

Se quiser, eu faço:

* 🧩 API REST em **Java puro**
* 🚀 API em **Spring Boot** estilo Express
* 🔁 Comparação Express × Spring

É só chamar, meu chefe 😎🔥
