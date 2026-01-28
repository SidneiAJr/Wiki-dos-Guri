# 🚀 Tutorial de Vercel – Deploy Rápido e Fácil
✅ Pré-requisitos

- Conta no GitHub
 (ou GitLab/Bitbucket)

- Conta no Vercel

Projeto pronto (pode ser site estático ou app React/Next.js/etc.)

## 1️⃣ Criar Conta na Vercel

Acesse https://vercel.com

Clique em Sign up

Conecte com sua conta GitHub (ou GitLab/Bitbucket)

Autorize a Vercel a acessar seus repositórios

## Selecionando Tipo de Conta:

![Criando Conta](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-22%20093920.png)

## Criando a Aplicação:

![Importando Aplicacao](https://github.com/SidneiAJr/Documentacao/blob/main/prints/Captura%20de%20tela%202025-10-22%20094011.png)

## 2️⃣ Subir Projeto no GitHub (se ainda não tiver)

Se seu projeto ainda não está no GitHub, faça isso:

```git
git init
git add .
git commit -m "primeiro commit"
git remote add origin https://github.com/seu-usuario/seu-repo.git
git push -u origin master
```

## 3️⃣ Fazer Deploy com Vercel

No painel da Vercel, clique em "Add New" > "Project"

Escolha o repositório do GitHub que você quer fazer deploy

A Vercel vai detectar o framework (HTML, React, Next.js, etc.)

Clique em "Deploy"

```git
https://nome-do-projeto.vercel.app
```

## 4️⃣ (Opcional) Usar o Vercel CLI
Instalar CLI:
npm install -g vercel

## 🛠️ Exemplos Rápidos
HTML puro

Coloque seus arquivos .html, .css e .js na raiz

Suba no GitHub e conecte à Vercel

React (Create React App)

Crie com:

npx create-react-app meu-app


Faça commit e push no GitHub

Deploy normalmente com a Vercel

Next.js (super integrado)

Crie com:

npx create-next-app meu-app
