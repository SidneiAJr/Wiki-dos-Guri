# 🐳 Introdução ao Docker e DevOps Básico

O Docker é uma ferramenta que permite empacotar aplicações e dependências dentro de containers, garantindo que rodem igual em qualquer lugar — seja no teu PC, servidor ou nuvem.
Já o DevOps é a cultura e conjunto de práticas que unem desenvolvimento (Dev) e operações (Ops) para entregar software de forma rápida, automatizada e confiável.


## 🧱 O que é um Container?

Um container é como uma caixa isolada que contém:

Seu código

Suas dependências

Seu sistema operacional mínimo

Isso garante que a aplicação funcione igual em qualquer ambiente.

## 📦 Exemplo:

"Funciona na minha máquina" não existe mais com Docker.

## ⚙️ Instalação

Windows / macOS: https://www.docker.com/get-started

Linux (Ubuntu):

sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker

## 🧩 Exemplo: Rodando um Container Ubuntu
docker run -it ubuntu bash


Isso abre um terminal dentro de um container Ubuntu isolado.

## 📦 Exemplo: Subindo um Servidor Web
docker run -d -p 8080:80 nginx


-d → roda em background

-p 8080:80 → mapeia a porta 8080 do host pra porta 80 do container

nginx → imagem do servidor web NGINX


Verifique se está instalado:

docker --version
