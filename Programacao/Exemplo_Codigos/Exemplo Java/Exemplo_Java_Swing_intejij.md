# Exemplo de codigo 

```Java
package Saudacao;

import javax.swing.JOptionPane;

public class Swing {
    public static void main(String[] args) {

        // Solicita ao usuário que digite o nome do aluno
        String Nome = JOptionPane.showInputDialog("Qual é seu Nome do Aluno? ");

        // Solicita a turma do aluno
        String Turma = JOptionPane.showInputDialog("Turma: ");

        // Solicita a idade do aluno (digitada como texto)
        String idade = JOptionPane.showInputDialog("Idade: ");

        // Converte a idade digitada (String) para número inteiro
        int id = Integer.parseInt(idade);

        // Exibe uma mensagem final com os dados preenchidos pelo usuário
        JOptionPane.showMessageDialog(
            null,
            "Olá " + Nome + " | Turma: " + Turma + " | Idade: " + id,
            "Boas vindas",
            JOptionPane.INFORMATION_MESSAGE
        );
    }
}
```
## 📘 Explicação para o GitHub
## 📝 Descrição

Este programa em Java utiliza JOptionPane para solicitar informações ao usuário e exibir uma saudação personalizada.

Ele pede:

Nome do aluno

Turma

Idade

Após o usuário digitar os dados, o sistema mostra uma mensagem de boas-vindas com essas informações.

## 🎯 Conceitos utilizados
| Conceito                          | Explicação                          |
| --------------------------------- | ----------------------------------- |
| `JOptionPane.showInputDialog()`   | Coleta texto digitado pelo usuário  |
| `JOptionPane.showMessageDialog()` | Exibe uma mensagem na tela          |
| `Integer.parseInt()`              | Converte uma String para inteiro    |
| Entrada e saída gráfica           | Interação sem uso do terminal (GUI) |
| Método `main`                     | Ponto de entrada do programa Java   |

