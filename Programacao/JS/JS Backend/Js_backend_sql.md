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

## Criando a seleção do banco

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



