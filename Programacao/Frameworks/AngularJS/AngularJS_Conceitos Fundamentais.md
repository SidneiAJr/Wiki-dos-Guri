# 📌 AngularJS — Conceitos Fundamentais

AngularJS é um framework JavaScript estruturado para criar páginas **dinâmicas** e baseadas em **dados**, utilizando uma arquitetura de **separação entre visual e lógica**.

Ele permite que o HTML seja estendido com atributos próprios, tornando a interface mais inteligente sem necessidade de manipulação direta do DOM.

---

## 1) Objetivo Principal
Organizar aplicações front-end utilizando uma **camada de lógica (Controller)** e uma **camada de exibição (View)**, mantendo a **sincronização automática** entre elas.

---

## 2) Arquitetura Central
AngularJS segue o padrão:

**MVC — Model, View, Controller**

| Camada | Função |
|------|--------|
| View | Interface exibida ao usuário (HTML) |
| Controller | Lógica da aplicação e manipulação dos dados |
| Model | Informações manipuladas e exibidas |

O fluxo é contínuo: alterações nos dados refletem na tela, e interações na tela atualizam os dados.

---

## 3) `ng-app`
É o ponto inicial da aplicação.  
Define onde o AngularJS começa a agir no documento, ativando suas funcionalidades.

---

## 4) `ng-controller`
Define um **controlador**, responsável pela lógica da interface.  
Ele gerencia dados, eventos e comportamentos ligados à view.

---

## 5) `$scope`
É o **objeto intermediário** entre o HTML e a lógica do JavaScript.  
Tudo o que é exibido ou manipulado na interface passa por ele.

Funções principais:
- Carregar dados para aparecer na tela
- Receber informações digitadas pelo usuário
- Comunicar a View com o Controller

---

## 6) Interpolação (`{{ }}`)
É o mecanismo que permite mostrar valores do `$scope` na tela.  
Funciona como um espaço onde variáveis podem ser apresentadas de forma dinâmica.

---

## 7) `ng-model`
Cria uma **ligação direta** entre campos de entrada e o `$scope`.  
Permite que alterações feitas pelo usuário sejam refletidas automaticamente na lógica da aplicação.

---

## 8) Two-Way Data Binding
É o comportamento onde View e Controller ficam sincronizados:
- Se o dado muda no Controller → muda na View.
- Se o usuário altera algo na View → o dado muda no Controller.

Esse é um dos pilares do AngularJS.

---

## 9) `ng-repeat`
Utilizado para **repetir elementos** na interface a partir de listas de dados.  
Permite gerar conteúdo dinâmico sem loops diretos no HTML.

---

## 10) `ng-click`
Permite associar ações da interface com funções definidas no Controller, mantendo a lógica separada da exibição.

---

## 11) Services e `$http`
Services são componentes usados para **organizar funcionalidades reutilizáveis**.  
O serviço `$http` é empregado para comunicação com APIs externas, possibilitando carregamento de dados remotos.

---

## 🧠 Resumo Conceitual

| Conceito | Significado |
|---------|-------------|
| `ng-app` | Define onde a aplicação AngularJS inicia |
| `ng-controller` | Controla lógica, dados e eventos |
| `$scope` | Liga Controller e View |
| `{{ }}` | Exibe valores no HTML dinamicamente |
| `ng-model` | Sincroniza campos com variáveis |
| `ng-repeat` | Renderiza listas de forma automática |
| `ng-click` | Relaciona ações da interface com funções |
| `$http` | Realiza requisições externas |

---

## 🎯 Visão Geral
AngularJS organiza o código e simplifica a construção de interfaces dinâmicas, permitindo que a interface e os dados se mantenham sincronizados sem manipulação manual do DOM.

