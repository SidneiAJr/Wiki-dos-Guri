# Introdução a Sistemas Operacionais

## O que é um Sistema Operacional?

Um **Sistema Operacional (SO)** é um conjunto de programas que atua como uma **interface entre o hardware e o usuário**, gerenciando recursos e controlando a execução dos programas.

### Principais Funções:
- **Gerenciamento de Processos:** controla a execução de programas, permitindo multitarefa e controle de concorrência.
- **Gerenciamento de Memória:** aloca e libera memória para processos.
- **Gerenciamento de Dispositivos:** coordena a comunicação entre software e hardware (drivers).
- **Gerenciamento de Arquivos:** organiza, lê e grava dados em sistemas de arquivos.
- **Segurança e Controle de Acesso:** protege recursos e dados contra uso indevido.

---

## Estrutura de um Sistema Operacional

Um sistema operacional é composto por **camadas**:

1. **Núcleo (Kernel):** coração do SO; controla o hardware e os recursos essenciais.  
2. **Chamadas de Sistema (Syscalls):** interface entre programas e o kernel.  
3. **Shell:** interpretador de comandos (ex: Bash, PowerShell).  
4. **Interface Gráfica (GUI):** camada visual usada pelos usuários comuns.

---

## Tipos de Sistemas Operacionais

| Tipo | Descrição | Exemplos |
|------|------------|-----------|
| **Monotarefa** | Executa apenas um programa por vez | MS-DOS |
| **Multitarefa** | Executa vários programas simultaneamente | Windows, Linux |
| **Tempo Real (RTOS)** | Responde a eventos em tempo previsível | QNX, FreeRTOS |
| **Distribuído** | Gerencia múltiplos computadores como um só | Amoeba, Plan 9 |
| **Embarcado** | Voltado para dispositivos específicos | Android Auto, firmware de roteadores |

---

## Gerenciamento de Processos

Um **processo** é um programa em execução.  
O SO controla:
- **Criação e término de processos**
- **Escalonamento (scheduling)**: define qual processo executa e por quanto tempo.
- **Estados:** Novo → Pronto → Executando → Esperando → Encerrado

---

## Gerenciamento de Memória

A memória é dividida entre processos. O SO faz:
- **Particionamento e paginação**
- **Memória virtual (swap)**
- **Proteção de endereços** para evitar interferência entre programas.

---

## Exemplos de Sistemas Operacionais

- **Windows:** interface amigável, foco em produtividade e compatibilidade.  
- **Linux:** código aberto, alta estabilidade, usado em servidores e sistemas embarcados.  
- **macOS:** baseado em Unix, com foco em desempenho e integração com hardware Apple.  
- **Android e iOS:** derivados de Linux e BSD, otimizados para dispositivos móveis.

---

## Comandos Básicos no Linux

```bash
ls       # Lista arquivos
cd       # Navega entre diretórios
mkdir    # Cria diretório
rm       # Remove arquivos
ps       # Lista processos
top      # Exibe uso de CPU e memória
