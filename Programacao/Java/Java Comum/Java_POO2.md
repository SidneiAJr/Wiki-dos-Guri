# Java POO

``` JAVA
// Classe principal — ponto de entrada do programa
public class Main {

    // Método main: é aqui que o programa começa a executar
    public static void main(String[] args) {
        // Exibe a mensagem "Alo?" no console
        System.out.printf("Alo?");

        // Cria um objeto da classe 'msg', passando dois parâmetros (String)
        msg m = new msg("Hello", "teste");

        // Chama os métodos da classe msg
        m.Teste();   // Chama método que imprime "Hello and welcome!"
        m.Teste4();  // Chama método que testa o valor de 'teste'
        m.Teste3();  // Chama outro método condicional
    }
}

// -------------------------------------------------------------
// Interface 'Verificar' — define um contrato (duas assinaturas de métodos)
// Toda classe que implementar essa interface deve ter Teste() e Teste2()
interface Verificar {
    void Teste();
    void Teste2();
}

// -------------------------------------------------------------
// Segunda interface 'Verificar2' — define outro conjunto de métodos
// Toda classe que implementar essa interface deve ter Teste3() e Teste4()
interface Verificar2 {
    void Teste3();
    void Teste4();
}

// -------------------------------------------------------------
// Classe abstrata 'ver' que implementa as duas interfaces anteriores
// Como é 'abstract', não pode ser instanciada diretamente
// Ela serve como uma base para outras classes herdarem
abstract class ver implements Verificar, Verificar2 {

    // Atributos da classe — armazenam dados que podem ser usados pelos métodos
    public String teste;
    public String teste2;

    // Construtor — executado quando uma subclasse (como msg) é criada
    // Ele inicializa os atributos 'teste' e 'teste2' com os valores recebidos
    ver(String teste, String teste2) {
        this.teste = teste;
        this.teste2 = teste2;
    }
}

// -------------------------------------------------------------
// Classe 'msg' herda de 'ver' (ou seja, estende a classe abstrata)
// Como 'ver' implementa interfaces, 'msg' precisa implementar todos os métodos exigidos
class msg extends ver {

    // Construtor — chama o construtor da superclasse ('ver') para inicializar os atributos
    msg(String teste, String teste2) {
        super(teste, teste2);
    }

    // Implementação do método Teste3(), exigido pela interface Verificar2
    // Verifica se a String 'teste' tem o valor "Hello Word"
    public void Teste3() {
        if (teste.equals("Hello Word")) {
            System.out.printf("Hello and welcome!");
        } else {
            System.out.printf("Your is Communist?");
        }
    }

    // Implementação do método Teste4(), também exigido pela interface Verificar2
    // Faz uma comparação com o texto "E tetra"
    public void Teste4() {
        if (teste.equals("E tetra")) {
            System.out.printf("Hello and welcome!");
        } else {
            System.out.printf("Your is Communist?");
        }
    }

    // Implementação do método Teste(), exigido pela interface Verificar
    // Apenas imprime uma mensagem no console
    @Override
    public void Teste() {
        System.out.printf("Hello and welcome!");
    }

    // Implementação do método Teste2(), também da interface Verificar
    @Override
    public void Teste2() {
        System.out.printf("Hello and welcome!");
    }
}

```
