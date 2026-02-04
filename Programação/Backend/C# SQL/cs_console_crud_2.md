# Visão geral

Este código é uma aplicação **Console em C#** que se conecta a um banco **MySQL** e executa operações básicas de **CRUD** (listar, atualizar, deletar), além de testar a conexão com o banco.

Ele segue um estilo **old school / didático**, tudo bem explícito, ideal pra aprendizado.

---

# 1. Estrutura principal (Main)

```csharp
class program
{
    public static void Main(string[] args)
```

Aqui é o **ponto de entrada** do programa. Tudo começa no `Main`.

O programa roda em **loop** até o usuário escolher a opção `5 - Sair`.

### Menu

* 1 → Testar conexão com o banco
* 2 → Listar funcionários
* 3 → Deletar funcionário
* 4 → Atualizar funcionário
* 5 → Sair

O `while (op != 5)` mantém o menu ativo.

O `int.TryParse` evita erro se o usuário digitar letra.

---

# 2. Switch (controle das opções)

```csharp
switch (op)
```

Cada `case` chama uma **classe específica**, separando responsabilidades:

* `ConectarBanco` → só testa conexão
* `ListaTodos` → SELECT
* `DeletarFuncionario` → DELETE
* `AtualizarFuncionario` → UPDATE

Isso já é um **mini princípio de organização (SRP)**.

---

# 3. Interface verificaBanco

```csharp
interface verificaBanco
{
    public void verificarconexção();
}
```

Define um **contrato**: toda classe que implementar essa interface **precisa** ter o método `verificarconexção()`.

É simples, mas já introduz o conceito de **interfaces**.

---

# 4. Classe ConectarBanco

Responsável **somente** por testar a conexão com o MySQL.

### Construtor

Recebe:

* Host
* Banco
* Porta
* Usuário
* Senha

E monta a `connectionString`.

### Método verificarconexção()

* Abre conexão com `MySqlConnection`
* Se conectar → mensagem de sucesso
* Se falhar → mostra o erro

Uso de `using` garante que a conexão será **fechada automaticamente**.

---

# 5. Classe ListaTodos (SELECT)

```sql
SELECT id_funcionario, nome_funcionario FROM funcionarios
```

* Abre conexão
* Executa um `SELECT`
* Usa `MySqlDataReader`
* Lê linha por linha com `reader.Read()`

Mostra os dados no console.

---

# 6. Classe DeletarFuncionario (DELETE)

Fluxo:

1. Usuário digita o ID
2. SQL com parâmetro `@id`
3. `ExecuteNonQuery()`
4. Verifica quantas linhas foram afetadas

Se `linhas > 0` → deletou
Se não → ID não existe

👉 Uso de **parâmetros** evita SQL Injection.

---

# 7. Classe AtualizarFuncionario (UPDATE)

Fluxo:

1. Usuário informa ID
2. Digita novo nome
3. SQL com `@nome` e `@id`
4. Executa UPDATE
5. Confere se atualizou alguém

---

# 8. Pontos positivos do código

✔ Separação por classes
✔ Uso de parâmetros SQL
✔ Uso de `using`
✔ Código claro e didático
✔ CRUD funcional

---

# 9. Pontos que podem melhorar (próximo nível)

* Centralizar `connectionString`
* Criar classe `Funcionario`
* Tratar `int.Parse` com `TryParse`
* Implementar INSERT
* Usar DAO / Repository
* Migrar para async/await

---


