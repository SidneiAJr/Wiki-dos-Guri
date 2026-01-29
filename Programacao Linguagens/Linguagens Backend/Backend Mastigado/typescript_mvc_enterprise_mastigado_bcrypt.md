# 📦 API Node.js em TypeScript — MVC Enterprise (Bem Mastigado)

Este canvas mostra uma **arquitetura MVC profissional**, usada em empresas, com **TypeScript**, **Express**, **MySQL** e **bcrypt**.
Tudo separado, organizado e explicado.

---

## 🗂 Estrutura de Pastas (Padrão Enterprise)

```
src/
├── config/
│   └── database.ts
│
├── controllers/
│   └── UserController.ts
│
├── models/
│   └── UserModel.ts
│
├── routes/
│   └── userRoutes.ts
│
├── services/
│   └── AuthService.ts
│
├── app.ts
└── server.ts
```

---

## ⚙️ Configuração do Banco (config/database.ts)

Responsável **somente** por conectar no banco.

```ts
import mysql from 'mysql2/promise';

export const connection = mysql.createPool({
  host: process.env.DB_HOST,
  user: process.env.DB_USER,
  password: process.env.DB_PASSWORD,
  database: process.env.DB_DATABASE,
});
```

---

## 🧱 Model (models/UserModel.ts)

Aqui só tem **acesso ao banco**, nada de regra de negócio.

```ts
import { connection } from '../config/database';

export class UserModel {
  static async findByEmail(email: string) {
    const [rows] = await connection.query(
      'SELECT * FROM usuarios WHERE email_usuario = ?',
      [email]
    );
    return rows as any[];
  }

  static async create(data: any) {
    const { nome_usuario, idade_usuario, email_usuario, senha } = data;
    await connection.query(
      'INSERT INTO usuarios (nome_usuario, idade_usuario, email_usuario, senha) VALUES (?,?,?,?)',
      [nome_usuario, idade_usuario, email_usuario, senha]
    );
  }
}
```

---

## 🧠 Service (services/AuthService.ts)

Aqui fica a **regra de negócio** (hash, validação etc).

```ts
import bcrypt from 'bcrypt';
import { UserModel } from '../models/UserModel';

export class AuthService {
  static async register(data: any) {
    const hash = await bcrypt.hash(data.senha, 15);
    data.senha = hash;
    await UserModel.create(data);
  }

  static async login(email: string, senha: string) {
    const users = await UserModel.findByEmail(email);

    if (users.length === 0) return false;

    const usuario = users[0];
    const valido = await bcrypt.compare(senha, usuario.senha);

    return valido ? usuario : false;
  }
}
```

---

## 🎮 Controller (controllers/UserController.ts)

Controller **só conversa com HTTP** (req / res).

```ts
import { Request, Response } from 'express';
import { AuthService } from '../services/AuthService';

export class UserController {
  static async register(req: Request, res: Response) {
    try {
      await AuthService.register(req.body);
      res.status(201).json({ message: 'Usuário cadastrado com sucesso' });
    } catch (err) {
      res.status(500).json({ error: 'Erro ao cadastrar usuário' });
    }
  }

  static async login(req: Request, res: Response) {
    const { email_usuario, senha } = req.body;

    const usuario = await AuthService.login(email_usuario, senha);

    if (!usuario) {
      return res.status(401).json({ error: 'Usuário ou senha inválidos' });
    }

    res.status(200).json({ message: 'Login realizado com sucesso' });
  }
}
```

---

## 🌐 Rotas (routes/userRoutes.ts)

Rotas **finas**, só apontam pra controller.

```ts
import { Router } from 'express';
import { UserController } from '../controllers/UserController';

const router = Router();

router.post('/register', UserController.register);
router.post('/login', UserController.login);

export default router;
```

---

## 🚀 App Principal (app.ts)

Configuração geral do Express.

```ts
import express from 'express';
import cors from 'cors';
import userRoutes from './routes/userRoutes';

export const app = express();

app.use(cors());
app.use(express.json());

app.use('/api', userRoutes);
```

---

## 🏁 Server (server.ts)

Arquivo que **sobe o servidor**.

```ts
import { app } from './app';

const PORT = 3000;

app.listen(PORT, () => {
  console.log(`🚀 Servidor rodando em http://localhost:${PORT}`);
});
```

---



Quando quiser, a gente sobe esse nível 😉
