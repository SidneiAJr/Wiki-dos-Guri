# 🧠 Conceitos Fundamentais de SQL

## 📘 O que é SQL
SQL (Structured Query Language) é a linguagem padrão para **gerenciar e manipular bancos de dados relacionais**.  
Ela permite **armazenar, consultar, atualizar e controlar** dados de forma estruturada e segura.

---

## 🧩 Estrutura de um Banco de Dados Relacional
Um **banco de dados relacional** organiza as informações em **tabelas**.  
Cada tabela contém **linhas** (registros) e **colunas** (campos).  
As tabelas podem se relacionar entre si através de **chaves**, formando uma estrutura coerente e integrada.

---

## 🔑 Conceitos Básicos

### Tabelas
São coleções de dados organizados em formato de linhas e colunas.  
Cada linha representa um **registro** individual, e cada coluna representa um **atributo**.

### Campos
São as **colunas** de uma tabela, definindo o tipo de informação armazenada, como texto, número ou data.

### Registros
São as **linhas** da tabela, representando uma instância única de dados.

### Esquema
É a **estrutura lógica** que define como as tabelas e outros objetos do banco de dados se organizam.

---

## 🔗 Chaves

### Chave Primária (Primary Key)
Identifica de forma **única** cada registro de uma tabela.  
Não pode haver valores duplicados ou nulos.

### Chave Estrangeira (Foreign Key)
Cria uma **relação** entre tabelas, conectando uma coluna de uma tabela a uma chave primária de outra.

### Chave Composta
É formada por **duas ou mais colunas** que juntas identificam um registro de maneira única.

---

## ⚙️ Tipos de Dados
Os bancos de dados suportam diferentes **tipos de dados**, como:
- Numéricos (inteiros, decimais)
- Textuais (strings, caracteres)
- Temporais (datas e horários)
- Booleanos (verdadeiro/falso)

---

## 📚 Operações Fundamentais

### Inserção
Adicionar novos registros em uma tabela.

### Consulta
Buscar e visualizar informações específicas dentro das tabelas.

### Atualização
Modificar dados existentes em registros.

### Exclusão
Remover registros de uma tabela.

Essas quatro operações são conhecidas como **CRUD** (Create, Read, Update, Delete).

---

## 🔒 Controle de Acesso e Permissões
SQL permite definir **usuários, papéis e permissões** para garantir que apenas pessoas autorizadas possam acessar ou modificar determinadas informações.

---

## 📈 Índices
Índices aceleram a **busca e filtragem** de dados em tabelas grandes, melhorando o desempenho das consultas.

---

## 🧮 Normalização
É o processo de **organizar os dados** para reduzir redundâncias e melhorar a integridade do banco.  
As tabelas são divididas e relacionadas de modo a evitar duplicações desnecessárias.

---

## 🔁 Transações
Uma transação é um **conjunto de operações** que devem ser executadas de forma completa e consistente.  
Se algo falhar, todas as alterações podem ser **revertidas** para garantir a integridade dos dados.

---

## 🧱 Views (Visões)
Views são **representações virtuais** de dados baseadas em consultas.  
Elas facilitam o acesso e o controle da informação sem duplicar os dados reais.

---

## ⚖️ Integridade Referencial
Garante que os relacionamentos entre tabelas sejam **consistentes** — por exemplo, impedindo que um registro referencie outro que não existe.

---

## 🧰 Stored Procedures e Funções
São **blocos de instruções armazenados** no banco de dados, usados para automatizar tarefas e padronizar operações repetitivas.

---

## 🧠 Conclusão
SQL é essencial para o **trabalho com dados estruturados**.  
Entender seus conceitos fundamentais permite criar, manter e explorar bancos de dados com segurança, eficiência e escalabilidade.

---
