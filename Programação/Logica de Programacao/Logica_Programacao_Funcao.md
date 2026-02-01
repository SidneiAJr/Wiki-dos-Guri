# 🧠 Funções em C#, JavaScript, TypeScript, C++ e Java

Neste documento, vamos entender como as funções são tratadas em diferentes linguagens de programação.  
A ideia é conhecer as principais diferenças entre **C#**, **JavaScript**, **TypeScript**, **C++** e **Java**, focando nos conceitos de **declaração**, **parâmetros**, **tipos de retorno**, e **suporte a funções anônimas**.

---

## 1) **C#**
Em C#, funções são chamadas de **métodos** e são sempre associadas a **classes** ou **estruturas**. Elas podem ou não retornar valores e podem receber parâmetros de tipos definidos.

### Características:
- **Funções associadas a classes**.
- Suporte a **métodos anônimos** (delegates).
- **Tipagem forte**: sempre definimos o tipo de retorno e os tipos dos parâmetros.
- Permite **sobrecarregar métodos** (mesmo nome, mas com diferentes parâmetros).

---

## 2) **JavaScript**
O JavaScript é **dinâmico** e permite o uso de funções de diversas formas. Funções podem ser **declaradas de forma tradicional**, **usando expressões de função** ou **arrow functions**.

### Características:
- **Funções podem ser tratadas como objetos** (podem ser passadas como parâmetros).
- Suporte a **funções anônimas**.
- **Sem tipagem estática**: os parâmetros e o retorno podem ser de qualquer tipo.
- As funções podem ser **utilizadas em qualquer lugar** do código, já que o JavaScript é uma linguagem de primeira classe.

---

## 3) **TypeScript**
O TypeScript é uma extensão do **JavaScript** com **tipagem estática**. A sintaxe de funções é bastante similar à do JavaScript, mas com **tipos definidos**.

### Características:
- **Funções podem ser tratadas como objetos**, assim como no JavaScript.
- Suporte a **funções anônimas** e **arrow functions**.
- **Tipagem estática**: os parâmetros e o tipo de retorno **devem** ser definidos.
- Pode usar **overload de funções** para definir múltiplos comportamentos dependendo do tipo de entrada.

---

## 4) **C++**
Em C++, as funções podem ser definidas fora de **classes** ou dentro delas (métodos). C++ oferece **tipagem forte** e controle explícito sobre a **alocação de memória**.

### Características:
- **Funções podem ser globais ou associadas a classes**.
- **Funções podem ser sobrecarregadas** (diferente número ou tipo de parâmetros).
- Suporte a **funções anônimas** (desde C++11, usando `std::function`).
- **Tipagem estática**: tipo de retorno e parâmetros precisam ser definidos explicitamente.
  
---

## 5) **Java**
Java segue um modelo de **programação orientada a objetos** e funções são sempre **métodos dentro de classes**.

### Características:
- **Funções (métodos) sempre dentro de classes**.
- **Funções podem ser sobrecarregadas** (mesmo nome, diferentes parâmetros).
- Suporte a **funções anônimas** (expressões lambda desde Java 8).
- **Tipagem forte**: tipo de retorno e parâmetros devem ser definidos.

---

## Resumo das Funções nas Linguagens

| Linguagem     | Função | Tipagem | Métodos Anônimos | Sobrecarga | Tipos de Retorno | Parâmetros |
|---------------|--------|---------|------------------|------------|------------------|------------|
| **C#**        | Métodos dentro de classes | Forte | Delegates | Sim | Definido | Definido |
| **JavaScript**| Funções independentes ou dentro de objetos | Dinâmica | Sim | Não | Qualquer tipo | Qualquer tipo |
| **TypeScript**| Funções como no JavaScript, mas com tipagem | Estática | Sim | Sim | Definido | Definido |
| **C++**       | Funções dentro de classes ou globais | Forte | Sim (std::function) | Sim | Definido | Definido |
| **Java**      | Métodos dentro de classes | Forte | Lambda (desde Java 8) | Sim | Definido | Definido |

---

## Conclusão
Cada linguagem tem suas próprias particularidades, mas todas compartilham os **conceitos básicos de funções**: capacidade de executar código, aceitar parâmetros e retornar valores.  
- **C#**, **Java** e **C++** têm **tipagem forte** e um modelo de métodos associado a classes.  
- **JavaScript** e **TypeScript** oferecem mais flexibilidade e suporte a **funções anônimas** e **tipagem dinâmica** ou **estática**, respectivamente.

Esses conceitos são fundamentais para qualquer desenvolvedor entender e usar **funções** de forma eficiente no seu código.

