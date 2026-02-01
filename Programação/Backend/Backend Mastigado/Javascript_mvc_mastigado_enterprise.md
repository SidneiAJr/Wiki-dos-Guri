# 🧠 API Express + MySQL — MVC Enterprise

Este documento mostra a **versão profissional (enterprise)** do teu backend em **Node.js + Express + MySQL**, usando **MVC de verdade**, com tudo **bem mastigado**, explicado **arquivo por arquivo**.

A ideia aqui é: **organização, clareza e padrão de empresa**.

---

## 🧱 O que é MVC (bem direto)

**MVC = Model, View, Controller**

* **Model** → fala com o banco (SQL)
* **Controller** → regra de negócio (o cérebro)
* **Routes** → caminhos HTTP
* **Config** → coisas globais (banco, env)

No backend **API REST**, normalmente:

* não existe View
* então ficamos com **Model + Controller + Routes**

---

## 📁 Estrutura de Pastas (Padrão Enterprise)

```
src/
│
├── config/
│   └── database.js        # conexão com o banco
│
├── models/
│   └── UserModel.js       # SQL / acesso a dados
│
├── controllers/
│   └── UserController.js  # regras de negócio
│
├── routes/
│   └── userRoutes.js      # rotas HTTP
│
├── app.js                 # configura o express
└── server.js              # sobe o servidor
```

👉 Cada pasta tem **uma responsabilidade só**.

---

## 🔧 config/database.js

Responsável **somente** por conectar no MySQL.

```js
const mysql = require('mysql2');
require('dotenv').config();

const connection = mysql.createConnection({
  host: process.env.DB_HOST,
  port: process.env.DB_PORT,
  user: process.env.DB_USER,
  password: process.env.DB_PASSWORD,
  database: process.env.DB_DATABASE
});

connection.connect(err => {
  if (err) {
    console.error('Erro ao conectar no banco:', err);
    return;
  }
  console.log('Banco conectado com sucesso');
});

module.exports = connection;
```

### 🧠 O que acontece aqui?

* Lê o `.env`
* Abre conexão com MySQL
* Exporta a conexão para o resto do projeto

---

## 🧠 models/UserModel.js

Aqui fica **APENAS SQL**.

```js
const connection = require('../config/database');

class UserModel {

  static findAll(callback) {
    connection.query('SELECT * FROM usuarios', callback);
  }

  static findById(id, callback) {
    connection.query('SELECT * FROM usuarios WHERE id_usuario = ?', [id], callback);
  }

  static findByEmail(email, callback) {
    connection.query('SELECT * FROM usuarios WHERE email_usuario = ?', [email], callback);
  }

  static create(data, callback) {
    const sql = 'INSERT INTO usuarios (nome_usuario, idade_usuario, email_usuario, senha) VALUES (?,?,?,?)';
    connection.query(sql, data, callback);
  }

  static update(id, data, callback) {
    const sql = 'UPDATE usuarios SET nome_usuario=?, idade_usuario=?, email_usuario=?, senha=? WHERE id_usuario=?';
    connection.query(sql, [...data, id], callback);
  }

  static delete(id, callback) {
    connection.query('DELETE FROM usuarios WHERE id_usuario=?', [id], callback);
  }
}

module.exports = UserModel;
```

### 🧠 Regra de ouro

> **Model nunca usa `req` nem `res`.**

Ele só conversa com o banco.

---

## 🎮 controllers/UserController.js

Aqui fica a **lógica da aplicação**.

```js
const UserModel = require('../models/UserModel');
const bcrypt = require('bcrypt');

class UserController {

  static list(req, res) {
    UserModel.findAll((err, users) => {
      if (err) return res.status(500).send('Erro ao buscar usuários');
      res.json(users);
    });
  }

  static getById(req, res) {
    const id = req.params.id;

    UserModel.findById(id, (err, result) => {
      if (err || result.length === 0)
        return res.status(404).send('Usuário não encontrado');

      res.json(result[0]);
    });
  }

  static async register(req, res) {
    const { nome_usuario, idade_usuario, email_usuario, senha } = req.body;

    const senhaHash = await bcrypt.hash(senha, 15);

    UserModel.create([
      nome_usuario,
      idade_usuario,
      email_usuario,
      senhaHash
    ], err => {
      if (err) return res.status(500).send('Erro ao cadastrar usuário');
      res.status(201).send('Usuário cadastrado com sucesso');
    });
  }

  static login(req, res) {
    const { email_usuario, senha } = req.body;

    UserModel.findByEmail(email_usuario, async (err, result) => {
      if (err || result.length === 0)
        return res.status(401).send('Usuário ou senha inválidos');

      const usuario = result[0];
      const senhaValida = await bcrypt.compare(senha, usuario.senha);

      if (!senhaValida)
        return res.status(401).send('Usuário ou senha inválidos');

      res.send('Login realizado com sucesso');
    });
  }

  static update(req, res) {
    const id = req.params.id;
    const { nome_usuario, idade_usuario, email_usuario, senha } = req.body;

    UserModel.update(id, [nome_usuario, idade_usuario, email_usuario, senha], (err, result) => {
      if (err) return res.status(500).send('Erro ao atualizar usuário');
      if (result.affectedRows === 0)
        return res.status(404).send('Usuário não encontrado');

      res.send('Usuário atualizado');
    });
  }

  static delete(req, res) {
    const id = req.params.id;

    UserModel.delete(id, err => {
      if (err) return res.status(500).send('Erro ao deletar usuário');
      res.send('Usuário deletado');
    });
  }
}

module.exports = UserController;
```

### 🧠 O Controller:

* Recebe `req` e `res`
* Valida dados
* Chama o Model
* Decide a resposta HTTP

---

## 🛣️ routes/userRoutes.js

Somente **rotas**, nada de lógica.

```js
const express = require('express');
const UserController = require('../controllers/UserController');

const router = express.Router();

router.get('/users', UserController.list);
router.get('/users/:id', UserController.getById);
router.post('/register', UserController.register);
router.post('/login', UserController.login);
router.put('/users/:id', UserController.update);
router.delete('/users/:id', UserController.delete);

module.exports = router;
```

---

## ⚙️ app.js

Configura o Express.

```js
const express = require('express');
const cors = require('cors');
const userRoutes = require('./routes/userRoutes');

const app = express();

app.use(express.json());
app.use(cors());

app.use(userRoutes);

module.exports = app;
```

---

## 🚀 server.js

Arquivo que **sobe o servidor**.

```js
const app = require('./app');

const PORT = 3000;

app.listen(PORT, () => {
  console.log(`Servidor rodando em http://localhost:${PORT}`);
});
```

---



* Service Layer
