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
```
}
