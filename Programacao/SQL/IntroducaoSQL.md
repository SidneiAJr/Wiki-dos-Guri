# 🧠 Introdução ao SQL (Structured Query Language)

SQL é a linguagem usada para criar, gerenciar e consultar bancos de dados relacionais (como MySQL, PostgreSQL, SQLite, SQL Server, etc).
É essencial para qualquer desenvolvedor backend, analista de dados ou DBA.

## 🧩 O que é um Banco de Dados?

Um banco de dados relacional armazena informações em tabelas (linhas e colunas), permitindo relacionamentos entre elas.
Exemplo:

Tabela clientes

Tabela pedidos

Relacionamento: um cliente pode ter vários pedidos.

# 🧱 Estrutura Básica
Conceito	Descrição	Exemplo
Banco de Dados	Conjunto de tabelas	CREATE DATABASE loja;
Tabela	Estrutura que guarda dados	CREATE TABLE produtos (...);
Linha (Registro)	Cada entrada da tabela	INSERT INTO produtos VALUES (...);
Coluna (Campo)	Tipo de dado de uma tabela	nome, preco, quantidade

## ⚙️ Criando e Selecionando um Banco de Dados
CREATE DATABASE loja;
USE loja;

# 🧙‍♂️ Banco de Dados — “Sraneis” (SQL) | Desafio TDS 2025
```sql
-- ========================================
-- 🎲 CRIAR O BANCO DE DADOS E USAR
-- ========================================
CREATE DATABASE sraneis;
USE sraneis;


🧬 Tabela: especie
-- Tabela que armazena as espécies (raças) dos personagens
CREATE TABLE especie(
    id_especie INT PRIMARY KEY AUTO_INCREMENT,  -- Identificador único
    nome_especie VARCHAR(100) NOT NULL          -- Nome da espécie (Ex: Elfo, Humano)
);

🧙‍♂️ Tabela: personagem
-- Armazena informações dos personagens
CREATE TABLE personagem(
    id_personagem INT PRIMARY KEY AUTO_INCREMENT, -- ID do personagem
    nome_personagem VARCHAR(100) NOT NULL,        -- Nome do personagem
    idade INT NOT NULL                            -- Idade (ou anos de existência)
);

⚔️ Tabela: armas
-- Lista de armas do mundo de Sraneis
CREATE TABLE armas(
    id_arma INT PRIMARY KEY AUTO_INCREMENT,
    nome_arma VARCHAR(55) NOT NULL
);

🗺️ Tabela: local_mapa
-- Locais importantes do mapa
CREATE TABLE local_mapa (
    id_local INT PRIMARY KEY AUTO_INCREMENT,
    nome_local VARCHAR(100) NOT NULL,
    descricao TEXT
);

💫 Tabela: habilidade
-- Habilidades mágicas ou físicas que personagens podem ter
CREATE TABLE habilidade (
    id_habilidade INT PRIMARY KEY AUTO_INCREMENT,
    nome_habilidade VARCHAR(100) NOT NULL,
    descricao TEXT
);

🧩 Tabela: caracteristica_personagem
-- Relação entre personagem, espécie, arma e habilidade
CREATE TABLE caracteristica_personagem(
    id_informacao INT PRIMARY KEY AUTO_INCREMENT,
    id_especie INT NOT NULL,
    id_personagem INT NOT NULL,
    id_habilidade INT NOT NULL,
    id_arma INT NOT NULL,
    
    -- Chaves estrangeiras
    FOREIGN KEY(id_especie) REFERENCES especie(id_especie),
    FOREIGN KEY(id_personagem) REFERENCES personagem(id_personagem),
    FOREIGN KEY(id_habilidade) REFERENCES habilidade(id_habilidade),
    FOREIGN KEY(id_arma) REFERENCES armas(id_arma)
);

👥 Inserindo Personagens
INSERT INTO personagem (nome_personagem, idade)
VALUES
  ("Saron", 2000),
  ("Elyndra", 134),
  ("Thorek Martelo-de-Ferro", 245),
  ("Nyssa Sombravento", 87),
  ("Kael'thas", 302),
  ("Mira Valeluz", 29),
  ("Drakar, o Flamejante", 520),
  ("Lira Nocturne", 105),
  ("Vornak, o Cruel", 399),
  ("Aeris Luminar", 56);

⚔️ Inserindo Armas
INSERT INTO armas (nome_arma)
VALUES
  ("Lâmina do Crepúsculo"),
  ("Espada da Luz Eterna"),
  ("Machado de Sangue"),
  ("Arco dos Ventos Silenciosos"),
  ("Cajado do Ancião"),
  ("Lança Sombria"),
  ("Adaga de Víbora"),
  ("Martelo de Tempestade"),
  ("Foice da Meia-Noite"),
  ("Espada de Fogo Vivo"),
  ("O Anel - Meu precioso");

✨ Inserindo Habilidades
INSERT INTO habilidade (nome_habilidade, descricao)
VALUES
  ("Bola de Fogo", "Lança uma bola flamejante que explode ao atingir o alvo."),
  ("Cura Rápida", "Regenera rapidamente a saúde do personagem."),
  ("Golpe Sombrio", "Um ataque furtivo com dano adicional."),
  ("Escudo Arcano", "Cria uma barreira mágica que absorve dano."),
  ("Fúria Berserker", "Aumenta temporariamente o ataque, mas reduz a defesa."),
  ("Teletransporte", "Move o personagem instantaneamente para outro local."),
  ("Flecha Congelante", "Ataca com uma flecha de gelo que pode paralisar o inimigo."),
  ("Chamado da Tempestade", "Invoca relâmpagos que atingem múltiplos inimigos."),
  ("Camuflagem", "Torna o personagem invisível por um curto período."),
  ("Toque da Morte", "Habilidade rara que pode derrotar inimigos instantaneamente.");

🧝 Inserindo Espécies


INSERT INTO especie (nome_especie)
VALUES
  ("Elfo"),
  ("Anão"),
  ("Humano"),
  ("Hobbit"),
  ("Mago (Istari)"),
  ("Orc"),
  ("Uruk-hai"),
  ("Ent"),
  ("Troll"),
  ("Dragão"),
  ("Nazgûl"),
  ("Maia"),
  ("Valar");

🧠 Relacionando um Personagem (Exemplo)
-- Liga um personagem a uma espécie, habilidade e arma específica
INSERT INTO caracteristica_personagem(id_especie, id_personagem, id_habilidade, id_arma)
VALUES
(1, 1, 1, 1);  -- Exemplo: Elfo (1), Saron (1), Bola de Fogo (1), Lâmina do Crepúsculo (1)

🧩 Consultas Úteis
-- Ver todos os personagens com suas espécies e habilidades
SELECT 
    p.nome_personagem,
    e.nome_especie,
    h.nome_habilidade,
    a.nome_arma
FROM caracteristica_personagem cp
JOIN personagem p ON p.id_personagem = cp.id_personagem
JOIN especie e ON e.id_especie = cp.id_especie
JOIN habilidade h ON h.id_habilidade = cp.id_habilidade
JOIN armas a ON a.id_arma = cp.id_arma;

```

