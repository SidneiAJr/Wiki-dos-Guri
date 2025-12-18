# ☕ C# Console + MySQL (CRUD)

Versão **100% Console**, no mesmo esquema do seu Java JDBC: entrada por `Console.ReadLine()` e saída no terminal.

---

## 📦 Dependência

Instale via **NuGet**:

```bash
MySql.Data
```

---

## 🔌 Conexão com Banco

```csharp
using MySql.Data.MySqlClient;

public class ConexaoDB
{
    private static string cs = "Server=localhost;Database=funcionarios;Uid=root;Pwd=root;";

    public static MySqlConnection Conectar()
    {
        return new MySqlConnection(cs);
    }
}
```

---

## 📋 MENU (Console)

```csharp
class Program
{
    static void Main()
    {
        int op;
        do
        {
            Console.WriteLine("\n1 - Inserir");
            Console.WriteLine("2 - Buscar por ID");
            Console.WriteLine("3 - Atualizar");
            Console.WriteLine("4 - Deletar");
            Console.WriteLine("0 - Sair");
            Console.Write("Opção: ");

            op = int.Parse(Console.ReadLine());

            switch (op)
            {
                case 1: Inserir(); break;
                case 2: Buscar(); break;
                case 3: Atualizar(); break;
                case 4: Deletar(); break;
            }

        } while (op != 0);
    }
```

---

## ➕ INSERT

```csharp
static void Inserir()
{
    Console.Write("Nome: ");
    string nome = Console.ReadLine();

    Console.Write("Cargo: ");
    string cargo = Console.ReadLine();

    string sql = "INSERT INTO funcionarios (nome, cargo) VALUES (@nome, @cargo)";

    using var conn = ConexaoDB.Conectar();
    using var cmd = new MySqlCommand(sql, conn);

    cmd.Parameters.AddWithValue("@nome", nome);
    cmd.Parameters.AddWithValue("@cargo", cargo);

    conn.Open();
    cmd.ExecuteNonQuery();

    Console.WriteLine("Funcionário inserido com sucesso!");
}
```

---

## 🔍 SELECT por ID

```csharp
static void Buscar()
{
    Console.Write("ID: ");
    int id = int.Parse(Console.ReadLine());

    string sql = "SELECT * FROM funcionarios WHERE id=@id";

    using var conn = ConexaoDB.Conectar();
    using var cmd = new MySqlCommand(sql, conn);

    cmd.Parameters.AddWithValue("@id", id);
    conn.Open();

    using var rd = cmd.ExecuteReader();

    if (rd.Read())
    {
        Console.WriteLine($"ID: {rd["id"]}");
        Console.WriteLine($"Nome: {rd["nome"]}");
        Console.WriteLine($"Cargo: {rd["cargo"]}");
    }
    else
    {
        Console.WriteLine("Funcionário não encontrado");
    }
}
```

---

## ✏️ UPDATE

```csharp
static void Atualizar()
{
    Console.Write("ID: ");
    int id = int.Parse(Console.ReadLine());

    Console.Write("Novo nome: ");
    string nome = Console.ReadLine();

    Console.Write("Novo cargo: ");
    string cargo = Console.ReadLine();

    string sql = "UPDATE funcionarios SET nome=@nome, cargo=@cargo WHERE id=@id";

    using var conn = ConexaoDB.Conectar();
    using var cmd = new MySqlCommand(sql, conn);

    cmd.Parameters.AddWithValue("@nome", nome);
    cmd.Parameters.AddWithValue("@cargo", cargo);
    cmd.Parameters.AddWithValue("@id", id);

    conn.Open();
    int linhas = cmd.ExecuteNonQuery();

    Console.WriteLine(linhas > 0 ? "Atualizado com sucesso" : "ID não encontrado");
}
```

---

## 🗑️ DELETE

```csharp
static void Deletar()
{
    Console.Write("ID: ");
    int id = int.Parse(Console.ReadLine());

    string sql = "DELETE FROM funcionarios WHERE id=@id";

    using var conn = ConexaoDB.Conectar();
    using var cmd = new MySqlCommand(sql, conn);

    cmd.Parameters.AddWithValue("@id", id);
    conn.Open();
    int linhas = cmd.ExecuteNonQuery();

    Console.WriteLine(linhas > 0 ? "Deletado com sucesso" : "ID não encontrado");
}
```

---

## 🧠 Observações

* Mesmo padrão do **Java JDBC Console**
* SQL parametrizado (seguro)
* `using` fecha conexão automaticamente
* Ideal para estudo e scripts

---

