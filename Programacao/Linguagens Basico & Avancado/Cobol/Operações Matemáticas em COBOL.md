# Operações Matemáticas em COBOL
➕ ADD (somar)
```Cobol
ADD 10 TO SALDO.
ADD VALOR1 VALOR2 GIVING TOTAL.

```

➖ SUBTRACT (subtrair)

```Cobol
SUBTRACT 5 FROM SALDO.
SUBTRACT DESPESAS FROM RECEITAS GIVING LUCRO.

```

✖️ MULTIPLY (multiplicar)

```Cobol
MULTIPLY PRECO BY QUANTIDADE GIVING TOTAL.

```

➗ DIVIDE (dividir)

```Cobol
DIVIDE TOTAL BY 2 GIVING METADE.
```

```cobol
IDENTIFICATION DIVISION.
PROGRAM-ID. CalculadoraSimples.

DATA DIVISION.
WORKING-STORAGE SECTION.
01  NUM1     PIC 9(3).
01  NUM2     PIC 9(3).
01  SOMA     PIC 9(4).
01  MEDIA    PIC 9(4)V9(2).

PROCEDURE DIVISION.
INICIO.
    DISPLAY "Digite o primeiro número: ".
    ACCEPT NUM1.
    DISPLAY "Digite o segundo número: ".
    ACCEPT NUM2.

    ADD NUM1 TO NUM2 GIVING SOMA.
    COMPUTE MEDIA = (NUM1 + NUM2) / 2.

    DISPLAY "Soma = " SOMA.
    DISPLAY "Média = " MEDIA.

    STOP RUN.

```
## 💡 Resumo Rápido

| Comando | Função |
|:--|:--|
| `ADD` | Soma valores |
| `SUBTRACT` | Subtrai valores |
| `MULTIPLY` | Multiplica valores |
| `DIVIDE` | Divide valores |
| `COMPUTE` | Executa expressões completas (com operadores) |
