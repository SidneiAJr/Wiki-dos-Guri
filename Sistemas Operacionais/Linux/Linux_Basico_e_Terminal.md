# 🐧 Linux Básico e Terminal

O **Linux** é um sistema operacional livre e aberto, usado em servidores, máquinas virtuais e dispositivos embarcados.  
Saber usar o **terminal (linha de comando)** é essencial para administrar e automatizar tarefas no sistema.

---

## 📂 Estrutura de Diretórios

| Diretório | Função Principal |
|------------|------------------|
| `/` | Raiz do sistema (pasta principal) |
| `/home` | Diretórios dos usuários |
| `/etc` | Arquivos de configuração |
| `/bin` | Comandos básicos do sistema |
| `/usr` | Programas e bibliotecas de usuários |
| `/var` | Dados variáveis (logs, cache, filas) |
| `/tmp` | Arquivos temporários |

---

## 💻 Comandos Essenciais do Terminal

### 📁 Navegação e Manipulação
```bash
pwd          # Mostra o diretório atual
ls           # Lista arquivos e pastas
cd /caminho  # Muda de diretório
mkdir nome   # Cria uma nova pasta
rm arquivo   # Remove arquivo
rmdir pasta  # Remove pasta vazia
cp origem destino   # Copia arquivo/pasta
mv origem destino   # Move ou renomeia arquivo/pasta

whoami            # Mostra o usuário atual
adduser nome      # Cria um novo usuário
passwd nome       # Define senha para usuário
sudo comando      # Executa comando como administrador
chmod 755 arquivo # Altera permissões
chown user:grupo arquivo # Muda dono e grupo
