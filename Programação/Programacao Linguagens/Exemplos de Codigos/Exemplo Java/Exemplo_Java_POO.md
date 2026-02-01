# Java | Exemplo POO com Menu, Interface e Herança

Este exemplo é **didático**, feito para treino de:

* `Scanner`
* `switch`
* `while` e `for`
* **Interface**
* **Implementação de interface**
* **Herança**
* **Construtor**
* **Polimorfismo básico**

Abaixo o código é **quebrado em partes**, com explicação simples para lembrar depois.

---

## 📦 Package

```java
package java1;
```

### O que isso faz?

* Define o **pacote** onde a classe está.
* Serve para **organização do projeto**.
* Evita conflito de nomes em projetos maiores.

---

## 📥 Importação

```java
import java.util.Scanner;
```

### O que é o Scanner?

* Classe usada para **ler dados digitados pelo usuário**.
* Aqui será usada para ler números do teclado.

---

## 🚀 Classe Principal

```java
public class Java1 {
```

* Classe principal do programa.
* O Java sempre começa a execução pelo `main`.

---

## 🔑 Método main

```java
public static void main(String[] args) {
```

* Ponto inicial do programa.
* Tudo começa aqui.

---

## ⌨️ Scanner de Entrada

```java
Scanner entrada = new Scanner(System.in);
```

* Cria um objeto `Scanner`.
* Permite ler valores digitados no console.

---

## 📜 Menu Inicial

```java
System.out.println("Insira uma Opcao\n1-Ninja\n2-Inimigo\n3-Quantidade de Lutas");
```

* Exibe o menu de opções.
* `\n` quebra linha no texto.

---

## 🔁 Controle do Menu (while)

```java
int opcao = 0;
while(opcao != 4) {
```

* Enquanto a opção **não for 4**, o programa continua.
* Obs: o menu não mostra a opção 4, mas ela encerra o loop.

---

## 📖 Leitura da Opção

```java
opcao = entrada.nextInt();
```

* Lê o número digitado pelo usuário.
* Armazena na variável `opcao`.

---

## 🔀 Estrutura switch

```java
switch(opcao) {
```

* Decide o que executar baseado na opção escolhida.
* Substitui vários `if/else`.

---

## 🥷 Caso 1 – Ninja

```java
ninja n1 = new ninja(100, "Inimigo", 5);
n1.ver();
```

* Cria um objeto da classe `ninja`.
* Chama o método `ver()`.
* Demonstra **instanciação de objeto**.

---

## 👾 Caso 2 – Inimigo

```java
inimigo i1 = new inimigo(100, 2);
i1.ver();
```

* Cria um objeto da classe `inimigo`.
* Chama o método `ver()`.

---

## ⚔️ Caso 3 – Luta

```java
luta l1 = new luta(1, 100, 2);
l1.ver();
```

* Cria um objeto da classe `luta`.
* Usa **herança**, pois `luta` herda de `inimigo`.

---

## ❌ Default – Opção Inválida

```java
System.out.println("Opção Indisponivel");
```

* Executado quando o número não é 1, 2 ou 3.

---

## 🔁 Menu Repete

```java
System.out.println("Insira uma Opcao\n1-Ninja\n2-Inimigo\n3-Quantidade de Lutas");
```

* Exibe o menu novamente após cada ação.

---

## 📐 Interface verificar

```java
interface verificar {
    void ver();
}
```

### O que é uma interface?

* Define um **contrato**.
* Quem implementar é **obrigado** a usar o método `ver()`.
* Não possui código, só assinatura do método.

---

## 🥷 Classe ninja

```java
class ninja implements verificar {
```

* Implementa a interface `verificar`.
* É obrigada a implementar `ver()`.

### Atributos

```java
protected int vida;
protected double dano;
protected String Nome;
```

* `protected`: acessível pela classe e pelas filhas.

---

## 🏗️ Construtor Ninja

```java
public ninja(double dano, String Nome, int vida) {
```

* Inicializa os atributos ao criar o objeto.

---

## 🔁 Método ver() do Ninja

```java
vida = 100;
dano = 1;
```

* Reinicia os valores.

```java
while(vida > 0) {
```

* Simula a luta enquanto o ninja está vivo.

```java
vida--;
dano += 0.02;
```

* Vida diminui.
* Dano aumenta.

---

## 👾 Classe inimigo

```java
class inimigo implements verificar {
```

* Também implementa a interface.

### Atributos

```java
protected int VidaInimogo;
protected int Dano;
```

---

## 🏗️ Construtor Inimigo

```java
public inimigo(int VidaInimogo, int Dano) {
```

* Inicializa vida e dano do inimigo.

---

## 🔁 Método ver() do Inimigo

```java
VidaInimogo = 100;
```

* Reinicia a vida.

```java
while(VidaInimogo > 0) {
```

* Loop até o inimigo morrer.

---

## ⚔️ Classe luta (Herança)

```java
class luta extends inimigo implements verificar {
```

* `extends inimigo` → herda atributos e métodos.
* `implements verificar` → obriga ter `ver()`.

---

## 🏗️ Construtor Luta

```java
super(VidaInimogo, Dano);
```

* Chama o construtor da classe `inimigo`.
* Reaproveita código.

---

## 🔢 Método ver() da Luta

```java
Scanner quant = new Scanner(System.in);
```

* Scanner exclusivo para quantidade de lutas.

```java
quantidadeLuta = quant.nextInt();
```

* Usuário define quantas lutas acontecerão.

```java
for(int i = 1; i <= quantidadeLuta; i++) {
```

* Loop `for` para repetir a luta.

---

## 🧠 Conceitos Trabalhados

* Programação Orientada a Objetos
* Interface
* Implementação
* Herança
* Construtor
* Laços de repetição
* Entrada de dados
* Menu interativo

---

📌 **Resumo mental**:

> Menu → Escolha → Objeto → Método `ver()` → Simulação
