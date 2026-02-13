## Hibernate em Java - Explicação Completa

### 1️⃣ O que é Hibernate?

Hibernate é um **framework de mapeamento objeto-relacional (ORM)** para Java. Ele permite que você trabalhe com **objetos Java** e deixe que o Hibernate cuide de salvar, atualizar, buscar e deletar esses objetos no banco de dados relacional.

**Objetivo principal:** abstrair o SQL e permitir que você trabalhe com objetos de forma natural.

---

### 2️⃣ Para que serve?

* Evita escrever SQL manualmente na maioria dos casos.
* Gerencia transações e conexões com o banco.
* Faz mapeamento automático entre classes Java e tabelas do banco.
* Suporta herança, relacionamentos (1:1, 1:N, N:M) e coleções.
* Permite cache de segundo nível para otimizar performance.

**Exemplo:**

```java
Usuario u = new Usuario("Alberto", "alberto@email.com", "hashsenha");
em.persist(u); // Hibernate gera INSERT automaticamente
```

Sem precisar escrever `INSERT INTO usuario ...` manualmente.

---

### 3️⃣ Propriedades importantes do Hibernate

O Hibernate usa **configurações de unidade de persistência** (`persistence.xml`) ou `hibernate.cfg.xml`. Algumas propriedades principais:

| Propriedade                       | Descrição                                                     |
| --------------------------------- | ------------------------------------------------------------- |
| `hibernate.dialect`               | Define o dialeto SQL do banco (MySQL, PostgreSQL, Oracle...)  |
| `hibernate.show_sql`              | true/false; mostra SQL gerado no console                      |
| `hibernate.hbm2ddl.auto`          | `create`, `update`, `validate`, `none`; define ação do schema |
| `javax.persistence.jdbc.url`      | URL de conexão com o banco                                    |
| `javax.persistence.jdbc.user`     | Usuário do banco                                              |
| `javax.persistence.jdbc.password` | Senha do banco                                                |
| `javax.persistence.jdbc.driver`   | Driver JDBC                                                   |

---

### 4️⃣ Principais classes e interfaces

* **Session / EntityManager**: gerencia o ciclo de vida das entidades.
* **Transaction**: inicia, comita ou faz rollback de transações.
* **SessionFactory / EntityManagerFactory**: cria instâncias de `Session`/`EntityManager`.
* **Query / TypedQuery**: para executar JPQL ou SQL nativo.

---

### 5️⃣ Vantagens do Hibernate

* Reduz código SQL repetitivo.
* Facilita manutenção e evolução do modelo de dados.
* Permite portabilidade entre bancos de dados.
* Suporta cache e lazy loading.
* Integra facilmente com Spring, Jakarta EE, etc.

### 6️⃣ Exemplo prático simples

```java
EntityManager em = HibernateUtil.getEntityManager();
em.getTransaction().begin();
Usuario u = new Usuario("Alberto", "email@ex.com", "hash");
em.persist(u);
em.getTransaction().commit();
em.close();
```

* Cria conexão com o banco.
* Inicia transação.
* Persiste objeto no banco.
* Comita transação.
* Fecha a conexão.

---

**Resumo:** Hibernate é a ponte entre seus **objetos Java** e o **banco relacional**, permitindo CRUD, consultas, relacionamentos e transações de forma fácil e organizada.
