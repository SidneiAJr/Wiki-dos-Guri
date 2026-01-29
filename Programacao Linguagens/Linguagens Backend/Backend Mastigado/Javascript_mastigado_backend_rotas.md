# 🧠 Explicação do código (Express + MySQL)

Esse código cria uma **API REST em Node.js** usando **Express** conectada a um **banco MySQL**, com operações de **CRUD** (Create, Read, Update, Delete) para usuários.

---

## 📦 Imports (bibliotecas usadas)

```js
const express = require('express')
const mysql = require('mysql2')
const cors = require('cors')
const dot = require('dotenv')
const bodyParser = require('body-parser')
```

* **express** → framework pra criar servidor e rotas HTTP
* **mysql2** → driver pra conectar no MySQL
* **cors** → permite que o frontend acesse a API (evita erro de CORS)
* **dotenv** → carrega variáveis do `.env`
* **body-parser** → (não usado no código, pode remover)

---

## 🚀 Inicialização do Express

```js
const app = express();

app.use(express.json());
app.use(cors());
```

* `express.json()` → permite receber JSON no body das requisições
* `cors()` → libera acesso externo (React, Vue, etc)

---

## 🌱 Variáveis de ambiente

```js
dot.config();
const {DB_HOST,DB_DATABASE,DB_PORT,DB_USER,DB_PASSWORD} = process.env;
```

* Carrega dados sensíveis do `.env`
* Evita deixar senha de banco hardcoded

---

## 🛢️ Conexão com o banco MySQL

```js
const connection = mysql.createConnection({
    host: DB_HOST,
    port: DB_PORT,
    user: DB_USER,
    password: DB_PASSWORD,
    database: DB_DATABASE
});
```

Cria a conexão com o banco usando os dados do `.env`

```js
connection.connect(error=>{
    if(error){
     console.error('Erro ao Conectar!'+error.stack);
    return;
    }
    console.log("Sucesso ao Conectar")
});
```

* Se der erro → loga no console
* Se conectar → confirma sucesso

---

## 📥 GET /users (listar todos usuários)

```js
app.get('/users',(req,res)=>{
   const consulta = `select * from usuarios`;
   connection.query(consulta,(erro,resultados)=>{
   if(erro){
    return res.status(500).set("Erro ao Selecionar dados");
   }
   return res.status(200).json(resultados);
   })
})
```

* Busca **todos os usuários**
* Retorna um array em JSON

---

## 🔍 GET /users/:id (buscar por ID)

```js
app.get('/users/:id',(req,res)=>{
    const id_usuario = parseInt(req.params.id);
    const consulta_id = 'select * from usuarios where id_usuario = ?'
    connection.query(consulta_id,[id_usuario],(erro,resultado)=>{
        if(erro){
          return res.status(500).set("Erro ao Selecionar dados");  
        }
        return res.status(200).json(resultado[0]);
    })
})
```

* Recebe `id` pela URL
* Usa `?` pra evitar SQL Injection
* Retorna **um único usuário**

---

## 📊 GET /Lista (contar usuários)

```js
app.get('/Lista',(req,res)=>{
   const consulta_lista = `select count (*) from usuarios`;
   connection.query(consulta_lista,(erro,resultados)=>{
    if(erro){
        return res.status(500).set("Erro ao listar usuarios");
    }
    return res.status(200).json(resultados);
   })
})
```

* Retorna a quantidade total de usuários
* ⚠️ Melhor usar `COUNT(*) AS total`

---

## ➕ POST /Insert (criar usuário)

```js
app.post('/Insert',(req,res)=>{
    const {nome_usuario,idade_usuario,email_usuario,senha} = req.body;
    const inserir_banco = `insert into usuarios(nome_usuario,idade_usuario,email_usuario,senha)values(?,?,?,?)`;
    connection.query(inserir_banco,[nome_usuario,idade_usuario,email_usuario,senha],(erro)=>{
        if(erro){
            return res.status(500).send("Erro ao Adicionar Usuario!");
        }
        return res.status(201).send("Sucesso ao Adicionar Usuario");
    })
})
```

* Recebe dados via JSON
* Insere novo usuário no banco

---

## ❌ DELETE /deletar/:id (remover usuário)

```js
app.delete('/deletar/:id',(req,res)=>{
    const id_usuario = parseInt(req.params.id);
    const deletar = `delete from usuarios where id_usuario =?`
    connection.query(deletar,[id_usuario],(erro)=>{
        if(erro){
            return res.status(500).send("Erro ao Apagar Usuario!");
        }
        return res.status(200).send("Sucesso ao Deletar Usuario!");
    })
})
```

* Apaga usuário pelo ID

---

## ✏️ PUT /update/:id (atualizar usuário)

```js
app.put('/update/:id', (req, res) => {
    const id_usuario = parseInt(req.params.id);
    const { nome_usuario, idade_usuario, email_usuario, senha } = req.body;

    if (!nome_usuario || !idade_usuario || !email_usuario || !senha) {
        return res.status(400).send("Todos os campos são obrigatórios!");
    }

    const dadosParaAtualizar = [nome_usuario, idade_usuario, email_usuario, senha, id_usuario];

    const update_id = `UPDATE usuarios SET nome_usuario = ?, idade_usuario = ?, email_usuario = ?, senha = ? WHERE id_usuario = ?`;

    connection.query(update_id, dadosParaAtualizar, (erro, resultados) => {
        if (erro) {
            return res.status(500).send("Erro ao Atualizar Usuário!");
        }

        if (resultados.affectedRows === 0) {
            return res.status(404).send("Usuário não encontrado!");
        }

        return res.status(200).send("Usuário Atualizado com Sucesso!");
    });
});
```

* Atualiza dados de um usuário
* Valida campos obrigatórios
* Verifica se o ID existe

---

## 🌐 Inicialização do servidor

```js
const port = 3000;
app.listen(port,()=>{
    console.log(`Servidor Rodando em http://localhost:${port}`)
});
```

* Sobe a API na porta **3000**

---

## ✅ Resumo rápido

* ✔️ API REST
* ✔️ CRUD completo
* ✔️ MySQL seguro com parâmetros
* ✔️ Separação de responsabilidades

Se quiser, no próximo passo posso:

* refatorar pra **MVC**
* converter pra **async/await**
* adicionar **bcrypt + JWT**
* ou integrar com **React/Vue** 🚀
