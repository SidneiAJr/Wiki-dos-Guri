# Java | SQL — Formas de Conexão

## Observações

* **JDBC**: Driver de conexão do Java
* **usuario**: Usuário do banco
* **senha**: Senha do banco
* **url**: Endereço de conexão
* **Porta padrão**: `3306` (MySQL)
* O **nome do banco não é fixo na URL** — ele será passado como parâmetro

---

## Importando as Libs

```java
import java.sql.Connection;
// Importa a classe DriveMaganer reposnavel por criar
import java.sql.DriverManager;
// Importa a interface connection que repsenta
import java.sql.ResultSet;
import java.sql.SQLException;
// Importa a classe sql excpetion que representa erro
import java.sql.Statement;
```
---

## Exemplo de Código em Java

```java
public class Conexao {

    private static final String URL_BASE = "jdbc:mysql://localhost:3306/";
    private static final String USER = "root";
    private static final String PASS = "root";

    public static Connection conectar(String nomeBanco) throws SQLException {
        String url = URL_BASE + nomeBanco;
        return DriverManager.getConnection(url, USER, PASS);
    }
}
```

---

## Observações Importantes

* Use `DriverManager.getConnection` para criar a conexão
* Trate exceções com `try/catch` ou `throws SQLException`
* Evite deixar usuário e senha fixos em produção (use variáveis de ambiente)
* Certifique-se de que o **driver JDBC do MySQL** está no projeto

---

## Exemplo de Uso

```java
Connection conn = Conexao.conectar("meu_banco");
```

## Conexção SQL:

```java
public static Connection conectarBanco(String nomeBanco) throws SQLException {
    // Cria a URL completa com o nome do banco
    String url = URL + nomeBanco;

    // Cria e retorna a conexão
    Connection conn = DriverManager.getConnection(url, USER, PASS);

    System.out.println("Conectado com sucesso");
    return conn;
}
```

---

## Codigo Comentado em SQl:

````java
// Classe responsável por gerenciar a conexão com o banco de dados
public class ConexBanco {

    // Nome do banco de dados que será utilizado
    private String nomeBanco;

    // Usuário do banco de dados
    private String usuario;

    // Senha do banco de dados
    private String senha;

    // Objeto que representa a conexão com o banco
    private Connection conn;

    // URL base de conexão com o MySQL
    // Não contém o nome do banco, pois ele será informado dinamicamente
    private static final String URL = "jdbc:mysql://localhost:3306/";

    // Construtor da classe
    // Recebe o nome do banco, usuário e senha como parâmetros
    public ConexBanco(String nomeBanco, String usuario, String senha) {
        this.nomeBanco = nomeBanco;
        this.usuario = usuario;
        this.senha = senha;
    }

    // Método responsável por estabelecer a conexão com o banco de dados
    // Retorna um objeto Connection
    // Lança SQLException caso ocorra algum erro durante a conexão
    public Connection conectar() throws SQLException {

        // Monta a URL completa de conexão, incluindo o nome do banco
        String urlCompleta = URL + nomeBanco;

        // Cria a conexão com o banco usando o DriverManager
        conn = DriverManager.getConnection(urlCompleta, usuario, senha);

        // Retorna a conexão criada
        return conn;
    }

    // Método responsável por encerrar a conexão com o banco de dados
    // Lança SQLException caso ocorra algum erro ao fechar a conexão
    public void fecharConexao() throws SQLException {

        // Verifica se a conexão existe antes de tentar fechá-la
        if (conn != null) {
            // Fecha a conexão com o banco
            conn.close();
        }
    }
}
````

## Codigo do Botão:

````java
private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {
    try {
        ConexBanco cx1 = new ConexBanco("test2", "root", "root");
        cx1.conectar();
        lb_saida.setText("Conectado com sucesso!");
    } catch (SQLException e) {
        lb_saida.setText("Erro: " + e.getMessage());
    }
}
````