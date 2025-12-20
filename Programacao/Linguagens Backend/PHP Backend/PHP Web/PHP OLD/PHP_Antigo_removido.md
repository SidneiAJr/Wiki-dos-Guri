# ☕ PHP Web 2 — Login Antigo (Mastigado, com Erros e Correção)

Esse código é **clássico de PHP antigo** (era comum em 2008–2012). Aqui eu vou:

1. Explicar **o que ele tenta fazer**
2. Apontar **os erros reais**
3. Explicar **por que é perigoso hoje**
4. Mostrar **como pensar corretamente**

Sem julgamento — isso aqui é **história da web**.

---

## 🧠 O que o código tenta fazer (em português claro)

1. Recebe usuário e senha de um formulário
2. Busca o usuário no banco
3. Se não existir → erro
4. Se existir → compara a senha
5. Se bater → cria sessão
6. Se não → erro

👉 A lógica está **conceitualmente correta**.

---

## 1️⃣ Recebendo dados do formulário

```php
$usuario = $_POST["f_usuario"];
$senha   = $_POST["f_senha"];
```

### O que isso faz:

* Pega dados enviados via POST

⚠️ Problema:

* Nenhuma validação
* Nenhum filtro
* Entrada direta do usuário

---

## 2️⃣ SQL montado com variável (ERRO GRAVE)

```php
$sql = "select * FROM tab_usuario where usu_login ='$usuario'";
```

### Por que isso é perigoso?

Isso permite **SQL Injection**:

```sql
' OR '1'='1
```

👉 Atacante entra sem senha.

---

## 3️⃣ Uso de mysql_* (OBSOLETO)

```php
$res = mysql_query(sql);
```

### Problemas sérios aqui:

❌ `mysql_*` foi **removido do PHP 7**
❌ Variável `$sql` está sem `$`
❌ Código **nem roda hoje**

📌 Hoje só se usa:

* `mysqli`
* `PDO`

---

## 4️⃣ Mistura mysql_* com mysqli_* (quebra tudo)

```php
$linha = mysqli_fetch_row($res);
```

### Por que isso é errado?

* `mysql_*` ≠ `mysqli_*`
* São APIs diferentes
* Isso gera erro fatal

📌 Nunca misture.

---

## 5️⃣ Comparação de senha (ERRO CRÍTICO)

```php
if($linha[0] == $senha)
```

### Problemas aqui:

❌ Senha em texto puro
❌ Índice errado (0 geralmente é ID)
❌ Nenhum hash

📌 Hoje isso é **inaceitável em produção**.

---

## 6️⃣ Session (única parte OK)

```php
session_start();
$_SESSION['loginok'] = 'ok';
```

### Isso está correto

* Session mantém estado
* Redirecionamento funciona

---

## 🧨 Resumo dos ERROS

| Erro                 | Gravidade |
| -------------------- | --------- |
| SQL Injection        | 🔥🔥🔥    |
| mysql_* obsoleto     | 🔥🔥🔥    |
| Senha sem hash       | 🔥🔥🔥    |
| Mistura mysql/mysqli | 🔥🔥      |
| Falta de validação   | 🔥        |

👉 Esse código **não pode rodar hoje**.

---

## ✅ COMO ISSO DEVE SER FEITO HOJE (mentalidade)

* PDO ou mysqli
* SQL parametrizado
* password_hash / password_verify
* Retornar resultado
* Controller decide redirect

---

## 🛠️ Versão CORRETA (PDO + segura)

```php
$sql = "SELECT id, senha FROM tab_usuario WHERE usu_login = ?";
$stmt = $pdo->prepare($sql);
$stmt->execute([$usuario]);

$user = $stmt->fetch(PDO::FETCH_ASSOC);

if ($user && password_verify($senha, $user['senha'])) {
    session_start();
    $_SESSION['loginok'] = true;
    header('Location: menuadm.php');
} else {
    header('Location: erro.html');
}
```

---



