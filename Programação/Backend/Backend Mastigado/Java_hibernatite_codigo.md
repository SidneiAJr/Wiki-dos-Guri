# ☕ Hibernate em Java — exemplos práticos com código

> Aqui vamos sair da teoria e ir para **código real**, do jeito que você vai ver em projeto backend Java.

---

## 📦 Exemplo de domínio

Vamos imaginar um sistema simples:

* Usuário
* Pedido

Um usuário pode ter vários pedidos.

---

## 🧱 Entidade básica (tabela simples)

### Classe Usuario

```java
import jakarta.persistence.*;

@Entity
@Table(name = "usuarios")
public class Usuario {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(nullable = false)
    private String nome;

    @Column(nullable = false, unique = true)
    private String email;

    // construtor vazio (obrigatório)
    public Usuario() {}

    public Usuario(String nome, String email) {
        this.nome = nome;
        this.email = email;
    }

    // getters e setters
}
```

📌 O que acontece aqui:

* `@Entity` → vira tabela
* `@Id` → chave primária
* `@GeneratedValue` → auto incremento

---

## 🔗 Relacionamento OneToMany / ManyToOne

### Classe Pedido

```java
import jakarta.persistence.*;

@Entity
@Table(name = "pedidos")
public class Pedido {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String descricao;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "usuario_id")
    private Usuario usuario;

    public Pedido() {}

    public Pedido(String descricao, Usuario usuario) {
        this.descricao = descricao;
        this.usuario = usuario;
    }
}
```

📌 Aqui:

* Muitos pedidos → um usuário
* Hibernate cria a **foreign key** automaticamente

---

## 🔁 Mapeamento do outro lado (OneToMany)

```java
@OneToMany(mappedBy = "usuario", fetch = FetchType.LAZY)
private List<Pedido> pedidos = new ArrayList<>();
```

📌 Importante:

* `mappedBy` diz quem é o dono da relação
* `LAZY` evita carregar tudo sem necessidade

---

## 💾 Salvando dados no banco (Hibernate puro)

```java
Session session = sessionFactory.openSession();
Transaction tx = session.beginTransaction();

Usuario usuario = new Usuario("João", "joao@email.com");
session.persist(usuario);

Pedido pedido1 = new Pedido("Notebook", usuario);
Pedido pedido2 = new Pedido("Mouse", usuario);

session.persist(pedido1);
session.persist(pedido2);

tx.commit();
session.close();
```

📌 Aqui o Hibernate:

* Abre transação
* Gera SQL automaticamente
* Insere nas tabelas

---

## 🔍 Buscando dados

```java
Usuario usuario = session.find(Usuario.class, 1L);
System.out.println(usuario.getNome());
```

O Hibernate gera:

```sql
SELECT * FROM usuarios WHERE id = 1;
```

---

## 🧠 Lazy Loading na prática

```java
Usuario usuario = session.find(Usuario.class, 1L);

// aqui NÃO busca pedidos ainda

List<Pedido> pedidos = usuario.getPedidos();
// aqui ele vai no banco buscar os pedidos
```

📌 Se a sessão estiver fechada aqui → erro (`LazyInitializationException`).

---

## 📝 JPQL (SQL orientado a objetos)

```java
String jpql = "SELECT p FROM Pedido p WHERE p.usuario.id = :id";

List<Pedido> pedidos = session.createQuery(jpql, Pedido.class)
    .setParameter("id", 1L)
    .getResultList();
```

📌 JPQL trabalha com **classes**, não com tabelas.

---

## 🧾 Atualizando dados

```java
Transaction tx = session.beginTransaction();

Usuario usuario = session.find(Usuario.class, 1L);
usuario.setNome("João Silva");

tx.commit();
```

Hibernate detecta mudança e executa `UPDATE` sozinho.

---

## ❌ Removendo dados

```java
Transaction tx = session.beginTransaction();

Pedido pedido = session.find(Pedido.class, 2L);
session.remove(pedido);

tx.commit();
```

---

## 🧩 Hibernate com Spring Boot (vida real)

### Repository

```java
public interface UsuarioRepository extends JpaRepository<Usuario, Long> {
}
```

### Service

```java
@Service
public class UsuarioService {

    @Autowired
    private UsuarioRepository repository;

    public Usuario salvar(Usuario usuario) {
        return repository.save(usuario);
    }
}
```

📌 Aqui o Hibernate roda por baixo, mas você quase não vê.

---

## ✅ Checklist de backend profissional

Se você entende esse canvas inteiro, você já sabe:

* ORM
* Relacionamento
* Transação
* Lazy loading
* CRUD real
* Backend Java

Isso é **base sólida de dev Java backend**.

---


