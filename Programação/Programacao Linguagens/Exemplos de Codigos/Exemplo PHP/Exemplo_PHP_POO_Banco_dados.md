# PHP | Exemplo de conexção de banco de dados usando poo:

- `interface` para verificação de informações
- `classe` que recebe o contrato com a interface via includes

```php
<?php

interface VerificarBanco {
    public function banco();
    public function acesso();
    public function testar_banco();
}

class Banco implements VerificarBanco {

    private string $nomebanco;
    private string $user;
    private string $password;
    private string $porta;
    private string $host;

    public function __construct(string $nomebanco, string $user, string $password, string $porta, string $host = "localhost")
    {
        $this->nomebanco = $nomebanco;
        $this->user = $user;
        $this->password = $password;
        $this->porta = $porta;
        $this->host = $host;
    }

    public function banco()
    {
        if ($this->nomebanco === "") {
            echo "Banco não encontrado!" . PHP_EOL;
            return false;
        } 
        
        echo "Banco encontrado: {$this->nomebanco}" . PHP_EOL;
        return true;
    }

    public function acesso()
    {
        if ($this->user === "" || $this->password === "") {
            echo "Erro: informe usuário e senha!" . PHP_EOL;
            return false;
        } 
        
        echo "Acesso OK — usuário informado." . PHP_EOL;
        return true;
    }

    public function testar_banco()
    {
        // Verifica credenciais
        if (!$this->banco() || !$this->acesso()) {
            return false;
        }

        // Tenta conexão
        $con = new mysqli($this->host, $this->user, $this->password, $this->nomebanco, (int)$this->porta);

        if ($con->connect_error) {
            error_log("Erro de conexão: " . $con->connect_error);
            echo "Erro interno. Tente novamente mais tarde." . PHP_EOL;
            return false;
        }

        $con->set_charset("utf8mb4");

        echo "Conectado ao banco com sucesso!" . PHP_EOL;

        return $con; // retorna conexão (profissional)
    }

    private function limparEntrada(string $valor): string
    {
        return htmlspecialchars(trim($valor), ENT_QUOTES, 'UTF-8');
    }
}

?>
```