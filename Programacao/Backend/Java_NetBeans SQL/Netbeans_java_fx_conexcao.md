# ☕ JavaFX + MySQL (CRUD) – Telas com Labels

Este documento converte o fluxo **Create / Read / Update / Delete** do seu projeto JDBC em **saídas visuais usando JavaFX**, com **Labels**, **TextFields** e **Buttons**.

---

## 📌 Estrutura Base (JavaFX)

```java
import javafx.application.Application;
import javafx.geometry.Insets;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.GridPane;
import javafx.stage.Stage;

public class App extends Application {

    @Override
    public void start(Stage stage) {
        GridPane grid = new GridPane();
        grid.setPadding(new Insets(20));
        grid.setHgap(10);
        grid.setVgap(10);

        Scene scene = new Scene(grid, 420, 300);
        stage.setTitle("Sistema Funcionários");
        stage.setScene(scene);
        stage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

---

## 🔌 Conexão com Banco (Classe Separada)

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class ConexaoDB {
    private static final String URL = "jdbc:mysql://localhost:3306/funcionarios";
    private static final String USER = "root";
    private static final String PASS = "root";

    public static Connection conectar() throws SQLException {
        return DriverManager.getConnection(URL, USER, PASS);
    }
}
```

---

## ➕ Inserir Funcionário (CREATE)

```java
Label lblNome = new Label("Nome:");
TextField txtNome = new TextField();

Label lblCargo = new Label("Cargo:");
TextField txtCargo = new TextField();

Button btnSalvar = new Button("Salvar");
Label lblStatus = new Label();

btnSalvar.setOnAction(e -> {
    String nome = txtNome.getText();
    String cargo = txtCargo.getText();

    String sql = "INSERT INTO funcionarios (nome, cargo) VALUES (?, ?)";

    try (var conn = ConexaoDB.conectar();
         var ps = conn.prepareStatement(sql)) {

        ps.setString(1, nome);
        ps.setString(2, cargo);
        ps.executeUpdate();

        lblStatus.setText("Funcionário cadastrado com sucesso!");

    } catch (Exception ex) {
        lblStatus.setText("Erro ao inserir funcionário");
    }
});
```

---

## 🔍 Buscar Funcionário por ID (READ)

```java
Label lblId = new Label("ID:");
TextField txtId = new TextField();

Label lblNomeOut = new Label("Nome: ");
Label lblCargoOut = new Label("Cargo: ");

Button btnBuscar = new Button("Buscar");

btnBuscar.setOnAction(e -> {
    String sql = "SELECT * FROM funcionarios WHERE id = ?";

    try (var conn = ConexaoDB.conectar();
         var ps = conn.prepareStatement(sql)) {

        ps.setInt(1, Integer.parseInt(txtId.getText()));
        var rs = ps.executeQuery();

        if (rs.next()) {
            lblNomeOut.setText("Nome: " + rs.getString("nome"));
            lblCargoOut.setText("Cargo: " + rs.getString("cargo"));
        } else {
            lblNomeOut.setText("Nome: não encontrado");
            lblCargoOut.setText("Cargo: -");
        }

    } catch (Exception ex) {
        lblNomeOut.setText("Erro na busca");
    }
});
```

---

## ✏️ Atualizar Funcionário (UPDATE)

```java
Button btnAtualizar = new Button("Atualizar");
Label lblUpdateStatus = new Label();

btnAtualizar.setOnAction(e -> {
    String sql = "UPDATE funcionarios SET nome = ?, cargo = ? WHERE id = ?";

    try (var conn = ConexaoDB.conectar();
         var ps = conn.prepareStatement(sql)) {

        ps.setString(1, txtNome.getText());
        ps.setString(2, txtCargo.getText());
        ps.setInt(3, Integer.parseInt(txtId.getText()));

        int linhas = ps.executeUpdate();
        lblUpdateStatus.setText(linhas > 0 ? "Atualizado com sucesso" : "ID não encontrado");

    } catch (Exception ex) {
        lblUpdateStatus.setText("Erro ao atualizar");
    }
});
```

---

## 🗑️ Deletar Funcionário (DELETE)

```java
Button btnDeletar = new Button("Deletar");
Label lblDeleteStatus = new Label();

btnDeletar.setOnAction(e -> {
    String sql = "DELETE FROM funcionarios WHERE id = ?";

    try (var conn = ConexaoDB.conectar();
         var ps = conn.prepareStatement(sql)) {

        ps.setInt(1, Integer.parseInt(txtId.getText()));
        int linhas = ps.executeUpdate();

        lblDeleteStatus.setText(linhas > 0 ? "Deletado com sucesso" : "ID não encontrado");

    } catch (Exception ex) {
        lblDeleteStatus.setText("Erro ao deletar");
    }
});
```

---

## 🧠 Observações Importantes

* JDBC funciona normalmente em **JavaFX (desktop)**
* Sempre use **PreparedStatement**
* Separe **UI**, **Conexão** e **Regras**
* Nunca use JDBC direto em Android

---

## ✅ Próximo nível

* Migrar para **FXML**
* Criar **DAO**
* Aplicar **MVC**
* Adicionar **Alert dialogs**

---

📦 Pronto para subir no GitHub 🚀
