# DAO (Data Access Object) em Java

Este documento explica **linha por linha** a classe **AlunoDao**, mostrando exatamente o que cada parte faz e qual é sua responsabilidade dentro do padrão DAO.

---

## O que é DAO?

DAO (**Data Access Object**) é um padrão de projeto usado para **isolar o acesso ao banco de dados**.

👉 A classe DAO:

* Apenas acessa o banco (CRUD)
* Não contém regra de negócio
* Não imprime dados

---

## Classe `AlunoDao`

```java
import java.sql.*;
import java.util.ArrayList;
import java.util.List;
```

### Explicação:

* `java.sql.*` → Classes do JDBC (`Connection`, `PreparedStatement`, `ResultSet`)
* `ArrayList` / `List` → Estruturas para armazenar vários alunos

---

```java
public class AlunoDao {
```

### Explicação:

* Declara a classe DAO
* Responsável por acessar a tabela `alunos`

---

## Método CREATE — Cadastrar Aluno

```java
public void cadastrar(Aluno aluno){
```

### Explicação:

* Método público
* Recebe um objeto `Aluno`
* Salva esse aluno no banco

---

```java
String sql = "INSERT INTO alunos (nome) VALUES (?)";
```

### Explicação:

* Comando SQL de inserção
* `?` evita SQL Injection

---

```java
try (
    Connection conn = ConnectionFactory.getConnection();
    PreparedStatement stmt = conn.prepareStatement(sql)
) {
```

### Explicação:

* Abre conexão com o banco
* Cria o `PreparedStatement`
* O Java fecha tudo automaticamente ao final

---

```java
stmt.setString(1, aluno.getNome());
```

### Explicação:

* Substitui o primeiro `?`
* Usa o nome do objeto `Aluno`

---

```java
stmt.executeUpdate();
```

### Explicação:

* Executa o INSERT
* Usado para INSERT, UPDATE e DELETE

---

```java
} catch (Exception e) {
    throw new RuntimeException("Erro ao cadastrar aluno", e);
}
```

### Explicação:

* Trata erros do banco
* Repassa a exceção para quem chamou

---

## Método READ — Listar Alunos

```java
public List<Aluno> listar(){
```

### Explicação:

* Retorna uma lista de alunos
* Busca dados no banco

---

```java
String sql = "SELECT id, nome FROM alunos";
```

### Explicação:

* Comando SQL SELECT

---

```java
List<Aluno> alunos = new ArrayList<>();
```

### Explicação:

* Cria lista vazia para armazenar resultados

---

```java
try (
    Connection conn = ConnectionFactory.getConnection();
    PreparedStatement stmt = conn.prepareStatement(sql);
    ResultSet rs = stmt.executeQuery()
) {
```

### Explicação:

* Executa o SELECT
* `ResultSet` guarda os dados retornados

---

```java
while (rs.next()) {
```

### Explicação:

* Percorre cada linha do resultado

---

```java
int id = rs.getInt("id");
String nome = rs.getString("nome");
```

### Explicação:

* Lê os valores das colunas da tabela

---

```java
Aluno aluno = new Aluno(id, nome);
```

### Explicação:

* Cria objeto Java a partir dos dados do banco

---

```java
alunos.add(aluno);
```

### Explicação:

* Adiciona o aluno na lista

---

```java
} catch (Exception e) {
    throw new RuntimeException("Erro ao listar alunos", e);
}
```

### Explicação:

* Trata erro do SELECT

---

```java
return alunos;
```

### Explicação:

* Retorna a lista pronta

---

## Resumo Final

```
Aluno          → representa a tabela
AlunoDao       → acessa o banco
ConnectionFactory → cria conexão
PreparedStatement → executa SQL seguro
ResultSet      → dados do SELECT
```

---

✔ DAO bem separado
✔ Código organizado
✔ Fácil de manter e evoluir
