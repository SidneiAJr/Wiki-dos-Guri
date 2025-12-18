# JavaScript | Estrutura de Backend

## Por que organizar a estrutura do backend?

Uma boa estrutura de pastas ajuda a:

* Manter o código organizado
* Facilitar manutenção
* Evitar arquivos gigantes
* Trabalhar melhor em equipe

---

## Estrutura básica recomendada

```txt
src/
 ├── controllers/
 ├── routes/
 ├── services/
 ├── database/
 ├── middlewares/
 ├── app.js
 └── server.js
```

---

## Descrição das pastas

### 📁 controllers/

Responsável por **receber a requisição** e **retornar a resposta**.

```js
// controllers/usuarioController.js
exports.listar = (req, res) => {
    res.send('Lista de usuários');
};
```

---

### 📁 routes/

Define as **rotas da aplicação**.

```js
// routes/usuariosRoutes.js
const express = require('express');
const router = express.Router();
const usuarioController = require('../controllers/usuarioController');

router.get('/', usuarioController.listar);

module.exports = router;
```

---

### 📁 services/

Contém a **lógica de negócio** e regras da aplicação.

```js
// services/usuarioService.js
exports.buscarUsuarios = () => {
    return [];
};
```

---

### 📁 database/

Configuração e conexão com o banco de dados.

```js
// database/connection.js
const mysql = require('mysql2');

module.exports = mysql.createConnection({
    host: 'localhost',
    user: 'root',
    password: 'root',
    database: 'banco_teste'
});
```

---

### 📁 middlewares/

Funções intermediárias entre req e res.

```js
// middlewares/auth.js
module.exports = (req, res, next) => {
    if (!req.headers.authorization) {
        return res.status(401).send('Não autorizado');
    }
    next();
};
```

---

## Arquivos principais

### app.js

Configura o Express e middlewares.

```js
const express = require('express');
const app = express();

app.use(express.json());

module.exports = app;
```

---

### server.js

Responsável por subir o servidor.

```js
const app = require('./app');

app.listen(3000, () => {
    console.log('Servidor rodando na porta 3000');
});
```

---

## Boas práticas

* Controllers finos
* Regras de negócio nos services
* Rotas apenas direcionam
* Separar configuração de execução

---

## Resumo rápido

* Estrutura organizada facilita manutenção
* Cada pasta tem responsabilidade clara
* Código mais limpo e profissional
