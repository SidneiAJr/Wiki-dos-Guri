# 🧠 Explicação do Código — API Express + MySQL + Bcrypt

Este projeto implementa uma **API REST em Node.js** usando **Express**, conectada a um **banco MySQL**, com **CRUD completo de usuários** e **autenticação com senha criptografada (bcrypt)**.

Abaixo está a explicação **bem mastigada**, rota por rota, exatamente do código que tu mandou.

---

## 📦 Imports das bibliotecas

```js
const express = require('express')
const mysql = require('mysql2')
const cors = require('cors')
const dot = require('dotenv')
const bodyParser = require('body-parser')
const bcrypt = require('bcrypt');
```

* **express** → framework HTTP
* **mysql2** → comunicação com MySQL
* **cors** → permite frontend acessar a API
* **dotenv** → carrega variáveis do `.env`
* **body-parser** → *não está sendo usado* (pode remover)
* **bcrypt** → criptografia de senha

---

## 🚀 Inicialização do servidor

```js
const app = express();

app.use(express.json());
app.use(cors());
```

* `express.json()` → permite receber JSON no body
* `cors()` → evita erro de CORS no frontend

---

## 🌱 Variáveis de ambiente

```js
dot.config();
const {DB_HOST,DB_DATABASE,DB_PORT,DB_USER,DB_PASSWORD} = process.env;
```

* Dados sensíveis ficam fora do código
* Boa prática profissional

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

Cria a conexão com o banco usando variáveis de ambiente.

```js
connection.connect(error=>{
    if(error){
     console.error('Erro ao Conectar!'+error.stack);
    return;
    }
    console.log("Sucesso ao Conectar")
});
```

* Se falhar → loga erro
* Se conectar → confirma sucesso

---

## 📥 GET /users — listar todos usuários

```js
app.get('/users',(req,res)=>{
   const consulta = `select * from usuarios`;
   connection.query(consulta,(erro,resultados)=>{
     if(erro){
       return res.status(500).send("Erro ao Selecionar dados");
     }
     return res.status(200).json(resultados);
   })
})
```

* Retorna **todos os usuários**
* Resultado vem como array JSON

---

## 🔍 GET /users/:id — buscar usuário por ID

```js
app.get('/users/:id',(req,res)=>{
    const id_usuario = parseInt(req.params.id);
    const consulta_id = 'select * from usuarios where id_usuario = ?'

    connection.query(consulta_id,[id_usuario],(erro,resultado)=>{
        if(erro){
          return res.status(500).send("Erro ao Selecionar dados");  
        }
        return res.status(200).json(resultado[0]);
    })
})
```

* Recebe ID pela URL
* Usa `?` para evitar SQL Injection

---

## 📊 GET /Lista — contar usuários

```js
app.get('/Lista',(req,res)=>{
   const consulta_lista = `select count (*) from usuarios`;
   connection.query(consulta_lista,(erro,resultados)=>{
     if(erro){
       return res.status(500).send("Erro ao listar usuarios");
     }
     return res.status(200).json(resultados);
   })
})
```

* Retorna a quantidade de usuários
* Sugestão: `COUNT(*) AS total`

---

## ➕ POST /Insert — criar usuário (SEM hash)

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

⚠️ **Senha em texto puro** — rota didática, não usar em produção.

---

## ❌ DELETE /deletar/:id — remover usuário

```js
app.delete('/deletar/:id',(req,res)=>{
    const id_usuario = parseInt(req.params.id);

    connection.query('delete from usuarios where id_usuario =?',[id_usuario],(erro)=>{
        if(erro){
            return res.status(500).send("Erro ao Apagar Usuario!");
        }
        return res.status(200).send("Sucesso ao Deletar Usuario!");
    })
})
```

---

## ✏️ PUT /update/:id — atualizar usuário

```js
app.put('/update/:id', (req, res) => {
    const id_usuario = parseInt(req.params.id);
    const { nome_usuario, idade_usuario, email_usuario, senha } = req.body;

    if (!nome_usuario || !idade_usuario || !email_usuario || !senha) {
        return res.status(400).send("Todos os campos são obrigatórios!");
    }

    const update_id = `UPDATE usuarios SET nome_usuario = ?, idade_usuario = ?, email_usuario = ?, senha = ? WHERE id_usuario = ?`;

    connection.query(update_id,[nome_usuario, idade_usuario, email_usuario, senha, id_usuario],(erro, resultados) => {
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

---

## 🔐 POST /Registrar — cadastro com senha criptografada

```js
app.post('/Registrar',async(req,res)=>{
    const { nome_usuario, idade_usuario, email_usuario, senha} = req.body;

    if(!senha){
        return res.status(400).send("Senha é Obrigatorio");
    }

    const senhaHash = await bcrypt.hash(senha, 15);

    connection.query(
        'Insert into usuarios (nome_usuario, idade_usuario, email_usuario, senha) values (?,?,?,?)',
        [nome_usuario, idade_usuario,email_usuario, senhaHash],
        (error)=>{
            if(error){
                return res.status(500).send('Erro ao cadastrar usuário');
            }
            return res.status(201).send('Usuário cadastrado com sucesso');
        }
    )
})
```

* Criptografa senha
* Nunca salva senha pura

---

## 🔑 POST /loginat — login

```js
app.post('/loginat',(req,res)=>{
    const {email_usuario, senha} = req.body;

    connection.query(
        'Select * from usuarios where email_usuario = ?',
        [email_usuario],
        async(error,results)=>{
            if(error || results.length===0){
              return res.status(401).send('Usuário ou senha inválidos');
            }

            const usuario = results[0];
            const senhaValida = await bcrypt.compare(senha, usuario.senha);

            if (!senhaValida) {
                return res.status(401).send('Usuário ou senha inválidos');
            }

            return res.status(200).send('Login realizado com sucesso');
        }
    )
})
```

* Busca usuário pelo email
* Compara senha digitada com hash
* Retorna 401 se falhar

---

## 🌐 Inicialização do servidor

```js
const port = 3000;
app.listen(port,()=>{
    console.log(`Servidor Rodando em http://localhost:${port}`)
});
```

---



Esse backend já tá **nível Júnior/Pleno forte** 🚀
