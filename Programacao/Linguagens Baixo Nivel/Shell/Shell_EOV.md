# 📌 EOV no Shell Script

No Shell Script, EOV não é um comando nem uma palavra reservada.
Ele é apenas um identificador usado como delimitador em um Heredoc.

Um Heredoc serve para enviar um bloco de texto para um comando, e você pode escolher qualquer palavra para marcar o início e o fim — inclusive EOV.

````bash
cat <<EOV
Linha 1
Linha 2
Este texto será enviado para o comando "cat"
EOV
````

## 🔍 O que está acontecendo?

- <<EOV → inicia um bloco de texto

- Tudo entre as duas ocorrências de EOV é enviado para o comando

- A palavra EOV é só um marcador

- Pode ser substituída por qualquer nome (EOF, END, FIM, TEXTO)
