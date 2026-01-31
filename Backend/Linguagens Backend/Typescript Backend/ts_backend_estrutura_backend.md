# TypeScript | Estrutura de Backend

## Estrutura recomendada para backend em TypeScript

A estrutura em TypeScript é **quase idêntica à do JavaScript**.
A diferença está nos **arquivos `.ts`** e na **organização de tipos**.

---

## Estrutura base

```txt
src/
 ├── controllers/
 ├── routes/
 ├── services/
 ├── middlewares/
 ├── models/
 ├── database/
 ├── app.ts
 └── server.ts
```

---

## Controllers

Responsáveis por lidar com `req` e `res`.

```ts
import { Request, Response } from 'express';

export function listar(req: Request, res: Response) {
    res.send('Controller funcionando');
}
```

---

## Services

Onde fica a lógica de negócio.

```ts
export function buscarUsuarios() {
    return [];
}
```

---

## Models

Definem o formato dos dados.

```ts
export interface Usuario {
    id?: number;
    nome: string;
    email: string;
}
```

---

## Routes

Definem os endpoints.

```ts
import { Router } from 'express';
import { listar } from '../controllers/usuarioController';

const router = Router();

router.get('/', listar);

export default router;
```

---

## app.ts

Configuração do Express.

```ts
import express from 'express';

const app = express();
app.use(express.json());

export default app;
```

---

## server.ts

Inicialização do servidor.

```ts
import app from './app';

app.listen(3000, () => {
    console.log('Servidor rodando na porta 3000');
});
```

---

## Boas práticas

* Controllers simples
* Lógica nos services
* Tipos bem definidos
* Estrutura clara

---

## Resumo rápido

* Estrutura em TS é igual ao JS
* Organização facilita manutenção
* Ideal para projetos médios e grandes
