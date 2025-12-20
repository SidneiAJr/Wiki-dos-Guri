# JavaScript | Variáveis de Ambiente

## O que são variáveis de ambiente?

Variáveis de ambiente são usadas para **armazenar configurações sensíveis** fora do código, como:

* Usuário do banco
* Senha
* Porta do servidor
* Chaves secretas

---

## Por que usar variáveis de ambiente?

* Evita expor dados sensíveis
* Facilita troca de ambiente (dev, prod)
* Boa prática profissional

---

## Usando dotenv

### Instalação

```bash
npm install dotenv
```

---

### Criando o arquivo .env

```env
PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASS=root
DB_NAME=banco_teste
```

⚠ O arquivo `.env` **não deve ser versionado**.

---

## Usando as variáveis no projeto

```js
require('dotenv').config();

const PORT = process.env.PORT;
const DB_HOST = process.env.DB_HOST;
```

---

## Exemplo com conexão ao banco

```js
const mysql = require('mysql2');

const connection = mysql.createConnection({
    host: process.env.DB_HOST,
    user: process.env.DB_USER,
    password: process.env.DB_PASS,
    database: process.env.DB_NAME
});
```

---

## Arquivo .gitignore

Adicione o `.env` ao `.gitignore`:

```txt
.env
```

---

## Boas práticas

* Nunca subir `.env` para o repositório
* Use nomes claros
* Separe variáveis por ambiente

---

## Resumo rápido

* Variáveis de ambiente protegem dados sensíveis
* Use `dotenv`
* `.env` nunca vai para o Git
