# JavaScript | Rotas REST

## O que são Rotas REST?

Rotas REST seguem um **padrão de comunicação** entre cliente e servidor, utilizando:

* **Verbos HTTP**
* **URLs bem definidas**

O nome da rota representa o **recurso**, e o verbo HTTP representa a **ação**.

---

## Verbos HTTP mais usados

* **GET** → Buscar dados
* **POST** → Criar dados
* **PUT** → Atualizar dados
* **DELETE** → Remover dados

---

## Exemplo de Rotas NÃO REST (evitar)

```txt
GET  /ler
POST /criarUsuario
PUT  /atualizarUsuario
DELETE /deletarUsuario
```

⚠ Essas rotas funcionam, mas **não seguem o padrão REST**.

---

## Exemplo de Rotas REST (recomendado)

```txt
GET    /usuarios
GET    /usuarios/:id
POST   /usuarios
PUT    /usuarios/:id
DELETE /usuarios/:id
```

---

## Exemplo prático com Express

```js
app.get('/usuarios', (req, res) => {
    res.send('Lista de usuários');
});

app.get('/usuarios/:id', (req, res) => {
    const { id } = req.params;
    res.send(`Usuário ${id}`);
});

app.post('/usuarios', (req, res) => {
    res.status(201).send('Usuário criado');
});

app.put('/usuarios/:id', (req, res) => {
    res.send('Usuário atualizado');
});

app.delete('/usuarios/:id', (req, res) => {
    res.send('Usuário removido');
});
```

---

## Por que usar REST?

* Padrão amplamente usado
* Código mais legível
* Facilita integração com frontend e outras APIs
* Facilita manutenção do sistema

---

## Resumo rápido

* A rota representa o **recurso** (`/usuarios`)
* O verbo HTTP representa a **ação**
* Não use verbo no nome da rota
* Use os métodos HTTP corretamente