## 🧠 Filtrando e Ordenando
```sql
SELECT * FROM produtos
WHERE preco BETWEEN 100 AND 1000
ORDER BY preco DESC;
```

## 🧩 Junções (JOIN)
```sql
SELECT c.nome, p.data_pedido
FROM clientes c
JOIN pedidos p ON c.id = p.id_cliente;
```

## 🗂️ Agrupamentos
```sql
SELECT id_cliente, COUNT(*) AS total_pedidos
FROM pedidos
GROUP BY id_cliente;
```

## 💾 Backup e Restore (MySQL)
```sql
Backup:

mysqldump -u root -p loja > backup_loja.sql


Restauração:

mysql -u root -p loja < backup_loja.sql
```

## 📌 Quadro Resumo — Comandos SQL Essenciais

| Categoria | Comando | Exemplo | Uso |
|-----------|--------|--------|-----|
| 🎮 **Banco de Dados** | `CREATE DATABASE nome;` | `CREATE DATABASE sraneis;` | Cria um banco |
| | `USE nome;` | `USE sraneis;` | Seleciona banco |
| | `DROP DATABASE nome;` | `DROP DATABASE sraneis;` | Apaga banco |
| 🧱 **Tabela** | `CREATE TABLE` | `CREATE TABLE personagem (...);` | Cria tabela |
| | `ALTER TABLE` | `ALTER TABLE personagem ADD reino VARCHAR(50);` | Altera estrutura |
| | `DROP TABLE` | `DROP TABLE personagem;` | Apaga tabela |
| 📥 **Inserir Dados** | `INSERT INTO` | `INSERT INTO personagem VALUES (...);` | Adiciona registro |
| 📤 **Consultar Dados** | `SELECT * FROM tabela;` | `SELECT * FROM personagem;` | Lista tudo |
| | `SELECT coluna1, coluna2 FROM tabela;` | `SELECT nome, idade FROM personagem;` | Colunas específicas |
| 🎯 **Filtros** | `WHERE` | `SELECT * FROM personagem WHERE idade > 100;` | Filtra |
| | `BETWEEN` | `SELECT * FROM armas WHERE id_arma BETWEEN 1 AND 5;` | Intervalo |
| | `LIKE` | `SELECT * FROM personagem WHERE nome LIKE 'S%';` | Busca por padrão |
| | `IN / NOT IN` | `SELECT * FROM especie WHERE nome_especie IN ('Elfo', 'Humano');` | Lista de valores |
| 🔄 **Atualizar / Deletar** | `UPDATE` | `UPDATE personagem SET idade = 300 WHERE id_personagem = 1;` | Atualiza |
| | `DELETE` | `DELETE FROM personagem WHERE id_personagem = 10;` | Deleta |
| 🔗 **JOIN — Relacionar Tabelas** | `INNER JOIN` | `SELECT * FROM personagem JOIN especie ON ...;` | Junta dados |
| 📊 **Agrupamento e Ordenação** | `GROUP BY` | `SELECT id_especie, COUNT(*) FROM personagem GROUP BY id_especie;` | Agrupa |
| | `ORDER BY` | `SELECT * FROM personagem ORDER BY idade DESC;` | Ordena |
| | `HAVING` | `HAVING COUNT(*) > 1` | Filtro pós-agrupamento |
| 📐 **Funções SQL** | `COUNT()` | `SELECT COUNT(*) FROM personagem;` | Quantidade |
| | `AVG()` | `SELECT AVG(idade) FROM personagem;` | Média |
| | `MAX() / MIN()` | `SELECT MAX(idade) FROM personagem;` | Maior/Menor |
| 💾 **Backup / Restore MySQL** | `mysqldump` | `mysqldump -u root -p sraneis > backup.sql` | Exporta |
| | `mysql <` | `mysql -u root -p sraneis < backup.sql` | Restaura |

