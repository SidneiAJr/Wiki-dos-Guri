# JavaScript | CRUD

## O que é CREATE, INSERT, UPDATE e DELETE?

Esses termos representam as **operações básicas de banco de dados**, muito utilizadas no desenvolvimento de backends.

---

## CREATE

**CREATE** significa **criar um novo registro** no banco de dados.

No SQL, a operação de CREATE (no contexto do CRUD) normalmente é realizada utilizando o comando **INSERT**.

### 📌 Exemplo

```js
const comandoBanco = "INSERT INTO usuarios (nome, email) VALUES (?, ?)";
```

## INSERT

O INSERT é o comando SQL responsável por inserir dados em uma tabela.

No contexto do CRUD
CREATE (CRUD) → INSERT (SQL)

### 📌 Exemplo completo
app.post('/usuarios', (req, res) => {
    const { nome, email } = req.body;

    const comandoBanco = "INSERT INTO usuarios (nome, email) VALUES (?, ?)";

    connection.query(comandoBanco, [nome, email], (erro) => {
        if (erro) {
            return res.status(500).send("Erro ao inserir usuário");
        }

        res.status(201).send("Usuário criado com sucesso");
    });
});

## UPDATE

O UPDATE é utilizado para atualizar informações de um registro que já existe no banco de dados.

📌 Exemplo
const comandoBanco = "UPDATE usuarios SET nome = ?, email = ? WHERE id = ?";

No contexto do CRUD
UPDATE (CRUD) → UPDATE (SQL)

## DELETE

O DELETE é utilizado para remover registros do banco de dados.

📌 Exemplo
const comandoBanco = "DELETE FROM usuarios WHERE id = ?";

No contexto do CRUD
DELETE (CRUD) → DELETE (SQL)

## `O que são os ? na query?`

Os ? são chamados de parâmetros preparados (prepared statements).

Eles servem para:

Evitar SQL Injection

Garantir mais segurança

Separar o comando SQL dos dados do usuário

📌 Exemplo
´´´js
connection.query(
    "INSERT INTO usuarios (nome, email) VALUES (?, ?)",
    [nome, email]
);
´´´

➡ O MySQL substitui cada ? pelo valor correspondente do array de forma segura.

## Resumo rápido

* CREATE → cria registros (INSERT)

* READ → lê registros (SELECT)

* UPDATE → atualiza registros (UPDATE)

* DELETE → remove registros (DELETE)

* ? → blindagem de parâmetros contra SQL Injection