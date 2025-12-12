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

`````javascript
const connection = mysql.createConnection({
    host: 'localhost', // Host
    port: 3306, // Porta
    user : 'root', // usuario
    password : 'root', // senha
    database: 'banco_teste' // Nome Banco
})
````
