# Java | JDBC Avançado (DAO, PreparedStatement, Transações)

## O que é JDBC?

**JDBC (Java Database Connectivity)** é a API padrão do Java para comunicação com bancos de dados relacionais.

No nível profissional, JDBC é usado com **boas práticas**, separando responsabilidades e garantindo segurança.

---

## Problemas do JDBC básico

❌ SQL misturado com regra de negócio
❌ Uso incorreto de `Statement`
❌ Falta de tratamento de erro
❌ Código difícil de manter

A solução é aplicar **DAO + PreparedStatement + Transações**.

---

## Padrão DAO (Data Access Object)

O DAO é responsável **apenas** pelo acesso ao banco de dados.

### Estrutura comum

```
model/
 └─ Usuario.java

dao/
 └─ UsuarioDAO.java

service/
 └─ UsuarioService.java
```

---

## Modelo (Entity)

```java
public class Usuario {
    private Long id;
    private String nome;
    private String email;

    // getters e setters
}
```

---

## Conexão com o banco

```java
public class ConexaoFactory {

    private static final String URL = "jdbc:mysql://localhost:3306/banco";
    private static final String USER = "root";
    private static final String PASS = "root";

    public static Connection getConnection() throws SQLException {
        return DriverManager.getConnection(URL, USER, PASS);
    }
}
```

---

## PreparedStatement (SEGURANÇA)

Evita **SQL Injection** e melhora desempenho.

```java
String sql = "INSERT INTO usuarios (nome, email) VALUES (?, ?)";

PreparedStatement stmt = conn.prepareStatement(sql);
stmt.setString(1, usuario.getNome());
stmt.setString(2, usuario.getEmail());
stmt.executeUpdate();
```

Nunca use `Statement` em produção.

---

## UsuarioDAO

```java
public class UsuarioDAO {

    public void salvar(Usuario usuario) throws SQLException {
        String sql = "INSERT INTO usuarios (nome, email) VALUES (?, ?)";

        try (Connection conn = ConexaoFactory.getConnection();
             PreparedStatement stmt = conn.prepareStatement(sql)) {

            stmt.setString(1, usuario.getNome());
            stmt.setString(2, usuario.getEmail());
            stmt.executeUpdate();
        }
    }

    public Usuario buscarPorId(Long id) throws SQLException {
        String sql = "SELECT * FROM usuarios WHERE id = ?";

        try (Connection conn = ConexaoFactory.getConnection();
             PreparedStatement stmt = conn.prepareStatement(sql)) {

            stmt.setLong(1, id);
            ResultSet rs = stmt.executeQuery();

            if (rs.next()) {
                Usuario u = new Usuario();
                u.setId(rs.getLong("id"));
                u.setNome(rs.getString("nome"));
                u.setEmail(rs.getString("email"));
                return u;
            }
        }
        return null;
    }
}
```

---

## Service Layer

```java
public class UsuarioService {

    private UsuarioDAO dao = new UsuarioDAO();

    public Usuario buscar(Long id) {
        try {
            Usuario usuario = dao.buscarPorId(id);

            if (usuario == null) {
                throw new RuntimeException("Usuário não encontrado");
            }
            return usuario;
        } catch (SQLException e) {
            throw new RuntimeException("Erro ao acessar banco", e);
        }
    }
}
```

---

## Transações

Usadas quando múltiplas operações precisam ser **atômicas**.

```java
Connection conn = ConexaoFactory.getConnection();

try {
    conn.setAutoCommit(false);

    // operação 1
    // operação 2

    conn.commit();
} catch (Exception e) {
    conn.rollback();
} finally {
    conn.close();
}
```

---

## JDBC + Streams

```java
List<Usuario> usuarios = dao.listarTodos();

List<String> emails = usuarios.stream()
    .map(Usuario::getEmail)
    .toList();
```

---

## Boas práticas

✅ Use DAO
✅ Use PreparedStatement
✅ Separe Service de DAO
✅ Use transações quando necessário
❌ SQL no controller

---

## Resumo final

* JDBC é base do Java backend
* DAO organiza o acesso a dados
* PreparedStatement garante segurança
* Transações evitam inconsistência
* Conhecimento esperado de dev sênior
