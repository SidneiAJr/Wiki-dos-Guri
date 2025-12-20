# MVC | Arquitetura

## O que é MVC?

MVC (Model–View–Controller) é um **padrão de arquitetura de software** que separa responsabilidades dentro de uma aplicação.

Ele não é uma linguagem, não é framework e não é regra absoluta. É um **jeito de organizar o código** para evitar bagunça, acoplamento excessivo e dor de cabeça no futuro.

A ideia central é simples:

> **Cada parte do sistema tem uma responsabilidade clara.**

---

## Como funciona?

O MVC divide a aplicação em três camadas principais:

### 🧠 Model (Modelo)

Responsável pela **regra de negócio** e **dados**.

O Model:

* Conversa com o banco de dados
* Valida dados (em nível de negócio)
* Aplica regras do sistema
* Não sabe nada sobre HTML, tela ou usuário

Exemplos de responsabilidade:

* Cadastrar usuário
* Calcular valores
* Validar permissões
* Executar consultas SQL

---

### 🎨 View (Visão)

Responsável pela **apresentação**.

A View:

* Mostra dados para o usuário
* Recebe ações (cliques, formulários)
* Não contém regra de negócio

Pode ser:

* HTML
* Templates
* JSON (em APIs)
* Interfaces gráficas

---

### 🎮 Controller (Controlador)

Responsável por **orquestrar** tudo.

O Controller:

* Recebe a requisição
* Chama o Model
* Decide qual View será exibida
* Não executa regra pesada

Ele é o **meio de campo** do sistema.

---

## Fluxo MVC (Passo a Passo)

1. O usuário faz uma requisição
2. A requisição chega no **Controller**
3. O Controller chama o **Model**
4. O Model processa os dados
5. O resultado volta ao Controller
6. O Controller envia os dados para a **View**
7. A View responde ao usuário

Visualmente:

```
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
```

---

## Estrutura de Projetos

Um exemplo simples de estrutura MVC:

```
/app
 ├── Controllers
 │    └── UsuarioController.php
 │
 ├── Models
 │    └── Usuario.php
 │
 └── Views
      └── usuario
           └── listar.php
```

### Controllers

* Lidam com rotas
* Recebem requisições
* Chamam Models
* Retornam Views

### Models

* Representam entidades
* Contêm regras de negócio
* Lidam com banco de dados

### Views

* Exibem dados
* Não fazem lógica complexa
* Apenas apresentação

---

## O que MVC NÃO é

MVC **não é**:

* Framework
* Obrigatório
* Solução para tudo
* Regra fixa

MVC é um **ponto de partida**, não um fim.

---

## Problemas comuns em MVC mal feito

* ❌ Controller gordo (muita regra dentro)
* ❌ Model fazendo HTML
* ❌ View com SQL
* ❌ Mistura total de responsabilidades

Quando isso acontece, o problema **não é o MVC**, é a implementação.

---

## Quando usar MVC?

* ✔️ Sistemas web
* ✔️ APIs
* ✔️ Sistemas médios e grandes
* ✔️ Projetos que precisam crescer

Para projetos muito pequenos, MVC pode ser exagero.

---
