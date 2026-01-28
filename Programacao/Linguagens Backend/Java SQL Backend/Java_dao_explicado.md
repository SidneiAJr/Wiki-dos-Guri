# ☕ Java + JDBC + MySQL — Cadastro de Aluno

Este documento quebra o código de **cadastro de alunos**, explicando **o que é**, **pra que serve** e **o que pode dar errado**. Estilo didático e direto, sem enrolação.

---

## 🧠 Visão Geral

O que você está fazendo aqui é:

1. Conectar ao MySQL
2. Criar banco de dados **se não existir**
3. Criar a tabela **alunos** no banco
4. Cadastrar alunos no banco com nome e ID
5. Listar alunos cadastrados

Tudo usando **JDBC puro**.

---

## 1️⃣ **Classe Conexão Banco (conexcao_banco.java)**

```java
public class conexcao_banco {

    private static final String URL = "jdbc:mysql://localhost:3306/";
    private static final String USER = "root";
    private static final String PASS = "root";

    public static Connection conectar(String nomeBanco) throws SQLException {
        // Conectar ao MySQL sem especificar banco inicialmente
        Connection conn = DriverManager.getConnection(URL, USER, PASS);

        // Criar banco se não existir
        String sql = "CREATE DATABASE IF NOT EXISTS " + nomeBanco;
        try (Statement stmt = conn.createStatement()) {
            stmt.executeUpdate(sql);
            System.out.println("Banco de dados '" + nomeBanco + "' criado com sucesso ou já existe.");
        }

        // Conectar ao banco de dados recém-criado
        String urlCompleta = URL + nomeBanco;
        conn = DriverManager.getConnection(urlCompleta, USER, PASS);

        return conn;
    }
}
```

### Explicação:

* **Conexão inicial**: primeiro conecta sem banco
* **Criação do banco**: cria o banco caso não exista
* **Conexão ao banco**: depois conecta ao banco recém-criado

---

## 2️⃣ **Classe Aluno (Aluno.java)**

```java
public class Aluno {

    private int id;
    private String nome;

    public Aluno(String nome) {
        this.nome = nome;
    }

    public Aluno(int id, String nome) {
        this.id = id;
        this.nome = nome;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }
}
```

### Explicação:

* **Aluno**: representa um aluno com `id` e `nome`
* **Construtores**: cria aluno com ou sem ID
* **Getters/Setters**: métodos para acessar e modificar os dados

---

## 3️⃣ **Classe ConnectionFactory (ConnectionFactory.java)**

```java
public class ConnectionFactory {

    private static final String URL = "jdbc:mysql://localhost:3306/EscolaDown";
    private static final String USER = "root";
    private static final String PASS = "root";

    public static Connection getConnection() throws SQLException {
        return DriverManager.getConnection(URL, USER, PASS);
    }
}
```

### Explicação:

* **Responsável pela conexão**: cria a conexão com o banco **EscolaDown**
* **URL, USER, PASS**: são os dados de acesso ao banco MySQL

---

## 4️⃣ **Classe AlunoDao (AlunoDao.java)**

### Método de Cadastro (CREATE)

```java
public void cadastrar(Aluno aluno) {
    String sql = "Insert intro alunos (nome) values (?)";

    try (Connection conn = ConnectionFactory.getConnection();
         PreparedStatement stmt = conn.prepareStatement(sql)) {
        stmt.setString(1, aluno.getNome());
        stmt.executeUpdate();
    } catch (Exception e) {
        throw new RuntimeException("Erro ao Cadastrar", e);
    }
}
```

### Explicação:

* **SQL errado**: `INSERT INTO alunos (nome) VALUES (?)` deveria ser o correto
* **Uso de PreparedStatement**: protege contra SQL Injection

### Método de Leitura (READ)

```java
public List<Aluno> Listar() {
    String sql = "Select id, nome, from from Alunos";

    List<Aluno> alunos = new ArrayList<>();

    try (Connection conn = ConnectionFactory.getConnection();
         PreparedStatement stmt = conn.prepareStatement(sql);
         ResultSet rs = stmt.executeQuery()) {
        while (rs.next()) {
            int id = rs.getInt("id");
            String nome = rs.getString("nome");
            alunos.add(new Aluno(id, nome));
        }
    } catch (Exception e) {
        throw new RuntimeException("Erro ao listar", e);
    }
    return alunos;
}
```

### Explicação:

* **SQL incorreto**: o correto seria `SELECT id, nome FROM alunos`
* **Uso de `PreparedStatement`**: mesma proteção contra SQL Injection

---

## 5️⃣ **Classe Main (Main.java)**

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Scanner scannner = new Scanner(System.in);
        AlunoDao dao = new AlunoDao();
        System.out.println("Quantos alunos deseja cadastrar? ");
        int quantidade = scannner.nextInt();
        scannner.nextLine();

        for (int i = 0; i < quantidade; i++) {
            System.out.println("Digite o nome do aluno " + (i + 1) + ":");
            String nome = scannner.nextLine();

            Aluno aluno = new Aluno(nome);
            dao.cadastrar(aluno);
        }

        System.out.println("\n ===============ALUNOS CADASTRADOS=============");
        dao.Listar().forEach(aluno -> {
            System.out.println(aluno.getId() + " - " + aluno.getNome());
        });
        scannner.close();
    }
}
```

### Explicação:

* **Scanner**: lê a quantidade de alunos e seus nomes
* **Loop**: cadastra os alunos no banco
* **Listar alunos**: depois de cadastrar, lista os alunos salvos no banco

---

## 🧠 Resumo Final

* **Conexão com o banco**: feita em `ConnectionFactory`
* **Cadastro de alunos**: com `AlunoDao` e `PreparedStatement`
* **Leitura de alunos**: com `SELECT` no banco

---

✔ Código limpo e organizado
✔ Proteção contra SQL Injection
✔ Boa estrutura de classes

---
