# 🧾 Tutorial COBOL
🏁 Introdução

COBOL (COmmon Business Oriented Language) é uma linguagem de programação voltada para processamento de dados empresariais.
Criada nos anos 1960, ainda hoje é usada em bancos, seguros, governos e mainframes.

É uma linguagem verbo-centrada, muito parecida com o inglês estruturado.

## 📁 Estrutura de um Programa COBOL

Um programa COBOL é dividido em divisões, seções, parágrafos e instruções.

```Cobol
IDENTIFICATION DIVISION.
PROGRAM-ID. MeuPrimeiroCOBOL.

ENVIRONMENT DIVISION.

DATA DIVISION.
WORKING-STORAGE SECTION.
01  NOME-USUARIO   PIC A(20).

PROCEDURE DIVISION.
INICIO.
    DISPLAY "Digite seu nome: ".
    ACCEPT NOME-USUARIO.
    DISPLAY "Ola, " NOME-USUARIO "!".
    STOP RUN.
```

## 🔍 Explicação

IDENTIFICATION DIVISION – Nome e identificação do programa.

ENVIRONMENT DIVISION – Configurações do ambiente (entrada, saída, arquivos).

DATA DIVISION – Declaração de variáveis e estruturas de dados.

PROCEDURE DIVISION – O código executável do programa.

## 💾 Tipos de Dados e Declarações

As variáveis são declaradas com níveis hierárquicos (01, 02, etc.) e descrições de formato (PIC).
```Cobol
01  IDADE         PIC 99.       *> dois dígitos numéricos
01  SALARIO       PIC 9(5)V99.  *> até 5 dígitos inteiros e 2 decimais
01  NOME          PIC A(20).    *> até 20 letras
01  CPF           PIC X(11).    *> 11 caracteres de qualquer tipo
```

## Estruturas de Controle

```Cobol
IF IDADE > 18
    DISPLAY "Maior de idade."
ELSE
    DISPLAY "Menor de idade."
END-IF.
```

## PERFORM (laços)
```Cobol
PERFORM VARYING CONTADOR FROM 1 BY 1 UNTIL CONTADOR > 5
    DISPLAY "Contador: " CONTADOR
END-PERFORM.
```

## 🧮 Operações Matemáticas

```Cobol
ADD 10 TO IDADE.
SUBTRACT 5 FROM SALARIO.
MULTIPLY PRECO BY QUANTIDADE GIVING TOTAL.
DIVIDE TOTAL BY 2 GIVING METADE.
```



