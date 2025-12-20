# ☕ Node.js | Express | MySQL — CRUD Pokédex (Explicado passo a passo)

Este documento quebra o código em partes pequenas, explicando **o que é**, **pra que serve** e **como funciona**, no estilo "bem mastigado" para consulta futura.

---

## 📦 Importação de bibliotecas

```js
const express = require('express');
const cors = require('cors');
const mysql = require('mysql2');
```

### O que cada uma faz:

* **express** → framework para criar API HTTP (rotas, requisições, respostas)
* **cors** → permite que outros domínios (ex: frontend React) acessem a API
* **mysql2** → driver para conectar o Node.js ao MySQL

---

## 🚀 Inicialização da aplicação

```js
const app = express();

app.use(express.json());
app.use(cors());
```

### Explicação:

* `express()` → cria a aplicação
* `express.json()` → permite receber JSON no body (POST / PUT)
* `cors()` → libera acesso externo à API

---

## 🗄️ Conexão com o banco de dados

```js
const connection = mysql.createConnection({
    host: 'localhost',
    port: 3306,
    user: 'root',
    password: 'root',
    database: 'pokedex'
});

connection.connect();
```

### O que está acontecendo:

* Cria uma **conexão direta** com o banco MySQL
* Aponta para o banco `pokedex`
* `connect()` abre a conexão

⚠️ Em produção, isso normalmente vai para **variáveis de ambiente**

---

## ➕ Rota INSERT (POST)

```js
app.post('/Inserir', (req, res) => {
    const { nome_pokemon, tipo_pokemon, tem_evolucao } = req.body;

    const comandoBanco = `
        INSERT INTO pokemons(nome_pokemon, tipo_pokemon, tem_evolucao)
        VALUES(?, ?, ?)
    `;

    connection.query(
        comandoBanco,
        [nome_pokemon, tipo_pokemon, tem_evolucao],
        (erro) => {
            if (erro) {
                return res.status(500).send("Erro ao Adicionar Pokemon ao Banco!");
            }
            return res.status(201).send("Sucesso ao Adicionar Pokemon ao Banco!");
        }
    );
});
```

### Conceitos importantes:

* `POST` → usado para **criar dados**
* `req.body` → dados enviados pelo frontend
* `?` → evita SQL Injection
* `201` → recurso criado com sucesso

---

## ❌ Rota DELETE (DELETE)

```js
app.delete('/deletar/:id', (req, res) => {
    const { id } = req.params;

    const comandoBanco = `DELETE FROM pokemons WHERE id = ?`;

    connection.query(comandoBanco, [id], (erro) => {
        if (erro) {
            return res.status(500).send("Erro ao Deletar Pokemon do Banco!");
        }
        return res.status(200).send("Sucesso ao Deletar Pokemon do Banco!");
    });
});
```

### Aqui:

* `:id` → parâmetro vindo da URL
* `req.params.id` → captura o ID
* DELETE remove um registro específico

---

## 📄 Rota LISTAR TODOS (GET)

```js
app.get('/Listar', (req, res) => {
    const comandoBanco = `SELECT * FROM pokemons`;

    connection.query(comandoBanco, (erro, resultados) => {
        if (erro) {
            return res.status(500).send("Erro ao Listar!");
        }
        return res.status(200).json(resultados);
    });
});
```

### Aqui:

* `GET` → buscar dados
* `json(resultados)` → retorna lista em formato JSON

---

## 🔍 Rota LISTAR POR ID (GET)

```js
app.get('/Listar/:id', (req, res) => {
    const { id } = req.params;

    const comandoBanco = `SELECT * FROM pokemons WHERE id = ?`;

    connection.query(comandoBanco, [id], (erro, resultados) => {
        if (erro) {
            return res.status(500).send("Erro ao Listar!");
        }
        return res.status(200).json(resultados);
    });
});
```

### Aqui:

* Busca **um Pokémon específico**
* Retorna um array com 0 ou 1 registro

---

## ✏️ Rota UPDATE (PUT)

```js
app.put('/atualizar/:id', (req, res) => {
    const { id } = req.params;
    const { nome_pokemon, tipo_pokemon, tem_evolucao } = req.body;

    const atualizacao = `
        UPDATE pokemons
        SET nome_pokemon = ?, tipo_pokemon = ?, tem_evolucao = ?
        WHERE id = ?
    `;

    connection.query(
        atualizacao,
        [nome_pokemon, tipo_pokemon, tem_evolucao, id],
        (erro) => {
            if (erro) {
                return res.status(500).send("Erro ao tentar atualizar o usuário");
            }
            res.status(200).send("Usuário atualizado com sucesso!");
        }
    );
});
```

### Aqui:

* `PUT` → atualizar dados existentes
* ID vem da URL
* Dados novos vêm do body

---

## 🌐 Inicialização do servidor

```js
const port = 3000;
app.listen(port, () => {
    console.log(`Servidor Rodando em http://localhost:${port}`);
});
```

### O que faz:

* Sobe o servidor na porta 3000
* API pronta para receber requisições

---

## 🧠 Resumo mental rápido

* Express → rotas
* MySQL → persistência
* POST → cria
* GET → lista
* PUT → atualiza
* DELETE → remove
* `?` → segurança

Esse código já é **CRUD completo**, padrão mercado, limpo e didático 👍
