# 🧠 Exemplo Banco 3 — SQL explicado passo a passo (bem mastigado)

Este material serve como **base de estudo** para SQL básico/intermediário.
A ideia é entender **o que cada comando faz**, não só copiar.

---

## 1️⃣ Criando o banco de dados

```sql
CREATE DATABASE aula07;
```

🔹 Cria um banco de dados chamado **aula07**.

```sql
USE aula07;
```

🔹 Diz ao MySQL: *"tudo que eu fizer agora é dentro desse banco"*.

---

## 2️⃣ Criando a tabela CLIENTES

```sql
CREATE TABLE clientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    cidade VARCHAR(50) NOT NULL,
    idade INT NOT NULL CHECK (idade >= 0 AND idade <= 120)
);
```

🔍 Quebra por partes:

* `id` → número automático, chave primária
* `nome` → texto obrigatório
* `cidade` → texto obrigatório
* `idade` → número entre 0 e 120 (validação no banco)

👉 **CHECK** evita idade inválida direto no banco.

---

## 3️⃣ Criando a tabela PRODUTOS

```sql
CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    categoria VARCHAR(50) NOT NULL,
    preco DECIMAL(10,2) NOT NULL CHECK (preco >= 0)
);
```

🔍 Aqui entra dinheiro:

* `DECIMAL(10,2)` → 10 dígitos no total, 2 casas decimais
* `CHECK (preco >= 0)` → preço nunca negativo

---

## 4️⃣ Inserindo dados na tabela CLIENTES

```sql
INSERT INTO clientes (id, nome, cidade, idade) VALUES (...);
```

🔹 Insere **vários registros de uma vez**.
🔹 Cada linha é um cliente.
🔹 Boa prática para popular banco de testes.

---

## 5️⃣ Inserindo dados na tabela PRODUTOS

```sql
INSERT INTO produtos (id, nome, categoria, preco) VALUES (...);
```

🔹 Mesma lógica dos clientes.
🔹 Cada linha representa um produto.

---

## 6️⃣ SELECT com filtro de preço (> 200)

```sql
SELECT * FROM produtos
WHERE preco > 200
ORDER BY preco DESC;
```

🔹 `WHERE` → filtra
🔹 `ORDER BY DESC` → do mais caro para o mais barato

---

## 7️⃣ SELECT com DISTINCT (sem repetir cidades)

```sql
SELECT DISTINCT cidade FROM clientes;
```

🔹 `DISTINCT` remove valores duplicados

---

## 8️⃣ SELECT com LIKE (busca parcial)

```sql
SELECT nome FROM produtos
WHERE nome LIKE '%game%';
```

🔹 `%` → qualquer coisa antes ou depois
🔹 Busca produtos que **contêm** a palavra

---

## 9️⃣ LIMIT (mais baratos)

```sql
SELECT * FROM produtos
ORDER BY preco ASC
LIMIT 3;
```

🔹 `ASC` → crescente
🔹 `LIMIT` → limita quantidade de resultados

---

## 🔟 OR (uma condição OU outra)

```sql
SELECT nome FROM clientes
WHERE cidade = 'Porto Alegre' OR cidade = 'Canoas';
```

🔹 Retorna quem mora em **qualquer uma** das cidades

---

## 1️⃣1️⃣ BETWEEN (intervalo)

```sql
SELECT nome FROM clientes
WHERE idade BETWEEN 30 AND 40;
```

🔹 Inclui 30 e 40
🔹 Mais legível que usar `>=` e `<=`

---

## 1️⃣2️⃣ ORDER + LIMIT (TOP N)

```sql
SELECT * FROM produtos
ORDER BY preco DESC
LIMIT 5;
```

🔹 Top 5 mais caros

---

## 1️⃣3️⃣ AND + OR (condição composta)

```sql
SELECT nome, categoria
FROM produtos
WHERE (categoria = 'Informática' OR categoria = 'Eletrônicos')
  AND preco > 1000;
```

🔹 Parênteses evitam lógica errada
🔹 Primeiro decide a categoria, depois o preço

---

## 1️⃣4️⃣ NOT (negação)

```sql
SELECT * FROM clientes
WHERE NOT cidade = 'São Paulo';
```

🔹 Retorna todos **menos** São Paulo

---

## 1️⃣5️⃣ NOT BETWEEN

```sql
SELECT * FROM produtos
WHERE NOT (preco BETWEEN 200 AND 800);
```

🔹 Tudo fora do intervalo

---

## 🧠 O que esse exercício ensina

✔ CREATE DATABASE / TABLE
✔ INSERT em massa
✔ SELECT
✔ WHERE
✔ ORDER BY
✔ LIMIT
✔ LIKE
✔ BETWEEN
✔ DISTINCT
✔ AND / OR / NOT

👉 Isso aqui é **SQL raiz**, base pra qualquer backend.

---


