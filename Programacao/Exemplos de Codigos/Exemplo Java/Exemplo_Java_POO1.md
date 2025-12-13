# POO em Java
```java
package javaapplication2;

public class JavaApplication2 {

    public static void main(String[] args) {

        // Mensagem inicial
        System.out.println("=== Bem vindo ===");

        // Criação de dois personagens com atributos diferentes
        Personagem pl = new Personagem("Guerreiro", 50, 34, 0, 80, 100, 0.5, 3.5);
        Personagem pl2 = new Personagem("Mago", 40, 20, 120, 70, 90, 0.8, 2.0);

        // Exibe status do Guerreiro
        pl.VerificarAP();
        pl.VerificarArmadura();
        pl.VerificarDano();
        pl.VerificarHP();

        System.out.println("------------------");

        // Exibe status do Mago
        pl2.VerificarAP();
        pl2.VerificarArmadura();
        pl2.VerificarDano();
        pl2.VerificarHP();
    }
}

// Interface definindo métodos obrigatórios
interface VerificarStatus {
    void VerificarHP();
    void VerificarArmadura();
    void VerificarDano();
    void VerificarAP();
}

// Classe abstrata com atributos comuns e construtor base
abstract class ClassePer implements VerificarStatus {

    public String NomePersonagem;
    public int Dano;
    public int Armadura;
    public int AP; // Poder mágico
    public int HP; // Vida atual
    public int VidaMax; // Vida máxima
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

// Classe concreta herdando da classe abstrata
class Personagem extends ClassePer {

    Personagem(String NomePersonagem, int Dano, int Armadura, int AP, int HP, int VidaMax, double AtaqueSpeed, double RouboVida) {
        super(NomePersonagem, Dano, Armadura, AP, HP, VidaMax, AtaqueSpeed, RouboVida);
    }

    @Override
    public void VerificarHP() {
        System.out.println("HP de " + NomePersonagem + ": " + HP + "/" + VidaMax);
    }

    @Override
    public void VerificarArmadura() {
        System.out.println("Armadura de " + NomePersonagem + ": " + Armadura);
    }

    @Override
    public void VerificarDano() {
        System.out.println("Dano de " + NomePersonagem + ": " + Dano);
    }

    @Override
    public void VerificarAP() {
        System.out.println("AP de " + NomePersonagem + ": " + AP);
    }
}
```
# 📘 Explicação pra colocar no GitHub
## 🎮 Projeto: Sistema simples de RPG com POO

Este código demonstra conceitos fundamentais de Programação Orientada a Objetos em Java usando personagens de RPG como exemplo.

## Conceitos utilizados
| Conceito                | Onde aparece                             |
| ----------------------- | ---------------------------------------- |
| Interface               | `VerificarStatus`                        |
| Classe abstrata         | `ClassePer`                              |
| Herança                 | `Personagem extends ClassePer`           |
| Polimorfismo            | Métodos sobrescritos (`@Override`)       |
| Encapsulamento lógico   | Atributos e comportamento por personagem |
| Instanciação de objetos | `new Personagem(...)`                    |
