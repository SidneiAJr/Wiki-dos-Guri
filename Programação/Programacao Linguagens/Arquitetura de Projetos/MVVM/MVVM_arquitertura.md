# 🧱 MVVM — Arquitetura

## O que é MVVM?

**MVVM** significa:

Model – View – ViewModel

MVVM é um padrão de arquitetura criado para separar interface de lógica,
muito usado em aplicações com interface rica e estado dinâmico.

---

## É comum em:

- Frontend moderno (React, Angular, Vue)
- Mobile (Android, iOS)
- Desktop (WPF, JavaFX)

---

## 📍 Quem é quem no MVVM?

Camada | Responsabilidade
------ | ----------------
Model | Dados e regras de negócio
View | Interface visual
ViewModel | Lógica da tela

---

## 🧠 Model

O Model representa os dados e as regras de negócio.

Ele:
- Acessa banco de dados ou API
- Executa validações de negócio
- Não conhece a View
- Não conhece o ViewModel

Model é independente da interface.

---

## 🎨 View

A View é a tela.

Ela:
- Exibe dados
- Captura eventos do usuário (cliques, inputs)
- Não contém regra de negócio
- Não acessa banco de dados

A View não decide nada.

---

## 🧩 ViewModel

O ViewModel é o cérebro da tela.

Ele:
- Recebe ações da View
- Chama o Model
- Processa dados
- Exponibiliza dados prontos para a View
- Não conhece detalhes visuais

O ViewModel não sabe como a tela é desenhada.

---

## 🔁 Fluxo do MVVM

Usuário  
↓  
View  
↓  
ViewModel  
↓  
Model  
↓  
ViewModel  
↓  
View  

---

## ✅ Regra de Ouro do MVVM

View mostra  
ViewModel pensa  
Model trabalha
