# ⚙️ Introdução a Batch File (Windows CMD) e Shell Script (Linux / macOS)

> Scripts de terminal automatizam tarefas, executam comandos e simplificam rotinas do sistema operacional.  
> O **Batch File** é usado no **Windows (cmd)** e o **Shell Script** no **Linux/macOS (bash/zsh)**.

---

## 🪟 Batch File (`.bat` ou `.cmd`)

### 📘 O que é?

Um **Batch File** é um arquivo de texto simples que contém comandos do **Prompt de Comando (cmd)**, executados em sequência.

---

### 🚀 Como Criar

1. Abra o **Bloco de Notas**  
2. Escreva seus comandos  
3. Salve como `meuscript.bat`  
4. Dê dois cliques para executar  

---

### 💡 Exemplo Simples

```bat
@echo off
echo Olá, mundo!
pause

@echo off
set nome=Sidnei
echo Olá %nome%!
pause


@echo off
set idade=18
if %idade% GEQ 18 (
    echo Maior de idade
) else (
    echo Menor de idade
)
pause


@echo off
for %%i in (1 2 3 4 5) do (
    echo Número: %%i
)
pause

@echo off
start notepad.exe
timeout /t 3
start calc.exe


@echo off
set /p nome=Digite seu nome:
echo Bem-vindo, %nome%!
pause


@echo off
echo Limpando arquivos temporários...
del /q /s "C:\Windows\Temp\*.*"
echo Concluído!
pause

#!/bin/bash
echo "Olá, mundo!"


#!/bin/bash
idade=18

if [ $idade -ge 18 ]; then
  echo "Maior de idade"
else
  echo "Menor de idade"
fi


#!/bin/bash
for i in {1..5}
do
  echo "Número $i"
done


#!/bin/bash
contador=1
while [ $contador -le 5 ]
do
  echo "Contador: $contador"
  ((contador++))
done


