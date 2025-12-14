# TypeScript | Erros e Exceptions

## O que são erros e exceptions?

Erros representam falhas que ocorrem durante a execução da aplicação.
No backend, eles precisam ser **tratados corretamente** para evitar travar o servidor.

---

## Tratando erros com try/catch

```ts
export async function listar(req: Request, res: Response) {
    try {
        res.status(200).json([]);
    } catch (error) {
        res.status(500).send('Erro interno do servidor');
    }
}
```

---

## Tipando erros

```ts
catch (error: unknown) {
    if (error instanceof Error) {
        res.status(500).send(error.message);
    }
}
```

---

## Criando erros personalizados

```ts
export class AppError extends Error {
    statusCode: number;

    constructor(message: string, statusCode: number) {
        super(message);
        this.statusCode = statusCode;
    }
}
```

---

## Usando erro personalizado

```ts
throw new AppError('Usuário não encontrado', 404);
```

---

## Middleware de erro global

```ts
import { Request, Response, NextFunction } from 'express';

export function errorHandler(
    err: Error,
    req: Request,
    res: Response,
    next: NextFunction
) {
    res.status(500).json({
        erro: err.message
    });
}
```

---

## Por que usar middleware de erro?

* Centraliza tratamento
* Código mais limpo
* Evita repetição

---

## Boas práticas

* Nunca retornar erro cru
* Usar status HTTP corretos
* Centralizar erros

---

## Resumo rápido

* try/catch para erros
* Erros tipados no TS
* Middleware global recomendado
