# 🧱 MVC em PHP — Arquitetura

## O que é MVC?

MVC significa:

Model – View – Controller

No PHP, MVC é muito usado em sistemas web tradicionais e APIs.

Ele separa:
- Regra de negócio
- Controle da aplicação
- Apresentação

---

## 📍 Quem é quem no MVC?

Camada | Responsabilidade
------ | ----------------
Model | Dados e regras de negócio
View | Apresentação (HTML)
Controller | Orquestra o fluxo

---

## 🧠 Model (PHP)

O Model:
- Acessa o banco de dados (PDO, MySQLi)
- Executa SQL
- Aplica regras de negócio
- Não sabe nada sobre HTML

Exemplos:
- User.php
- Produto.php

---

## 🎨 View (PHP)

A View:
- Renderiza HTML
- Mostra dados
- Não acessa banco
- Não contém regra de negócio

Exemplos:
- listar.php
- editar.php

---

## 🎮 Controller (PHP)

O Controller:
- Recebe requisições HTTP
- Lê GET e POST
- Chama o Model
- Decide qual View mostrar

Exemplos:
- UserController.php

---

## 🔁 Fluxo MVC no PHP

Usuário  
↓  
Controller  
↓  
Model  
↓  
Controller  
↓  
View  
↓  
Usuário  

---

## 🧱 Estrutura de Pastas (PHP)

app/
├── Controllers
│   └── UserController.php
├── Models
│   └── User.php
├── Views
│   └── user
│       ├── listar.php
│       └── editar.php
└── Core
    └── Database.php

---

## ✅ Regra de Ouro

Controller decide  
Model trabalha  
View mostra
