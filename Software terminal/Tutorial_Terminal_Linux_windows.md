# 💻 Tutorial de Terminal — Linux 🐧 | Windows 💠

> Comandos básicos para navegação e manipulação de arquivos via **linha de comando (CLI)**.

---

## ⚙️ No Windows (CMD / PowerShell)

| Comando | Descrição | Exemplo |
|:--|:--|:--|
| `cd` | Navega entre pastas (change directory) | `cd Documentos` |
| `dir` | Lista os arquivos e pastas do diretório atual | `dir` |
| `color` | Altera a cor do texto no terminal | `color a` (verde) |
| `cls` | Limpa a tela do terminal | `cls` |
| `mkdir` | Cria uma nova pasta | `mkdir projetos` |
| `del` | Exclui arquivos | `del teste.txt` |
| `rmdir` | Remove pastas vazias | `rmdir temp` |
| `copy` | Copia arquivos | `copy texto.txt backup.txt` |
| `move` | Move ou renomeia arquivos | `move foto.jpg imagens\` |
| `echo` | Exibe mensagens ou cria arquivos de texto | `echo Olá > mensagem.txt` |

📌 *Dica:* pra abrir o terminal rapidamente, digita `cmd` na barra de pesquisa do Windows.

---

## 🐧 No Linux (Bash / Terminal)

| Comando | Descrição | Exemplo |
|:--|:--|:--|
| `cd` | Navega entre diretórios | `cd /home/usuario/Documentos` |
| `ls` | Lista arquivos e pastas | `ls` |
| `ls -a` | Lista **todos** os arquivos (incluindo ocultos) | `ls -a` |
| `ls -d */` | Lista **somente diretórios** | `ls -d */` |
| `ls -lh` | Lista com tamanhos legíveis (KB, MB) | `ls -lh` |
| `cp` | Copia arquivos | `cp arquivo.txt backup/` |
| `mv` | Move ou renomeia arquivos | `mv foto.png imagens/` |
| `rm` | Remove arquivos | `rm velho.txt` |
| `rm -r` | Remove pastas recursivamente | `rm -r pasta_velha/` |
| `mkdir` | Cria pastas | `mkdir projetos` |
| `cat` | Mostra o conteúdo de um arquivo | `cat notas.txt` |
| `pwd` | Mostra o diretório atual | `pwd` |
| `clear` | Limpa o terminal | `clear` |
| `man` | Mostra o manual de um comando | `man ls` |

📌 *Dica:* usa `Tab` pra **auto-completar** nomes de arquivos e `↑ / ↓` pra navegar no histórico de comandos.

---

## 🔄 Comandos equivalentes

| Ação | Windows | Linux |
|:--|:--|:--|
| Listar arquivos | `dir` | `ls` |
| Mudar de diretório | `cd` | `cd` |
| Limpar a tela | `cls` | `clear` |
| Criar pasta | `mkdir` | `mkdir` |
| Copiar arquivo | `copy` | `cp` |
| Mover arquivo | `move` | `mv` |
| Apagar arquivo | `del` | `rm` |
| Mostrar caminho atual | `cd` | `pwd` |

---

## 🧩 Extras úteis

- `history` → mostra o histórico de comandos (Linux)  
- `echo $PATH` → mostra variáveis de ambiente (Linux)  
- `echo %PATH%` → mostra variáveis de ambiente (Windows)  
- `whoami` → mostra o nome do usuário logado  
- `exit` → fecha o terminal  

---

> 💬 *Resumo:*  
> - **Windows** usa comandos próprios do **CMD** (base MS-DOS).  
> - **Linux** usa o **Bash** (shell poderoso com centenas de comandos).  
> - Ambos podem automatizar tarefas com **scripts** (`.bat` no Windows, `.sh` no Linux).

---
