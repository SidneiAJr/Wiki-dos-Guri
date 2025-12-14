# TypeScript | Configuração do Backend e Libs Mais Usadas

## TypeScript no Backend — Visão Geral

O **TypeScript (TS)** no backend mantém os mesmos conceitos do JavaScript, porém adiciona **tipagem estática**, melhor organização e mais segurança.

Nada muda em:

* HTTP
* Rotas
* Controllers
* Services
* CRUD

O que muda é **como o código é validado antes de rodar**.

---

## Configuração do Backend com TypeScript (`tsconfig.json`)

O arquivo `tsconfig.json` define como o TypeScript será compilado para JavaScript.

### Exemplo recomendado para backend Node.js

```json
{
  "compilerOptions": {
    "target": "es6",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "outDir": "./dist",
    "rootDir": "./src"
  },
  "include": ["src/**/*.ts"],
  "exclude": ["node_modules"]
}
```

### Principais opções

* **target** → versão do JavaScript final
* **module** → padrão de módulos (Node.js usa `commonjs`)
* **strict** → ativa tipagem rigorosa (recomendado)
* **outDir** → pasta de saída do JS compilado
* **rootDir** → pasta do código fonte

---

## Libs Mais Usadas no Backend com TypeScript

### 1️⃣ Express

Framework web mais usado no Node.js.

```ts
import express, { Request, Response } from 'express';

const app = express();
app.use(express.json());

app.get('/', (req: Request, res: Response) => {
  res.send('API rodando');
});
```

---

### 2️⃣ OAuth2 (Autenticação)

Padrão de autenticação usado para login com terceiros (Google, GitHub, etc.).

Usado geralmente com:

* `passport`
* `passport-google-oauth20`

```ts
import passport from 'passport';
import { Strategy as GoogleStrategy } from 'passport-google-oauth20';

passport.use(
  new GoogleStrategy(
    {
      clientID: 'CLIENT_ID',
      clientSecret: 'CLIENT_SECRET',
      callbackURL: '/auth/google/callback'
    },
    (accessToken, refreshToken, profile, done) => {
      return done(null, profile);
    }
  )
);
```

---

### 3️⃣ TypeORM

ORM orientado a objetos para bancos SQL.

* MySQL
* PostgreSQL
* SQLite

```ts
import { DataSource } from 'typeorm';

export const AppDataSource = new DataSource({
  type: 'mysql',
  host: 'localhost',
  port: 3306,
  username: 'root',
  password: 'root',
  database: 'banco_teste',
  entities: [],
  synchronize: true
});
```

---

### 4️⃣ Prisma

ORM moderno com foco em produtividade e tipagem forte.

```ts
import { PrismaClient } from '@prisma/client';

const prisma = new PrismaClient();

async function main() {
  const usuario = await prisma.usuario.create({
    data: {
      nome: 'João',
      email: 'joao@email.com'
    }
  });
  console.log(usuario);
}
```

---

### 5️⃣ JWT (JSON Web Token)

Usado para autenticação stateless.

```ts
import jwt from 'jsonwebtoken';

const token = jwt.sign(
  { id: 1 },
  'secret_key',
  { expiresIn: '1h' }
);
```

---

## Qual ORM escolher?

* **TypeORM** → bom para POO
* **Prisma** → moderno, simples e tipado (recomendado hoje)

---

## Resumo Rápido

* TS não muda o backend, só protege
* `tsconfig.json` é obrigatório
* Express domina APIs REST
* OAuth e JWT cuidam da autenticação
* Prisma e TypeORM cuidam do banco
