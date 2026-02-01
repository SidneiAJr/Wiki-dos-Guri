# MySQLi vs PDO 

Vamos no **jeito aula + prática**, pra ficar claro **o que é**, **pra que serve** e **quando usar cada um**.

---

## 🔹 O que é MySQLi?

**MySQLi** (MySQL Improved) é uma **extensão do PHP feita exclusivamente para MySQL**.

Ou seja:

* Só funciona com **MySQL / MariaDB**
* É direta, simples e rápida

### Características do MySQLi

* Funciona **somente com MySQL**
* Pode ser usado de forma **procedural** ou **orientada a objetos**
* Suporte a **prepared statements** (muito importante pra segurança)

### Exemplo simples com MySQLi

```php
$conn = new mysqli("localhost", "root", "root", "pokedex");

$sql = "SELECT * FROM pokemons";
$result = $conn->query($sql);

while ($row = $result->fetch_assoc()) {
    echo $row['nome_pokemon'];
}
```

### 👍 Prós

* Mais simples pra quem tá começando
* Menos código
* Ótimo pra projetos pequenos

### 👎 Contras

* Se trocar de banco (Postgres, SQLite…), tem que **refazer tudo**

---

## 🔹 O que é PDO?

**PDO (PHP Data Objects)** é uma **camada de abstração de banco de dados**.

Traduzindo:

* Um **mesmo código** pode funcionar com **MySQL, PostgreSQL, SQLite, SQL Server** etc.

### Características do PDO

* Funciona com **vários bancos**
* **Totalmente orientado a objetos**
* Prepared statements mais flexíveis

### Exemplo simples com PDO

```php
$pdo = new PDO("mysql:host=localhost;dbname=pokedex", "root", "root");

$stmt = $pdo->prepare("SELECT * FROM pokemons");
$stmt->execute();

while ($row = $stmt->fetch()) {
    echo $row['nome_pokemon'];
}
```

### 👍 Prós

* Mais seguro
* Mais profissional
* Ideal pra projetos médios e grandes

### 👎 Contras

* Um pouco mais verboso
* Curva de aprendizado maior no começo

---

## 🔥 Prepared Statements (parte importante)

Tanto **MySQLi quanto PDO** evitam **SQL Injection**.

Exemplo perigoso ❌:

```php
$sql = "SELECT * FROM pokemons WHERE id = $id";
```

Exemplo seguro ✅:

```php
$stmt = $pdo->prepare("SELECT * FROM pokemons WHERE id = ?");
$stmt->execute([$id]);
```

---

## 🤔 Qual usar então?

### Use MySQLi se:

* Tá aprendendo PHP agora
* O projeto é simples
* Vai usar **apenas MySQL**

### Use PDO se:

* Quer escrever código mais profissional
* Pode trocar de banco no futuro
* Tá pensando em **API / backend sério**

👉 **No mercado**, PDO é mais comum.

---

## 🧠 Ligando com o que tu já fez em Node.js

Isso aqui no Node:

```js
connection.query("SELECT * FROM pokemons WHERE id = ?", [id])
```

É basicamente o **mesmo conceito do PDO/MySQLi com prepared statements**.

Mudou a linguagem, a ideia é a mesma 😉

---

Se quiser, no próximo passo eu:

* converto teu backend Express pra **PHP puro**
* ou faço uma **API CRUD em PHP + PDO** estilo a que tu já fez 🚀
