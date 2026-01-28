# PHP | MVC — Com POO vs Sem POO

Este documento explica **MVC em PHP** de duas formas:

* ✅ MVC **com POO** (padrão profissional)
* ⚠️ MVC **sem POO** (didático / legado)

Assim tu entende **a evolução**, não só o final.

---

## O que é MVC?

**MVC (Model–View–Controller)** é um padrão arquitetural que separa responsabilidades:

* **Model** → regra de negócio e dados
* **View** → interface (HTML)
* **Controller** → coordena Model e View

Objetivo:

* código organizado
* fácil manutenção
* separação de responsabilidades

---

# 🧱 MVC SEM POO (Procedural)

⚠️ Usado em projetos antigos ou estudos iniciais.

## Estrutura

```
mvc_sem_poo/
 ├─ index.php
 ├─ controller.php
 ├─ model.php
 └─ view.php
```

---

## model.php

```php
<?php
function buscarUsuarios() {
    return [
        ['nome' => 'João', 'email' => 'joao@email.com'],
        ['nome' => 'Maria', 'email' => 'maria@email.com']
    ];
}
```

---

## controller.php

```php
<?php
require 'model.php';

$usuarios = buscarUsuarios();
require 'view.php';
```

---

## view.php

```php
<?php foreach ($usuarios as $u): ?>
  <p><?= $u['nome'] ?> - <?= $u['email'] ?></p>
<?php endforeach; ?>
```

---

## index.php

```php
<?php
require 'controller.php';
```

---

### Problemas do MVC sem POO

❌ Funções globais
❌ Difícil de escalar
❌ Testes quase impossíveis
❌ Código acoplado

---

# 🧠 MVC COM POO (Padrão Profissional)

✅ Forma usada no mercado (Laravel, Symfony).

## Estrutura

```
mvc_com_poo/
 ├─ app/
 │   ├─ Controllers/
 │   │   └─ UsuarioController.php
 │   ├─ Models/
 │   │   └─ Usuario.php
 │   └─ Views/
 │       └─ usuarios.php
 └─ public/
     └─ index.php
```

---

## Model (Usuario.php)

```php
<?php
class Usuario {
    public function listar() {
        return [
            ['nome' => 'João', 'email' => 'joao@email.com'],
            ['nome' => 'Maria', 'email' => 'maria@email.com']
        ];
    }
}
```

---

## Controller (UsuarioController.php)

```php
<?php
require_once '../Models/Usuario.php';

class UsuarioController {
    public function index() {
        $model = new Usuario();
        $usuarios = $model->listar();
        require '../Views/usuarios.php';
    }
}
```

---

## View (usuarios.php)

```php
<?php foreach ($usuarios as $u): ?>
  <p><?= $u['nome'] ?> - <?= $u['email'] ?></p>
<?php endforeach; ?>
```

---

## index.php (Front Controller)

```php
<?php
require '../app/Controllers/UsuarioController.php';

$controller = new UsuarioController();
$controller->index();
```

---

## Vantagens do MVC com POO

✅ Código organizado
✅ Fácil manutenção
✅ Escalável
✅ Testável
✅ Base de frameworks modernos

---

## Comparação direta

| MVC sem POO     | MVC com POO         |
| --------------- | ------------------- |
| Procedural      | Orientado a Objetos |
| Difícil escalar | Escalável           |
| Código acoplado | Separação clara     |
| Legado          | Profissional        |

---

## Quando usar cada um?

* **Sem POO** → estudo inicial / legado
* **Com POO** → projetos reais

---

## Conclusão

MVC **sem POO** ajuda a entender o conceito.
MVC **com POO** é o que o mercado usa.

👉 Todo framework PHP moderno é MVC + POO.
