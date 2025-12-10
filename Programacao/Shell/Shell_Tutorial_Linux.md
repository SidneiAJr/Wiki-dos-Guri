# 🐚 Shell Script | Uso no Linux

O Shell no Linux permite automatizar tarefas, manipular arquivos, processar dados e controlar o sistema de forma extremamente poderosa.
Criar scripts no terminal agiliza processos repetitivos e deixa o ambiente muito mais produtivo.

📄 Criando Scripts no Linux (com Vim ou Nano)

Para criar um script, utilize qualquer editor de texto:

````shell
vim meu_script.sh
````

## 🔧 Dando Permissão de Execução

## Permitir execução:
````shell
chmod +x meu_script.sh
````

## Dar permissão total (não recomendado):
````shell
chmod 777 meu_script.sh
````

`✔️ Recomendado: usar apenas o necessário, como +x`

`❌ Não recomendado: usar 777, pois abre permissão total.`

## ▶️ Executando o Script
````shell
./meu_script.sh
````

## ⚙️ Exemplo Básico

````shell
#!/bin/bash

echo "Olá, Shell Script!"
````

| Recurso       | Descrição              |
| ------------- | ---------------------- |
| `#!/bin/bash` | Define o interpretador |
| `chmod +x`    | Permite executar       |
| `echo`        | Exibe texto            |
| `read`        | Lê entrada             |
| `if/else`     | Lógica condicional     |
| `for/while`   | Repetições             |
| `$variavel`   | Variáveis              |
| `"$@"`        | Argumentos do script   |
| `exit 0`      | Finaliza com sucesso   |
