# Async / Await Avançado em C#

## 📌 Introdução

Async/await simplifica o trabalho com operações assíncronas.  
É essencial para aplicações modernas — web, API, desktop e serviços.

---

## 🎯 Objetivo

Executar tarefas demoradas sem bloquear a thread principal.

---

## 🧠 Conceitos-Chave

### **async**
Informa que o método contém operações assíncronas.

### **await**
Suspende execução até a conclusão da tarefa, sem bloquear a thread.

### **Synchronization Context**
Garante retorno à thread original (UI / Request HTTP).

### **Task vs ValueTask**
- Task: padrão, recomendado na maioria dos casos.
- ValueTask: otimiza cenários de alta performance.

---

## ⚠️ Erros Comuns

| Erro | Problema |
|------|---------|
`.Result` / `.Wait()` | Deadlock |
`async void` | Não controla falhas, só usar em eventos |
Ignorar cancellation | Tasks que nunca param |
Misturar sync + async | Bloqueios inesperados |

---

## 🧭 Boas Práticas

- Sempre preferir `await` a `.Result`
- Cancelamento com `CancellationToken`
- Evitar `.ConfigureAwait(false)` exceto libs
- Usar logging para monitorar Tasks

---

## ✅ Quando usar async/await

- Operações I/O (DB, HTTP, arquivos)
- Processos em background
- APIs e microservices

---

## ❌ Quando NÃO usar

- Cálculos pequenos e rápidos
- Processamento CPU-bound sem paralelismo
