# Java Concurrency & Threading — Conceitos Fundamentais

## 📌 Introdução

Concorrência em Java é a capacidade de executar múltiplas tarefas ao mesmo tempo.  
Isso permite que programas sejam mais rápidos, responsivos e capazes de lidar com múltiplas operações simultâneas.

Uma **thread** é a menor unidade de execução dentro de um processo.  
Um programa pode possuir múltiplas threads rodando em paralelo.

---

## 🎯 Objetivo da Programação Concorrente

A concorrência em Java busca:

- Melhorar desempenho  
- Aumentar a responsividade  
- Utilizar múltiplos núcleos do processador  
- Processar tarefas independentes ao mesmo tempo  
- Evitar bloqueios em operações demoradas  

---

## 🧠 Quando usar

Use concorrência quando você precisa:

- Executar tarefas em background  
- Processar grandes volumes de dados  
- Realizar múltiplas requisições simultâneas  
- Trabalhar com sistemas reativos ou distribuídos  
- Melhorar tempo de resposta de aplicações  

---

## ❗ Riscos e Desafios

Concorrência não é simples. Sem cuidado, pode gerar:

- Condições de corrida (*race conditions*)  
- Deadlocks (duas threads esperando uma à outra)  
- Problemas de sincronização  
- Dados inconsistentes  
- Dificuldade de depuração  
- Baixo desempenho se usado incorretamente  

---

## 🧵 Conceitos Importantes

### Thread  
Fluxo de execução independente dentro de um programa.

### Process  
Programa em execução contendo uma ou mais threads.

### Task  
Unidade lógica de trabalho que pode ser executada por uma thread.

### Sincronização  
Mecanismo para controlar acesso a recursos compartilhados e evitar conflitos.

### Deadlock  
Situação onde threads ficam bloqueadas esperando recursos que nunca serão liberados.

### Race Condition  
Quando duas threads acessam e modificam dados ao mesmo tempo, criando resultados imprevisíveis.

### Executor Service  
Abstração que gerencia pools de threads para evitar criação de threads manualmente.

### Future / CompletableFuture  
Mecanismos para trabalhar com tarefas assíncronas e capturar seus resultados no futuro.

---

## 🧩 Problemas Clássicos na Concorrência

- Condição de corrida  
- Deadlock  
- Starvation (uma thread nunca executa)  
- Livelock (threads ficam mudando de estado sem progredir)  
- Contenção de recurso  

---

## 🧭 Boas Práticas

- Minimizar compartilhamento de estado  
- Usar APIs de alto nível (Executor, CompletableFuture)  
- Evitar criar threads manualmente  
- Priorizar imutabilidade de dados  
- Evitar blocos `synchronized` grandes demais  
- Não bloquear threads desnecessariamente  
- Monitorar o uso de CPU e threads  

---

## 🏛️ Frameworks e APIs Relacionadas

- Java Threads API  
- Executor Framework  
- Future e Callable  
- CompletableFuture  
- Fork/Join Framework  
- Parallel Streams  

---

## 📘 Quando não usar concorrência

Evite usar quando:

- O programa é simples e linear  
- Não há ganho significativo de performance  
- A lógica fica mais complexa sem necessidade  
- O hardware tem poucos recursos  
- A operação depende fortemente de I/O lento (sem async)  

---

> 📎 **Dica:** concorrência traz poder, mas exige disciplina, planejamento e conhecimento.  
Dominar esse tema te coloca em outro nível como desenvolvedor Java. 🚀
