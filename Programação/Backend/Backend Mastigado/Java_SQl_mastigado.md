# ☕ Java + JDBC + MySQL (CRUD) — Versão Mastigada

Este documento **quebra todo o teu código em partes pequenas**, explicando **o que é**, **pra que serve** e **o que pode dar errado**. Sem frescura, no estilo raiz.

---

## 🧠 Visão Geral

O que tu fez aqui é basicamente:

1. Conectar no MySQL
2. Criar banco
3. Criar tabela
4. Inserir dados
5. Consultar dados
6. Atualizar dados
7. Deletar dados

Tudo usando **JDBC puro**.

---

## 1️⃣ Imports (as ferramentas)

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.util.Scanner;
```

### O que cada um faz:

* **Connection** → representa a conexão com o banco
* **DriverManager** → abre a conexão JDBC
* **SQLException** → erros do banco
* **Statement** → executa SQL simples (sem parâmetros)
* **PreparedStatement** → executa SQL com `?` (seguro)
* **ResultSet** → resultado de SELECT
* **Scanner** → entrada pelo teclado

📌 Regra prática:

* `Statement` → criar banco/tabela
* `PreparedStatement` → INSERT, UPDATE, DELETE, SELECT

---

## 2️⃣ Variáveis de conexão

```java
final String URL = "jdbc:mysql://localhost:3306/";
final String USER = "root";
final String PASS = "root";
```

### O que é isso:

* **URL** → endereço do banco
* **USER/PASS** → login do MySQL

📌 Observação:

* Quando **não tem banco ainda**, a URL termina em `3306/`
* Quando **já existe banco**, vira `3306/funcionarios`

---

## 3️⃣ Teste de conexão

```java
try {
    Connection conexao = DriverManager.getConnection(URL, USER, PASS);
    System.out.println("Conectou!");
    conexao.close();
} catch (SQLException e) {
    System.out.println("Não conectou");
}
```

### O que acontece aqui:

1. JDBC tenta conectar
2. Se conectar → imprime sucesso
3. Fecha a conexão
4. Se falhar → cai no `catch`

📌 Isso **não cria banco**, só testa acesso.

---

## 4️⃣ Criar banco de dados

```java
String sql = "CREATE DATABASE IF NOT EXISTS funcionarios";
stm.execute(sql);
```

### Por que funciona:

* `IF NOT EXISTS` evita erro
* `Statement` é suficiente

📌 Aqui ainda **não tem tabela**, só o banco.

---

## 5️⃣ Criar tabela

```java
String sql = "CREATE TABLE IF NOT EXISTS funcionarios (" +
             "id INT AUTO_INCREMENT PRIMARY KEY," +
             "nome VARCHAR(80) NOT NULL," +
             "cargo VARCHAR(50) NOT NULL" +
             ")";
```

### O que cada campo faz:

* `id` → identificador único
* `AUTO_INCREMENT` → cresce sozinho
* `PRIMARY KEY` → chave principal

📌 Sem tabela = nada funciona depois.

---

## 6️⃣ INSERT com Scanner (seguro)

```java
String sql = "INSERT INTO funcionarios (nome, cargo) VALUES (?, ?)";
```

```java
stm.setString(1, nome);
stm.setString(2, cargo);
```

### Por que usar `?`:

* Evita SQL Injection
* Evita erro de aspas

❌ ERRADO:

```sql
INSERT INTO funcionarios VALUES ('" + nome + "')
```

✅ CERTO:

```sql
INSERT INTO funcionarios VALUES (?, ?)
```

---

## 7️⃣ SELECT por ID

```java
String sql = "SELECT * FROM funcionarios WHERE id = ?";
```

```java
stm.setInt(1, id);
ResultSet rs = stm.executeQuery();
```

### Como o SELECT funciona:

* `executeQuery()` → retorna ResultSet
* `rs.next()` → verifica se achou alguém

📌 Se não usar `rs.next()`, quebra.

---

## 8️⃣ UPDATE (perigoso sem WHERE)

❌ PERIGO:

```sql
UPDATE funcionarios SET cargo = 'Dev'
```

👉 Atualiza TODO MUNDO

✅ SEGURO:

```sql
UPDATE funcionarios SET cargo = ?, nome = ? WHERE id = ?
```

📌 UPDATE sem WHERE = justa causa.

---

## 9️⃣ DELETE (mais perigoso ainda)

❌ NUNCA FAÇA:

```sql
DELETE FROM funcionarios;
```

👉 Apaga tudo.

✅ CERTO:

```sql
DELETE FROM funcionarios WHERE id = ?;
```

📌 DELETE sem WHERE = demissão instantânea.

---

## 🔟 Padrão mental pra JDBC

Sempre pense assim:

1. Conectar
2. Montar SQL
3. Preparar statement
4. Passar parâmetros
5. Executar
6. Tratar retorno
7. Fechar conexão

---

## 🧱 O que tu já domina (real oficial)

✔ JDBC puro
✔ CRUD completo
✔ SQL parametrizado
✔ Scanner + banco
✔ Try-with-resources

Isso **já é base de backend Java**.

---

