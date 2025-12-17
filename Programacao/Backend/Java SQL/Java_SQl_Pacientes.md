# ☕ Java | Sistema Paciente com 🎲SQL 

* `Criando Conexção do Banco`
* `Criando o banco`
* `Criando Tabela`
* `Inserindo Informação`

## Comandos SQL | Usado:

```sql
CREATE DATABASE if not exists Hospital
"CREATE TABLE IF NOT EXISTS Pacientes(" +
                    "id INT auto_increment primary key,"+
                    "nome varchar(80) not null,"+
                    "idade int not null,"+
                    "plano varchar(50) not null"+
                    ")";
INSERT INTO pacientes (nome,idade,plano) values (?,?,?)
--- Porque os ?? porque sim, Brinks
--- Server para SQL Injection proteção 🛡️
```

## Comando SQl | Similar Usado no banco 🎲🎲:

```sql
-- Cria o banco de dados caso ainda não exista
CREATE DATABASE IF NOT EXISTS Hospital;

-- Seleciona o banco
USE Hospital;

-- Cria a tabela de pacientes
CREATE TABLE IF NOT EXISTS Pacientes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(80) NOT NULL,
    idade INT NOT NULL,
    plano VARCHAR(50) NOT NULL
);

-- Inserção segura de dados (usada via PreparedStatement no Java)
INSERT INTO pacientes (nome, idade, plano) 
VALUES (?, ?, ?);
```


## Menu:

* `While serve para ficar rodando o menu`
* `Opcao e iniciada com 0.`
* `Scanner le a entrada do usuario`
* `case 1 | Cria a conexcao`
* `case 2 | Cria o Banco`
* `Case 3 | Cria a tabela | Insere os campos`
* `Case 4 | Insere Informação na tabela desejada`
* `Case 5 | Default Fecha o While`

> Importante:```java final String URL = "jdbc:mysql://localhost:3306/"; // Aqui na criacao da tabela referenciar ao JBDC o caminho do banco ⚠️ Cuidado com Letras Maiusculas e Minusculas```

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
            System.out.println("5-Sair");
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
                default:
                    System.out.println("Alo tem erro");
                    break;
            }
        }
        entrada.close();
    }
}
```



## Conexção de Banco:
```java
import java.sql.*; // Import de Lib de conexção

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

## Criar Banco:
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

## Criar tabela:

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Scanner;

public class CriarTabela {
    final String URL = "jdbc:mysql://localhost:3306/hospital";  // URL do MySQL (sem especificar o banco)
    final String USER = "root";  // Usuário do MySQL
    final String PASS = "root";  // Senha do MySQL
    public void criarTabela(){
        try(Connection conexao = DriverManager.getConnection(URL,USER,PASS);Statement stm = conexao.createStatement()){
            // Comando sql para criar o banco de dados
            // if not existis evita erro caso o banco ja exista
            String sql = "CREATE TABLE IF NOT EXISTS Pacientes(" +
                    "id INT auto_increment primary key,"+
                    "nome varchar(80) not null,"+
                    "idade int not null,"+
                    "plano varchar(50) not null"+
                    ")";
            stm.executeUpdate(sql);
            // confirmação no console
            System.out.println("Tabela criada com sucesso!");
        }catch(SQLException e){
            System.out.println("Erro ao criar  a Tabela.");
        }
    }
}
````

## Inserindo Tabela:
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

