# Java - POO 

```Java
import pessoa.Pessoa; // Importa a classe Pessoa que está no pacote 'pessoa'

public class Main { // Classe principal do programa
    public static void main(String[] args) { // Método main: ponto de entrada do programa
        // Cria um objeto da classe Pessoa, passando nome, idade e cidade
        Pessoa p1 = new Pessoa("Joao", 21, "SL");

        // Chama métodos da classe Pessoa para mostrar informações e verificar dados
        p1.VerificarNome();    // Verifica se o nome é "Kalleo" e imprime mensagem correspondente
        p1.VerificarIdade();   // Verifica se a idade é maior ou menor de idade e imprime
        p1.CidadePessoa();     // Mostra o nome completo da cidade com base no código
        p1.Apresentacao();     // Mostra os dados da pessoa formatados
    }
}
```

``` Java
package pessoa; // Define o pacote da classe, útil para organizar o projeto

public class Pessoa { // Classe Pessoa representa uma pessoa com nome, idade e cidade

    // Atributos da classe
    String NomePessoa;   // Nome da pessoa
    int IdadePessoa;     // Idade da pessoa
    String cidadePessoa; // Código da cidade (ex: "SP", "SL", "NH")

    // Construtor público da classe Pessoa
    public Pessoa(String NomePessoa, int IdadePessoa, String cidadePessoa){
        this.cidadePessoa = cidadePessoa; // Inicializa a cidade
        this.NomePessoa = NomePessoa;     // Inicializa o nome
        this.IdadePessoa = IdadePessoa;   // Inicializa a idade
    }

    // Método para verificar o nome da pessoa
    public void VerificarNome(){
        if(NomePessoa.equals("Kalleo")){
            System.out.println("Nome Bonito em..."); // Caso o nome seja Kalleo
        } else {
            System.out.println("Ta sem Nome");       // Caso contrário
        }
    }

    // Método para verificar se a pessoa é maior ou menor de idade
    public void VerificarIdade(){
        if(IdadePessoa <= 18){ // <=18 é considerado menor de idade
            System.out.println("Maior de Idade " + IdadePessoa); // Atenção: lógica está invertida
        } else {
            System.out.println("Menor de Idade " + IdadePessoa);
        }
    }

    // Método para mostrar o nome completo da cidade baseado no código
    public void CidadePessoa(){
        switch (cidadePessoa){
            case "SP":
                System.out.println("São Paulo");
                break;
            case "Sl":
                System.out.println("São Leopoldo");
                break;
            case "NH":
                System.out.println("Novo Hamburgo");
                break;
            default:
                System.out.println("Cidade desconhecida");
                break;
        }
    }

    // Método para apresentar todos os dados da pessoa de forma formatada
    public void Apresentacao(){
        System.out.println("Nome: " + NomePessoa + ", Idade: " + IdadePessoa + ", Cidade: " + cidadePessoa);
    }
}
```
