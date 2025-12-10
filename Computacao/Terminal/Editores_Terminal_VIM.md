# ✍️ Vim (Vi Improved)

O vim é um editor poderoso e completo, baseado no clássico vi.
É ideal para usuários mais avançados e para automação de tarefas com scripts.

▶️ Abrir ou criar um arquivo:

```bash
vim arquivo.txt
```

| Ação                     | Comando |
| ------------------------ | ------- |
| Entrar no modo de edição | `i`     |
| Sair do modo edição      | `Esc`   |
| Salvar o arquivo         | `:w`    |
| Sair do `vim`            | `:q`    |
| Salvar e sair            | `:wq`   |
| Sair sem salvar          | `:q!`   |


Comandos para o vim 
- Sudo apt install vim -y
- vim nome-arquivo.sh
- Depois disso dar permissão com chmod +x ou chmod +777
> ⚠️ Cuidado: 777 dá permissão total (pode ser perigoso em ambientes de produção).
***O ideal é usar só o +x mesmo.***

| Ação                      | Comando | Explicação                        |
| ------------------------- | ------- | --------------------------------- |
| Entrar no modo de edição  | `i`     | Digita texto normalmente          |
| Voltar ao modo de comando | `Esc`   | Sai do modo de edição             |
| Salvar arquivo            | `:w`    | *Write (escrever no disco)*       |
| Sair do Vim               | `:q`    | *Quit (sair)*                     |
| Salvar e sair             | `:wq`   | *Write + Quit*                    |
| Sair sem salvar           | `:q!`   | *Quit forçado, ignora alterações* |
