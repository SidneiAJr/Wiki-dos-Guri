# PHP | Projeto estudo | CRUD - Json

## Criando a conexção com Banco:
```php
<?php
// Conexão com o banco de dados
$host = 'localhost';
$user = 'root';
$password = 'root';
$database = 'pokedex';
$conn = new mysqli($host, $user, $password, $database);
if ($conn->connect_error) {
    die("Falha na conexão com o banco de dados: " . $conn->connect_error);
}
header("Content-Type: application/json");

$request_method = $_SERVER["REQUEST_METHOD"];
```

## Switch de Rotas:
```php
// Rotas
switch ($request_method) {
    case 'POST':
        inserirPokemon($conn);
        break;
    case 'GET':
        if (isset($_GET['id'])) {
            listarPokemonPorId($conn);
        } else {
            listarPokemons($conn);
        }
        break;
    case 'DELETE':
        deletarPokemon($conn);
        break;
    case 'PUT':
        atualizarPokemon($conn);
        break;
    default:
        echo json_encode(["message" => "Método não permitido"]);
        break;
}
```
## Função para Inserir Pokemon:
```php
function inserirPokemon($conn) {
    $data = json_decode(file_get_contents("php://input"));

    $nome_pokemon = $data->nome_pokemon;
    $tipo_pokemon = $data->tipo_pokemon;
    $tem_evolucao = $data->tem_evolucao;

    $query = "INSERT INTO pokemons (nome_pokemon, tipo_pokemon, tem_evolucao) VALUES ('$nome_pokemon', '$tipo_pokemon', '$tem_evolucao')";
    if ($conn->query($query) === TRUE) {
        echo json_encode(["message" => "Pokémon inserido com sucesso"]);
    } else {
        echo json_encode(["message" => "Erro ao inserir Pokémon"]);
    }
}
````
