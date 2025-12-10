# 🧠 Comparativo entre SQL, SQLite, PostgreSQL e MongoDB

> Diferenças principais entre os sistemas de gerenciamento de banco de dados mais usados:  
> **SQL (conceito), SQLite, PostgreSQL e MongoDB**.

---

## 🧩 Tabela Comparativa

| 🗃️ Característica | 💬 **SQL (conceito)** | 📦 **SQLite** | 🐘 **PostgreSQL** | 🍃 **MongoDB** |
|:--|:--|:--|:--|:--|
| 🏗️ **Tipo de Banco** | Relacional (modelo tabular) | Relacional leve (local) | Relacional avançado (servidor) | Não relacional (documentos) |
| 💡 **Estrutura dos Dados** | Tabelas (linhas e colunas) | Tabelas simples em arquivo único | Tabelas com tipos complexos e relacionamentos | Documentos JSON (coleções) |
| 💾 **Armazenamento** | Depende do SGBD (MySQL, etc.) | Arquivo `.db` local | Servidor dedicado | Servidor com coleções BSON |
| ⚙️ **Linguagem de Consulta** | SQL padrão | SQL padrão | SQL + extensões (PL/pgSQL) | Mongo Query Language (MQL) |
| 🔗 **Relacionamentos** | Sim (chaves primárias e estrangeiras) | Sim, mas simples | Sim, complexos e robustos | Não diretamente (usa referências ou embutidos) |
| 📈 **Escalabilidade** | Vertical (depende do hardware) | Limitada (uso local) | Alta (multiusuário e cluster) | Horizontal (sharding, cluster distribuído) |
| 🚀 **Performance** | Boa para dados estruturados | Excelente para apps locais | Alta em ambientes grandes | Alta em leitura e escrita distribuída |
| 🧩 **Transações (ACID)** | Sim (depende do SGBD) | Sim (totalmente ACID) | Sim (totalmente ACID) | Parcial (depende da operação) |
| ⚙️ **Instalação** | Depende do SGBD (MySQL, PostgreSQL etc.) | Nenhuma (biblioteca embutida) | Requer servidor ativo | Requer servidor ativo |
| 🔒 **Segurança e Permissões** | Depende do SGBD | Limitada (uso local) | Avançada (usuários, roles, SSL) | Avançada (roles, autenticação, criptografia) |
| 🧠 **Uso Ideal** | Conceito geral e base da maioria dos bancos relacionais | Aplicações locais, mobile, testes, embedded | Sistemas complexos, APIs, grandes bases de dados | Big data, apps em tempo real, dados flexíveis |
| 🧩 **Exemplo de Arquivo** | — | `meubanco.db` | Servidor com `.sql` dump | Coleção `.bson` ou `.json` |
| ⚙️ **Suporte a JSON** | Parcial (dependendo do banco) | Limitado | Nativo (colunas JSONB) | Total (baseado em JSON) |

---

## 💬 **Resumo Prático**

| Situação | Banco Ideal |
|:--|:--|
| 💻 Precisa de **banco local simples e rápido** | **SQLite** |
| 🧠 Precisa de **banco relacional completo e escalável** | **PostgreSQL** |
| ⚙️ Precisa aprender **conceitos e sintaxe SQL padrão** | **SQL (conceito base)** |
| 🌐 Precisa de **dados flexíveis, sem estrutura fixa** | **MongoDB** |

---

## 🧰 **Exemplos de Uso**

| Exemplo | Ferramenta |
|:--|:--|
| App mobile ou local (sem servidor) | `SQLite` |
| Sistema web com API e relacionamentos | `PostgreSQL` |
| Protótipos rápidos e aprendizado de SQL | `MySQL` / `SQLite` |
| Aplicações com dados em JSON dinâmico (ex: redes sociais) | `MongoDB` |

---

## 🔗 **Links Úteis**

- 📘 [SQLite Docs](https://www.sqlite.org/docs.html)  
- 🐘 [PostgreSQL Docs](https://www.postgresql.org/docs/)  
- 🍃 [MongoDB Docs](https://www.mongodb.com/docs/)  
- 💡 [W3Schools SQL Tutorial](https://www.w3schools.com/sql/)  

---

> 💬 *Resumo rápido:*  
> **SQL** é a linguagem.  
> **SQLite** é leve e local.  
> **PostgreSQL** é robusto e completo.  
> **MongoDB** é flexível e não relacional.

---
