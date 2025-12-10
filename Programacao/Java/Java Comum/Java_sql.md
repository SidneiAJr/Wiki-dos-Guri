# 🗄️ JDBC Básico — CRUD com MySQL

Este guia ensina como conectar o Java a um banco de dados **MySQL** e realizar operações básicas de **CRUD** (Create, Read, Update, Delete) utilizando **JDBC (Java Database Connectivity)**.

---

## ⚙️ Pré-requisitos

- Ter o **MySQL Server** instalado.  
- Ter o **JDK 8+** configurado.  
- Adicionar o **Driver JDBC do MySQL** (arquivo `.jar`) ao projeto.

> 💡 Dica: Se estiver usando o NetBeans, vá em  
> `Project Properties → Libraries → Add JAR/Folder`  
> e selecione o arquivo `mysql-connector-j-X.X.X.jar`.

---

## 🧱 1. Criar o Banco de Dados

No MySQL, crie um banco e uma tabela de exemplo:

```sql
CREATE DATABASE loja;
USE loja;

CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    preco DECIMAL(10,2),
    quantidade INT
);
```

## Conectando Java:

```Java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class Conexao {
    private static final String URL = "jdbc:mysql://localhost:3306/loja";
    private static final String USER = "root";
    private static final String PASSWORD = "1234"; // troque pela sua senha

    public static Connection getConnection() {
        try {
            return DriverManager.getConnection(URL, USER, PASSWORD);
        } catch (SQLException e) {
            System.out.println("Erro na conexão: " + e.getMessage());
            return null;
        }
    }
}
import java.sql.Connection;
import java.sql.PreparedStatement;

public class InserirProduto {
    public static void main(String[] args) {
        String sql = "INSERT INTO produtos (nome, preco, quantidade) VALUES (?, ?, ?)";

        try (Connection conn = Conexao.getConnection();
             PreparedStatement stmt = conn.prepareStatement(sql)) {

            stmt.setString(1, "Mouse Gamer");
            stmt.setDouble(2, 199.90);
            stmt.setInt(3, 10);
            stmt.executeUpdate();

            System.out.println("Produto inserido com sucesso!");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
import java.sql.*;

public class ListarProdutos {
    public static void main(String[] args) {
        String sql = "SELECT * FROM produtos";

        try (Connection conn = Conexao.getConnection();
             Statement stmt = conn.createStatement();
             ResultSet rs = stmt.executeQuery(sql)) {

            while (rs.next()) {
                System.out.println(
                    rs.getInt("id") + " | " +
                    rs.getString("nome") + " | R$" +
                    rs.getDouble("preco") + " | qtd: " +
                    rs.getInt("quantidade")
                );
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
import java.sql.Connection;
import java.sql.PreparedStatement;

public class AtualizarProduto {
    public static void main(String[] args) {
        String sql = "UPDATE produtos SET preco = ? WHERE nome = ?";

        try (Connection conn = Conexao.getConnection();
             PreparedStatement stmt = conn.prepareStatement(sql)) {

            stmt.setDouble(1, 149.90);
            stmt.setString(2, "Mouse Gamer");
            int linhas = stmt.executeUpdate();

            System.out.println(linhas + " produto(s) atualizado(s).");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
import java.sql.Connection;
import java.sql.PreparedStatement;

public class DeletarProduto {
    public static void main(String[] args) {
        String sql = "DELETE FROM produtos WHERE nome = ?";

        try (Connection conn = Conexao.getConnection();
             PreparedStatement stmt = conn.prepareStatement(sql)) {

            stmt.setString(1, "Mouse Gamer");
            int linhas = stmt.executeUpdate();

            System.out.println(linhas + " produto(s) removido(s).");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}

```
