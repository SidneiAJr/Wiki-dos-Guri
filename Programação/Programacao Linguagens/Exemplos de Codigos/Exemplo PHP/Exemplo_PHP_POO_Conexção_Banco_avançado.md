# Exemplo PHP | POO | Conexção Banco

````php
<?php

interface VerificarBanco {
    public function banco(): bool;            // Verifica se o banco existe
    public function acesso(): bool;           // Verifica se as credenciais estão corretas
    public function testar_banco(): ?mysqli;  // Testa a conexão com o banco
}

class Banco implements VerificarBanco {

    private string $nomebanco;
    private string $user;
    private string $password;
    private string $porta;
    private string $host;
    private ?mysqli $conexao = null; // A conexão será armazenada aqui

    // Construtor para configurar os dados do banco
    public function __construct(string $nomebanco, string $user, string $password, string $porta, string $host = "localhost")
    {
        $this->nomebanco = $this->limparEntrada($nomebanco);
        $this->user = $this->limparEntrada($user);
        $this->password = $this->limparEntrada($password);
        $this->porta = $this->limparEntrada($porta);
        $this->host = $host;  // O host pode ser diferente, caso seja necessário
    }

    // Verifica se o nome do banco foi informado corretamente
    public function banco(): bool
    {
        if (empty($this->nomebanco)) {
            echo "Banco não encontrado!" . PHP_EOL;
            return false;
        } 
        echo "Banco encontrado: {$this->nomebanco}" . PHP_EOL;
        return true;
    }

    // Verifica se o usuário e senha foram informados corretamente
    public function acesso(): bool
    {
        if (empty($this->user) || empty($this->password)) {
            echo "Erro: usuário ou senha não informados!" . PHP_EOL;
            return false;
        }
        echo "Acesso OK — usuário informado." . PHP_EOL;
        return true;
    }

    // Testa a conexão ao banco de dados
    public function testar_banco(): ?mysqli
    {
        // Verifica se as credenciais e banco estão corretos
        if (!$this->banco() || !$this->acesso()) {
            return null;
        }

        // Tentando conectar ao banco
        $con = new mysqli($this->host, $this->user, $this->password, $this->nomebanco, (int)$this->porta);

        // Verifica se houve erro na conexão
        if ($con->connect_error) {
            error_log("Erro de conexão: " . $con->connect_error);
            echo "Erro interno. Tente novamente mais tarde." . PHP_EOL;
            return null;
        }

        // Configura o charset para UTF-8, evitando problemas com codificação
        $con->set_charset("utf8mb4");

        echo "Conectado ao banco com sucesso!" . PHP_EOL;
        return $con; // Retorna a conexão
    }

    // Limpa e sanitiza entradas para evitar ataques como XSS
    private function limparEntrada(string $valor): string
    {
        // Escapa os caracteres especiais para evitar XSS
        return htmlspecialchars(trim($valor), ENT_QUOTES, 'UTF-8');
    }

    // Exemplo de como usar prepared statements para segurança
    public function verificarUsuario(string $usuario, string $senha): bool
    {
        // Testa a conexão
        $con = $this->testar_banco();

        if ($con) {
            // Prepara a consulta SQL com parâmetro de segurança
            $sql = "SELECT id, nome, senha FROM usuarios WHERE usuario = ?";
            $stmt = $con->prepare($sql);

            // Verifica se a preparação foi bem-sucedida
            if ($stmt === false) {
                echo "Erro ao preparar a consulta: " . $con->error . PHP_EOL;
                return false;
            }

            // Vincula o parâmetro (usuario)
            $stmt->bind_param("s", $usuario);

            // Executa a consulta
            $stmt->execute();

            // Obtém o resultado da consulta
            $resultado = $stmt->get_result();

            // Verifica se algum usuário foi encontrado
            if ($resultado->num_rows > 0) {
                // Recupera os dados do usuário
                $linha = $resultado->fetch_assoc();

                // Verifica se a senha fornecida é válida
                if (password_verify($senha, $linha['senha'])) {
                    echo "Usuário autenticado com sucesso!" . PHP_EOL;
                    return true;
                } else {
                    echo "Senha incorreta!" . PHP_EOL;
                    return false;
                }
            } else {
                echo "Usuário não encontrado!" . PHP_EOL;
                return false;
            }
        }
        return false;
    }
}
?>
````
