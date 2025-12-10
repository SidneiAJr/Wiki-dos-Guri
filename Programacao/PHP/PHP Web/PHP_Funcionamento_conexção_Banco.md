# PHP | Funcionamento de Banco de Dados e Variáveis

No PHP, existem duas formas principais de fazer conexão com banco de dados:

- Programação Estruturada (Procedural)

- POO (Programação Orientada a Objetos)

Ambas funcionam, mas a forma POO é mais moderna e recomendada.

## `Variáveis Básicas de Conexão`

```php
$host     = "localhost";   // Servidor do banco
$banco    = "Nome_Banco";  // Nome do banco de dados
$user     = "Usuario";     // Usuário do banco
$password = "Senha_banco"; // Senha do banco
```

## `Conexão Procedural (mysqli_connect)`

`Forma clássica, muito usada em PHP antigo.`

- ✔ Fácil

- ✔ Amplamente compatível

```php
$host     = "localhost";
$banco    = "Nome_Banco";
$user     = "Usuario";
$password = "Senha_banco";

$conexao = mysqli_connect($host, $user, $password, $banco);

if(!$conexao){
    die("Erro ao conectar: " . mysqli_connect_error());
}
```

## Conexão com PDO (A melhor e mais moderna)

- Suporta vários bancos (MySQL, SQLite, PostgreSQL…)

- Mais seguro

- Melhor tratamento de erros

- Permite prepared statements avançados

```php
$host     = "localhost";
$banco    = "Nome_Banco";
$user     = "Usuario";
$password = "Senha_banco";

try {
    $conexao = new PDO("mysql:host=$host;dbname=$banco;charset=utf8", $user, $password);
    $conexao->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

} catch (PDOException $erro) {
    echo "Erro na conexão: " . $erro->getMessage();
}
```

## Resumo Comparativo

| Estilo            | Fácil | Seguro | Moderno | Ideal para                    |
| ----------------- | ----- | ------ | ------- | ----------------------------- |
| mysqli procedural | ✔     | ❌      | ❌       | sistemas antigos, técnicos    |
| mysqli OOP        | ✔     | ✔      | ✔       | projetos médios               |
| PDO               | ✔     | ✔✔✔    | ✔✔✔     | qualquer sistema profissional |


## Formulario(Get & POST):

## GET vs POST
- `$_GET`: usado para parâmetros na URL (ex: excluir?id=3)
- `$_POST`: usado para formulários sensíveis (ex: login)
- `$_SESSION`: guarda dados temporários de login e controle de acesso

