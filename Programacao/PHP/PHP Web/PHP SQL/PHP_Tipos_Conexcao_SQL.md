# PHP | Tipos de Conexçao Banco de dados SQl

## 🐘 1️⃣ PDO (PHP Data Objects) — o mais recomendado

### Tu já conhece, mas vale o resumo:
- ✔ suporta vários bancos (MySQL, PostgreSQL, SQLite, SQL Server…)
- ✔ prepared statements
- ✔ mais seguro contra SQL Injection
- ✔ padrão moderno

## 🐬 2️⃣ MySQLi (MySQL Improved)
- Só funciona com MySQL / MariaDB.
- Modos:
- Procedural
- Orientado a Objetos
- Exemplo OO:
```php
$conn = new mysqli("localhost", "user", "senha", "banco");

if ($conn->connect_error) {
    die("Erro: " . $conn->connect_error);
}
```
### Quando usar?
- projeto legado
- sistemas antigos
- código simples só com MySQL

## 🗄️ 4️⃣ Extensões específicas por banco
### Dependendo do banco, o PHP tem extensões próprias:
- PostgreSQL
- pg_connect();
- SQL Server
- sqlsrv_connect();
- Oracle
- oci_connect();
- SQLite
- new SQLite3("db.sqlite");