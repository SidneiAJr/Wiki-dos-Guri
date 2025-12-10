# PHP | Sessão Web PHP

# PHP | Manejo de Sessões e Cookies

Neste tutorial, vamos aprender a trabalhar com **sessões** e **cookies** em PHP. Ambos são importantes para manter dados persistentes durante a navegação do usuário, como informações de login ou preferências.

---

## 🧑‍💻 **Sessões em PHP**

### O que é uma Sessão?

Uma **sessão** é usada para armazenar informações sobre o usuário enquanto ele navega por várias páginas. As sessões permitem que você armazene variáveis que podem ser acessadas em diferentes páginas, sem precisar passá-las pela URL.

### 1. **Iniciando uma Sessão**

Para começar a usar sessões em PHP, você precisa chamar `session_start()` no início de cada página onde você deseja acessar ou armazenar dados da sessão.

```php
session_start(); // Inicia a sessão ou retoma a sessão existente
```

### Armazenando Dados em Sessão
```php
session_start(); // Inicia a sessão

$_SESSION['nome'] = 'João'; // Armazena o nome do usuário na sessão
$_SESSION['email'] = 'joao@exemplo.com'; // Armazena o e-mail do usuário
```
### Acessando Dados da Sessão
```php
session_start(); // Inicia a sessão

echo "Nome: " . $_SESSION['nome']; // Exibe o nome armazenado na sessão
echo "E-mail: " . $_SESSION['email']; // Exibe o e-mail armazenado na sessão
```
### Destruindo Sessões
```php
session_start();
session_unset();  // Remove todas as variáveis de sessão
session_destroy();  // Destroi a sessão
```


