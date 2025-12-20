# PHP | Tutorial de Conexão de Banco de Dados

Para começar a trabalhar com PHP e banco de dados, você deve ter um servidor local como **XAMPP**, **WAMP** ou qualquer outra ferramenta que possibilite rodar PHP. Depois, siga os seguintes passos:

---

## 🛠️ Configuração do Ambiente

1. **Instale o XAMPP ou WAMP**: Faça o download e instale o XAMPP ou WAMP, que já vêm com o PHP e o MySQL prontos para uso.

2. **Crie o arquivo de conexão**: Crie um arquivo PHP chamado `conexao.php`, onde vamos definir a conexão com o banco de dados.

3. **Defina as variáveis de conexão**: No arquivo `conexao.php`, defina os parâmetros necessários para se conectar ao banco.

---

## 📄 Exemplo de Código para Conexão com Banco de Dados

### Definição das Variáveis de Conexão

```php
$host = 'localhost'; // Host do banco
$db   = 'meu_banco'; // Nome do banco
$user = 'root'; // Usuário do banco
$pass = 'minha_senha'; // Senha do banco
$charset = 'utf8mb4'; // Charset para garantir a codificação correta
````

### Explicação do Código:

- $dsn: O Data Source Name (DSN) contém as informações necessárias para conectar ao banco de dados, incluindo o host (localhost), nome do banco e charset.

- new PDO(): Cria uma nova instância do PDO (PHP Data Object), responsável pela conexão com o banco de dados. Ele recebe o DSN, o usuário e a senha do banco.

- $pdo->setAttribute(): Define atributos para a conexão, neste caso, configuramos para lançar exceções em caso de erro.

- try/catch: Usado para tratar possíveis erros de conexão. Caso a conexão falhe, a mensagem de erro será exibida.

### 🔒 Boas Práticas de Conexão com Banco de Dados

- Use PDO (PHP Data Object): PDO é mais flexível e seguro, pois permite o uso de prepared statements, prevenindo SQL Injection.

- Evite armazenar senhas em texto claro: Sempre use funções como password_hash() para armazenar senhas de forma segura.

- Utilize try/catch para tratamento de exceções: Sempre trate erros de conexão para evitar vazamento de informações sensíveis.

### 🧱 Diferenças entre PDO e MySQLi

| Característica                 | PDO                                                         | MySQLi                        |
| ------------------------------ | ----------------------------------------------------------- | ----------------------------- |
| **Suporte a múltiplos bancos** | ✅ Suporta diversos bancos (MySQL, SQLite, PostgreSQL, etc.) | ❌ Suporta apenas MySQL        |
| **Preparação de Consultas**    | ✅ Suporta prepared statements                               | ✅ Suporta prepared statements |
| **Orientação a Objetos**       | ✅ Sim                                                       | ✅ Sim                         |
| **Procedural**                 | ❌ Não                                                       | ✅ Sim                         |
