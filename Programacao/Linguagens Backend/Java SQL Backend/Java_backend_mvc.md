# ☕ Java + JDBC + MySQL — MVC (Cadastro de Aluno)

Este documento mostra **o mesmo cadastro de alunos**, agora organizado no padrão **MVC (Model–View–Controller)**.
Didático, direto e sem firula — focado em **entender a responsabilidade de cada parte**.

---

## 🧠 Visão Geral do MVC

No MVC você separa o sistema em **três camadas claras**:

* **Model** → dados + regras (Aluno, DAO)
* **Controller** → lógica de controle (orquestra tudo)
* **View** → entrada e saída de dados (console, tela, etc.)

Isso evita:

* `Main` gigante
* Código SQL espalhado
* Bagunça entre regra de negócio e interface

---

## 📁 Estrutura de Pastas

```text
src/
 ├─ model/
 │   ├─ Aluno.java
 │   └─ AlunoDAO.java
 │
 ├─ controller/
 │   └─ AlunoController.java
 │
 ├─ view/
 │   └─ AlunoView.java
 │
 ├─ factory/
 │   └─ ConnectionFactory.java
 │
 └─ Main.java
```

---

## 1️⃣ MODEL — Aluno (Aluno.java)

```java
package model;

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

    public String getNome() {
        return nome;
    }
}
```

### Responsabilidade:

* Representar **apenas os dados** do aluno
* Nenhuma lógica de banco ou tela aqui

---

## 2️⃣ MODEL — DAO (AlunoDAO.java)

```java
package model;

import factory.ConnectionFactory;
import java.sql.*;
import java.util.*;

public class AlunoDAO {

    public void cadastrar(Aluno aluno) {
        String sql = "INSERT INTO alunos (nome) VALUES (?)";

        try (Connection conn = ConnectionFactory.getConnection();
             PreparedStatement stmt = conn.prepareStatement(sql)) {

            stmt.setString(1, aluno.getNome());
            stmt.executeUpdate();

        } catch (SQLException e) {
            throw new RuntimeException("Erro ao cadastrar aluno", e);
        }
    }

    public List<Aluno> listar() {
        String sql = "SELECT id, nome FROM alunos";
        List<Aluno> alunos = new ArrayList<>();

        try (Connection conn = ConnectionFactory.getConnection();
             PreparedStatement stmt = conn.prepareStatement(sql);
             ResultSet rs = stmt.executeQuery()) {

            while (rs.next()) {
                alunos.add(new Aluno(
                    rs.getInt("id"),
                    rs.getString("nome")
                ));
            }

        } catch (SQLException e) {
            throw new RuntimeException("Erro ao listar alunos", e);
        }
        return alunos;
    }
}
```

### Responsabilidade:

* **Falar com o banco**
* Executar SQL
* Converter dados do banco em objetos

---

## 3️⃣ CONTROLLER — AlunoController (AlunoController.java)

```java
package controller;

import model.*;
import java.util.List;

public class AlunoController {

    private AlunoDAO dao = new AlunoDAO();

    public void cadastrarAluno(String nome) {
        if (nome == null || nome.isBlank()) {
            throw new IllegalArgumentException("Nome inválido");
        }
        dao.cadastrar(new Aluno(nome));
    }

    public List<Aluno> listarAlunos() {
        return dao.listar();
    }
}
```

### Responsabilidade:

* Regras de negócio
* Validações
* Fazer a ponte entre View e Model

---

## 4️⃣ VIEW — AlunoView (AlunoView.java)

```java
package view;

import controller.AlunoController;
import model.Aluno;
import java.util.*;

public class AlunoView {

    private Scanner scanner = new Scanner(System.in);
    private AlunoController controller = new AlunoController();

    public void executar() {
        System.out.print("Quantos alunos deseja cadastrar? ");
        int qtd = scanner.nextInt();
        scanner.nextLine();

        for (int i = 0; i < qtd; i++) {
            System.out.print("Nome do aluno " + (i + 1) + ": ");
            controller.cadastrarAluno(scanner.nextLine());
        }

        System.out.println("\n=== ALUNOS CADASTRADOS ===");
        for (Aluno a : controller.listarAlunos()) {
            System.out.println(a.getId() + " - " + a.getNome());
        }
    }
}
```

### Responsabilidade:

* Entrada e saída de dados
* **Nunca** acessa banco direto

---

## 5️⃣ Main (Main.java)

```java
import view.AlunoView;

public class Main {
    public static void main(String[] args) {
        new AlunoView().executar();
    }
}
```

### Responsabilidade:

* Apenas iniciar o sistema

---

## 🧠 Resumo Final

| Camada     | Faz o quê       |
| ---------- | --------------- |
| Model      | Dados + SQL     |
| Controller | Regras + fluxo  |
| View       | Entrada e saída |
| Main       | Inicialização   |

MVC deixa o projeto:

* Mais organizado
* Fácil de manter
* Fácil de evoluir (GUI, API, Web)


