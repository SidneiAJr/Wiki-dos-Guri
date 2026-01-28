# TypeScript | Backend — Diferenças em relação ao JavaScript

## O que muda ao usar TypeScript no backend?

O **TypeScript (TS)** é um superconjunto do **JavaScript (JS)**.
Isso significa que **todo código JavaScript válido também é TypeScript**, mas o TS adiciona **tipagem e regras extras** que ajudam a evitar erros.

👉 No backend, os **conceitos não mudam**, apenas a **segurança e organização do código** aumentam.

---

## O que NÃO muda do JS para o TS

No backend, continuam exatamente iguais:

* Requisição e resposta (`req`, `res`)
* HTTP
* Express / Fastify
* CRUD
* Rotas
* Controllers
* Services
* Middlewares
* Banco de dados (SQL / NoSQL)
* Promises e `async/await`

📌 Exemplo idêntico:

```js
app.get('/usuarios', (req, res) => {
    res.json([]);
});
```

```ts
app.get('/usuarios', (req, res) => {
    res.json([]);
});
```

---

## Principal diferença: Tipagem

### JavaScript

```js
function soma(a, b) {
    return a + b;
}
```

### TypeScript

```ts
function soma(a: number, b: number): number {
    return a + b;
}
```

✔ O erro é detectado **antes de rodar o código**.

---

## Tipando Request e Response

No backend com TS, é comum tipar `req` e `res`.

```ts
import { Request, Response } from 'express';

function listarUsuarios(req: Request, res: Response): void {
    res.json([]);
}
```

---

## Interfaces (contrato de dados)

Interfaces definem o formato dos dados.

```ts
interface Usuario {
    nome: string;
    email: string;
}

const usuario: Usuario = {
    nome: 'João',
    email: 'joao@email.com'
};
```

✔ Garante que o objeto siga um padrão.

---

## Comparação JS vs TS no backend

| JavaScript               | TypeScript                        |
| ------------------------ | --------------------------------- |
| Dinâmico                 | Tipado                            |
| Erros em runtime         | Erros em tempo de desenvolvimento |
| Mais rápido para iniciar | Mais seguro para crescer          |
| Menos configuração       | Mais organização                  |

---

## Preciso reaprender backend para usar TS?

❌ **Não.**

Se você já sabe:

* Express
* CRUD
* SQL
* Rotas

👉 Você já sabe **TypeScript no backend**.

O aprendizado fica em:

* tipos básicos
* interfaces
* enums
* generics simples

---

## Quando usar JavaScript ou TypeScript?

### Use JavaScript quando:

* projeto pequeno
* estudo inicial
* protótipo rápido

### Use TypeScript quando:

* projeto médio ou grande
* trabalho em equipe
* código precisa escalar
* evitar bugs em produção

---

## Verdade importante

> TypeScript **não muda a arquitetura do backend**.
> Ele apenas deixa o código **mais previsível e seguro**.

---

## Resumo rápido

* Backend em TS funciona igual ao JS
* HTTP e arquitetura não mudam
* TS adiciona tipagem e segurança
* Ideal para projetos que crescem
