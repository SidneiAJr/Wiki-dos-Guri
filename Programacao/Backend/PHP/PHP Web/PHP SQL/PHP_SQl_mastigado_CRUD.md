# ☕ PHP + MySQL (CRUD com PDO) — Versão Mastigada

Este material é o **equivalente direto do teu JDBC em Java**, só que em **PHP raiz com PDO**.
Sem framework, sem Laravel, sem frescura.

---

## 🧠 Visão Geral (mentalidade correta)

Em PHP + MySQL, o fluxo é sempre:

1. Conectar no banco (PDO)
2. Montar SQL
3. Preparar a query
4. Passar parâmetros
5. Executar
6. Ler resultado (se houver)

👉 É **o mesmo conceito do JDBC**, só muda a sintaxe.

---

## 1️⃣ Conexão com o banco (PDO)

```php
<?php
$host = "localhost";
$db   = "funcionarios";
$user = "root";
$pass = "root";

try {
    $pdo = new PDO("mysql:host=$host;dbname=$db;charset=utf8", $user, $pass);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    echo "Conectado com sucesso!";
} catch (PDOException $e) {
    echo "Erro na conexão";
}
```

### O que é o quê:

* **PDO** → camada de acesso ao banco (igual DriverManager)
* **ERRMODE_EXCEPTION** → força erro aparecer

📌 Sem isso, o erro morre silencioso.

---

## 2️⃣ Criar banco de dados

```php
$sql = "CREATE DATABASE IF NOT EXISTS funcionarios";
$pdo->exec($sql);
```

### Observações:

* `exec()` → usado quando não tem retorno
* Igual `Statement.execute()` do Java

---

## 3️⃣ Criar tabela

```php
$sql = "CREATE TABLE IF NOT EXISTS funcionarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(80) NOT NULL,
    cargo VARCHAR(50) NOT NULL
)";

$pdo->exec($sql);
```

📌 Sem tabela, nada funciona depois.

---

## 4️⃣ INSERT (seguro, sem SQL Injection)

```php
$sql = "INSERT INTO funcionarios (nome, cargo) VALUES (?, ?)";
$stmt = $pdo->prepare($sql);
$stmt->execute(["João", "Dev Jr"]);
```

### Por que usar `?`

* Evita SQL Injection
* Evita erro de aspas

❌ ERRADO:

```sql
INSERT INTO funcionarios VALUES ('$nome')
```

✅ CERTO:

```sql
INSERT INTO funcionarios VALUES (?, ?)
```

---

## 5️⃣ INSERT com formulário HTML

```php
$nome  = $_POST['nome'];
$cargo = $_POST['cargo'];

$sql = "INSERT INTO funcionarios (nome, cargo) VALUES (?, ?)";
$stmt = $pdo->prepare($sql);
$stmt->execute([$nome, $cargo]);
```

📌 Mesma lógica do `Scanner` no Java.

---

## 6️⃣ SELECT por ID

```php
$sql = "SELECT * FROM funcionarios WHERE id = ?";
$stmt = $pdo->prepare($sql);
$stmt->execute([1]);

$resultado = $stmt->fetch(PDO::FETCH_ASSOC);

if ($resultado) {
    echo $resultado['nome'];
} else {
    echo "Funcionário não encontrado";
}
```

### fetch():

* Retorna **1 linha**
* `false` se não existir

---

## 7️⃣ SELECT todos

```php
$sql = "SELECT * FROM funcionarios";
$stmt = $pdo->query($sql);

foreach ($stmt as $row) {
    echo $row['nome'] . " - " . $row['cargo'] . "<br>";
}
```

---

## 8️⃣ UPDATE (NUNCA sem WHERE)

❌ PERIGO:

```sql
UPDATE funcionarios SET cargo = 'Dev'
```

👉 Atualiza todo mundo.

✅ CERTO:

```php
$sql = "UPDATE funcionarios SET nome = ?, cargo = ? WHERE id = ?";
$stmt = $pdo->prepare($sql);
$stmt->execute(["Carlos", "Dev Pleno", 1]);
```

📌 UPDATE sem WHERE = justa causa.

---

## 9️⃣ DELETE (mais perigoso ainda)

❌ NUNCA:

```sql
DELETE FROM funcionarios;
```

✅ CERTO:

```php
$sql = "DELETE FROM funcionarios WHERE id = ?";
$stmt = $pdo->prepare($sql);
$stmt->execute([1]);
```

📌 DELETE sem WHERE = apagar produção.

---

## 🔟 Comparação mental Java x PHP

| Java JDBC         | PHP PDO     |
| ----------------- | ----------- |
| DriverManager     | new PDO     |
| PreparedStatement | prepare()   |
| setString()       | execute([]) |
| ResultSet         | fetch()     |

👉 Conceito é o mesmo.

---


