# Concurrency em C# — Tasks & Paralelismo

## 📌 Introdução

Concorrência em C# permite executar múltiplas operações simultaneamente, aumentando performance e responsividade.  
O .NET fornece a *Task Parallel Library (TPL)* para gerenciar execuções assíncronas e paralelas de forma eficiente.

---

## 🎯 Objetivos da Programação Concorrente

- Melhorar desempenho em operações demoradas
- Utilizar múltiplos núcleos do processador
- Evitar travamentos em aplicações GUI e Web
- Processar múltiplas tarefas simultaneamente

---

## 🧠 Conceitos Fundamentais

### **Task**
Representa uma unidade de trabalho assíncrona gerenciada pela TPL.

### **Thread Pool**
Grupo de threads reutilizáveis gerenciadas pelo runtime .NET.

### **Task Scheduler**
Componente que decide como as Tasks serão executadas.

### **Parallelism vs Concurrency**

| Conceito | Significado |
|---------|-------------|
Concorrência | Alterna tarefas para melhorar responsividade |
Paralelismo | Executa várias tarefas DE FATO ao mesmo tempo |

---

## ⚠️ Riscos da Concorrência

- Race conditions
- Deadlocks
- Acesso simultâneo a dados
- Alto consumo de CPU se mal implementado

---

## 💡 Boas Práticas

- Usar **Task.Run** somente quando necessário
- Compartilhar o mínimo possível de estado
- Preferir estruturas thread-safe
- Monitorar o uso do ThreadPool

---

## 🏁 Quando usar Tasks

✅ Operações I/O demoradas  
✅ Processamento pesado paralelo  
✅ Aplicações web com múltiplas requisições  

❌ Tarefas muito curtas (custo de criar Task)  
❌ Quando o código é 100% síncrono e rápido  

---

## 🧭 Conclusão

O modelo baseado em **Tasks e TPL** é a base da concorrência moderna no C#, sendo mais eficiente e seguro que threads manuais.
