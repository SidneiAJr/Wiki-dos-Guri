# 🐳 Docker — Comandos e Exemplos Práticos

> Lista de comandos e exemplos de uso do Docker com SQL, Linux, Hello World e subsistemas Linux no Windows.

---

## 1. Comandos básicos do Docker

| Comando                            | Descrição                                 |
| ---------------------------------- | ----------------------------------------- |
| `docker --version`                 | Ver versão do Docker instalada            |
| `docker pull <imagem>`             | Baixar uma imagem do Docker Hub           |
| `docker images`                    | Listar imagens baixadas                   |
| `docker ps`                        | Listar containers ativos                  |
| `docker ps -a`                     | Listar todos os containers, ativos ou não |
| `docker run <imagem>`              | Executar um container                     |
| `docker stop <container>`          | Parar um container ativo                  |
| `docker start <container>`         | Iniciar um container parado               |
| `docker rm <container>`            | Remover um container                      |
| `docker rmi <imagem>`              | Remover uma imagem                        |
| `docker logs <container>`          | Visualizar logs do container              |
| `docker exec -it <container> bash` | Acessar shell dentro do container         |

---

## 2. Docker com SQL (ex: MySQL/MariaDB/PostgreSQL)

```bash
# Baixar a imagem
docker pull mysql:8.0

# Executar container MySQL
docker run --name meu_mysql -e MYSQL_ROOT_PASSWORD=senha123 -p 3306:3306 -d mysql:8.0

# Acessar o container
docker exec -it meu_mysql bash

# Entrar no MySQL
mysql -u root -p
```

> Observação: para PostgreSQL, trocar `mysql:8.0` por `postgres:15` e usar `psql` dentro do container.

---

## 3. Docker Hello World

```bash
# Baixar e executar imagem Hello World
docker run hello-world
```

> Teste rápido para verificar se o Docker está funcionando corretamente.

---

## 4. Docker com Linux

```bash
# Baixar imagem Linux (Ubuntu)
docker pull ubuntu:22.04

# Executar container interativo com shell
docker run -it ubuntu:22.04 bash

# Comandos dentro do container
apt update && apt install -y vim curl
```

> Útil para testar comandos Linux sem instalar nada no host.

---

## 5. Subsistemas Linux no Windows

* **WSL (Windows Subsystem for Linux)** permite rodar um ambiente Linux dentro do Windows.
* **Instalação básica:**

```powershell
# Ativar WSL
wsl --install

# Escolher distribuição Linux
wsl --install -d Ubuntu
```

* **Integração com Docker Desktop:**

  * Docker Desktop para Windows usa WSL 2 como backend.
  * Permite rodar containers Linux diretamente no Windows.

---

*Documento base — Docker comandos, exemplos com SQL, Linux, Hello World e WSL no Windows.*
