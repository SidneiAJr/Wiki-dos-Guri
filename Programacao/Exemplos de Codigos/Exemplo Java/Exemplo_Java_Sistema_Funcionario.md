# Sistema de Funcionários – Herança + Classe Abstrata + Interface

Este exemplo demonstra:

- ✔️ Interface (Verificadora)

- ✔️ Classe Abstrata (Pessoa)

- ✔️ Herança entre classes

- ✔️ Polimorfismo nos métodos VerificarSalario()

- ✔️ Sobrescrita de métodos (override)

````java
// Classe principal — Ponto de entrada do programa
class Main {
    public static void main(String[] args) {

        // Criando instâncias das classes
        Gerente gerente1 = new Gerente("Pedro Antonio", 20, 4000);
        Estagiario estagiario1 = new Estagiario("Pedro Jr", 17, 1000);
        MenorAprendiz menorAprendiz = new MenorAprendiz("Gabriel Silva", 14, 500);
        CEO ceo = new CEO("Pedro Alcantara Junior", 55, 25000);

        // Chamando métodos polimórficos
        estagiario1.VerificarSalario();
        menorAprendiz.VerificarSalario();
        ceo.VerificarSalario();
        gerente1.VerificarSalario();
    }
}


/* ===========================================================
   Interface Verificadora
   Define um contrato obrigatório para métodos relacionados à
   verificação de idade e salário de pessoas.
   =========================================================== */
interface Verificadora {
    void VerificarIdade();
    void VerificarSalario();
}


/* ===========================================================
   Classe Abstrata Pessoa
   Representa o modelo genérico de qualquer pessoa da empresa.
   Esta classe NÃO pode ser instanciada.
   =========================================================== */
abstract class Pessoa {
    public String NomePessoa;
    public int IdadePessoa;
    public double Salario;

    Pessoa(String NomePessoa, int IdadePessoa, double Salario) {
        this.NomePessoa = NomePessoa;
        this.IdadePessoa = IdadePessoa;
        this.Salario = Salario;
    }
}


/* ===========================================================
   Classe Gerente
   Herda atributos de Pessoa e possui sua própria regra de
   ajuste salarial.
   =========================================================== */
class Gerente extends Pessoa {

    Gerente(String NomePessoa, int IdadePessoa, double Salario) {
        super(NomePessoa, IdadePessoa, Salario);
    }

    @Override
    public void VerificarSalario() {
        if (Salario >= 4000) {
            Salario -= 0.27; // Ajuste simbólico
            System.out.printf("Salário ajustado: R$ %.2f | Nome: %s%n", Salario, NomePessoa);
        } else {
            System.out.println("Salário sem desconto.");
        }
    }

    @Override
    public void VerificarIdade() {}
}


/* ===========================================================
   Classe Estagiario
   Aumenta salário caso seja muito baixo.
   =========================================================== */
class Estagiario extends Pessoa {

    Estagiario(String NomePessoa, int IdadePessoa, double Salario) {
        super(NomePessoa, IdadePessoa, Salario);
    }

    @Override
    public void VerificarSalario() {
        if (Salario <= 1000) {
            Salario += 100; // Bônus para estagiários
            System.out.printf("Salário ajustado: R$ %.2f | Nome: %s%n", Salario, NomePessoa);
        } else {
            System.out.printf("Salário: R$ %.2f%n", Salario);
        }
    }

    @Override
    public void VerificarIdade() {}
}


/* ===========================================================
   Classe MenorAprendiz
   Regra simples de aumento salarial base.
   =========================================================== */
class MenorAprendiz extends Pessoa {

    MenorAprendiz(String NomePessoa, int IdadePessoa, double Salario) {
        super(NomePessoa, IdadePessoa, Salario);
    }

    @Override
    public void VerificarSalario() {
        if (Salario <= 500) {
            Salario += 70;
            System.out.printf("Salário ajustado: R$ %.2f | Nome: %s%n", Salario, NomePessoa);
        } else {
            System.out.printf("Salário: R$ %.2f%n", Salario);
        }
    }

    @Override
    public void VerificarIdade() {}
}


/* ===========================================================
   Classe CEO
   Aumenta o salário caso esteja abaixo do teto definido.
   =========================================================== */
class CEO extends Pessoa {

    CEO(String NomePessoa, int IdadePessoa, double Salario) {
        super(NomePessoa, IdadePessoa, Salario);
    }

    @Override
    public void VerificarSalario() {
        if (Salario <= 50000) {
            Salario += 1000;
            System.out.printf("Salário ajustado: R$ %.2f | Nome: %s%n", Salario, NomePessoa);
        } else {
            System.out.printf("Salário: R$ %.2f%n", Salario);
        }
    }

    @Override
    public void VerificarIdade() {}
}

````

