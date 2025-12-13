# Java | Exemplo de Conexção do Java com POO:

## `Java|Exemplo de conexção com banco SQL` - Swing 

- Segurança Fraca

````java
class Con{
    protected String Nome_banco;
    protected String Senha;
    protected String usuario;

    public Con(String Nome_banco, String Senha, String usuario) {
        this.Nome_banco = Nome_banco;
        this.Senha = Senha;
        this.usuario = usuario;
    }
    
    public Connection conex(){
         Connection conn = null;
          try {
            // Substitua o URL com a URL do seu banco
            String url = "jdbc:mysql://localhost:3306/" + Nome_banco;
            // Realiza a conexão
            conn = DriverManager.getConnection(url, usuario, Senha);
        } catch (SQLException e) {
        }
        return conn;
    }        
    }
    public void listauser(Connection conn) {
    try {
        // Cria o statement para executar a consulta SQL
        Statement stmt = conn.createStatement();
        String sql = "SELECT nome_usuario, id FROM usuario";  // Corrigido SQL
        
        // Executa a consulta SQL e obtém o resultado
        ResultSet rs = stmt.executeQuery(sql);
        
        while(rs.next()){
            String NomeUsuario = rs.getString("nome_usuario");
        int id = rs.getInt("id");

       Jt_usuarios.append("ID: " + id + " - Nome de Usuário: " + NomeUsuario + "\n");
        }
        // Itera sobre os resultados e exibe os dados
        
        
    } catch (SQLException e) {
        // Se houver erro na consulta, exibe a mensagem de erro
        jt_saida.setText("Erro ao listar usuários: " + e.getMessage());
    }
}

 
    private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:
        Con con = new Con("teste", "root", "root");

        // Chama o método conex() para tentar a conexão
        Connection conn = con.conex();

        // Verifica se a conexão foi bem-sucedida e atualiza o label de saída
        if (conn != null) {
            jt_saida.setText("Bem vindo | Lista de Usuarios Cadastrados!");
             listauser(conn);
            
        } else {
            jt_saida.setText("Falha na conexão!");
        }
        
    }                                                 
}
````

## `Banco de dados de estudo`

- Banco de estudo & Testes.
- Banco com senha salva no banco, não pode.
- Banco somente para teste.

```SQL
DROP DATABASE teste;

CREATE DATABASE teste;

use teste;

CREATE TABLE usuario(
 id int auto_increment primary key not null,
 nome_usuario varchar(50) not null,
 senha varchar(50) not null
);

INSERT INTO usuario (nome_usuario,senha) values 
("Pedro Mesa","123"),
("Pedro Mesa","123"),
("Ana Souza","456"),
("Carlos Lima","789"),
("Maria Fernandes","abc"),
("João Araujo","xyz"),
("Beatriz Gomes","654"),
("Lucas Pereira","321"),
("Fernanda Alves","159"),
("Rafael Santos","753"),
("Juliana Castro","951");



create table produtos(
     id int auto_increment primary key not null,
     nome_Produto varchar(50) not null,
     quantidade_produto int not null,
     preco_produto decimal(7,2) not null
);

INSERT INTO produtos (nome_produto, quantidade_produto, preco_produto) VALUES
("Camiseta Estampada", 15, 49.90),
("Cafeteira Elétrica", 8, 199.99),
("Fone de Ouvido Bluetooth", 25, 149.50),
("Bolsa de Couro", 10, 229.00),
("Caderno Universitário", 50, 15.75),
("Relógio de Pulso", 12, 129.90),
("Tênis Esportivo", 20, 169.99),
("Guitarra Elétrica", 5, 799.00),
("Papel Higiênico", 200, 12.99),
("Lâmpada LED", 100, 10.50),
("Mouse Óptico", 40, 29.99),
("Cadeira Gamer", 7, 499.00),
("Câmera Fotográfica Digital", 3, 1200.00),
("Controle de Videogame", 30, 99.90),
("Sofá Retrátil", 2, 2299.99);
````
