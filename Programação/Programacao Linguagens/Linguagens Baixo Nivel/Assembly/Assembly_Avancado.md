## 🚀 Tópicos Avançados em Assembly

Depois de entender os registradores e a estrutura básica, podemos mergulhar em conceitos mais avançados que mostram o poder real da linguagem Assembly.

---

### 🧩 1. Modos de Endereçamento

O **modo de endereçamento** define **como o processador acessa dados** (valores, variáveis, ponteiros etc.).  
Cada instrução precisa saber **de onde vem** e **para onde vai** a informação.

| Tipo | Exemplo | Descrição |
|:------|:---------|:-----------|
| **Imediato** | `mov eax, 5` | O valor é passado diretamente. |
| **Direto** | `mov eax, [var]` | Usa o endereço da variável na memória. |
| **Registrador** | `mov eax, ebx` | Copia o valor de um registrador pra outro. |
| **Indexado** | `mov eax, [ebx + 4]` | Usa o valor de um registrador + deslocamento. |
| **Base + Deslocamento** | `mov eax, [ebp - 8]` | Acesso típico de variáveis locais na pilha. |

---

### 🧮 2. Pilha (Stack)

A **pilha** é uma área de memória usada para armazenar **valores temporários, endereços de retorno e parâmetros de funções**.  
Funciona com o princípio **LIFO (Last In, First Out)**.

| Instrução | Função |
|:-----------|:--------|
| **PUSH valor** | Empilha um valor. |
| **POP destino** | Desempilha o valor mais recente. |
| **CALL função** | Chama uma função (empilha o endereço de retorno). |
| **RET** | Retorna da função (usa o endereço desempilhado). |

💡 *A pilha é fundamental para chamadas de função e recursão.*

---

### 🧠 3. Flags (Bandeiras da CPU)

As **flags** são bits especiais no registrador de status (**EFLAGS**) que informam o resultado de operações lógicas e aritméticas.

| Flag | Significado | Exemplo |
|:------|:--------------|:----------|
| **ZF (Zero Flag)** | Liga quando o resultado é zero. | `cmp eax, 0` |
| **CF (Carry Flag)** | Indica overflow em operações sem sinal. | `add eax, ebx` |
| **SF (Sign Flag)** | Indica se o resultado é negativo. | `sub eax, ebx` |
| **OF (Overflow Flag)** | Indica overflow em operações com sinal. | `imul eax, ebx` |
| **PF (Parity Flag)** | Verifica se o número de bits 1 é par. | Operações lógicas |

Essas flags são usadas em **instruções condicionais**, como:

```asm
cmp eax, ebx    ; Compara os dois valores
je  iguais      ; Jump if Equal (ZF = 1)
jl  menor       ; Jump if Less (SF != OF)
jg  maior       ; Jump if Greater (SF = OF e ZF = 0)
```

## 🧩 Interrupções, Subrotinas e Macros em Assembly

| Conceito | Descrição | Exemplo |
|:----------|:------------|:-----------|
| **🧠 Interrupções (INT)** | Permitem que o programa **chame funções do sistema operacional** diretamente (syscalls). | `int 0x80` — chama o kernel no Linux. |
| **⚙️ Chamadas de Sistema (Syscalls)** | São **funções do sistema operacional** acessadas via interrupções. Cada função é identificada por um número em `EAX`. | `mov eax, 4` → `sys_write` (escrever na tela). |
| **🧮 Subrotinas (Funções)** | Trechos de código reutilizáveis que **recebem parâmetros, executam operações e retornam valores**. | `CALL soma` → executa a função `soma:` e depois retorna com `RET`. |
| **📦 Pilha (Stack)** | Usada para **armazenar parâmetros** e o **endereço de retorno** das funções. | `PUSH valor`, `POP destino`. |
| **🔁 Macros** | Blocos de código **reutilizáveis** que são expandidos pelo montador antes da execução. | `%macro PRINT 2 ... %endmacro`. |
| **💡 Vantagem das Macros** | Evitam repetição de código e facilitam manutenção. | `PRINT msg, 13` imprime texto sem reescrever as instruções. |
