# 🧠 MVC — QUEM FAZ O QUÊ 
## Ideia central
Cada parte do sistema tem UMA responsabilidade.
- Se cada parte faz só o que deve, o sistema fica:
- fácil de entender
- fácil de arrumar
- difícil de virar bagunça

## 🎮 CONTROLLER — O “PORTEIRO”
### O que ele faz?
- Recebe a requisição (site, formulário, API)
- Decide o que precisa ser feito
- Chama quem realmente trabalha
- O que ele NÃO faz?
- ❌ Não acessa banco
- ❌ Não faz regra de negócio
- ❌ Não valida regra complexa
- Frase-chave:
- Controller não pensa, ele encaminha.

## 🧠 MODEL — O “CÉREBRO”
### O que ele faz?
- Regras do sistema
- Validação de negócio
- Decide se algo pode ou não acontecer
- O que ele NÃO faz?
- ❌ Não recebe requisição
- ❌ Não imprime HTML
- ❌ Não decide rota
- Frase-chave:
- Model decide se algo é válido.

## 🗄️ DATABASE / CORE — O “TELEFONE”
### O que ele faz?
- Conecta no banco
- Executa SQL
- Retorna dados crus
- O que ele NÃO faz?
- ❌ Não entende regra de negócio
- ❌ Não sabe quem é usuário
- ❌ Não toma decisão
- Frase-chave:
- Database só fala com o banco.

```bash
Usuário
  ↓
Controller
  ↓
Model
  ↓
Database
  ↑
Model
  ↑
Controller
  ↑
View
  ↑
Usuário
```

## FRASE FINAL PRA GUARDAR
- Controller coordena
- Model decide
- Database executa
- View mostra