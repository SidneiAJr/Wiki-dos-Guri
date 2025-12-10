# ☕ Criar e Rodar Programas Java Comuns (main) no NetBeans

## 🎯 Objetivo
Aprender a criar e executar programas Java simples no NetBeans, usando o método `main`, que é o ponto de entrada de toda aplicação Java.

---

## 🧱 O que é o método `main()`
Todo programa Java começa pelo método:

```java
public static void main(String[] args) {
    // código aqui
}
```

## 🧰 Criando um Projeto Java no NetBeans

Abra o NetBeans.

Vá em File → New Project.

Escolha Java with Ant → Java Application.

Clique em Next.

Dê um nome pro projeto (ex: PrimeiroPrograma).

Deixe marcada a opção Create Main Class.

Clique em Finish.

package primeiroprograma;

```java
public class PrimeiroPrograma {
    public static void main(String[] args) {
        System.out.println("Olá, Mundo! 👋");
    }
}
```

```
import java.util.Scanner;

public class EntradaUsuario {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Digite seu nome: ");
        String nome = sc.nextLine();
        System.out.println("Bem-vindo, " + nome + "!");
    }
}
```
