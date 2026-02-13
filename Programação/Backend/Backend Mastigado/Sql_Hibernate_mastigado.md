## Backend Java com JPA/Hibernate - Explicação Detalhada

Este documento reúne e explica, parte por parte, o código que você enviou: `Usuario`, `HibernateUtil`, `UsuarioDao` e `AuthService`.

---

### 1️⃣ Classe `Usuario` (Modelo de Dados)

```java
package Model;

import jakarta.persistence.*;

@Entity
@Table(name = "usuario")
public class Usuario {
    @Id
    @GeneratedValue(strategy = GenerationType.AUTO)
    @Column(nullable = false, length = 80)
    private int id;

    @Column(nullable = false, length = 80)
    private String usuario;

    @Column(nullable = false, length = 255, unique = true)
    private String email;

    @Column(name = "senha_rash", nullable = false, length = 100)
    private String senhaHash;

    // Construtor vazio obrigatório para JPA
    public Usuario() {}

    // Construtor para facilitar criação de instâncias
    public Usuario(String usuario, String email, String senhaHash) {
        this.usuario = usuario;
        this.email = email;
        this.senhaHash = senhaHash;
    }

    // Getters e setters
    public String getUsuario() { return usuario; }
    public void setUsuario(String usuario) { this.usuario = usuario; }

    public String getEmail() { return email; }
    public void setEmail(String email) { this.email = email; }

    public String getSenhaHash() { return senhaHash; }
    public void setSenhaHash(String senhaHash) { this.senhaHash = senhaHash; }
}
```

**Explicação:**

* `@Entity` e `@Table` indicam que esta classe é mapeada para a tabela `usuario` no banco.
* `@Id` + `@GeneratedValue` define a chave primária com auto incremento.
* `@Column` define restrições de banco (nullable, tamanho, unique).
* Campos `usuario`, `email`, `senhaHash` armazenam os dados principais.
* Getters e setters são obrigatórios para o JPA funcionar.

**O que importa:** Essa é a **estrutura do seu usuário no banco**. Tudo que você faz de cadastro ou login vai usar essa classe.

---

### 2️⃣ Classe `HibernateUtil` (Gerenciador de EntityManager)

```java
package Util;

import jakarta.persistence.*;

public class HibernateUtil {
    private static final EntityManagerFactory emf =
        Persistence.createEntityManagerFactory("myJpaUnit");

    public static EntityManager getEntityManager() {
        return emf.createEntityManager();
    }
}
```

**Explicação:**

* `EntityManagerFactory` é criado **uma vez** para a unidade de persistência `myJpaUnit` (definida no `persistence.xml`).
* `getEntityManager()` retorna sempre um **novo EntityManager**.
* Sempre feche o `EntityManager` após usar (`em.close()`).

**O que importa:** Essa classe é a porta de entrada para **qualquer operação no banco** usando JPA/Hibernate.

---

### 3️⃣ Classe `UsuarioDao` (Acesso a Dados)

```java
package DAO;

import jakarta.persistence.*;
import Model.Usuario;
import Util.HibernateUtil;

public class UsuarioDao {

    public void salvar(Usuario u) {
        EntityManager em = HibernateUtil.getEntityManager();
        try {
            em.getTransaction().begin();
            em.persist(u); // Insere no banco
            em.getTransaction().commit();
        } catch (Exception e) {
            if (em.getTransaction().isActive()) em.getTransaction().rollback();
            throw e;
        } finally {
            em.close();
        }
    }

    public Usuario buscarPorEmail(String usuario) {
        EntityManager em = HibernateUtil.getEntityManager();
        try {
            TypedQuery<Usuario> q = em.createQuery(
                "SELECT u FROM Usuario u WHERE u.usuario = :usuario",
                Usuario.class
            );
            q.setParameter("usuario", usuario);
            var lista = q.getResultList();
            return lista.isEmpty() ? null : lista.get(0);
        } finally {
            em.close();
        }
    }
}
```

**Explicação:**

* `salvar`: insere um usuário no banco dentro de uma transação.
* `buscarPorEmail`: faz uma consulta JPQL para retornar o usuário pelo nome de usuário.
* Uso de `getResultList()` evita exceções se não encontrar resultado.

**O que importa:** Essa classe **centraliza todas as operações de banco** para `Usuario`. É o “DAO” clássico do padrão MVC.

---

### 4️⃣ Classe `AuthService` (Regras de Negócio / Autenticação)

```java
package service;

import DAO.UsuarioDao;
import Model.Usuario;
import org.mindrot.jbcrypt.BCrypt;

public class AuthService {
    private final UsuarioDao dao = new UsuarioDao();

    private static final String REGEX_EMAIL = "^[A-Za-z0-9+_.-]+@(.+)$";
    private static final String REGEX_SENHA = "^(?=.*[A-Z])(?=.*\\d).{8,}$";

    public String cadastrar(String usuario, String email, String senha) {
        usuario = (usuario == null) ? "" : usuario.trim();
        email = (email == null) ? "" : email.trim().toLowerCase();

        if (usuario.length() < 2) return "Nome inválido (mínimo 2 letras).";
        if (!email.matches(REGEX_EMAIL)) return "E-mail inválido.";
        if (!senha.matches(REGEX_SENHA)) return "Senha fraca: mínimo 8, 1 maiúscula e 1 número.";
        if (dao.buscarPorEmail(email) != null) return "Este e-mail já está cadastrado.";

        String hash = BCrypt.hashpw(senha, BCrypt.gensalt(10));
        dao.salvar(new Usuario(usuario, email, hash));

        return null; // cadastro OK
    }

    public Usuario login(String usuario, String senha) {
        usuario = (usuario == null) ? "" : usuario.trim().toLowerCase();
        Usuario u = dao.buscarPorEmail(usuario);
        if (u == null) return null;

        boolean ok = BCrypt.checkpw(senha, u.getSenhaHash());
        return ok ? u : null;
    }
}
```

**Explicação:**

* `cadastrar`: valida nome, email e senha; checa duplicidade; gera hash com BCrypt; salva no banco.
* `login`: busca usuário; compara senha com hash; retorna usuário ou null.
* Regex de senha força **senha forte** (mínimo 8 caracteres, 1 maiúscula, 1 número).

**O que importa:** Essa classe é a **camada de negócio** do seu backend. Nela você aplica regras, validações e segurança antes de tocar no banco.

---

### ⚡ Resumo do Fluxo Completo

1. `AuthService` recebe uma requisição de cadastro/login.
2. Valida dados (nome, email, senha).
3. Usa `UsuarioDao` para consultar ou salvar no banco.
4. `UsuarioDao` usa `HibernateUtil` para criar `EntityManager` e fazer operações JPA.
5. `Usuario` é a entidade que representa o usuário no banco.
6. Hash da senha é feito com BCrypt antes de salvar.

---

