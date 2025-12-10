# Spring Web - Java

```Java
// A anotação @Entity marca essa classe como uma entidade JPA (Java Persistence API), 
// ou seja, ela será mapeada para uma tabela em um banco de dados relacional.
@Entity
public class Produto {

    // A anotação @Id define que o campo 'id' é a chave primária da tabela no banco de dados.
    @Id
    
    // A anotação @GeneratedValue define que o valor do campo 'id' será gerado automaticamente
    // pelo banco de dados (geralmente usando um auto incremento).
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;  // O 'id' é o identificador único do produto no banco de dados.

    // Nome do produto, representado como uma String.
    private String nomeProduto;

    // O valor do produto (preço) em forma de número inteiro, por exemplo, em centavos.
    private Integer valor;

    // Quantidade disponível do produto em estoque, representada como um inteiro.
    private Integer quantEstoque;

    // Nome do fabricante do produto, também representado como uma String.
    private String fabricante;

    // Métodos Getters e Setters gerados para permitir acessar e modificar os valores das propriedades.

    // Getter para o campo 'id'
    public Long getId() {
        return id;
    }

    // Setter para o campo 'id'
    public void setId(Long id) {
        this.id = id;
    }

    // Getter para o campo 'nomeProduto'
    public String getNomeProduto() {
        return nomeProduto;
    }

    // Setter para o campo 'nomeProduto'
    public void setNomeProduto(String nomeProduto) {
        this.nomeProduto = nomeProduto;
    }

    // Getter para o campo 'valor'
    public Integer getValor() {
        return valor;
    }

    // Setter para o campo 'valor'
    public void setValor(Integer valor) {
        this.valor = valor;
    }

    // Getter para o campo 'quantEstoque'
    public Integer getQuantEstoque() {
        return quantEstoque;
    }

    // Setter para o campo 'quantEstoque'
    public void setQuantEstoque(Integer quantEstoque) {
        this.quantEstoque = quantEstoque;
    }

    // Getter para o campo 'fabricante'
    public String getFabricante() {
        return fabricante;
    }

    // Setter para o campo 'fabricante'
    public void setFabricante(String fabricante) {
        this.fabricante = fabricante;
    }
}
```
