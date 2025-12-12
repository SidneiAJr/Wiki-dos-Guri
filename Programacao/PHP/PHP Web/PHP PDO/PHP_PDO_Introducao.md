# O que é PDO?

PDO (PHP Data Objects) é uma extensão do PHP que permite conectar seu código a vários bancos de dados usando uma única interface padrão.

Em outras palavras:
- 🔹 É um “motor de conexão”
- 🔹 Funciona com vários bancos: MySQL, MariaDB, PostgreSQL, SQLite, SQL Server, Oracle…
- 🔹 Você aprende uma vez e usa em qualquer banco
- 🔹 Oferece segurança e performance melhores que mysqli e mysql_* (que já morreu)

## `💡 Por que usar PDO?`
- ✔ Suporta múltiplos bancos
- Você troca apenas o driver (ex: mysql:, pgsql:).
- ✔ Prepared Statements = Segurança
- Evita SQL Injection automaticamente.
- ✔ Melhor tratamento de erros
- PDO pode lançar exceções limpas e detalhadas.
- ✔ Código mais organizado
- Perfeito para POO, MVC e APIs.

## Script Basico:

```php
<?php

try {
    $pdo = new PDO(
        "mysql:host=localhost;dbname=meu_banco;charset=utf8mb4",
        "root",
        ""
    );

    echo "Conectado com sucesso!";

} catch (PDOException $e) {
    echo "Erro ao conectar: " . $e->getMessage();
}
````

## 🔍 O que cada parte faz?
### ▶ "mysql:host=localhost;dbname=meu_banco;charset=utf8mb4"
- É a string de conexão (DSN).
- Ela diz:
- qual banco → mysql
- onde está → host=localhost
- nome do banco → dbname=meu_banco
- charset → utf8mb4
### ▶ "root", ""
- Usuário e senha do banco.
### ▶ new PDO()
- Cria a conexão.
### ▶ catch (PDOException $e)
- Pega qualquer erro, como:
- banco inexistente
- porta errada
- senha errada
- MySQL desligado

## Ativando erros importantes (recomendado)

Sempre ative:
```php
$pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
```

## 📌 Executando uma query simples
```php
$sql = "SELECT * FROM usuarios";
$stmt = $pdo->query($sql);
$resultados = $stmt->fetchAll(PDO::FETCH_ASSOC);
print_r($resultados);
```

## 🚀 Inserindo dados com Prepared Statement
```php
$sql = "INSERT INTO usuarios (nome, email) VALUES (:nome, :email)";

$stmt = $pdo->prepare($sql);

$stmt->execute([
    ':nome'  => "João",
    ':email' => "joao@email.com"
]);
```


