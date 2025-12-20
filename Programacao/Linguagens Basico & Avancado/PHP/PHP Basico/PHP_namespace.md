# 🧩 PHP | Namespace

## O que é Namespace?

Namespace é uma forma de **organizar classes, funções e constantes** no PHP para **evitar conflito de nomes**.

Ele funciona como um **sobrenome** para as classes.

Em vez de existir apenas uma classe `Usuario`, você pode ter:
- `App\Models\Usuario`
- `App\Controllers\Usuario`

Mesmo nome, **lugares diferentes**.

---

## Por que Namespace existe?

Sem namespace:
- Tudo fica no mesmo espaço
- Classes com o mesmo nome entram em conflito
- O código vira bagunça em projetos grandes

Com namespace:
- Código organizado
- Sem conflito de nomes
- Base para MVC, autoload e frameworks

📌 Namespace é essencial em PHP moderno.

---

## Exemplo SEM Namespace (problema)

```php
<?php

class Usuario {
    public function nome() {
        return "Usuário do sistema";
    }
}

class Usuario {
    public function nome() {
        return "Usuário do admin";
    }
}

// ❌ Isso gera erro, pois duas classes têm o mesmo nome.
```

## Exemplo COM Namespace (solução)
```php
<?php

namespace App\Models;

class Usuario {
    public function nome() {
        return "Usuário do Model";
    }
}
<?php

namespace App\Controllers;

class Usuario {
    public function nome() {
        return "Usuário do Controller";
    }
}

```
