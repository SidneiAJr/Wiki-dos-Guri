# 🐘 API PHP + MySQL — **MVC Enterprise (bem mastigado)**

Aqui é o **mesmo conceito enterprise** que fizemos em TypeScript, **só que em PHP**, do jeito que empresa usa:

* MVC bem separado
* PDO (seguro)
* Código organizado
* Fácil de manter e crescer

---

## 🧠 MVC em PHP (sem enrolação)

* **Model** → fala com o banco (SQL)
* **Controller** → regra de negócio
* **Routes (ou index.php)** → recebe a requisição e chama o controller

👉 Request → Controller → Model → Controller → Response

---

## 📁 Estrutura de pastas (padrão profissional)

```text
src/
├── config/
│   └── Database.php
│
├── app/
│   ├── Models/
│   │   └── UserModel.php
│   │
│   ├── Controllers/
│   │   └── UserController.php
│   │
│   └── Interfaces/
│       └── UserInterface.php
│
├── public/
│   └── index.php
│
└── routes/
    └── user.php
```

Isso aqui é **estrutura de empresa**, não script solto.

---

## 🔐 config/Database.php (conexão com MySQL)

**Responsabilidade:** apenas conectar no banco.

```php
<?php
class Database {
    private static $conn;

    public static function connect() {
        if (!self::$conn) {
            self::$conn = new PDO(
                "mysql:host=" . $_ENV['DB_HOST'] . ";dbname=" . $_ENV['DB_DATABASE'],
                $_ENV['DB_USER'],
                $_ENV['DB_PASSWORD'],
                [PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION]
            );
        }
        return self::$conn;
    }
}
```

📌 PDO protege contra SQL Injection.

---

## 🧩 app/Interfaces/UserInterface.php

**Responsabilidade:** definir estrutura do usuário.

```php
<?php
interface UserInterface {
    public function getAll();
    public function getById(int $id);
    public function create(array $data);
    public function update(int $id, array $data);
    public function delete(int $id);
}
```

📌 Isso força padrão (bem enterprise).

---

## 🛢️ app/Models/UserModel.php

**Responsabilidade:** SQL puro.

```php
<?php
require_once __DIR__ . '/../../config/Database.php';
require_once __DIR__ . '/../Interfaces/UserInterface.php';

class UserModel implements UserInterface {
    private $db;

    public function __construct() {
        $this->db = Database::connect();
    }

    public function getAll() {
        return $this->db->query("SELECT * FROM usuarios")->fetchAll();
    }

    public function getById(int $id) {
        $stmt = $this->db->prepare("SELECT * FROM usuarios WHERE id_usuario = ?");
        $stmt->execute([$id]);
        return $stmt->fetch();
    }

    public function create(array $data) {
        $sql = "INSERT INTO usuarios (nome_usuario, idade_usuario, email_usuario, senha)
                VALUES (?, ?, ?, ?)";
        $stmt = $this->db->prepare($sql);
        return $stmt->execute(array_values($data));
    }

    public function update(int $id, array $data) {
        $sql = "UPDATE usuarios SET nome_usuario=?, idade_usuario=?, email_usuario=?, senha=?
                WHERE id_usuario=?";
        $stmt = $this->db->prepare($sql);
        return $stmt->execute([...array_values($data), $id]);
    }

    public function delete(int $id) {
        $stmt = $this->db->prepare("DELETE FROM usuarios WHERE id_usuario=?");
        return $stmt->execute([$id]);
    }
}
```

📌 Model **não sabe nada de HTTP**.

---

## 🎯 app/Controllers/UserController.php

**Responsabilidade:** regra de negócio + resposta HTTP.

```php
<?php
require_once __DIR__ . '/../Models/UserModel.php';

class UserController {
    private $model;

    public function __construct() {
        $this->model = new UserModel();
    }

    public function index() {
        echo json_encode($this->model->getAll());
    }

    public function show($id) {
        $user = $this->model->getById($id);
        if (!$user) {
            http_response_code(404);
            echo 'Usuário não encontrado';
            return;
        }
        echo json_encode($user);
    }

    public function store() {
        $data = json_decode(file_get_contents('php://input'), true);
        $this->model->create($data);
        http_response_code(201);
        echo 'Usuário criado';
    }

    public function update($id) {
        $data = json_decode(file_get_contents('php://input'), true);
        $this->model->update($id, $data);
        echo 'Usuário atualizado';
    }

    public function delete($id) {
        $this->model->delete($id);
        echo 'Usuário deletado';
    }
}
```

📌 Controller **não escreve SQL**.

---

## 🛣️ routes/user.php

**Responsabilidade:** mapear rotas.

```php
<?php
require_once '../app/Controllers/UserController.php';

$controller = new UserController();

$method = $_SERVER['REQUEST_METHOD'];
$id = $_GET['id'] ?? null;

if ($method === 'GET' && !$id) $controller->index();
if ($method === 'GET' && $id) $controller->show($id);
if ($method === 'POST') $controller->store();
if ($method === 'PUT') $controller->update($id);
if ($method === 'DELETE') $controller->delete($id);
```

---

## 🌐 public/index.php (entrada da API)

```php
<?php
require_once '../routes/user.php';
```

📌 **Front Controller** (padrão profissional).

---



Se quiser, eu **evoluo isso contigo passo a passo**, tipo mentoria de backend 👊
