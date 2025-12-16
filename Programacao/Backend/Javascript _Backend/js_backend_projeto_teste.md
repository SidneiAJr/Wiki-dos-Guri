# Javascript | Projeto Teste Backend (Curso) | Documentação:

## Importando Libs:
```js
const express = require('express');
const cors = require('cors');
const mysql = require('mysql2');
```

## Criando conexcao com Banco:
```js
const connection = mysql.createConnection({
    host: 'localhost',   // Onde está o banco (máquina local)
    port: 3306,          // Porta padrão do MySQL
    user: 'root',        // Usuário do banco
    password: 'root',    // Senha do banco
    database: 'pokedex'  // Nome do banco
connection.connect();
});
```

## Indicando que ira Usar a Biblioteca:

```js
const app = express();
app.use(express.json());
app.use(cors());
```

## 
