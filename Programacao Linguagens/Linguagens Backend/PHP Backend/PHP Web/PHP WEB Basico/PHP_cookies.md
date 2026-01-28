# PHP | Cookies:

## O que é um Cookie?

Um cookie é um pequeno arquivo de dados que é armazenado no computador do usuário e enviado ao servidor com cada requisição. Os cookies podem ser usados para armazenar informações sobre o usuário, como preferências ou status de login.

### Criando um Cookie
```php
// Cria um cookie que expira em 30 dias
setcookie("usuario", "João", time() + (86400 * 30), "/"); // O '/' significa que o cookie estará disponível em todo o domínio
```

### Lendo um Cookie
```php
if (isset($_COOKIE['usuario'])) {
    echo "Bem-vindo, " . $_COOKIE['usuario']; // Exibe o valor do cookie
} else {
    echo "Cookie não encontrado!";
}
```

### Atualizando um Cookie
```php
setcookie("usuario", "Maria", time() + (86400 * 30), "/"); // Atualiza o cookie
```

### Deletando um Cookie
```php
setcookie("usuario", "", time() - 3600, "/"); // Exclui o cookie
```

### 🧱 Diferenças entre Sessões e Cookies

| Característica     | **Sessões**                                     | **Cookies**                                                |
| ------------------ | ----------------------------------------------- | ---------------------------------------------------------- |
| **Armazenamento**  | Armazenado no servidor (mais seguro)            | Armazenado no navegador do cliente                         |
| **Tempo de Vida**  | Persiste enquanto a sessão estiver ativa        | Pode expirar ou ser permanente                             |
| **Capacidade**     | Limitação depende do servidor                   | Limitado pelo navegador (geralmente 4KB)                   |
| **Segurança**      | Mais seguro (não exposto ao cliente)            | Menos seguro (pode ser acessado e manipulado pelo cliente) |
| **Acessibilidade** | Disponível em todas as páginas durante a sessão | Disponível no navegador durante o tempo de vida do cookie  |


### 🛠️ Boas Práticas

Uso seguro de cookies: Sempre use a flag HttpOnly para evitar que cookies sejam acessados via JavaScript. Se for um cookie sensível, também use Secure para garantir que o cookie só será enviado via HTTPS.

```php
setcookie("usuario", "João", time() + (86400 * 30), "/", "", true, true); // Usando flags Secure e HttpOnly
```
