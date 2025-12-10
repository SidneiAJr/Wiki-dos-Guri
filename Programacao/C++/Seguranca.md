# 🔐 Segurança em C++

## 🎯 Objetivo
Aprender boas práticas de **segurança e prevenção de vulnerabilidades** em programas C++.

---

## ⚠️ Riscos Comuns

| Tipo de Falha | Descrição | Exemplo |
|----------------|------------|----------|
| **Buffer Overflow** | Estouro de limite em arrays ou ponteiros. | `char nome[10]; gets(nome);` |
| **Use-after-free** | Acessar memória após liberar com `delete`. | `delete ptr; cout << *ptr;` |
| **Memory Leak** | Esquecer de liberar memória alocada. | `new int[100];` sem `delete[]` |
| **Input Injection** | Falta de validação de entrada de usuário. | `system(userInput);` |
| **Race Condition** | Acesso simultâneo indevido a recursos. | Threads sem mutex. |

---

## 🧠 Boas Práticas

✅ **Sempre inicialize variáveis**
```cpp
int x = 0;
char buffer[50] = {0};
```
