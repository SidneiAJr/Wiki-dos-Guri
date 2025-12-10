# 📥 Entrada de Dados

Em COBOL, a entrada padrão é feita com o comando ACCEPT, que lê dados do teclado (ou de uma fonte definida no ambiente).

```Cobol
IDENTIFICATION DIVISION.
PROGRAM-ID. EntradaSimples.

DATA DIVISION.
WORKING-STORAGE SECTION.
01  NOME-USUARIO   PIC A(20).
01  IDADE          PIC 99.

PROCEDURE DIVISION.
INICIO.
    DISPLAY "Digite seu nome: ".
    ACCEPT NOME-USUARIO.
    DISPLAY "Digite sua idade: ".
    ACCEPT IDADE.
    DISPLAY "Nome: " NOME-USUARIO " | Idade: " IDADE.
    STOP RUN.
```

## 📤 Saída de Dados

A saída é feita com DISPLAY, que escreve no console (ou terminal).

Exemplos:
```Cobol
DISPLAY "Olá, mundo!".
DISPLAY "O valor é: " VARIAVEL.
```

## 🧾 Formatação e Mensagens

É possível concatenar texto e variáveis em um mesmo DISPLAY:

```Cobol
DISPLAY "Resultado: " VALOR " pontos.".
```

```Cobol
ENVIRONMENT DIVISION.
INPUT-OUTPUT SECTION.
FILE-CONTROL.
    SELECT ARQ-CLIENTES ASSIGN TO "clientes.txt"
    ORGANIZATION IS LINE SEQUENTIAL.

DATA DIVISION.
FILE SECTION.
FD  ARQ-CLIENTES.
01  REG-CLIENTE.
    05 NOME-CLIENTE   PIC A(20).
    05 IDADE-CLIENTE  PIC 99.

PROCEDURE DIVISION.
    OPEN OUTPUT ARQ-CLIENTES.
    MOVE "JOAO" TO NOME-CLIENTE.
    MOVE 25 TO IDADE-CLIENTE.
    WRITE REG-CLIENTE.
    CLOSE ARQ-CLIENTES.
    STOP RUN.
```



