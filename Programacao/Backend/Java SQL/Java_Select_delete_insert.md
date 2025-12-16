# ☕Java | Delete | Insert | Create 

## Importandos libs:
```java
import java.sql.Connection; // Import de Lib de conexção
import java.sql.DriverManager; // Import do drive de conexção
import java.sql.SQLException; // Excessoes do SQL
import java.sql.Statement;
import java.util.Scanner;
```

## Variaveis Locais:
```java
 final String URL = "jdbc:mysql://localhost:3306/";  // URL do MySQL (sem especificar o banco)
final String USER = "root";  // Usuário do MySQL
final String PASS = "root";  // Senha do MySQL
String Banco = "Funcionarios"; //Nome do banco vai ser criado
```

## Tentativa | Try:
```java
 try{
Connection conexao = DriverManager.getConnection(URL,USER,PASS);
System.out.println("Conexao Efetuada com Sucesso!");
 //Fecha Conexcao.
conexao.close();
}
```

## Tratamento de Excesão SQl:
```java
catch(SQLException e){
             // Tratamento de erro
             System.out.println("Deu ruim Erro! Não conecto Corre berg!!");
         }
```

## Conectando ao Banco | Classe Conexção:

```java
public class conexcao {
    public static void main(String[] args) {
         final String URL = "jdbc:mysql://localhost:3306/";  // URL do MySQL (sem especificar o banco)
         final String USER = "root";  // Usuário do MySQL
         final String PASS = "root";  // Senha do MySQL
         String Banco = "Funcionarios"; //Nome do banco vai ser criado
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

## Criando o Banco: 
```java
public class criar_banco {
    public static void main(String[] args) {
        final String URL = "jdbc:mysql://localhost:3306/";  // URL do MySQL (sem especificar o banco)
        final String USER = "root";  // Usuário do MySQL
        final String PASS = "root";  // Senha do MySQL
        try(Connection conexao = DriverManager.getConnection(URL,USER,PASS);Statement stm = conexao.createStatement()){
         // Comando sql para criar o banco de dados
            // if not existis evita erro caso o banco ja exista
            String sql = "CREATE DATABASE if not exists funcionarios";
            stm.execute(sql);
            System.out.println("Banco de dados Criado com sucesso!");
        }catch(SQLException e){
            System.out.println("Erro ao criar  o banco.");
        }
    }
}
```

## Criando a tabela:
```java
public class insert_banco {
    public static void main(String[] args) {
        final String URL = "jdbc:mysql://localhost:3306/funcionarios";  // URL do MySQL (sem especificar o banco)
        final String USER = "root";  // Usuário do MySQL
        final String PASS = "root";  // Senha do MySQL
        try(Connection conexao = DriverManager.getConnection(URL,USER,PASS);Statement stm = conexao.createStatement()){
            // Comando sql para criar o banco de dados
            // if not existis evita erro caso o banco ja exista
            String sql = "CREATE TABLE IF NOT EXISTS funcionarios(" +
                    "id INT auto_increment primary key,"+
                    "nome varchar(80) not null,"+
                    "cargo varchar(50)not null"+
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

## Deletando Tudo | AVISO EXTREMAMENTE PERIGOSO | ⚠️⚠️AMBIENTE DE TESTES:
```java
public class deletando_banco {
    public static void main(String[] args) {
        final String URL = "jdbc:mysql://localhost:3306/funcionarios";  // URL do MySQL (sem especificar o banco)
        final String USER = "root";  // Usuário do MySQL
        final String PASS = "root";  // Senha do MySQL
        String sql =
                "DELETE FROM funcionarios";
        try(Connection conexao = DriverManager.getConnection(URL,USER,PASS); PreparedStatement stm = conexao.prepareStatement(sql)){
            //subtituil os parametros da sql
            stm.executeUpdate();

        } catch (SQLException e) {
            System.out.println("Erro ao conectar ao banco de dados.");
        }




    }
}
```
