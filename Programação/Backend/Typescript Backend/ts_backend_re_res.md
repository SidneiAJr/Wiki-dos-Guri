# TypeScript | Tipos para Request e Response

## Por que tipar req e res?

No TypeScript, tipar `req` e `res` evita erros comuns e melhora o autocomplete.

---

## Importando os tipos

```ts
import { Request, Response } from 'express';
```

---

## Tipando um controller

```ts
export function listar(req: Request, res: Response): void {
    res.json([]);
}
```

---

## Tipando req.params

```ts
export function buscarPorId(req: Request, res: Response) {
    const { id } = req.params;
    res.send(`ID recebido: ${id}`);
}
```

---

## Tipando req.body

```ts
interface CriarUsuarioBody {
    nome: string;
    email: string;
}

export function criar(req: Request<{}, {}, CriarUsuarioBody>, res: Response) {
    const { nome, email } = req.body;
    res.send('Usuário criado');
}
```

---

## Tipando req.query

```ts
export function listar(req: Request<{}, {}, {}, { page?: string }>, res: Response) {
    const { page } = req.query;
    res.send(`Página: ${page}`);
}
```

---

## Erros comuns evitados

* Acessar campo inexistente
* Enviar tipo errado
* Confundir body, params e query

---

## Boas práticas

* Criar interfaces para body
* Tipar params quando necessário
* Manter controllers simples

---

## Resumo rápido

* `Request` e `Response` vêm do Express
* Tipagem aumenta segurança
* Código mais previsível
