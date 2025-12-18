# ☕ Java | CRUD Pacientes | Completos | Console Scanner:


## ´Menu´

```java
import java.util.Scanner;

public class Menu {
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);
        int op =0;
        while (op!=5){
            System.out.println("====Menu====");
            System.out.println("1-Conexão Banco");
            System.out.println("2-Criar Banco");
            System.out.println("3-Criar Tabela");
            System.out.println("4-Inserir Paciente");
            System.out.println("5- Update Paciente por ID");
            System.out.println("6- Deletar por ID");
            System.out.println("7 - Sair");
            op = entrada.nextInt();
            switch (op){
                case 1:
                    ConexcaoBanco c1 = new ConexcaoBanco();
                    c1.Conectar();
                    break;
                case 2:
                    criarBanco c2 = new criarBanco();
                    c2.CriarBanco();
                    break;
                case 3:
                    CriarTabela c3 = new CriarTabela();
                    c3.criarTabela();
                    break;
                case 4:
                    inserindoPaciente c4 = new inserindoPaciente();
                    c4.Inserir();
                    break;
                case 5:
                    updatePaciente c5 = new updatePaciente();
                    c5.Update();
                    break;
                case 6:
                    deletaPaciente c6 = new deletaPaciente();
                    c6.Delete();
                    break;
                default:
                    System.out.println("Alo tem Erro");
                    break;
            }
        }
        entrada.close();
    }
}
```

1- Chamando classe pelo nome criando o um nova chamada
2- Passando Parametro
3- Inicializando uma Opção com 0
4 - Colocando while


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

## Delete com Where | Com metodo:

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;
import java.util.Scanner;

public class deletaPaciente {
    final String URL = "jdbc:mysql://localhost:3306/hospital";  // URL do MySQL (sem especificar o banco)
    final String USER = "root";  // Usuário do MySQL
    final String PASS = "root";  // Senha do MySQL

    public void Delete() {
        Scanner entrada = new Scanner(System.in);
        System.out.println("Informe o ID : ");
        int id = entrada.nextInt();

        entrada.nextLine();

        String sql =
                "DELETE FROM pacientes WHERE id = ?";
        try (Connection conexao = DriverManager.getConnection(URL, USER, PASS); PreparedStatement stm = conexao.prepareStatement(sql)) {
            //subtituil os parametros da sql
            stm.setInt(1, id);
            stm.executeUpdate();
            System.out.println("Paciente Removido com Sucesso");

        } catch (SQLException e) {
            System.out.println("Erro ao conectar ao banco de dados.");
        }
    }
}
````
