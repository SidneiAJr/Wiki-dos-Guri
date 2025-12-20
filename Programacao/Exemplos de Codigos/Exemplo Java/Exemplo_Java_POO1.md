# 🎮 POO em Java — Sistema simples de RPG (Explicado)

Este documento quebra **todo o código em pedaços**, explicando **o que é**, **para que serve** e **como funciona**, no estilo wiki pessoal para consulta futura.

---

## 📦 Pacote

```java
package javaapplication2;
```

### O que é

Define o **pacote** onde as classes estão organizadas.

### Para que serve

* Organizar o projeto
* Evitar conflito de nomes de classes
* Facilitar manutenção

---

## 🚀 Classe Principal (`main`)

```java
public class JavaApplication2 {

    public static void main(String[] args) {
        System.out.println("=== Bem vindo ===");

        Personagem pl = new Personagem("Guerreiro", 50, 34, 0, 80, 100, 0.5, 3.5);
        Personagem pl2 = new Personagem("Mago", 40, 20, 120, 70, 90, 0.8, 2.0);

        pl.VerificarAP();
        pl.VerificarArmadura();
        pl.VerificarDano();
        pl.VerificarHP();

        System.out.println("------------------");

        pl2.VerificarAP();
        pl2.VerificarArmadura();
        pl2.VerificarDano();
        pl2.VerificarHP();
    }
}
```

### O que acontece aqui

* Ponto de entrada do programa (`main`)
* Criação de **dois objetos** do tipo `Personagem`
* Cada objeto recebe atributos diferentes
* Chamada de métodos para exibir status

### Conceito aplicado

✅ **Instanciação de objetos**

---

## 📜 Interface `VerificarStatus`

```java
interface VerificarStatus {
    void VerificarHP();
    void VerificarArmadura();
    void VerificarDano();
    void VerificarAP();
}
```

### O que é

Uma **interface** define um **contrato**.

### O que isso significa

Toda classe que implementar essa interface é **obrigada** a implementar esses métodos.

### Por que usar

* Padronização
* Organização
* Base para polimorfismo

---

## 🧱 Classe Abstrata `ClassePer`

```java
abstract class ClassePer implements VerificarStatus {

    public String NomePersonagem;
    public int Dano;
    public int Armadura;
    public int AP;
    public int HP;
    public int VidaMax;
    public double AtaqueSpeed;
    public double RouboVida;

    ClassePer(String NomePersonagem, int Dano, int Armadura, int AP, int HP, int VidaMax, double AtaqueSpeed, double RouboVida) {
        this.NomePersonagem = NomePersonagem;
        this.Dano = Dano;
        this.Armadura = Armadura;
        this.AP = AP;
        this.HP = HP;
        this.VidaMax = VidaMax;
        this.AtaqueSpeed = AtaqueSpeed;
        this.RouboVida = RouboVida;
    }
}
```

### O que é

Uma **classe abstrata** serve como base para outras classes.

### Regras

* ❌ Não pode ser instanciada (`new ClassePer()` não funciona)
* ✅ Pode ter atributos
* ✅ Pode ter construtor
* ✅ Pode implementar interface

### Função aqui

Centralizar **atributos comuns** de qualquer personagem.

### Conceitos aplicados

* Classe abstrata
* Herança futura
* Reaproveitamento de código

---

## 🧍 Classe Concreta `Personagem`

```java
class Personagem extends ClassePer {

    Personagem(String NomePersonagem, int Dano, int Armadura, int AP, int HP, int VidaMax, double AtaqueSpeed, double RouboVida) {
        super(NomePersonagem, Dano, Armadura, AP, HP, VidaMax, AtaqueSpeed, RouboVida);
    }
```

### O que é

Classe **real**, que pode ser instanciada.

### O que `extends` faz

Herda tudo da classe `ClassePer`:

* Atributos
* Construtor base
* Contrato da interface

### `super()`

Chama o construtor da classe pai.

---

## 🔁 Métodos sobrescritos (`@Override`)

```java
@Override
public void VerificarHP() {
    System.out.println("HP de " + NomePersonagem + ": " + HP + "/" + VidaMax);
}
```

### O que é

Implementação real dos métodos definidos na interface.

### Por que usar `@Override`

* Garante que o método existe na interface
* Evita erro de digitação
* Facilita manutenção

### Métodos implementados

* `VerificarHP()` → Vida atual
* `VerificarArmadura()` → Defesa
* `VerificarDano()` → Dano físico
* `VerificarAP()` → Poder mágico

### Conceito aplicado

✅ **Polimorfismo**

---

## 🧠 Resumo mental (cola rápida)

```
Interface → contrato
Classe abstrata → base
extends → herança
super() → construtor pai
@Override → implementação obrigatória
new → cria objeto
```

---

## 📌 O que esse projeto demonstra bem

* Estrutura correta de POO
* Separação de responsabilidades
* Código limpo e didático
* Excelente material para portfólio e estudo

---

## ✅ Próximos passos naturais (se quiser evoluir)

* Encapsular atributos (`private` + getters)
* Criar subclasses (`Guerreiro`, `Mago`)
* Criar sistema de batalha
* Usar listas (`ArrayList<Personagem>`)

Esse código está **perfeito para wiki pessoal e revisão futura**.
