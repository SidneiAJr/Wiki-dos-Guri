# Exemplo de codigo:

```java
package java1;

import java.util.Scanner;

public class Java1 {

    public static void main(String[] args) {
        // Criação do Scanner para leitura da entrada do usuário
        Scanner entrada = new Scanner(System.in);
        // Exibe o menu de opções para o usuário
        System.out.println("Insira uma Opcao\n1-Ninja\n2-Inimigo\n3-Quantidade de Lutas");
        
        int opcao = 0;
        // O loop continua até o usuário digitar a opção 4
        while(opcao != 4) {
            // Lê a opção escolhida pelo usuário
            opcao = entrada.nextInt();
            
            // Switch para executar ações conforme a opção do usuário
            switch(opcao) {
                case 1:
                    // Caso o usuário escolha "1", cria um objeto Ninja e chama o método ver()
                    ninja n1 = new ninja(100, "Inimigo", 5);
                    n1.ver();
                    break;
                case 2:
                    // Caso o usuário escolha "2", cria um objeto Inimigo e chama o método ver()
                    inimigo i1 = new inimigo(100, 2);
                    i1.ver();
                    break;
                case 3:
                    // Caso o usuário escolha "3", cria um objeto Luta e chama o método ver()
                    luta l1 = new luta(1, 100, 2);
                    l1.ver();
                    break;
                default:
                    // Se a opção não for 1, 2 ou 3, exibe uma mensagem de opção inválida
                    System.out.println("Opção Indisponivel");
                    break;
            }
            // Exibe novamente as opções
            System.out.println("Insira uma Opcao\n1-Ninja\n2-Inimigo\n3-Quantidade de Lutas");
        }
    }
}

// Interface que define o método ver() para as classes Ninja, Inimigo e Luta
interface verificar {
    void ver();
}

// Classe Ninja, implementa a interface "verificar"
class ninja implements verificar {
    // Definindo atributos da classe Ninja
    protected int vida;
    protected double dano;
    protected String Nome;

    // Construtor que recebe valores para vida, nome e dano
    public ninja(double dano, String Nome, int vida) {
        this.dano = dano;
        this.Nome = Nome;
        this.vida = vida;
    }

    // Método ver() implementado da interface "verificar"
    @Override
    public void ver() {
        // A vida é resetada para 100 e o dano começa com 1
        vida = 100;
        dano = 1;
        
        // Loop para simular a luta até o ninja morrer
        while(vida > 0) {
            vida--;  // Decrementa a vida do ninja a cada interação
            dano += 0.02;  // Aumenta o dano do ninja conforme o tempo
            // Exibe informações da luta
            System.out.println("Ninja esta lutando contra " + Nome + " Vida esta diminuindo " + vida + " E o dano esta Aumentando " + dano);
        }
        // Quando a vida do ninja chega a 0
        System.out.println("Ninja Morreu kkkk!");
    }
}

// Classe Inimigo, também implementa a interface "verificar"
class inimigo implements verificar {
    // Definindo atributos da classe Inimigo
    protected int VidaInimogo;
    protected int Dano;

    // Construtor que recebe valores para vida e dano
    public inimigo(int VidaInimogo, int Dano) {
        this.VidaInimogo = VidaInimogo;
        this.Dano = Dano;
    }

    // Método ver() implementado da interface "verificar"
    public void ver() {
        // A vida do inimigo começa em 100
        VidaInimogo = 100;
        
        // Loop para simular a luta até o inimigo morrer
        while(VidaInimogo > 0) {
            VidaInimogo--;  // Decrementa a vida do inimigo
            // Exibe informações da luta
            System.out.println("Inimigo Lutando contra Ninja " + VidaInimogo + " Dano Inimgo " + Dano);
        }
        // Quando a vida do inimigo chega a 0
        System.out.println("Inimigo Morreu kk!");
    }
}

// Classe Luta, herda de Inimigo e implementa a interface "verificar"
class luta extends inimigo implements verificar {
    // Atributo para a quantidade de lutas
    protected int quantidadeLuta;

    // Construtor que recebe valores para a quantidade de lutas, vida do inimigo e dano
    public luta(int quantidadeLuta, int VidaInimogo, int Dano) {
        super(VidaInimogo, Dano);  // Chama o construtor da classe "inimigo"
        this.quantidadeLuta = quantidadeLuta;
    }

    // Método ver() implementado da interface "verificar"
    @Override
    public void ver() {
        // Criação de um novo Scanner para ler a quantidade de lutas
        Scanner quant = new Scanner(System.in);
        // Pede ao usuário para inserir a quantidade de lutas (0 a 5)
        System.out.println("Insira a quantidade de Lutas (0 a 5)");
        quantidadeLuta = quant.nextInt();
        
        // Loop para exibir a quantidade de lutas
        for(int i = 1; i <= quantidadeLuta; i++) {
            System.out.println(" Quantidade de Lutas entre Ninja e Inimigo " + i);
        }
    }
}

 
```
   
