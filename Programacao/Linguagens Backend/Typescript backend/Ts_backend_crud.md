# TypeScript | CRUD Backend

## CRUD no backend com TypeScript

O CRUD no **TypeScript** funciona exatamente igual ao JavaScript.
A diferença é que agora temos **tipagem**, o que deixa o código mais seguro e organizado.

CRUD significa:

* **CREATE** → Criar registros
* **READ** → Ler registros
* **UPDATE** → Atualizar registros
* **DELETE** → Remover registros

---

## Exemplo de estrutura básica

```txt
src/
 ├── controllers/
 ├── services/
 ├── routes/
 ├── database/
 ├── app.ts
 └── server.ts
```

---

## Interface do modelo

```ts
// models/Usuario.ts
export interface Usuario {
    id?: number;
    nome: string;
    email: string;
}
```

---

## CREATE — Criar usuário

```ts
// controllers/usuarioController.ts
import { Request, Response } from 'express';
import { Usuario } from '../models/Usuario';

export async function criar(req: Request, res: Response) {
    const usuario: Usuario = req.body;

    res.status(201).json({
        mensagem: 'Usuário criado com sucesso',
        usuario
    });
}
```

---

## READ — Listar usuários

```ts
export async function listar(req: Request, res: Response) {
    res.status(200).json([]);
}
```

---

## UPDATE — Atualizar usuário

```ts
export async function atualizar(req: Request, res: Response) {
    const { id } = req.params;
    const usuario: Usuario = req.body;

    res.status(200).json({
        mensagem: `Usuário ${id} atualizado`,
        usuario
    });
}
```

---

## DELETE — Remover usuário

```ts
export async function remover(req: Request, res: Response) {
    const { id } = req.params;

    res.status(200).json({
        mensagem: `Usuário ${id} removido`
    });
}
```

---

## Rotas

```ts
// routes/usuariosRoutes.ts
import { Router } from 'express';
import * as usuarioController from '../controllers/usuarioController';

const router = Router();

router.post('/', usuarioController.criar);
router.get('/', usuarioController.listar);
router.put('/:id', usuarioController.atualizar);
router.delete('/:id', usuarioController.remover);

export default router;
```

---

## O que o TypeScript melhora no CRUD?

* Tipagem dos dados
* Menos erros em runtime
* Melhor autocomplete
* Código mais previsível

---

## Resumo rápido

* CRUD em TS funciona igual ao JS
* Diferença está na tipagem
* Ideal para projetos que crescem
