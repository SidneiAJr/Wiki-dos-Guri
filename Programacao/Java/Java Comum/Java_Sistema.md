# Sistema sem IC - Alura Oracle Next Education:

```Java
import java.util.Scanner;  // Importa a classe Scanner para ler entradas do usuário

public class Main {

    // Método principal (main) onde a execução do programa começa
    public static void main(String[] args) {
        
        Scanner entrada = new Scanner(System.in);  // Cria um objeto Scanner para ler entradas do usuário
        System.out.println("Digite a Opção:  ");   // Exibe uma mensagem pedindo para o usuário digitar a opção
        int opcao = entrada.nextInt();             // Lê a opção do usuário (um número inteiro)
        double salario = 0;                        // Inicializa a variável salario com 0 (pode ser alterado conforme as opções)
        
        // Loop principal que continua enquanto a opção do usuário for diferente de 5
        while (opcao != 5) {
            switch (opcao) {
                case 1:
                    salario = sacar(salario, entrada);   // Chama o método sacar, passando o salário e o scanner
                    break;
                case 2:
                    salario = Info(salario, entrada);    // Chama o método Info para informar dados ao usuário
                    break;
                case 3:
                    salario = emp(salario, entrada);     // Chama o método emp para simulação de empréstimo
                    break;
                case 4:
                    salario = financiamento(salario, entrada); // Chama o método financiamento para simulação de financiamento
                    break;
                default:
                    System.out.println("Opção inválida."); // Caso a opção não seja nenhuma das anteriores, mostra mensagem de erro
            }
        }
    }

    // Método que simula um saque, diminuindo o valor do salário
    public static double sacar(double salario, Scanner entrada) {
        System.out.println("Bem-vindo ao programa!");
        System.out.println("Por Favor, Informe seu Nome:");  // Pede o nome do usuário
        String nome = entrada.next();   // Lê o nome do usuário
        System.out.println("Por Favor, Informe o Valor da Retirada:");  // Pede o valor da retirada
        double retirada = entrada.nextDouble();  // Lê o valor da retirada

        // Verifica se o valor da retirada é menor ou igual ao saldo do usuário
        if (retirada <= salario) {
            salario -= retirada;  // Deduz o valor retirado do saldo do usuário
            System.out.println("Retirada de R$ " + String.format("%.2f", retirada) + " realizada com sucesso!");  // Exibe a mensagem de sucesso
            System.out.println("Seu novo saldo é: R$ " + String.format("%.2f", salario));  // Exibe o novo saldo após o saque
        } else {
            System.out.println("Saldo insuficiente para a retirada.");  // Se o saldo for insuficiente, mostra a mensagem de erro
        }
        return salario;  // Retorna o novo saldo (pode ser atualizado no método principal)
    }

    // Método que coleta informações sobre o usuário e oferece um empréstimo com base no salário
    public static double Info(double salario, Scanner entrada) {
        System.out.println("Bem-vindo ao programa!");
        System.out.println("Por Favor, Informe seu Nome:");  // Pede o nome do usuário
        String nome = entrada.next();  // Lê o nome do usuário
        System.out.println("Informe Seu Salário:");  // Pede o salário do usuário
        salario = entrada.nextDouble();  // Lê o salário do usuário

        // Calcula o valor máximo do empréstimo como 30% do salário
        double emprestimo = salario * 0.30;
        System.out.println("Temos uma oferta para você de R$ " + String.format("%.2f", emprestimo));  // Exibe o valor da oferta
        System.out.println("Olá " + nome + ", bem-vindo!");  // Mensagem de boas-vindas
        System.out.println("Saldo disponível: R$ " + String.format("%.2f", salario));  // Exibe o saldo disponível

        return salario;  // Retorna o salário atualizado
    }

    // Método que simula a solicitação de um empréstimo
    public static double emp(double salario, Scanner entrada) {
        System.out.println("Bem-vindo ao sistema de Empréstimos!");
        System.out.println("Faça Simulação de Empréstimos!");
        System.out.println("Insira o Valor que Gostaria de Retirar R$: ");  // Solicita o valor do empréstimo
        double valor = entrada.nextDouble();  // Lê o valor do empréstimo
        System.out.println("Quantidade de Parcelas ");  // Solicita a quantidade de parcelas
        int parcela = entrada.nextInt();  // Lê a quantidade de parcelas

        // Calcula os juros totais do empréstimo (20% sobre o valor)
        double jurosTotais = valor * 0.20;
        double valorTotal = valor + jurosTotais;  // Valor total do empréstimo com juros
        double emprestimototal = valorTotal / parcela;  // Valor da parcela mensal

        // Exibe as informações sobre o empréstimo e as parcelas
        System.out.println("Valor Total do Empréstimo será R$ " + String.format("%.2f", valorTotal));
        System.out.println("Valor da Parcela será R$ " + String.format("%.2f", emprestimototal));

        return valorTotal;  // Retorna o valor total do empréstimo
    }

    // Método que simula a solicitação de um financiamento, com diferentes taxas de juros dependendo do valor
    public static double financiamento(double salario, Scanner entrada) {
        System.out.println("Bem-vindo ao sistema de Empréstimos!");
        System.out.println("Faça Simulação de Financiamento!");
        System.out.println("Insira o Valor que Gostaria de Retirar R$: ");  // Solicita o valor do financiamento
        double valor = entrada.nextDouble();  // Lê o valor do financiamento
        System.out.println("Quantidade de Parcelas: ");  // Solicita a quantidade de parcelas
        int parcela = entrada.nextInt();  // Lê a quantidade de parcelas

        double jurosTotais = 0;  // Inicializa a variável de juros
        double valorTotal = 0;   // Inicializa o valor total
        double emprestimototal = 0;  // Inicializa o valor da parcela total

        // Aplica diferentes taxas de juros dependendo do valor do financiamento
        if (valor >= 1000000) {
            jurosTotais = valor * 0.50;  // Se o valor for maior ou igual a 1 milhão, aplica 50% de juros
            valorTotal = valor + jurosTotais;  // Calcula o valor total com juros
            emprestimototal = valorTotal / parcela;  // Calcula o valor das parcelas
            System.out.println("Valor Total do Empréstimo será R$ " + String.format("%.2f", valorTotal));
            System.out.println("Valor da Parcela será R$ " + String.format("%.2f", emprestimototal));
        } else if (valor >= 500000) {
            jurosTotais = valor * 0.35;  // Se o valor for maior ou igual a 500 mil, aplica 35% de juros
            valorTotal = valor + jurosTotais;
            emprestimototal = valorTotal / parcela;
            System.out.println("Valor Total do Empréstimo será R$ " + String.format("%.2f", valorTotal));
            System.out.println("Valor da Parcela será R$ " + String.format("%.2f", emprestimototal));
        } else {
            System.out.println("Valor de empréstimo abaixo do limite permitido.");  // Se o valor não for suficiente, exibe mensagem de erro
            return 0;
        }

        return valorTotal;  // Retorna o valor total do financiamento
    }
}
```
