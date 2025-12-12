# 🐘 PHP | CRUD completo com PDO

CRUD = Create, Read, Update, Delete
As quatro operações básicas de qualquer sistema com banco de dados.

## Estrutura básica usada no exemplo

```bash
crud/
 ├── Database.php
 ├── Usuario.php
 └── index.php
```

## `Banco de Dados | Teste`

```sql
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100)
);
```

## Use PDO

```php
use PDO;
use PDOException;
```

## Propriedades da classe

```php
private string $host = "localhost";
private string $db   = "meu_banco";
private string $user = "root";
private string $password = "";
private string $charset = "utf8mb4";
private ?PDO $connection = null;
```

## Metodo de Conexção

```php
public function getConnection(): PDO
    {
        if ($this->connection === null) {
            try {
                $this->connection = new PDO(
                    "mysql:host={$this->host};dbname={$this->db};charset={$this->charset}",
                    $this->user,
                    $this->password,
                    [
                        PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION
                    ]
                );
            } catch (PDOException $e) {
                die("Erro ao conectar: " . $e->getMessage());
            }
        }
    }
````

## Retorno

```php
return $this->connection;
```

## Model com CRUD (Usuario.php)

```php
<?php

use PDO;

class Usuario {

    private PDO $db;

    public function __construct(PDO $connection)
    {
        $this->db = $connection;
    }

    // CREATE
    public function create(string $nome, string $email): bool
    {
        $sql = "INSERT INTO usuarios (nome, email) VALUES (:nome, :email)";
        $stmt = $this->db->prepare($sql);

        return $stmt->execute([
            ':nome'  => $nome,
            ':email' => $email
        ]);
    }

    // READ - todos
    public function all(): array
    {
        $sql = "SELECT * FROM usuarios";
        $stmt = $this->db->query($sql);

        return $stmt->fetchAll(PDO::FETCH_ASSOC);
    }

    // READ - por ID
    public function find(int $id): ?array
    {
        $sql = "SELECT * FROM usuarios WHERE id = :id";
        $stmt = $this->db->prepare($sql);
        $stmt->execute([':id' => $id]);

        $result = $stmt->fetch(PDO::FETCH_ASSOC);
        return $result ?: null;
    }

    // UPDATE
    public function update(int $id, string $nome, string $email): bool
    {
        $sql = "UPDATE usuarios SET nome = :nome, email = :email WHERE id = :id";
        $stmt = $this->db->prepare($sql);

        return $stmt->execute([
            ':id'    => $id,
            ':nome'  => $nome,
            ':email' => $email
        ]);
    }

    // DELETE
    public function delete(int $id): bool
    {
        $sql = "DELETE FROM usuarios WHERE id = :id";
        $stmt = $this->db->prepare($sql);

        return $stmt->execute([':id' => $id]);
    }
}
```

## Index.php 

```php
<?php

require "Database.php";
require "Usuario.php";

$db = new Database();
$conn = $db->getConnection();

$usuario = new Usuario($conn);

// CREATE
$usuario->create("João", "joao@email.com");

// READ
print_r($usuario->all());

// READ por ID
print_r($usuario->find(1));

// UPDATE
$usuario->update(1, "João Silva", "joao.silva@email.com");

// DELETE
$usuario->delete(1);
````

## Resumo do CRUD

| Operação | Método             | SQL    |
| -------- | ------------------ | ------ |
| Create   | `create()`         | INSERT |
| Read     | `all()` / `find()` | SELECT |
| Update   | `update()`         | UPDATE |
| Delete   | `delete()`         | DELETE |
