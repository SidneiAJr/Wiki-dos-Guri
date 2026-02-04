# Conversão para MVC (arquivos separados)

A seguir está a **conversão do teu código Console C# + MySQL para MVC**, mantendo o espírito **didático / old school**, mas com organização profissional.

---

# Estrutura de pastas (MVC)

```
ProjetoMVC
│
├── Program.cs
│
├── Controllers
│   └── FuncionarioController.cs
│
├── Models
│   ├── Funcionario.cs
│   └── FuncionarioModel.cs
│
├── Views
│   └── FuncionarioView.cs
│
├── Data
│   └── Database.cs
```

👉 Mesmo sendo Console, o padrão MVC **funciona perfeitamente**.

---

# 1. Model — Entidade (Models/Funcionario.cs)

Representa a tabela `funcionarios`.

```csharp
public class Funcionario
{
    public int Id { get; set; }
    public string Nome { get; set; }
}
```

---

# 2. Model — Acesso a Dados (Models/FuncionarioModel.cs)

Aqui fica **todo SQL** (CRUD).

```csharp
using MySql.Data.MySqlClient;
using System.Collections.Generic;

public class FuncionarioModel
{
    private string connectionString = "Server=localhost;Port=3306;Database=empresa;Uid=root;Pwd=root;";

    public List<Funcionario> Listar()
    {
        List<Funcionario> lista = new List<Funcionario>();
        string sql = "SELECT id_funcionario, nome_funcionario FROM funcionarios";

        using (MySqlConnection conn = new MySqlConnection(connectionString))
        {
            conn.Open();
            using (MySqlCommand cmd = new MySqlCommand(sql, conn))
            using (MySqlDataReader reader = cmd.ExecuteReader())
            {
                while (reader.Read())
                {
                    lista.Add(new Funcionario
                    {
                        Id = reader.GetInt32(0),
                        Nome = reader.GetString(1)
                    });
                }
            }
        }
        return lista;
    }

    public bool Deletar(int id)
    {
        string sql = "DELETE FROM funcionarios WHERE id_funcionario = @id";
        using (MySqlConnection conn = new MySqlConnection(connectionString))
        {
            conn.Open();
            using (MySqlCommand cmd = new MySqlCommand(sql, conn))
            {
                cmd.Parameters.AddWithValue("@id", id);
                return cmd.ExecuteNonQuery() > 0;
            }
        }
    }

    public bool Atualizar(int id, string nome)
    {
        string sql = "UPDATE funcionarios SET nome_funcionario = @nome WHERE id_funcionario = @id";
        using (MySqlConnection conn = new MySqlConnection(connectionString))
        {
            conn.Open();
            using (MySqlCommand cmd = new MySqlCommand(sql, conn))
            {
                cmd.Parameters.AddWithValue("@nome", nome);
                cmd.Parameters.AddWithValue("@id", id);
                return cmd.ExecuteNonQuery() > 0;
            }
        }
    }
}
```

---

# 3. View — Console (Views/FuncionarioView.cs)

Responsável **somente por entrada e saída de dados**.

```csharp
using System;
using System.Collections.Generic;

public class FuncionarioView
{
    public void MostrarLista(List<Funcionario> funcionarios)
    {
        foreach (var f in funcionarios)
        {
            Console.WriteLine($"ID: {f.Id} | Nome: {f.Nome}");
        }
    }

    public int PedirId()
    {
        Console.Write("Digite o ID: ");
        return int.Parse(Console.ReadLine());
    }

    public string PedirNome()
    {
        Console.Write("Digite o nome: ");
        return Console.ReadLine();
    }
}
```

---

# 4. Controller (Controllers/FuncionarioController.cs)

Faz a **ponte entre View e Model**.

```csharp
using System;

public class FuncionarioController
{
    private FuncionarioModel model = new FuncionarioModel();
    private FuncionarioView view = new FuncionarioView();

    public void Listar()
    {
        var lista = model.Listar();
        view.MostrarLista(lista);
    }

    public void Deletar()
    {
        int id = view.PedirId();
        if (model.Deletar(id))
            Console.WriteLine("Funcionário deletado!");
        else
            Console.WriteLine("Funcionário não encontrado");
    }

    public void Atualizar()
    {
        int id = view.PedirId();
        string nome = view.PedirNome();
        if (model.Atualizar(id, nome))
            Console.WriteLine("Funcionário atualizado!");
        else
            Console.WriteLine("Funcionário não encontrado");
    }
}
```

---

# 5. Program.cs (Main)

Somente menu e controle.

```csharp
using System;

class Program
{
    static void Main()
    {
        FuncionarioController controller = new FuncionarioController();
        int op = 0;

        while (op != 5)
        {
            Console.WriteLine("1- Listar | 2- Deletar | 3- Atualizar | 5- Sair");
            op = int.Parse(Console.ReadLine());

            switch (op)
            {
                case 1: controller.Listar(); break;
                case 2: controller.Deletar(); break;
                case 3: controller.Atualizar(); break;
            }
        }
    }
}
```

---

# Por que isso é MVC de verdade?

* **Model** → Banco e regras
* **View** → Console (entrada/saída)
* **Controller** → Orquestra tudo

Isso é a mesma lógica usada em:

* ASP.NET MVC
* APIs
* Sistemas grandes

---



