# Garbage Collector no .NET

## 📌 Introdução

O **Garbage Collector (GC)** gerencia memória automaticamente no .NET, liberando objetos não utilizados e evitando vazamentos.

---

## 🧠 Como funciona

O GC identifica objetos que não possuem mais referências e os remove.

Trabalha com **gerações de memória**:

| Geração | Objetos |
|--------|---------|
Gen 0 | Objetos curtos / temporários |
Gen 1 | Intermediários |
Gen 2 | Objetos de longa duração |

---

## 🏗️ Conceitos Importantes

### **Managed Heap**
Onde os objetos alocados existem.

### **Stack vs Heap**

| Stack | Heap |
|------|------|
Armazena variáveis locais | Objetos e classes |
Pequeno & rápido | Maior & mais lento |
Liberação automática | GC limpa depois |

---

## ⚙️ Tipos de Coleta

- **Workstation GC**
- **Server GC** (alto desempenho, múltiplos threads)
- **Concurrent / Background GC**

---

## ⚠️ Evitando Pressão no GC

- Reutilizar objetos
- Preferir `Span<>`, `Memory<>` para alta performance
- Liberar recursos com `IDisposable`
- Evitar objetos grandes desnecessários

---

## 🎯 Boas Práticas

- Usar `using` para liberar recursos nativos
- Evitar alocações dentro de loops intensos
- Monitorar com ferramentas como:
  - dotMemory
  - PerfView
  - Visual Studio Profiler

---

## 🧭 Conclusão

O GC é poderoso, mas **entender como a memória funciona** ajuda a evitar gargalos e criar software mais eficiente.
