# 🧱 CRUD no MVC — Explicação Mastigada
## O que é CRUD?
* CRUD representa as 4 operações básicas de qualquer sistema backend:
* Letra	Nome	O que faz
* C	Create	Criar dados
* R	Read	Ler dados
* U	Update	Atualizar dados
* D	Delete	Apagar dados
* 👉 Se tem banco de dados, tem CRUD.

* 📍 Onde o CRUD fica no MVC?
* CRUD não fica em um arquivo só.
* Ele é dividido por responsabilidade.

# 🧠 Model (Regra de Negócio + Banco)
* O Model é quem executa o CRUD de verdade.
* Ele:
### `Conversa com o banco:`
* Executa SQL
* Valida regras de negócio
* Retorna dados
* Exemplo de responsabilidades do Model:
* createUser()
* getUserById()
* updateUser()
* deleteUser()

### 📌 `Model NÃO sabe quem é o usuário e não mostra nada na tela.`
* 🎮 Controller (Orquestrador)
* O Controller é quem manda o Model trabalhar.
* Ele:
* Recebe a requisição
* Valida dados simples (campos vazios)
* Chama o Model
* Decide a resposta

### 📌 Controller NÃO faz SQL.
* 🎨 View (Apresentação)
* A View só mostra o resultado.
* Ela:
* Exibe dados
* Renderiza HTML ou JSON
* Não contém regra de negócio
* 📌 View NÃO fala com banco.

## Fluxo do CRUD no MVC
```bash
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

## CRUD NA PRÁTICA (Fluxo Mental)

### CREATE (Criar)
```bash
Formulário
   ↓
Controller (recebe dados)
   ↓
Model (INSERT no banco)
   ↓
Controller (ok ou erro)
   ↓
View (mensagem)
```

### READ (Ler)
```bash
Usuário pede dados
   ↓
Controller
   ↓
Model (SELECT)
   ↓
Controller
   ↓
View (lista dados)
```

### UPDATE (Atualizar)
```bash
Formulário de edição
   ↓
Controller
   ↓
Model (UPDATE)
   ↓
Controller
   ↓
View (confirmação)
```

### DELETE (Excluir)
```bash
Clique em excluir
   ↓
Controller
   ↓
Model (DELETE)
   ↓
Controller
   ↓
View (mensagem)
```

## Exemplo de Estrutura MVC com CRUD
```bash
/app
 ├── Controllers
 │    └── UserController.php
 │
 ├── Models
 │    └── User.php
 │
 ├── Views
 │    └── user
 │         ├── list.php
 │         ├── create.php
 │         └── edit.php
 │
 └── Core
      └── Database.php
```

