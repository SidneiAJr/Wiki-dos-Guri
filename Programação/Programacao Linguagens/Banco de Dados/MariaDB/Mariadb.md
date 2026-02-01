# 📘 SQL — Documentação Base para PostgreSQL e SQL Server

> Versão adaptada para **PostgreSQL** e **SQL Server**, separando comandos específicos, sintaxe e boas práticas.

---

## 🧠 Introdução ao SQL

SQL (Structured Query Language) é a linguagem padrão para criar, consultar e gerenciar bancos de dados relacionais. Essencial para desenvolvedores, analistas de dados e DBAs.

### Bancos de Dados Suportados

* **PostgreSQL** (Open Source, ACID completo)
* **SQL Server** (Microsoft, enterprise)

## 🧩 Conceitos Fundamentais

| Conceito         | Descrição                        |
| ---------------- | -------------------------------- |
| Banco de Dados   | Conjunto de tabelas relacionadas |
| Tabela           | Estrutura que armazena dados     |
| Linha (Registro) | Cada entrada da tabela           |
| Coluna (Campo)   | Tipo de dado de uma tabela       |

## ⚙️ Criando e Selecionando Banco de Dados

### PostgreSQL

```sql
-- Criar banco
CREATE DATABASE loja;
-- Conectar ao banco
\c loja
```

### SQL Server

```sql
-- Criar banco
CREATE DATABASE loja;
-- Usar banco
USE loja;
```

## 🧱 Estrutura Básica de Tabelas

### PostgreSQL

```sql
CREATE TABLE personagem (
    id_personagem SERIAL PRIMARY KEY,
    nome_personagem VARCHAR(100) NOT NULL,
    idade INT NOT NULL
);
```

### SQL Server

```sql
CREATE TABLE personagem (
    id_personagem INT IDENTITY(1,1) PRIMARY KEY,
    nome_personagem NVARCHAR(100) NOT NULL,
    idade INT NOT NULL
);
```

## 📥 Inserindo Dados

### PostgreSQL

```sql
INSERT INTO personagem (nome_personagem, idade)
VALUES ('Saron', 2000), ('Elyndra', 134);
```

### SQL Server

```sql
INSERT INTO personagem (nome_personagem, idade)
VALUES ('Saron', 2000), ('Elyndra', 134);
```

## 📤 Consultas Básicas

```sql
-- Selecionar todos os registros
SELECT * FROM personagem;

-- Selecionar colunas específicas
SELECT nome_personagem, idade FROM personagem;
```

## 🎯 Filtros

### PostgreSQL e SQL Server

```sql
-- Condição WHERE
SELECT * FROM personagem WHERE idade > 100;

-- BETWEEN
SELECT * FROM armas WHERE id_arma BETWEEN 1 AND 5;

-- LIKE
SELECT * FROM personagem WHERE nome_personagem LIKE 'S%';

-- IN / NOT IN
SELECT * FROM especie WHERE nome_especie IN ('Elfo', 'Humano');
```

## 🔄 Atualizar e Deletar

### Atualizar

```sql
UPDATE personagem SET idade = 300 WHERE id_personagem = 1;
```

### Deletar

```sql
DELETE FROM personagem WHERE id_personagem = 10;
```

## 🔗 Junções (JOIN)

### PostgreSQL / SQL Server

```sql
SELECT p.nome_personagem, e.nome_especie
FROM personagem p
INNER JOIN especie e ON p.id_especie = e.id_especie;
```

## 🗂️ Agrupamentos e Ordenação

```sql
-- Agrupar e contar
SELECT id_especie, COUNT(*) AS total_personagens
FROM personagem
GROUP BY id_especie;

-- Ordenar
SELECT * FROM personagem ORDER BY idade DESC;
```

## 📐 Funções SQL Comuns

| Função      | Exemplo                            | Descrição             |
| ----------- | ---------------------------------- | --------------------- |
| COUNT()     | SELECT COUNT(*) FROM personagem;   | Contagem de registros |
| AVG()       | SELECT AVG(idade) FROM personagem; | Média                 |
| MAX()/MIN() | SELECT MAX(idade) FROM personagem; | Maior/menor           |

## 💾 Backup e Restore

### PostgreSQL

```bash
-- Backup
pg_dump -U usuario loja > backup_loja.sql

-- Restore
psql -U usuario -d loja -f backup_loja.sql
```

### SQL Server

```sql
-- Backup
BACKUP DATABASE loja TO DISK = 'C:\backup_loja.bak';

-- Restore
RESTORE DATABASE loja FROM DISK = 'C:\backup_loja.bak';
```

## 📌 Resumo de Comandos Essenciais

| Categoria | Comando                     | PostgreSQL            | SQL Server            | Uso               |
| --------- | --------------------------- | --------------------- | --------------------- | ----------------- |
| Banco     | CREATE DATABASE             | CREATE DATABASE loja; | CREATE DATABASE loja; | Cria DB           |
| Banco     | USE                         | \c loja               | USE loja;             | Seleciona DB      |
| Tabela    | CREATE TABLE                | CREATE TABLE ...      | CREATE TABLE ...      | Cria tabela       |
| Inserir   | INSERT INTO                 | INSERT INTO ...       | INSERT INTO ...       | Adiciona registro |
| Consultar | SELECT                      | SELECT ...            | SELECT ...            | Consulta          |
| Filtrar   | WHERE / BETWEEN / LIKE / IN | SELECT ... WHERE ...  | SELECT ... WHERE ...  | Filtra dados      |
| Atualizar | UPDATE                      | UPDATE ...            | UPDATE ...            | Atualiza registro |
| Deletar   | DELETE                      | DELETE ...            | DELETE ...            | Remove registro   |
| Join      | INNER JOIN                  | JOIN ...              | JOIN ...              | Relaciona tabelas |
| Agrupar   | GROUP BY / HAVING           | GROUP BY ...          | GROUP BY ...          | Agrupa dados      |
| Ordenar   | ORDER BY                    | ORDER BY ...          | ORDER BY ...          | Ordena registros  |
| Funções   | COUNT/AVG/MAX/MIN           | COUNT(...)            | COUNT(...)            | Estatísticas      |
| Backup    | pg_dump / BACKUP DATABASE   | pg_dump ...           | BACKUP DATABASE ...   | Backup DB         |
| Restore   | psql -f / RESTORE DATABASE  | psql -f ...           | RESTORE DATABASE ...  | Restaurar DB      |

*Documento base — SQL adaptado para PostgreSQL e SQL Server, pronto para estudos ou implementação.*
