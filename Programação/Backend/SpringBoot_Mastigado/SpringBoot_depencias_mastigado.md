# Exemplo de Dependências Java sem HydroRS

## 1️⃣ Spring Boot Starter Data JPA

**O que é:** Permite usar JPA/Hibernate para persistência de dados.

**Exemplo de código:**

```java
import org.springframework.data.jpa.repository.JpaRepository;

public interface PessoaRepository extends JpaRepository<Pessoa, Long> {
    List<Pessoa> findByCidade(String cidade);
}
```

* Aqui você consegue buscar pessoas por cidade sem escrever SQL.

---

## 2️⃣ MySQL Connector

**O que é:** Driver JDBC para conectar Java com MySQL.

**Exemplo de application.properties:**

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/testdb
spring.datasource.username=root
spring.datasource.password=1234
spring.jpa.hibernate.ddl-auto=update
```

* Conecta a aplicação Spring Boot a um banco MySQL genérico.

---

## 3️⃣ Lombok

**O que é:** Biblioteca que reduz código repetitivo.

**Exemplo de código:**

```java
import lombok.Data;
import jakarta.persistence.Entity;
import jakarta.persistence.Id;

@Data
@Entity
public class Pessoa {
    @Id
    private Long id;
    private String nome;
    private String cidade;
}
```

* Gera getters, setters e construtores automaticamente.

---

## 4️⃣ Spring Boot Starter Web

**O que é:** Framework para criar APIs REST e gerenciar requisições HTTP.

**Exemplo de Controller:**

```java
import org.springframework.web.bind.annotation.*;
import java.util.List;

@RestController
@RequestMapping("/pessoas")
public class PessoaController {

    @GetMapping
    public List<Pessoa> listarPessoas() {
        return List.of(new Pessoa()); // exemplo simples
    }

    @GetMapping("/cidade/{nome}")
    public List<Pessoa> listarPorCidade(@PathVariable String nome) {
        return List.of(new Pessoa());
    }
}
```

* Cria endpoints para listar pessoas ou filtrar por cidade.

---

## 5️⃣ Spring Boot Starter Data JPA Test

**O que é:** Biblioteca de testes para JPA.

**Exemplo de teste:**

```java
import org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTest;
import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;

@DataJpaTest
public class PessoaRepositoryTest {
    @Autowired
    private PessoaRepository repository;

    @Test
    public void testFindByCidade() {
        var pessoas = repository.findByCidade("Porto Alegre");
        assertNotNull(pessoas);
    }
}
```

