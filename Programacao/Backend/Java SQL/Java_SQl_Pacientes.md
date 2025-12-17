# ☕ Java | Sistema Paciente com 🎲SQL 

## Menu:

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

