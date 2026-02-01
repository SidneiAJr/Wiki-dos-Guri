# ⚙️ Introdução à Linguagem Assembly

A **Assembly** é uma **linguagem de programação de baixo nível**, usada para escrever instruções que **se comunicam diretamente com o hardware** da máquina.

---

## 🧠 O que é Assembly?

Assembly (ou ASM) é uma linguagem que serve como **ponte entre o código binário e as linguagens de alto nível** (como C, Python, Java, etc).

Cada linha de código Assembly representa **uma instrução executada diretamente pelo processador**, como mover dados, somar números ou acessar memória.

> 💡 Em vez de “variáveis” e “funções”, o programador trabalha com **registradores**, **endereços de memória** e **instruções da CPU**.

---

## 🧩 Características Principais

| Conceito | Descrição |
|:-----------|:-----------|
| **Baixo nível** | Muito próximo da linguagem de máquina (binário). |
| **Dependente de arquitetura** | Cada processador (Intel, AMD, ARM, RISC-V) tem seu próprio conjunto de instruções (ISA). |
| **Rápido e eficiente** | Permite controle total sobre o hardware, mas exige muito conhecimento técnico. |
| **Usado em** | Sistemas embarcados, drivers, BIOS, otimizações e engenharia reversa. |

---

## ⚙️ Exemplo simples (x86 Assembly)

```asm
section .data
    msg db "Ola, mundo!", 0Ah  ; Mensagem com quebra de linha

section .text
    global _start

_start:
    mov eax, 4      ; Chamada do sistema: escrever (sys_write)
    mov ebx, 1      ; Saída padrão (stdout)
    mov ecx, msg    ; Endereço da mensagem
    mov edx, 13     ; Tamanho da mensagem
    int 0x80        ; Interrupção (executa a chamada)

    mov eax, 1      ; Chamada do sistema: sair (sys_exit)
    xor ebx, ebx    ; Código de saída 0
    int 0x80
```

## 🧮 Registradores Comuns (x86)

| Registrador | Função |
|:-------------|:--------|
| **EAX / AX** | Acumulador — usado em operações aritméticas. |
| **EBX / BX** | Base — usado para endereçamento de memória. |
| **ECX / CX** | Contador — usado em loops e repetições. |
| **EDX / DX** | Dados — usado em operações de entrada/saída (I/O). |
| **ESI / EDI** | Ponteiros de origem e destino em cópias de dados. |
| **EBP / ESP** | Controle da pilha (*stack*) de execução. |

| Registrador | Tipo | Função |
|:-------------|:------|:--------|
| **EAX / AX** | Geral | Acumulador — usado em operações aritméticas. |
| **EBX / BX** | Geral | Base — usado para endereçamento de memória. |
| **ECX / CX** | Geral | Contador — usado em loops e repetições. |
| **EDX / DX** | Geral | Dados — usado em operações de entrada/saída (I/O). |
| **ESI / EDI** | Ponteiro | Ponteiros de origem e destino em cópias de dados. |
| **EBP / ESP** | Pilha | Controle da pilha (*stack*) de execução. |


