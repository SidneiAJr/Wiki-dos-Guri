# PHP | Estrutura MVC — Sem POO vs Com POO

Este documento mostra **a estrutura MVC em PHP** de duas formas:

* 🔹 MVC **sem POO** (procedural)
* 🔹 MVC **com POO** (padrão moderno)

A ideia é **igual ao que tu fez em TS**, mudando apenas a linguagem.

---

## 🧠 Relembrando: O que é MVC?

* **Model** → dados + regras de negócio
* **View** → interface (HTML)
* **Controller** → recebe requisição e coordena tudo

Objetivo:

* separar responsabilidades
* facilitar manutenção
* permitir crescimento do projeto

---

# 🔹 MVC SEM POO (Procedural)

Usado em projetos antigos ou para entender o conceito.

## 📁 Estrutura de Pastas

```
php-mvc-sem-poo/
 ├─ index.php
 ├─ controllers/
 │   └─ usuario_controller.php
 ├─ models/
 │   └─ usuario_model.php
 └─ views/
     └─ usuarios.php
```

---

## 📦 Model (models/usuario_model.php)

```php
<?php
function listarUsuarios() {
    return [
        ['id' => 1, 'nome' => 'João'],
        ['id' => 2, 'nome' => 'Maria']
    ];
}
```

---

## 🎮 Controller (controllers/usuario_controller.php)

```php
<?php
require_once 'models/usuario_model.php';

$usuarios = listarUsuarios();
require 'views/usuarios.php';
```

---

## 🖥️ View (views/usuarios.php)

```php
<?php foreach ($usuarios as $u): ?>
    <p><?= $u['id'] ?> - <?= $u['nome'] ?></p>
<?php endforeach; ?>
```

---

## 🚪 index.php (Front Controller)

```php
<?php
require 'controllers/usuario_controller.php';
```

---

### ⚠️ Limitações do MVC sem POO

❌ Funções globais
❌ Código acoplado
❌ Difícil testar
❌ Escala mal

---

# 🔹 MVC COM POO (Padrão Profissional)

Usado em projetos modernos e frameworks.

## 📁 Estrutura de Pastas

```
php-mvc-com-poo/
 ├─ app/
 │   ├─ Controllers/
 │   │   └─ UsuarioController.php
 │   ├─ Models/
 │   │   └─ Usuario.php
 │   └─ Views/
 │       └─ usuarios.php
 ├─ public/
 │   └─ index.php
 └─ vendor/ (composer)
```

---

## 📦 Model (app/Models/Usuario.php)

```php
<?php
class Usuario {
    public function listar(): array {
        return [
            ['id' => 1, 'nome' => 'João'],
            ['id' => 2, 'nome' => 'Maria']
        ];
    }
}
```

---

## 🎮 Controller (app/Controllers/UsuarioController.php)

```php
<?php
require_once __DIR__ . '/../Models/Usuario.php';

class UsuarioController {
    public function index() {
        $model = new Usuario();
        $usuarios = $model->listar();
        require __DIR__ . '/../Views/usuarios.php';
    }
}
```

---

## 🖥️ View (app/Views/usuarios.php)

```php
<?php foreach ($usuarios as $u): ?>
    <p><?= $u['id'] ?> - <?= $u['nome'] ?></p>
<?php endforeach; ?>
```

---

## 🚪 public/index.php (Front Controller)

```php
<?php
require_once '../app/Controllers/UsuarioController.php';

$controller = new UsuarioController();
$controller->index();
```

---

## 📊 Comparação direta (PHP vs TS)

| Conceito   | PHP       | TypeScript         |
| ---------- | --------- | ------------------ |
| Controller | Classe    | Classe             |
| Model      | Classe    | Classe             |
| View       | PHP/HTML  | Template / JSON    |
| Entrada    | index.php | server.ts / app.ts |

---

## 🧠 Conclusão

* MVC **sem POO** → didático / legado
* MVC **com POO** → profissional
* A estrutura mental é **a mesma do TS backend**

👉 Mudou a linguagem, **não mudou a arquitetura**.
