# 🐘 PHP | CRUD com JSON (API REST) usando PDO

Este exemplo mostra como criar uma API REST simples que recebe e retorna JSON, sem HTML, ideal para uso com JS, Thunder Client, Postman, Fetch, Axios, etc.

## 🗄️ Banco de Dados (exemplo)
```php
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100)
);
```
## 🧠 Database.php (conexão PDO)

```php
<?php

use PDO;
use PDOException;

class Database {

    private string $host = "localhost";
    private string $db   = "meu_banco";
    private string $user = "root";
    private string $password = "";
    private string $charset = "utf8mb4";

    private ?PDO $connection = null;

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
                http_response_code(500);
                echo json_encode(["erro" => "Erro ao conectar ao banco"]);
                exit;
            }
        }

        return $this->connection;
    }
}
```

## Usuario.php (Model com CRUD)

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

    // READ (todos)
    public function all(): array
    {
        return $this->db
            ->query("SELECT * FROM usuarios")
            ->fetchAll(PDO::FETCH_ASSOC);
    }

    // READ (por ID)
    public function find(int $id): ?array
    {
        $stmt = $this->db->prepare(
            "SELECT * FROM usuarios WHERE id = :id"
        );
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
        $stmt = $this->db->prepare(
            "DELETE FROM usuarios WHERE id = :id"
        );

        return $stmt->execute([':id' => $id]);
    }
}
```

## 🚦 index.php 

```php
<?php

header("Content-Type: application/json");

require "Database.php";
require "Usuario.php";

$db = new Database();
$conn = $db->getConnection();
$usuario = new Usuario($conn);

$method = $_SERVER['REQUEST_METHOD'];
$id = $_GET['id'] ?? null;

// Lê JSON do corpo da requisição
$input = json_decode(file_get_contents("php://input"), true);

switch ($method) {

    // CREATE
    case "POST":
        if (!isset($input['nome'], $input['email'])) {
            http_response_code(400);
            echo json_encode(["erro" => "Dados inválidos"]);
            break;
        }

        $usuario->create($input['nome'], $input['email']);
        echo json_encode(["status" => "criado"]);
        break;

    // READ
    case "GET":
        if ($id) {
            echo json_encode($usuario->find((int)$id));
        } else {
            echo json_encode($usuario->all());
        }
        break;

    // UPDATE
    case "PUT":
        if (!$id || !isset($input['nome'], $input['email'])) {
            http_response_code(400);
            echo json_encode(["erro" => "Dados inválidos"]);
            break;
        }

        $usuario->update((int)$id, $input['nome'], $input['email']);
        echo json_encode(["status" => "atualizado"]);
        break;

    // DELETE
    case "DELETE":
        if (!$id) {
            http_response_code(400);
            echo json_encode(["erro" => "ID não informado"]);
            break;
        }

        $usuario->delete((int)$id);
        echo json_encode(["status" => "deletado"]);
        break;

    default:
        http_response_code(405);
        echo json_encode(["erro" => "Método não permitido"]);
}
```

## Testando no Thunder

```json
POST /api/index.php
Body (JSON):
{
  "nome": "Carlos",
  "email": "carlos@email.com"
}
```

## 📄 Database.php (com explicação | Mastigada | Pra Lembrar Depois)
```php
<?php

// Importa as classes do PDO
use PDO;
use PDOException;
```

## ⬆️ Diz pro PHP:

“Vou usar PDO e PDOException”
```php
class Database {
```
## ⬆️ Cria uma classe chamada Database
```php
Classe = molde / receita

    private string $host = "localhost";
    private string $db   = "meu_banco";
    private string $user = "root";
    private string $password = "";
    private string $charset = "utf8mb4";
```

## ⬆️ Propriedades da classe
Não são métodos, são variáveis internas do objeto
```php
    private ?PDO $connection = null;
```

## ⬆️ Aqui vai ficar a conexão PDO
```php
Começa null (vazia)

Depois vira um objeto PDO

