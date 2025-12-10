# ASP.NET Core - Estrutura de Projeto

## O que é ASP.NET Core
Framework para desenvolvimento de aplicações Web e APIs na plataforma .NET.

## Estrutura Padrão de Diretórios
- Program.cs → Ponto de entrada da aplicação
- appsettings.json → Configurações da aplicação
- Controllers → Lida com requisições HTTP
- Models → Representação de dados
- Views → Interface visual (quando MVC)
- wwwroot → Arquivos estáticos (CSS, JS, imagens)

## Ciclo de Funcionamento
1. Requisição HTTP chega na aplicação
2. Middleware processa
3. Controller responde
4. Retorno para o cliente
