# ☕ Java | CRUD Pacientes | Completos | Console Scanner:

## Importando todas as Libs do Jva SQl:
```java
import java.sql.*; // Import de Lib de conexção
```

## Conexção do Banco | Com Metodo Conectar
```java
public class ConexcaoBanco {
    final String URL = "jdbc:mysql://localhost:3306/";  // URL do MySQL (sem especificar o banco)
    final String USER = "root";  // Usuário do MySQL
    final String PASS = "root";  // Senha do MySQL
    String Banco = "Funcionarios"; //Nome do banco vai ser criado
    public void Conectar(){
        try{
            Connection conexao = DriverManager.getConnection(URL,USER,PASS);
            System.out.println("Conexao Efetuada com Sucesso!");
            //Fecha Conexcao.
            conexao.close();
        }catch(SQLException e){
            // Tratamento de erro
            System.out.println("Deu ruim Erro! Não conecto Corre berg!!");
        }
    }
}
```

## Criar Banco | Com Metodo:

```java
import java.sql.*; // Import de Lib de conexção

public class criarBanco {
    final String URL = "jdbc:mysql://localhost:3306/";  // URL do MySQL (sem especificar o banco)
    final String USER = "root";  // Usuário do MySQL
    final String PASS = "root";  // Senha do MySQL
        public void CriarBanco(){
            try(Connection conexao = DriverManager.getConnection(URL,USER,PASS);Statement stm = conexao.createStatement()){
                // Comando sql para criar o banco de dados
                // if not existis evita erro caso o banco ja exista
                String sql = "CREATE DATABASE if not exists Hospital";
                stm.execute(sql);
                System.out.println("Banco de dados Criado com sucesso!");
            }catch(SQLException e){
                System.out.println("Erro ao criar  o banco.");
            }
        }
}
```

## Inserindo Informações na Tabela 

```java
import java.sql.*; // Import de Lib de conexção
import java.util.Scanner;

public class inserindoPaciente {
    final String URL = "jdbc:mysql://localhost:3306/hospital";  // URL do MySQL (sem especificar o banco)
    final String USER = "root";  // Usuário do MySQL
    final String PASS = "root";  // Senha do MySQL
    public void Inserir(){
        Scanner entrada = new Scanner(System.in);
        System.out.println("Informe Nome: ");
        String nome = entrada.nextLine();
        System.out.println("Informe Idade: ");
        int Idade = entrada.nextInt();
        entrada.nextLine();
        System.out.println("Insira o Plano: ");
        String plano = entrada.nextLine();
        /*
        SQl parametrização
        o uso de ?  evita sql injection
         */
        String sql =
                // Insert into funcionarios (nome) values ('jesus'); from funcionarios ('1'='1');
                "INSERT INTO pacientes (nome,idade,plano) values (?,?,?)";
        try(Connection conexao = DriverManager.getConnection(URL,USER,PASS); PreparedStatement stm = conexao.prepareStatement(sql)){
            //subtituil os parametros da sql
            stm.setString(1,nome);
            stm.setInt(2,Idade);
            stm.setString(3,plano);
            stm.executeUpdate();
            System.out.println("Paciente Inserido com Sucesso");

        } catch (SQLException e) {
            System.out.println("Erro ao conectar ao banco de dados.");
        }
    }
}
```

## Update com Where | Com metodo:

```java
import java.sql.*; // Import de Lib de conexção
import java.util.Scanner;

public class updatePaciente {
    final String URL = "jdbc:mysql://localhost:3306/hospital";  // URL do MySQL (sem especificar o banco)
    final String USER = "root";  // Usuário do MySQL
    final String PASS = "root";  // Senha do MySQL

    public void Update() {
        Scanner entrada = new Scanner(System.in);
        System.out.println("Informe o ID : ");
        int id = entrada.nextInt();

        entrada.nextLine();

        System.out.println("Informe o Novo Plano: ");
        String plano = entrada.nextLine();

        String sql =
                "UPDATE pacientes set plano = ? WHERE id = ?";
        try (Connection conexao = DriverManager.getConnection(URL, USER, PASS); PreparedStatement stm = conexao.prepareStatement(sql)) {
            //subtituil os parametros da sql
            stm.setString(1, plano);
            stm.setInt(2, id);
            stm.executeUpdate();
            System.out.println("Paciente Atualizado com Sucesso");

        } catch (SQLException e) {
            System.out.println("Erro ao conectar ao banco de dados.");
        }
    }
}
```

