# ☕ TypeScript | CRUD Console (equivalente ao Java + JDBC + Scanner)

Este material é a **conversão direta** do teu CRUD em Java POO para **TypeScript rodando no terminal**, usando MySQL.

A ideia é a mesma do Java:

* entrada via terminal
* SQL parametrizado
* conexão direta com o banco
* sem web, sem API, sem framework

---

## 1️⃣ Bibliotecas utilizadas (equivalente aos imports do Java)

### 📦 Dependências

```bash
npm init -y
npm install mysql2
```

### 📥 Imports no código

```ts
import mysql from "mysql2/promise"; // equivalente ao DriverManager
import readline from "readline";     // equivalente ao Scanner
```

---

## 2️⃣ Configuração da conexão com o banco

### 📄 db.ts (equivalente à classe Conexao)

```ts
import mysql from "mysql2/promise";

export const dbConfig = {
  host: "localhost",
  user: "root",
  password: "root", // pode ser qualquer senha (local)
  database: "funcionarios"
};

export async function conectar() {
  return await mysql.createConnection(dbConfig);
}
```

🔹 **Quem é quem**:

* `mysql.createConnection` → igual ao `DriverManager.getConnection`
* retorna uma conexão pronta

---

## 3️⃣ Leitura de dados no terminal (Scanner do Java)

### 📄 input.ts

```ts
import readline from "readline";

const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});

export function perguntar(pergunta: string): Promise<string> {
  return new Promise(resolve => {
    rl.question(pergunta, resposta => resolve(resposta));
  });
}

export function fecharInput() {
  rl.close();
}
```

🔹 Isso substitui totalmente o `Scanner` do Java.

---

## 4️⃣ INSERT (Novo Funcionário)

### 📄 insert.ts

```ts
import { conectar } from "./db";
import { perguntar, fecharInput } from "./input";

async function inserirFuncionario() {
  const nome = await perguntar("Informe o nome: ");
  const cargo = await perguntar("Informe o cargo: ");

  const sql = "INSERT INTO funcionarios (nome, cargo) VALUES (?, ?)";

  const conn = await conectar();
  await conn.execute(sql, [nome, cargo]);
  await conn.end();

  console.log("Funcionário inserido com sucesso!");
  fecharInput();
}

inserirFuncionario();
```

🔹 `?` funciona igual ao `PreparedStatement`

---

## 5️⃣ SELECT por ID

### 📄 select.ts

```ts
import { conectar } from "./db";
import { perguntar, fecharInput } from "./input";

async function buscarPorId() {
  const id = await perguntar("Informe o ID: ");

  const sql = "SELECT * FROM funcionarios WHERE id = ?";
  const conn = await conectar();

  const [rows]: any = await conn.execute(sql, [id]);

  if (rows.length > 0) {
    const f = rows[0];
    console.log(`ID: ${f.id} | Nome: ${f.nome} | Cargo: ${f.cargo}`);
  } else {
    console.log("Funcionário não encontrado");
  }

  await conn.end();
  fecharInput();
}

buscarPorId();
```

🔹 `rows[0]` = `ResultSet.next()`

---

## 6️⃣ UPDATE por ID

### 📄 update.ts

```ts
import { conectar } from "./db";
import { perguntar, fecharInput } from "./input";

async function atualizarFuncionario() {
  const id = await perguntar("Informe o ID: ");
  const nome = await perguntar("Novo nome: ");
  const cargo = await perguntar("Novo cargo: ");

  const sql = "UPDATE funcionarios SET nome = ?, cargo = ? WHERE id = ?";
  const conn = await conectar();

  const [result]: any = await conn.execute(sql, [nome, cargo, id]);

  if (result.affectedRows > 0) {
    console.log("Funcionário atualizado com sucesso");
  } else {
    console.log("Funcionário não encontrado");
  }

  await conn.end();
  fecharInput();
}

atualizarFuncionario();
```

---

## 7️⃣ DELETE por ID

### 📄 delete.ts

```ts
import { conectar } from "./db";
import { perguntar, fecharInput } from "./input";

async function deletarFuncionario() {
  const id = await perguntar("Informe o ID: ");

  const sql = "DELETE FROM funcionarios WHERE id = ?";
  const conn = await conectar();

  const [result]: any = await conn.execute(sql, [id]);

  if (result.affectedRows > 0) {
    console.log("Funcionário deletado");
  } else {
    console.log("Funcionário não encontrado");
  }

  await conn.end();
  fecharInput();
}

deletarFuncionario();
```

---

## 8️⃣ Resumo mental (Java → TS)

* Classe de conexão → `db.ts`
* Scanner → `readline`
* JDBC → `mysql2/promise`
* PreparedStatement → `execute(sql, params)`
* ResultSet → `rows[]`

---

📌 **Isso aqui é backend raiz**, ótimo pra aprender banco antes de ir pra API, Express ou Nest.


