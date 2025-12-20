# 🧱 MVC em TypeScript — Arquitetura

## O que é MVC?

MVC significa:

Model – View – Controller

No TypeScript, MVC é muito usado em:
- APIs (Node.js)
- Backends REST
- Express / Fastify / Nest (conceito)

---

## 📍 Quem é quem no MVC?

Camada | Responsabilidade
------ | ----------------
Model | Dados e regras de negócio
View | Resposta (JSON / HTML)
Controller | Controle das requisições

---

## 🧠 Model (TypeScript)

O Model:
- Representa entidades
- Acessa banco (ORM ou query)
- Aplica regras de negócio
- Não conhece HTTP

Exemplos:
- User.ts
- Produto.ts

---

## 🎨 View (TypeScript)

Em APIs, a View geralmente é:
- JSON
- Status HTTP

Ela:
- Apenas devolve dados
- Não faz regra de negócio

---

## 🎮 Controller (TypeScript)

O Controller:
- Recebe requisições HTTP
- Lê body, params, query
- Chama o Model
- Retorna resposta

Exemplos:
- UserController.ts

---

## 🔁 Fluxo MVC em TypeScript

Cliente  
↓  
Controller  
↓  
Model  
↓  
Controller  
↓  
View (JSON)  
↓  
Cliente  

---

## 🧱 Estrutura de Pastas (TypeScript)

src/
├── controllers
│   └── UserController.ts
├── models
│   └── User.ts
├── views
│   └── response.ts
└── core
    └── database.ts

---

## ✅ Regra de Ouro

Controller coordena  
Model executa  
View responde
