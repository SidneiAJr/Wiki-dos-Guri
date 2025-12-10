# PHP | Passando Variáveis (GET, POST e Validação)

Quando trabalhamos com formulários ou URLs no PHP, precisamos receber, validar e usar as variáveis enviadas pelo navegador.

## No PHP, existem três formas mais comuns de receber dados:

`$_GET → pega dados enviados na URL`

`$_POST → pega dados enviados por formulário`


## `Recebendo uma variável com POST`

```php
$nome = $_POST["nome"];  // "nome" é o atributo name="" do input HTML
```

```html
<form action="recebe.php" method="POST">
    <input type="text" name="nome" />
    <button type="submit">Enviar</button>
</form>
```

```php
$nome = $_POST["nome"];
echo "Nome recebido: $nome";
```

## `Verificando se a variável está vazia` 

```php
if (empty($nome)) {
    echo "O campo nome não pode ficar vazio!";
} else {
    echo "Segue o baile! Valor recebido: $nome";
}
```

## Exemplo completo (RECEBER + VALIDAR)

```php
if (isset($_POST["nome"])) {

    $nome = $_POST["nome"];

    if (empty($nome)) {
        echo "O campo nome é obrigatório!";
    } else {
        echo "Nome recebido com sucesso: $nome";
    }

} else {
    echo "Nenhuma variável foi enviada.";
}
```

| Tipo      | Como recebe        | Exemplo   | Quando usar     |
| --------- | ------------------ | --------- | --------------- |
| `$_GET`   | pela URL           | ?id=10    | buscas, filtros |
| `$_POST`  | formulário         | POST      | login, cadastro |
| `empty()` | verifica vazio     | empty($x) | validação       |
| `isset()` | verifica se existe | isset($x) | segurança       |



