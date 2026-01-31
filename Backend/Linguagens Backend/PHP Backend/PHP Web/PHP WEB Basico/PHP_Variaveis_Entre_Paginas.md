# PHP | Formas de Passar Variáveis Entre Páginas

### `GET – pela URL`

### `POST – via formulário`

### `SESSION – variáveis temporárias de login`

### `COOKIE – gravadas no navegador por dias/semanas`

```php
$usuario = $_GET["usuario"];
$id      = $_GET["id"];

echo "Usuário: $usuario | ID: $id";
````

````html
<form action="cadastro.php" method="POST">
    <input type="text" name="nome">
    <button type="submit">Enviar</button>
</form>
````

````php
$nome = $_POST["nome"];
echo "Nome recebido: $nome";

````

## Passando Variáveis com SESSION (`Login, Permissões, Painéis`)

````php
//Criando sessão
session_start();
//Lendo sessão em outra página
$_SESSION["usuario"] = "Pedro";
session_start();
echo $_SESSION["usuario"];
//Apagar sessão (Logout)
session_start();
session_destroy();
````

## Passando Variáveis com COOKIE

````php
setcookie("tema", "dark", time() + 3600); // dura 1 hora
echo $_COOKIE["tema"];
setcookie("tema", "", time() - 3600);
````

## Diferença Geral (Resumo)

| Método  | Duração              | Segurança   | Onde fica           | Usado em       |
| ------- | -------------------- | ----------- | ------------------- | -------------- |
| GET     | até carregar página  | baixa       | URL                 | filtros, busca |
| POST    | só no envio          | média       | corpo da requisição | formulários    |
| SESSION | até fechar navegador | alta        | servidor            | login, painel  |
| COOKIE  | dias/meses           | média/baixa | navegador           | preferências   |


## Página A – formulário (POST)

````html
<form action="pg2.php" method="POST">
    <input type="text" name="nome">
    <button>Enviar</button>
</form>
````

## Página B – recebe POST e cria SESSION

````php
session_start();

$nome = $_POST["nome"];
$_SESSION["nome"] = $nome;

header("Location: pg3.php");
````

## Página C – pega da sessão

````php
session_start();
echo "Bem-vindo, " . $_SESSION["nome"];
````


