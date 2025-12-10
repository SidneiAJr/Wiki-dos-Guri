# Exemplo Java | POO Retorno 

````java
package exemplo;

public class Calculadora {

    // Método estático que não retorna nada (void)
    public static void exibirMensagem(String mensagem) {
        System.out.println(mensagem);  // Apenas imprime uma mensagem
    }

    // Método estático que retorna um valor inteiro (int)
    public static int somar(int a, int b) {
        return a + b;  // Retorna a soma dos dois números
    }

    // Método estático que retorna um valor double
    public static double dividir(double a, double b) {
        if (b == 0) {
            System.out.println("Erro: divisão por zero");
            return 0;  // Retorna 0 em caso de erro de divisão por zero
        }
        return a / b;  // Retorna o resultado da divisão
    }

    // Método de instância que retorna uma string (String)
    public String saudacao(String nome) {
        return "Olá, " + nome + "!";  // Retorna uma saudação personalizada
    }

    public static void main(String[] args) {
        // Chamando o método estático sem instanciar a classe
        exibirMensagem("Bem-vindo à Calculadora!");

        // Chamando o método estático que retorna int
        int resultadoSoma = somar(10, 5);
        System.out.println("Resultado da soma: " + resultadoSoma);

        // Chamando o método estático que retorna double
        double resultadoDivisao = dividir(10.0, 2.0);
        System.out.println("Resultado da divisão: " + resultadoDivisao);

        // Criando uma instância da classe para chamar o método de instância
        Calculadora calc = new Calculadora();
        String mensagemSaudacao = calc.saudacao("João");
        System.out.println(mensagemSaudacao);
    }
}
````

## `Quadro Comparativo - Métodos em Java`

| **Tipo de Retorno** | **Método**                                            | **Exemplo de Uso**                                   | **Explicação**                                                                                                   |
| ------------------- | ----------------------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| **`void`**          | Método que não retorna valor                          | `public static void exibirMensagem(String mensagem)` | O método **`void`** não retorna nada. Serve para realizar ações, como imprimir ou modificar variáveis.           |
| **`int`**           | Método que retorna um valor inteiro                   | `public static int somar(int a, int b)`              | O método **`int`** retorna um valor inteiro. Ideal para cálculos que geram números inteiros.                     |
| **`double`**        | Método que retorna um valor decimal (ponto flutuante) | `public static double dividir(double a, double b)`   | O método **`double`** retorna um valor de ponto flutuante. Usado para cálculos que exigem precisão decimal.      |
| **`String`**        | Método que retorna uma string                         | `public String saudacao(String nome)`                | O método **`String`** retorna uma cadeia de caracteres (texto). Usado para retornar mensagens ou dados textuais. |

## `Exemplo de Métodos com Diferentes Tipos de Retorno:`

| **Tipo de Método** | **Exemplo de Método**                                | **Explicação**                                                          |
| ------------------ | ---------------------------------------------------- | ----------------------------------------------------------------------- |
| **`void`**         | `public static void exibirMensagem(String mensagem)` | Não retorna nenhum valor. Apenas executa ações como mostrar algo.       |
| **`int`**          | `public static int somar(int a, int b)`              | Retorna um valor inteiro (exemplo: soma de dois números).               |
| **`double`**       | `public static double dividir(double a, double b)`   | Retorna um valor decimal (exemplo: divisão de dois números decimais).   |
| **`String`**       | `public String saudacao(String nome)`                | Retorna uma cadeia de caracteres (exemplo: uma saudação personalizada). |


