# 📚Javascript | Backend Tutorial Com Crud:

## Criando o servidor:

````javascript
const PORT = 3000
````

## Importando as Libs express & mysql2:

````javascript
const express = require('express')
// Importando a biblioteca do mysql2 que tem funções para se conctar a interagir com meu banco dados
const mysql = require('mysql2')
const app = express()
````

## Criando a conexção com Banco: 

````javascript
const connection = mysql.createConnection({
    host: 'localhost', // Host
    port: 3306, // Porta
    user : 'root', // usuario
    password : 'root', // senha
    database: 'banco_teste' // Nome Banco
})

````

## Criando o Insert para o Banco: Banco de Exemplo

````javascript
//Inserção de Informação
app.post('/usuarios',(req,res)=>{
    const {nome,email}=req.body
    const comandobanco = "INSERT INTO usuarios (nome,email) values(?,?)"
    // FUnção que me permite executar um comando de banco de dados
    connection.query(comandobanco,[nome,email],(erro)=>{
         if(erro){
          return res.status(500).send("Erro ao adicionar usuario!")
         }
         return res.status(201).send("Usuario Adicionado com sucesso!")
    })
})
````

## Criando a seleção do banco | Seleção Tudo do Banco

```javascript
// Seleciona tudo do banco
app.get('/ler',(req,res)=>{
    const leitura = "SELECT * FROM banco_teste.usuarios";
     connection.query(leitura,(erro,resultado)=>{
         if(erro){
          return res.status(500).send("Erro | Leitura nâo Realizada")
         }
         res.status(200).json(resultado)

    })
})
````

## Criando a seleção do banco | Seleção por ID

```javascript
// Selecionando Pelo ID & Retorna de um usuario especifico
app.get('/ler/:id',(req,res)=>{
    // Pegue atravez do parametro da requesição
    const {id}= req.params
    const leitura = "SELECT * from usuarios where id = ?";
     connection.query(leitura,[id],(erro,resultado)=>{
         if(erro){
          return res.status(500).send("Erro | Leitura nâo Realizada")
         }
         res.status(200).json(resultado)
    })
})
````

## Atualização de Informações:

```javascript
// Atualiza as informações de usuario:
app.put('/at/:id',(req,res)=>{
    const {id} = req.params
    const {nome,email} = req.body
    const atualizao = "Update usuarios set nome = ?,email = ? where id = ?";
     connection.query(atualizao,[nome,email,id],(erro,resultado)=>{
         if(erro){
          return res.status(500).send("Erro | ao tentar atualizar o usuario")
         }
         res.status(200).send("Usuario Atualizado com sucesso!!!")
    })
})
```

## Deletar Informação:

````javacript
//rota para deletar
app.delete('/deletar/:id',(req,res)=>{
    const {id} = req.params
    const atualizao = "delete from usuarios where id = ?";
     connection.query(atualizao,[id],(erro,resultado)=>{
         if(erro){
          return res.status(500).send("Erro | ao tentar deletar usuario")
         }
         res.status(200).send("Usuario Deletado com sucesso!!!")
    })
})
````



