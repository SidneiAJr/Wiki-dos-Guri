# ☕ Java + JDBC + MySQL (CRUD) — Jogo (Versão Mastigada)

Este canvas aplica o **modelo mastigado raiz** diretamente no **projeto Jogo**, usando:

* `Jogo` (Model)
* `JogoDAO` (DAO)
* `ConnectionFactory` (Util)

Objetivo: **olhar isso daqui no futuro e lembrar exatamente quem faz o quê e por quê**.

---

## 🧠 Visão Geral (o que esse sistema faz)

No projeto do **Jogo**, tu construiu:

1. Conexão com MySQL
2. Persistência de jogos no banco
3. CRUD completo (Create, Read, Update, Delete)
4. Separação em camadas (MVC raiz)

Tudo usando **JDBC puro**, sem Spring, sem ORM.

---

## 🧱 Arquitetura Mental (MVC simplificado)

```
Controller (futuro / main / servlet)
   ↓
JogoDAO (SQL + JDBC)
   ↓
Jogo (dados)
   ↓
ConnectionFactory (conexão)
```

📌 Regra de ouro:

> Model não fala com banco. DAO fala.

---

## 1️⃣ ConnectionFactory — conexão com o banco

📦 **Pacote:** `util`

### O que é?

Classe responsável **somente** por abrir conexão com o MySQL.

### O que faz?

* Centraliza URL, usuário e senha
* Retorna um `Connection`

### O que NÃO faz?

* ❌ Não executa SQL
* ❌ Não conhece `Jogo`
* ❌ Não tem regra de negócio

### Por que existe?

Sem ela, cada DAO teria código de conexão duplicado.

> **ConnectionFactory = tomada do banco** 🔌

---

## 2️⃣ Model — `Jogo`

📦 **Pacote:** `model`

### O que é?

Representa um **jogo no sistema**.

### O que guarda?

* `id`
* `titulo`
* `plataforma`
* `preco`
* `imagemPath`

### O que faz?

* Apenas guarda dados
* Possui construtores
* Possui getters e setters

### O que NÃO faz?

* ❌ Não acessa banco
* ❌ Não executa SQL
* ❌ Não imprime nada

📌 Se começar a ter SQL aqui → arquitetura quebrou.

---

## 3️⃣ DAO — `JogoDAO`

📦 **Pacote:** `dao`

### O que é?

Classe responsável por **todo acesso ao banco** relacionado a jogos.

### O que faz?

* Executa SQL
* Converte dados do banco em objetos `Jogo`
* Recebe objetos `Jogo` e persiste no banco

### O que NÃO faz?

* ❌ Não guarda dados próprios
* ❌ Não decide regra de interface

> **DAO = tradutor entre Java e MySQL**

---

## 4️⃣ CREATE — Inserir jogo

### O que acontece?

1. Um objeto `Jogo` é criado
2. O `JogoDAO` recebe esse objeto
3. Um `INSERT` é executado

### SQL mental

```sql
INSERT INTO jogo (titulo, plataforma, preco, imagem_path)
VALUES (?, ?, ?, ?)
```

### Por que usar `PreparedStatement`?

* Evita SQL Injection
* Evita erro de aspas
* Código mais seguro

📌 INSERT sem `?` é pedir problema.

---

## 5️⃣ READ — Listar jogos

### O que acontece?

1. DAO executa `SELECT * FROM jogo`
2. O `ResultSet` guarda o resultado
3. Cada linha vira um objeto `Jogo`
4. Retorna `List<Jogo>`

### Ponto crítico

* Sempre usar `rs.next()`
* Sempre mapear coluna → atributo certo

📌 Errou nome de coluna = bug silencioso.

---

## 6️⃣ UPDATE — Atualizar jogo

### O que acontece?

1. Um `Jogo` com `id` é enviado
2. DAO executa `UPDATE`
3. Apenas o jogo com aquele ID é alterado

### SQL mental

```sql
UPDATE jogo
SET titulo = ?, plataforma = ?, preco = ?, imagem_path = ?
WHERE id = ?
```

❌ UPDATE sem WHERE = tragédia.

---

## 7️⃣ DELETE — Excluir jogo

### O que acontece?

1. DAO recebe um `id`
2. Executa `DELETE`

### SQL mental

```sql
DELETE FROM jogo WHERE id = ?
```

📌 DELETE sem WHERE = apagar o banco emocionalmente.

---

## 🔁 Fluxo completo do sistema

1. Controller cria ou recebe um `Jogo`
2. Chama `JogoDAO`
3. DAO pede conexão à `ConnectionFactory`
4. SQL roda no MySQL
5. Banco responde
6. DAO devolve objetos prontos

---

## 🧠 Padrão mental pra lembrar (sempre)

1. Model = dados
2. DAO = SQL
3. Util = conexão
4. Controller = orquestra

Se misturar isso, o projeto vira caos.

---

## 🧱 O que tu já domina aqui

✔ MVC raiz
✔ JDBC puro
✔ CRUD completo
✔ SQL parametrizado
✔ Separação de camadas

> Quem domina isso, entende qualquer backend Java depois.

---

## 📌 Frase final pra memória muscular

> **Código simples, responsabilidade clara, manutenção fácil.**
