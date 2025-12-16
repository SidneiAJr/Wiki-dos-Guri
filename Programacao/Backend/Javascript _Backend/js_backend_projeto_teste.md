# Javascript | Projeto Teste Backend (Curso) | Documentação:

## Banco de dados do Projeto | Estudo:
```sql
CREATE database pokedex;
use pokedex;

create table pokemons(
id int primary key auto_increment not null,
nome_pokemon varchar(255) not null,
tipo_pokemon varchar(255) not null,
tem_evolucao enum ("sim","não")
);

-- Inserir dados na tabela pokemons
INSERT INTO pokemons (nome_pokemon, tipo_pokemon, tem_evolucao) 
VALUES 
    ('Bulbasaur', 'Grama/Poison', 'sim'),
    ('Charmander', 'Fogo', 'sim'),
    ('Squirtle', 'Água', 'sim'),
    ('Pikachu', 'Elétrico', 'sim'),
    ('Eevee', 'Normal', 'sim'),
    ('Jigglypuff', 'Normal/Fada', 'sim'),
    ('Meowth', 'Normal', 'não'),
    ('Mankey', 'Lutador', 'sim'),
    ('Zubat', 'Venenoso/Voador', 'sim'),
    ('Snorlax', 'Normal', 'não');
```

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

## Criando Rota do Insert:
```js
app.post('/Inserir', (req, res) => {
    const { nome_pokemon, tipo_pokemon, tem_evolucao } = req.body;
    const comandoBanco = `INSERT INTO pokemons(nome_pokemon, tipo_pokemon, tem_evolucao) VALUES(?, ?, ?)`;
    connection.query(comandoBanco, [nome_pokemon, tipo_pokemon, tem_evolucao], (erro) => {
        if (erro) {
            return res.status(500).send("Erro ao Adicionar Pokemon ao Banco!");
        }
        return res.status(201).send("Sucesso ao Adicionar Pokemon ao Banco!");
    });
});
```

## Criando Rota do Delete:
```js
app.delete('/deletar/:id', (req, res) => {  // Corrigido para aceitar o id via parâmetro
    const { id } = req.params;
    const comandoBanco = `DELETE FROM pokemons WHERE id = ?`;  // Corrigido a query
    connection.query(comandoBanco, [id], (erro) => {
        if (erro) {
            return res.status(500).send("Erro ao Deletar Pokemon do Banco!");
        }
        return res.status(200).send("Sucesso ao Deletar Pokemon do Banco!");
    });
});
```

## Rota para Listar
```js
app.get('/Listar', (req, res) => {
    const comandoBanco = `SELECT * FROM pokemons`;  // Verifique se você está consultando a tabela correta
    connection.query(comandoBanco, (erro, resultados) => {
        if (erro) {
            return res.status(500).send("Erro ao Listar!");
        }
        return res.status(200).json(resultados);  // Envia os dados como JSON
    });
});
````

## Rota de Listar por ID:
```js
app.get('/Listar/:id', (req, res) => {
    const { id } = req.params; 
    const comandoBanco = `SELECT * FROM pokemons Where id=?`;  // Verifique se você está consultando a tabela correta
    connection.query(comandoBanco,[id], (erro, resultados) => {
        if (erro) {
            return res.status(500).send("Erro ao Listar!");
        }
        return res.status(200).json(resultados);  // Envia os dados como JSON
    });
});
````

## Rota para Atualizar por ID:
```js
app.put('/atualizar/:id', (req, res) => {

    // ID vem da URL
    const { id } = req.params

    // Nome e email vêm do body
    const { nome_pokemon,tipo_pokemon, tem_evolucao} = req.body

    const atualizacao = `
        UPDATE pokemons
        SET nome_pokemon = ?, tipo_pokemon = ?,tem_evolucao=?
        WHERE id = ?
    `

    connection.query(atualizacao, [nome_pokemon,tipo_pokemon,tem_evolucao , id], (erro) => {

        if (erro) {
            return res.status(500).send("Erro ao tentar atualizar o usuário")
        }

        res.status(200).send("Usuário atualizado com sucesso!")
    })
})
````

## Porta do Servidor:
```js

const port = 3000;
app.listen(port, () => {
    console.log(`Servidor Rodando em http://localhost:${port}`);
});
````

