# 🏗️ API Express + MySQL em TypeScript — **MVC (Enterprise, bem mastigado)**

Este guia mostra **como estruturar e entender** uma API **profissional**, usando **TypeScript + Express + MySQL**, no padrão **MVC**, do jeito que se usa em projeto real de empresa.

A ideia aqui é:

* Código **organizado**
* **Responsabilidades separadas**
* Fácil de **manter**, **testar** e **crescer**

---

## 🧠 O que é MVC (sem papo complicado)

**MVC = Model + Controller + Route**

* **Model** → conversa com o banco (SQL)
* **Controller** → regra de negócio (o que fazer)
* **Routes** → define as URLs da API

👉 A rota chama o controller
👉 O controller chama o model
👉 O model acessa o banco

---

## 📁 Estrutura de pastas (padrão enterprise)

```text
src/
├── config/
│   └── database.ts
│
├── models/
│   └── UserModel.ts
│
├── controllers/
│   └── UserController.ts
│
├── routes/
│   └── user.routes.ts
│
├── interfaces/
│   └── User.ts
│
├── app.ts
└── server.ts
```

Essa estrutura é **padrão de mercado**.

---

## 🌱 config/database.ts (conexão com o banco)

**Responsabilidade:** apenas conectar no MySQL.

```ts
import mysql from 'mysql2'
import dotenv from 'dotenv'

dotenv.config()

export const db = mysql.createPool({
  host: process.env.DB_HOST,
  port: Number(process.env.DB_PORT),
  user: process.env.DB_USER,
  password: process.env.DB_PASSWORD,
  database: process.env.DB_DATABASE,
  waitForConnections: true,
  connectionLimit: 10
})
```

📌 **Por que pool?**

* Mais rápido
* Aguenta mais requisições
* Padrão enterprise

---

## 🧩 interfaces/User.ts (tipagem forte)

**Responsabilidade:** definir como é um usuário.

```ts
export interface User {
  id_usuario?: number
  nome_usuario: string
  idade_usuario: number
  email_usuario: string
  senha: string
}
```

📌 Aqui o TypeScript começa a brilhar ✨

---

## 🛢️ models/UserModel.ts (acesso ao banco)

**Responsabilidade:** SQL puro, sem lógica de HTTP.

```ts
import { db } from '../config/database'
import { User } from '../interfaces/User'

export class UserModel {

  static findAll(callback: Function) {
    db.query('SELECT * FROM usuarios', callback)
  }

  static findById(id: number, callback: Function) {
    db.query('SELECT * FROM usuarios WHERE id_usuario = ?', [id], callback)
  }

  static count(callback: Function) {
    db.query('SELECT COUNT(*) AS total FROM usuarios', callback)
  }

  static create(user: User, callback: Function) {
    const sql = `
      INSERT INTO usuarios
      (nome_usuario, idade_usuario, email_usuario, senha)
      VALUES (?, ?, ?, ?)
    `

    db.query(sql, [
      user.nome_usuario,
      user.idade_usuario,
      user.email_usuario,
      user.senha
    ], callback)
  }

  static delete(id: number, callback: Function) {
    db.query('DELETE FROM usuarios WHERE id_usuario = ?', [id], callback)
  }

  static update(id: number, user: User, callback: Function) {
    const sql = `
      UPDATE usuarios
      SET nome_usuario = ?, idade_usuario = ?, email_usuario = ?, senha = ?
      WHERE id_usuario = ?
    `

    db.query(sql, [
      user.nome_usuario,
      user.idade_usuario,
      user.email_usuario,
      user.senha,
      id
    ], callback)
  }
}
```

📌 Model **não conhece Express**, só banco.

---

## 🎯 controllers/UserController.ts (regra de negócio)

**Responsabilidade:** validar dados + responder HTTP.

```ts
import { Request, Response } from 'express'
import { UserModel } from '../models/UserModel'

export class UserController {

  static getAll(req: Request, res: Response) {
    UserModel.findAll((err: any, data: any) => {
      if (err) return res.status(500).send('Erro ao buscar usuários')
      res.json(data)
    })
  }

  static getById(req: Request, res: Response) {
    const id = Number(req.params.id)

    UserModel.findById(id, (err: any, data: any[]) => {
      if (err) return res.status(500).send('Erro ao buscar usuário')
      if (data.length === 0) return res.status(404).send('Usuário não encontrado')
      res.json(data[0])
    })
  }

  static count(req: Request, res: Response) {
    UserModel.count((err: any, data: any[]) => {
      if (err) return res.status(500).send('Erro ao contar usuários')
      res.json(data[0])
    })
  }

  static create(req: Request, res: Response) {
    const user = req.body

    if (!user.nome_usuario || !user.email_usuario || !user.senha) {
      return res.status(400).send('Campos obrigatórios faltando')
    }

    UserModel.create(user, (err: any) => {
      if (err) return res.status(500).send('Erro ao criar usuário')
      res.status(201).send('Usuário criado com sucesso')
    })
  }

  static delete(req: Request, res: Response) {
    const id = Number(req.params.id)

    UserModel.delete(id, (err: any) => {
      if (err) return res.status(500).send('Erro ao deletar usuário')
      res.send('Usuário deletado com sucesso')
    })
  }

  static update(req: Request, res: Response) {
    const id = Number(req.params.id)
    const user = req.body

    UserModel.update(id, user, (err: any, result: any) => {
      if (err) return res.status(500).send('Erro ao atualizar usuário')
      if (result.affectedRows === 0) return res.status(404).send('Usuário não encontrado')
      res.send('Usuário atualizado com sucesso')
    })
  }
}
```

📌 Controller **não escreve SQL**.

---

## 🛣️ routes/user.routes.ts (rotas)

**Responsabilidade:** mapear URLs.

```ts
import { Router } from 'express'
import { UserController } from '../controllers/UserController'

const router = Router()

router.get('/users', UserController.getAll)
router.get('/users/:id', UserController.getById)
router.get('/lista', UserController.count)
router.post('/insert', UserController.create)
router.delete('/deletar/:id', UserController.delete)
router.put('/update/:id', UserController.update)

export default router
```

📌 Rotas **não têm lógica**.

---

## 🚀 app.ts (configuração da aplicação)

```ts
import express from 'express'
import cors from 'cors'
import userRoutes from './routes/user.routes'

const app = express()

app.use(express.json())
app.use(cors())

app.use(userRoutes)

export default app
```

---

## 🌐 server.ts (subir servidor)

```ts
import app from './app'

const PORT = 3000

app.listen(PORT, () => {
  console.log(`Servidor rodando em http://localhost:${PORT}`)
})
```

---


