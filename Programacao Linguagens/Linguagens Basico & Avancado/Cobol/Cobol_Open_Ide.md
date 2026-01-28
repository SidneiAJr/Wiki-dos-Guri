# 🖥️ Tutorial — OpenCobolIDE (Ambiente de Desenvolvimento COBOL)

O **OpenCobolIDE** é uma IDE simples e gratuita para programar em **COBOL**, baseada no compilador **GnuCOBOL**.  
Ideal para estudantes e profissionais que desejam praticar lógica estruturada e processamento de dados em linguagem de mainframe.

---

## ⚙️ Instalação do OpenCobolIDE

### 🔹 Passo 1 — Baixar a IDE
- Escolha a versão compatível com seu sistema operacional:
  - **Windows:** `.exe` instalador direto  
  - **Linux:** `.tar.gz` (ou via pacote `pip install open-cobol-ide`)
  - **MacOS:** pode usar via `Homebrew` com `brew install gnucobol`

---

### 🔹 Passo 2 — Instalar o compilador GnuCOBOL

O OpenCobolIDE precisa do compilador **GnuCOBOL** (também conhecido como OpenCOBOL) para transformar o código COBOL em executável.

#### 🧩 Windows


Durante a instalação, marque a opção:
> “Add GnuCOBOL to PATH”

#### 🧩 Linux / WSL
```bash
sudo apt update
sudo apt install open-cobol
```

```cobol
IDENTIFICATION DIVISION.
PROGRAM-ID. HELLO-COBOL.

ENVIRONMENT DIVISION.

DATA DIVISION.

PROCEDURE DIVISION.
    DISPLAY "HELLO, MUNDO COBOL!".
    STOP RUN.

```

## Lento Arquivo

```
IDENTIFICATION DIVISION.
PROGRAM-ID. LER-ARQUIVO.

ENVIRONMENT DIVISION.
INPUT-OUTPUT SECTION.
FILE-CONTROL.
    SELECT ARQ ASSIGN TO "dados.txt"
    ORGANIZATION IS LINE SEQUENTIAL.

DATA DIVISION.
FILE SECTION.
FD  ARQ.
01  REGISTRO.
    05  NOME   PIC A(30).
    05  IDADE  PIC 9(2).

PROCEDURE DIVISION.
    OPEN INPUT ARQ
    READ ARQ
        AT END DISPLAY "FIM DO ARQUIVO"
        NOT AT END DISPLAY "NOME: " NOME " - IDADE: " IDADE
    END-READ
    CLOSE ARQ
    STOP RUN.
```

