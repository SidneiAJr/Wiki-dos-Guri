# TypeScript | Controller e Service Pattern

## O que é o Controller-Service Pattern?

É um padrão de organização onde:

* **Controller** lida com HTTP (`req`, `res`)
* **Service** contém a lógica de negócio

Esse padrão deixa o código mais limpo, testável e organizado.

---

## Por que usar esse padrão?

* Controllers mais simples
* Regras de negócio centralizadas
* Código fácil de manter
* Muito usado no mercado

---

## Estrutura de pastas

```txt
src/
 ├── controllers/
 │    └── usuarioController.ts
 ├── services/
 │    └── usuarioService.ts
 ├── routes/
 │    └── usuariosRoutes.ts
```

---

## Service (regra de negócio)

```ts
// services/usuarioService.ts
import { Usuario } from '../models/Usuario';

export async function listarUsuarios(): Promise<Usuario[]> {
    return [];
}
```

---

## Controller (HTTP)

```ts
// controllers/usuarioController.ts
import { Request, Response } from 'express';
import { listarUsuarios } from '../services/usuarioService';

export async function listar(req: Request, res: Response) {
    const usuarios = await listarUsuarios();
    res.status(200).json(usuarios);
}
```

---

## Routes

```ts
import { Router } from 'express';
import { listar } from '../controllers/usuarioController';

const router = Router();
router.get('/', listar);

export default router;
```

---

## O que NÃO fazer

❌ Colocar SQL direto no controller
❌ Controller com muita lógica
❌ Misturar regra de negócio com HTTP

---

## Boas práticas

* Controllers finos
* Services reutilizáveis
* Separar responsabilidades

---

## Resumo rápido

* Controller = HTTP
* Service = regra de negócio
* Código mais limpo e profissional
