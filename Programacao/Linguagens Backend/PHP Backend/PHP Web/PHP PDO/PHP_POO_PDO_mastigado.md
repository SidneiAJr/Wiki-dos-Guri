# ☕ PHP OOP + PDO — Interface, Classe Abstrata e Login (Mastigado)

Este material **quebra teu código PHP Web 3 em partes pequenas**, explicando **o que é**, **pra que serve** e **como pensar igual dev backend de verdade**.

O código está **muito acima da média pra iniciante** — isso aqui já é **POO de mercado**.

---

## 🧠 Visão Geral (o que você construiu)

Você criou:

1. Uma **interface** (contrato)
2. Uma **classe abstrata** (base comum)
3. Uma **classe concreta** (implementação real)
4. Conexão com banco usando **PDO**
5. Sistema de **login seguro**

👉 Isso é **arquitetura**, não só PHP.

---

## 1️⃣ Interface — o contrato

```php
interface VerificarInformacao {
    public function Login($usuario, $senha);
}
```

### O que é uma interface?

* É um **contrato**
* Não tem código interno
* Só define **o que a classe é obrigada a ter**

📌 Tradução direta:

> "Se você implementar essa interface, você PROMETE que terá o método Login()."

### Quando usar?

* Autenticação
* Gateways
* Serviços
* Regras de negócio

---

## 2️⃣ Classe Abstrata — a base comum

```php
abstract class UsuarioBase implements VerificarInformacao {
    protected $pdo;

    public function __construct() {
        // conexão PDO
    }
}
```

### O que é uma classe abstrata?

* **Não pode ser instanciada** (`new UsuarioBase()` ❌)
* Serve como **base** para outras classes
* Pode ter código pronto

📌 Aqui você centralizou:

* Conexão com banco
* Configuração PDO

👉 Isso evita **duplicação de código**.

---

## 3️⃣ protected $pdo — encapsulamento correto

```php
protected $pdo;
```

### Por que `protected`?

* `private` → só a própria classe
* `protected` → classe + filhas
* `public` → mundo inteiro (ruim)

📌 Escolha **profissional**.

---

## 4️⃣ Construtor — conexão automática

```php
public function __construct() {
    $this->pdo = new PDO(...);
}
```

### O que acontece aqui?

* Sempre que você faz `new Usuario()`
* O PHP automaticamente:

  * conecta no banco
  * configura o PDO

📌 Igual ao `DriverManager` no Java, só que OO.

---

## 5️⃣ Classe concreta — onde a regra vive

```php
class Usuario extends UsuarioBase {
    public function Login($usuario, $senha) {
        // lógica real
    }
}
```

### O que é classe concreta?

* Pode ser instanciada
* Implementa métodos obrigatórios
* Contém **regra de negócio**

📌 Aqui você decidiu:

> como o login funciona

---

## 6️⃣ SQL com placeholders (SEGURANÇA)

```php
$sql = "SELECT * FROM usuarios WHERE nome = :usuario AND senha = :senha";
```

### Por que `:usuario`?

* Evita SQL Injection
* Evita erro de aspas
* Evita ataque básico

❌ ERRADO:

```sql
SELECT * FROM usuarios WHERE nome = '$usuario'
```

✅ CERTO:

```sql
SELECT * FROM usuarios WHERE nome = :usuario
```

---

## 7️⃣ prepare + bindParam

```php
$stmt = $this->pdo->prepare($sql);
$stmt->bindParam(":usuario", $usuario);
$stmt->bindParam(":senha", $senha);
$stmt->execute();
```

### O que acontece aqui?

1. SQL é preparado
2. Parâmetros são injetados com segurança
3. Banco executa

📌 Mesmo conceito de `PreparedStatement` no Java.

---

## 8️⃣ rowCount() — verificação de login

```php
if ($stmt->rowCount() > 0)
```

### O que isso faz?

* Verifica se encontrou usuário
* > 0 = login válido

📌 Funciona, mas **fetch() também é aceitável**.

---

## 9️⃣ Session — estado do usuário

```php
session_start();
$_SESSION["usuario"] = $dados["nome"];
```

### O que é isso?

* Mantém usuário logado
* Dados ficam no servidor

📌 Base de qualquer sistema web.

---

## 🔟 O que você FEZ CERTO (muito certo)

✔ Interface (contrato)
✔ Classe abstrata
✔ Herança
✔ Encapsulamento
✔ PDO seguro
✔ Arquitetura limpa

👉 Isso **não é código de iniciante**.

---

## ⚠️ Pontos de melhoria (nível profissional)

### 1️⃣ Nunca guardar senha em texto puro

Use:

```php
password_hash()
password_verify()
```

### 2️⃣ Separar responsabilidades

* UsuarioDAO → banco
* UsuarioService → regra
* Controller → requisição

### 3️⃣ Retornar valores, não echo

```php
return true;
```

Controller decide o que exibir.

---

## 🧠 Comparação mental Java x PHP

| Java           | PHP            |
| -------------- | -------------- |
| interface      | interface      |
| abstract class | abstract class |
| protected      | protected      |
| JDBC           | PDO            |

👉 Mesma arquitetura, linguagem muda.

---

