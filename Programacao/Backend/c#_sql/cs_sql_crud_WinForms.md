# ☕ C# + MySQL (CRUD) – Telas com Labels (WinForms)

Este documento converte o fluxo **Create / Read / Update / Delete** (antes em Java/JDBC/JavaFX) para **C# com WinForms**, usando **Labels**, **TextBox** e **Buttons**.

---

## 📦 Pacote Necessário

Instale via **NuGet**:

```bash
MySql.Data
```

Namespace usado:

```csharp
using MySql.Data.MySqlClient;
```

---

## 🔌 Conexão com Banco (Classe Separada)

```csharp
using MySql.Data.MySqlClient;

public class ConexaoDB
{
    private static string conexaoString =
        "Server=localhost;Database=funcionarios;Uid=root;Pwd=root;";

    public static MySqlConnection Conectar()
    {
        return new MySqlConnection(conexaoString);
    }
}
```

---

## 🖥️ Estrutura da Tela (WinForms)

### Componentes:

* TextBox: `txtId`, `txtNome`, `txtCargo`
* Label: `lblResultado`
* Buttons: `btnInserir`, `btnBuscar`, `btnAtualizar`, `btnDeletar`

---

## ➕ Inserir Funcionário (CREATE)

```csharp
private void btnInserir_Click(object sender, EventArgs e)
{
    string sql = "INSERT INTO funcionarios (nome, cargo) VALUES (@nome, @cargo)";

    using (var conn = ConexaoDB.Conectar())
    using (var cmd = new MySqlCommand(sql, conn))
    {
        cmd.Parameters.AddWithValue("@nome", txtNome.Text);
        cmd.Parameters.AddWithValue("@cargo", txtCargo.Text);

        conn.Open();
        cmd.ExecuteNonQuery();

        lblResultado.Text = "Funcionário inserido com sucesso!";
    }
}
```

---

## 🔍 Buscar Funcionário por ID (READ)

```csharp
private void btnBuscar_Click(object sender, EventArgs e)
{
    string sql = "SELECT * FROM funcionarios WHERE id = @id";

    using (var conn = ConexaoDB.Conectar())
    using (var cmd = new MySqlCommand(sql, conn))
    {
        cmd.Parameters.AddWithValue("@id", txtId.Text);
        conn.Open();

        using (var reader = cmd.ExecuteReader())
        {
            if (reader.Read())
            {
                txtNome.Text = reader["nome"].ToString();
                txtCargo.Text = reader["cargo"].ToString();
                lblResultado.Text = "Funcionário encontrado";
            }
            else
            {
                lblResultado.Text = "Funcionário não encontrado";
            }
        }
    }
}
```

---

## ✏️ Atualizar Funcionário (UPDATE)

```csharp
private void btnAtualizar_Click(object sender, EventArgs e)
{
    string sql = "UPDATE funcionarios SET nome=@nome, cargo=@cargo WHERE id=@id";

    using (var conn = ConexaoDB.Conectar())
    using (var cmd = new MySqlCommand(sql, conn))
    {
        cmd.Parameters.AddWithValue("@nome", txtNome.Text);
        cmd.Parameters.AddWithValue("@cargo", txtCargo.Text);
        cmd.Parameters.AddWithValue("@id", txtId.Text);

        conn.Open();
        int linhas = cmd.ExecuteNonQuery();

        lblResultado.Text = linhas > 0
            ? "Funcionário atualizado com sucesso"
            : "ID não encontrado";
    }
}
```

---

## 🗑️ Deletar Funcionário (DELETE)

```csharp
private void btnDeletar_Click(object sender, EventArgs e)
{
    string sql = "DELETE FROM funcionarios WHERE id=@id";

    using (var conn = ConexaoDB.Conectar())
    using (var cmd = new MySqlCommand(sql, conn))
    {
        cmd.Parameters.AddWithValue("@id", txtId.Text);
        conn.Open();
        int linhas = cmd.ExecuteNonQuery();

        lblResultado.Text = linhas > 0
            ? "Funcionário deletado com sucesso"
            : "ID não encontrado";
    }
}
```

---

## 🧠 Boas Práticas

* Sempre use **parâmetros** (evita SQL Injection)
* Use `using` para fechar conexão automaticamente
* Separe **UI** e **Banco** em projetos maiores
* Ideal para **desktop (WinForms / WPF)**

---

## 🚀 Próximo nível

* Migrar para **WPF (MVVM)**
* Criar **Repository / Service**
* Usar **Entity Framework**

---

