# 🧠 Lógica de Programação — Estruturas de Controle

Este documento explica como funcionam as principais estruturas usadas para **controlar o fluxo** de um programa: `if`, `else`, `else if`, `switch` e laços de repetição.

---

## 1) Condições

Condições são usadas para **tomar decisões** no código.  
Elas permitem que o programa siga **caminhos diferentes** dependendo de uma situação.

---

### 1.1 IF (Se)

O `if` verifica uma condição.  
Se a condição for **verdadeira**, um bloco é executado.  
Se for **falsa**, o bloco é ignorado.

> Use `if` para **testar algo diretamente**.

---

### 1.2 ELSE (Senão)

O `else` é executado **apenas quando o `if` é falso**.  
Ele representa a alternativa ao primeiro caminho.

> Use `else` quando existe **uma ação padrão** caso a condição não seja atendida.

---

### 1.3 ELSE IF (Senão se)

O `else if` permite testar **outras condições** caso o `if` inicial seja falso.  
Ele cria uma **cadeia de decisões**.

> Use `else if` quando existem **múltiplas possibilidades de resultado**.

---

### Resumo das Condições

| Estrutura | Quando Usar | Exemplo de Situação |
|---------|-------------|---------------------|
| **if** | Verificar algo diretamente | "Se tiver dinheiro" |
| **else if** | Tentar outras análises | "Se não tiver dinheiro, mas tiver cartão" |
| **else** | Caso contrário | "Se nada disso for possível" |

---

## 2) SWITCH (Escolha)

`switch` é usado quando temos **muitas comparações** envolvendo **um mesmo valor**.

Ao invés de vários `if / else if`, o `switch` organiza melhor os caminhos possíveis.

> Use `switch` quando há **várias opções fixas**  
> Ex.: dias da semana, menus, comandos, categorias.

O `switch` verifica um valor e escolhe **apenas um caso correspondente**.

---

## 3) Laços de Repetição (Loops)

Loops são usados quando algo precisa **se repetir**.  
A repetição continua até que **uma condição deixe de ser verdadeira**.

---

### 3.1 Loop Controlado por Contador

É quando sabemos **quantas vezes** algo deve ser repetido.

- Chamado de laço **contado**
- Usado para tarefas previsíveis

> Ex.: repetir uma ação 10 vezes.

---

### 3.2 Loop Controlado por Condição

É quando **não sabemos quantas vezes** algo repetirá.  
A repetição ocorre enquanto **uma condição permanecer válida**.

> Ex.: repetir até que o usuário finalize uma ação.

---

### 3.3 Loop Infinito

Quando a condição **nunca se torna falsa**, a repetição continua para sempre.  
Geralmente **não é desejado**, exceto em sistemas contínuos (ex.: servidores).

---

## 4) Interrupções no Loop

- **Parar a repetição** (quando necessário)
- **Pular uma execução** e continuar nas próximas

Esses controles servem para ajustar o comportamento do loop durante sua execução.

---

