# PHP | Conexção com banco SQL em POO | PDO

Um guia simples e organizado para conectar ao banco usando Programação Orientada a Objetos

## `Criando uma Interface para padronizar qualquer conexão`

A interface garante que qualquer classe de banco que você fizer (MySQL, PostgreSQL, SQLite…) siga o mesmo contrato.

```php
<?php
interface DatabaseInterface {
    public function connect();
    public function getConnection();
}
```

## `Criando a classe de conexão (MySQL) usando PDO`

```php
class Database implements DatabaseInterface
```

## `Parametros`

```php
    private string $host = "localhost";
    private string $db   = "meu_banco";
    private int $port    = 3306;
    private string $user = "root";
    private string $password = "";
    private string $charset = "utf8mb4";
    private ?PDO $connection = null;
```

## ` Usando Try`

```php
try {
            $this->connection = new PDO(
                "mysql:host={$this->host};dbname={$this->db};port={$this->port};charset={$this->charset}",
                $this->user,
                $this->password,
                [
                    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION
                ]
            );

            return true;

        } catch (PDOException $e) {
            die("Erro ao conectar: " . $e->getMessage());
        }
    }
```

## `Script Completo`
```php
<?php
use PDO;
use PDOException;

class Database implements DatabaseInterface
{
    private string $host = "localhost";
    private string $db   = "meu_banco";
    private int $port    = 3306;
    private string $user = "root";
    private string $password = "";
    private string $charset = "utf8mb4";

    private ?PDO $connection = null;

    public function connect()
    {
        try {
            $this->connection = new PDO(
                "mysql:host={$this->host};
                 dbname={$this->db};
                 port={$this->port};
                 charset={$this->charset}",
                $this->user,
                $this->password,
                [
                    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION
                ]
            );

            return true;

        } catch (PDOException $e) {
            die("Erro ao conectar: " . $e->getMessage());
        }
    }

    public function getConnection(): PDO
    {
        if ($this->connection === null) {
            $this->connect();
        }

        return $this->connection;
    }
}
```
