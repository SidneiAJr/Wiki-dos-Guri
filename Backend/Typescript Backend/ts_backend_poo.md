# ☕ Java CRUD ➜ TypeScript (POO • Console • MySQL)

Este documento converte **seu CRUD em Java (JDBC + Scanner)** para **TypeScript em POO**, rodando **no console**, usando **Node.js + MySQL**.

Tudo aqui segue o **mesmo conceito do Java**, só muda a stack.

---

## 📦 Dependências (libs)

```bash
npm init -y
npm install mysql2 readline-sync
npm install -D typescript ts-node @types/node
```

---

## 📁 Estrutura do projeto (POO)

```
src/
 ├─ database/
 │   └─ Database.ts
 ├─ models/
 │   └─ Funcionario.ts
 ├─ repositories/
 │   └─ FuncionarioRepository.ts
 ├─ services/
 │   └─ FuncionarioService.ts
 └─ main.ts
```

---

## 1️⃣ Database.ts (equivale ao DriverManager)

```ts
import mysql from "mysql2/promise";

export class Database {
  static async getConnection() {
    return mysql.createConnection({
      host: "localhost",
      user: "root",
      password: "",
      database: "funcionarios"
    });
  }
}
```

🔹 **Java equivalente:** `DriverManager.getConnection()`

---

## 2️⃣ Model (Entidade)

### Funcionario.ts

```ts
export class Funcionario {
  constructor(
    public id: number | null,
    public nome: string,
    public cargo: string
  ) {}
}
```

🔹 **Java equivalente:** classe POJO `Funcionario`

---

## 3️⃣ Repository (SQL puro)

### FuncionarioRepository.ts

```ts
import { Database } from "../database/Database";
import { Funcionario } from "../models/Funcionario";

export class FuncionarioRepository {

  async inserir(func: Funcionario) {
    const conn = await Database.getConnection();
    await conn.execute(
      "INSERT INTO funcionarios (nome, cargo) VALUES (?, ?)",
      [func.nome, func.cargo]
    );
    await conn.end();
  }

  async buscarPorId(id: number): Promise<Funcionario | null> {
    const conn = await Database.getConnection();
    const [rows]: any = await conn.execute(
      "SELECT * FROM funcionarios WHERE id = ?",
      [id]
    );
    await conn.end();

    if (rows.length === 0) return null;

    return new Funcionario(rows[0].id, rows[0].nome, rows[0].cargo);
  }

  async atualizar(func: Funcionario) {
    const conn = await Database.getConnection();
    await conn.execute(
      "UPDATE funcionarios SET nome = ?, cargo = ? WHERE id = ?",
      [func.nome, func.cargo, func.id]
    );
    await conn.end();
  }

  async deletar(id: number) {
    const conn = await Database.getConnection();
    await conn.execute(
      "DELETE FROM funcionarios WHERE id = ?",
      [id]
    );
    await conn.end();n  }
}
```

🔹 **Java equivalente:** `PreparedStatement + ResultSet`

---

## 4️⃣ Service (regra de negócio)

### FuncionarioService.ts

```ts
import { Funcionario } from "../models/Funcionario";
import { FuncionarioRepository } from "../repositories/FuncionarioRepository";

export class FuncionarioService {
  private repo = new FuncionarioRepository();

  async criar(nome: string, cargo: string) {
    await this.repo.inserir(new Funcionario(null, nome, cargo));
  }

  async buscar(id: number) {
    return this.repo.buscarPorId(id);
  }

  async atualizar(id: number, nome: string, cargo: string) {
    await this.repo.atualizar(new Funcionario(id, nome, cargo));
  }

  async deletar(id: number) {
    await this.repo.deletar(id);
  }
}
```

🔹 **Java equivalente:** classes tipo `AtualizarporID`, `NovoFuncionario`

---

## 5️⃣ Main (Console + Scanner)

### main.ts

```ts
import readline from "readline-sync";
import { FuncionarioService } from "./services/FuncionarioService";

const service = new FuncionarioService();

console.log("1 - Inserir");
console.log("2 - Buscar por ID");
console.log("3 - Atualizar");
console.log("4 - Deletar");

const opcao = readline.questionInt("Escolha: ");

(async () => {
  switch (opcao) {
    case 1:
      await service.criar(
        readline.question("Nome: "),
        readline.question("Cargo: ")
      );
      console.log("Inserido com sucesso");
      break;

    case 2:
      const f = await service.buscar(readline.questionInt("ID: "));
      console.log(f ?? "Não encontrado");
      break;

    case 3:
      await service.atualizar(
        readline.questionInt("ID: "),
        readline.question("Novo nome: "),
        readline.question("Novo cargo: ")
      );
      console.log("Atualizado");
      break;

    case 4:
      await service.deletar(readline.questionInt("ID: "));
      console.log("Deletado");
      break;
  }
})();
```

🔹 **Java equivalente:** `Scanner + switch + main`

---

## 🧠 Resumo mental (Java ➜ TS)

* `Scanner` ➜ `readline-sync`
* `DriverManager` ➜ `mysql2/promise`
* `PreparedStatement` ➜ `execute(sql, params)`
* Classe Java ➜ Classe TS
* POO idêntico, só muda a sintaxe

---


