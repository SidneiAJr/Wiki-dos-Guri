# PHP | 📘 Sistema de Login em PHP (Interface + Classe Abstrata + PDO)

### Este projeto demonstra um exemplo completo e bem estruturado de orientação a objetos em PHP, utilizando:

- ✔ Interface
- ✔ Classe abstrata
- ✔ PDO com Prepared Statements
- ✔ Herança
- ✔ Sessão
- ✔ Autenticação segura

```php
<?php

// 🔹 INTERFACE
// Uma interface serve para definir um "contrato" que as classes devem seguir.
// Ou seja, qualquer classe que implementar essa interface será obrigada a ter o método Login().
interface VerificarInformacao {
    // Método obrigatório: toda classe que implementar essa interface
    // precisa ter uma função chamada Login que receba usuário e senha.
    public function Login($usuario, $senha);
}



// 🔹 CLASSE ABSTRATA
// Uma classe abstrata serve de base para outras classes herdarem.
// Ela pode ter atributos, construtores e até métodos prontos,
// mas não pode ser instanciada diretamente (ou seja, não dá pra fazer new UsuarioBase()).
abstract class UsuarioBase implements VerificarInformacao {
    
    // Propriedade protegida — será usada pelas classes filhas.
    // Aqui guardamos a conexão com o banco de dados (objeto PDO).
    protected $pdo;

    // Construtor — executado automaticamente quando a classe é instanciada.
    // Ele cria uma conexão com o banco de dados MySQL usando PDO.
    public function __construct() {
        // Dados de configuração do banco (poderiam vir de um arquivo separado)
        $host = "localhost";     // Servidor do banco de dados
        $dbname = "banco_teste"; // Nome do banco
        $usuario = "root";       // Usuário do banco
        $senha = "";             // Senha (vazia por padrão no XAMPP)

        try {
            // Cria o objeto PDO e guarda na variável $pdo
            // O charset=utf8 garante que acentos e caracteres especiais funcionem corretamente
            $this->pdo = new PDO("mysql:host=$host;dbname=$dbname;charset=utf8", $usuario, $senha);

            // Configura o modo de erro para exceção (mostra mensagens de erro mais claras)
            $this->pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

        } catch (PDOException $e) {
            // Se a conexão falhar, o script é encerrado e mostra a mensagem de erro
            die("Erro ao conectar: " . $e->getMessage());
        }
    }
}



// 🔹 CLASSE CONCRETA
// Essa classe herda tudo da classe abstrata (inclusive a conexão com o banco).
// Aqui é onde o método Login() realmente é implementado, conforme exigido pela interface.
class Usuario extends UsuarioBase {

    // Implementação do método obrigatório da interface VerificarInformacao
    public function Login($usuario, $senha) {
        
        // Cria o comando SQL para buscar um usuário com nome e senha correspondentes.
        // Os dois pontos (:) são placeholders usados com PDO para evitar SQL Injection.
        $sql = "SELECT * FROM usuarios WHERE nome = :usuario AND senha = :senha";

        // Prepara a consulta (segura e eficiente)
        $stmt = $this->pdo->prepare($sql);

        // Substitui os placeholders pelos valores reais
        $stmt->bindParam(":usuario", $usuario);
        $stmt->bindParam(":senha", $senha);

        // Executa o comando SQL no banco
        $stmt->execute();

        // Verifica se encontrou algum registro correspondente
        if ($stmt->rowCount() > 0) {
            // Se encontrou, pega os dados da linha (como nome, id, etc.)
            $dados = $stmt->fetch(PDO::FETCH_ASSOC);

            // Inicia uma sessão para armazenar informações do usuário logado
            session_start();
            $_SESSION["usuario"] = $dados["nome"];

            // Exibe mensagem de sucesso
            echo "✅ Bem-vindo, " . $dados["nome"];
        } else {
            // Caso nenhum usuário seja encontrado, exibe erro
            echo "❌ Usuário ou senha incorretos.";
        }
    }
}

// 🔹 EXEMPLO DE USO
// Aqui criamos um objeto da classe Usuario (que já conecta ao banco automaticamente)
$login = new Usuario();

// Chamamos o método Login passando o nome e a senha para testar a autenticação.
$login->Login("s", "1234");

?>
````

## Pontos do Sistema:

| Recurso             | Benefício                     |
| ------------------- | ----------------------------- |
| Interface           | Padronização                  |
| Classe Abstrata     | Reutilização de código        |
| PDO                 | Segurança e desempenho        |
| Try/Catch           | Tratamento de erros           |
| Prepared Statements | Proteção contra SQL Injection |
| Sessão              | Login persistente             |
| OOP                 | Código limpo e organizado     |