    public function getConnection(): PDO
```

## ⬆️ Método

Função da classe

Retorna um PDO
```php
        if ($this->connection === null) {
```

## ⬆️ Se ainda não conectou, conecta
Se já conectou, só reutiliza
```php
            try {

```
## ⬆️ Tentativa (try/catch = segurança)
```php
                $this->connection = new PDO(
                    "mysql:host={$this->host};dbname={$this->db};charset={$this->charset}",
                    $this->user,
                    $this->password,
                    [
                        PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION
                    ]
                );

```
## ⬆️ AQUI ACONTECE A CONEXÃO
```php
new PDO() cria a conexão

Se errar → pula pro catch

            } catch (PDOException $e) {
                die("Erro ao conectar: " . $e->getMessage());
            }

```
## ⬆️ Se falhar, o script para e mostra o erro
```php
        }

        return $this->connection;
```
## ⬆️ Devolve a conexão pronta

## 2️⃣ Usuario.php

👉 Responsável pelo CRUD

### 📄 Usuario.php (explicado)
```php
<?php

use PDO;
```

## ⬆️ Usa PDO

class Usuario {


## ⬆️ Classe que representa a tabela usuarios
```php
    private PDO $db;

```
## ⬆️ Aqui fica a conexão recebida
```php
    public function __construct(PDO $connection)
    {
        $this->db = $connection;
    }
```

## ⬆️ Quando cria new Usuario(...),
ele recebe a conexão e guarda
```php
CREATE
    public function create(string $nome, string $email): bool
```

## ⬆️ Método para inserir
```php
        $sql = "INSERT INTO usuarios (nome, email) VALUES (:nome, :email)";
```

## ⬆️ SQL com placeholders (segurança)
```php
        $stmt = $this->db->prepare($sql);
```

## ⬆️ Prepara a query
```php
        return $stmt->execute([
            ':nome'  => $nome,
            ':email' => $email
        ]);
```

## ⬆️ Executa passando os dados
✔ Protege contra SQL Injection
```php
READ (todos)
    public function all(): array
```

## ⬆️ Retorna lista
```php
        return $this->db
            ->query("SELECT * FROM usuarios")
            ->fetchAll(PDO::FETCH_ASSOC);
```

## ⬆️ Busca tudo e retorna como array
```php
READ (por ID)
    public function find(int $id): ?array
```

## ⬆️ Busca um registro
```php
        $stmt = $this->db->prepare("SELECT * FROM usuarios WHERE id = :id");
```

## ⬆️ SQL seguro
```php
        $stmt->execute([':id' => $id]);
```

## ⬆️ Executa passando o ID
```php
        $result = $stmt->fetch(PDO::FETCH_ASSOC);
        return $result ?: null;
```

## ⬆️ Se não achou → null
```php
UPDATE
    public function update(int $id, string $nome, string $email): bool
```

## ⬆️ Atualiza registro
```php
        $sql = "UPDATE usuarios SET nome = :nome, email = :email WHERE id = :id";
```

## ⬆️ SQL de update
```php
        return $stmt->execute([
            ':id'    => $id,
            ':nome'  => $nome,
            ':email' => $email
        ]);
```

## ⬆️ Executa

DELETE
    public function delete(int $id): bool


## ⬆️ Remove registro
```php
        $stmt = $this->db->prepare("DELETE FROM usuarios WHERE id = :id");
        return $stmt->execute([':id' => $id]);
```
## ⬆️ Executa

## 3️⃣ index.php
```php
👉 Entrada da API (recebe JSON)

header("Content-Type: application/json");
```

## ⬆️ Diz:

“Tudo aqui é JSON”
```php
require "Database.php";
require "Usuario.php";
```

## ⬆️ Carrega as classes
```php
$db = new Database();
$conn = $db->getConnection();
$usuario = new Usuario($conn);
```

## ⬆️ Fluxo:

Cria banco

Pega conexão

Cria model

$method = $_SERVER['REQUEST_METHOD'];
$id = $_GET['id'] ?? null;


## ⬆️ Detecta:
```php
POST

GET

PUT

DELETE

$input = json_decode(file_get_contents("php://input"), true);
```

## ⬆️ Lê JSON enviado
```php
Switch (coração da API)
POST (CREATE)
case "POST":


Se mandou POST → cria

GET (READ)
case "GET":


Se tem ID → um
Se não → todos

PUT (UPDATE)
case "PUT":


Atualiza

DELETE
case "DELETE":

```
Remove

## 🔄 Fluxo COMPLETO
```php
Thunder / JS
   ↓ JSON
index.php
   ↓
Usuario.php
   ↓
PDO
   ↓
```
