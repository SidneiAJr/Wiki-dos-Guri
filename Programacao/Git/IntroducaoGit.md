# 🧭 Guia Completo de Git & GitHub

💬 O Git é um sistema de controle de versão distribuído — ele permite registrar e gerenciar o histórico de alterações do seu código.
O GitHub é uma plataforma online para armazenar, colaborar e compartilhar projetos Git.

## ⚙️ Configuração Inicial

Antes de usar o Git, configure seu nome e e-mail (isso aparece nos commits):
```git
git config --global user.name "SeuNome"
git config --global user.email "seuemail@exemplo.com"
```
# Verifique as configurações
```git
git config --list
```
## 🏗️ Criando um Repositório

Crie uma pasta para o projeto:
```git
mkdir meu_projeto
cd meu_projeto


Inicialize o repositório:

git init


Adicione seus arquivos:

git add .
```

Crie o primeiro commit:

## 🌐 Conectando com o GitHub

No GitHub, crie um novo repositório.

Copie o link HTTPS ou SSH.

Conecte o repositório local ao remoto:
```git
git remote add origin https://github.com/SeuUsuario/SeuRepositorio.git
git branch -M main
git push -u origin main
```
## 🚀 Fluxo Básico de Trabalho (Ciclo Git)
# Verificar status dos arquivos
```git
git status

# Adicionar todos os arquivos modificados
git add .

# Criar um commit com mensagem
git commit -m "Descrição das mudanças"
```
# Enviar para o GitHub
git push origin main

## 🌿 Branches (Ramificações)

As branches permitem trabalhar em novas funcionalidades sem alterar a versão principal.
```git
# Criar nova branch
git checkout -b feature/menu-principal

# Listar branches
git branch

# Voltar para a principal
git checkout main

# Mesclar mudanças
git merge feature/menu-principal

# Apagar uma branch
git branch -d feature/menu-principal

git commit -m "Primeiro commit"
```

# 🔄 ***Atualizando o Projeto (Sincronização)***

Antes de começar a alterar qualquer coisa no projeto, puxa as mudanças mais recentes do GitHub:
```git
git pull origin main
```
