# 🐳 Docker — Volumes e Rodando Aplicações Web

> Canvas focado em **persistência de dados com volumes** e **execução de aplicações web em containers**.

---

## 1️⃣ Volumes e Persistência de Dados

### O que são volumes?

* Volumes são **armazenamentos externos aos containers**, permitindo que os dados sobrevivam mesmo se o container for deletado.
* Diferente de bind mounts, volumes são gerenciados pelo Docker e mais portáveis.

### Criando e usando volumes

```bash
# Criar um volume
docker volume create meu_volume

# Rodar container usando o volume
docker run -d \
  --name meu_mysql \
  -e MYSQL_ROOT_PASSWORD=senha123 \
  -v meu_volume:/var/lib/mysql \
  mysql:8.0
```

> Aqui `/var/lib/mysql` é o diretório do MySQL dentro do container.

### Benefícios dos volumes

* Persistência de dados mesmo após `docker rm` do container
* Compartilhamento de dados entre containers
* Backup e restauração facilitados

---

## 2️⃣ Rodando Aplicações Web

### Exemplo 1: Nginx

```bash
# Baixar imagem Nginx
docker pull nginx:latest

# Rodar container Nginx
docker run -d -p 8080:80 --name meu_nginx nginx:latest
```

* Acesse no navegador: `http://localhost:8080`

### Exemplo 2: Node.js (aplicação simples)

```bash
# Estrutura de diretórios:
# app/
# ├─ index.js
# └─ package.json

# Dockerfile
FROM node:18
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node", "index.js"]

# Build da imagem
docker build -t minha_app_node .

# Rodar container
docker run -d -p 3000:3000 minha_app_node
```

* Acesse no navegador: `http://localhost:3000`

### Integrando Volume em Aplicação Web

```bash
docker run -d -p 8080:80 -v /meu_site:/usr/share/nginx/html nginx
```

> Permite atualizar arquivos do site localmente e ver as mudanças refletidas no container.

---

## 3️⃣ Boas práticas

* Separe **dados e código** usando volumes
* Nomeie volumes de forma clara (`db_data`, `app_logs`)
* Use **docker-compose** para orquestrar múltiplos containers com volumes compartilhados
* Limite permissões e usuários para segurança

---

*Canvas Docker — foco em persistência de dados e execução de aplicações web.*
