# ☕ O que é o Java JDK?

O Java Development Kit (JDK) é o kit oficial para desenvolvimento Java, que inclui o compilador, bibliotecas e ferramentas necessárias para criar, compilar e executar programas Java.

Para programar em Java, você precisa ter o JDK instalado no seu computador.

Você pode baixar o JDK oficial da Oracle em:
https://www.oracle.com/java/technologies/javase-jdk17-downloads.html

## 📘 Tutorial de Instalação do IntelliJ IDEA para Java

IntelliJ IDEA é uma IDE poderosa e popular para desenvolvimento em Java, Kotlin e outras linguagens.

Download do IntelliJ IDEA: https://www.jetbrains.com/idea/download/

## 🛠️ Etapas de Instalação

Baixe o instalador no link acima (recomendo a versão Community, gratuita).

Execute o instalador e siga as instruções padrão.

Abra o IntelliJ IDEA após a instalação.

## 🚀 Criando um Projeto Java

Na tela inicial, clique em "New Project".

Escolha Java no menu lateral.

Certifique-se de que o JDK está configurado (se não estiver, pode adicionar um JDK instalado no seu PC).

Clique em Next e depois Finish.

## 🧩 Explorando o Editor

O painel à esquerda é o Project Explorer, onde ficam os arquivos do projeto.

A área central é o editor de código.

Na parte inferior, você encontra o console, erros, e ferramentas de execução.

## ⌨️ Atalhos de Teclado Úteis no IntelliJ IDEA

| Ação                  | Atalho (Windows/Linux) | Atalho (macOS)      |
|-----------------------|------------------------|---------------------|
| Executar o Projeto    | `Shift + F10`          | `Ctrl + R`          |
| Construir Projeto     | `Ctrl + F9`            | `Cmd + F9`          |
| Comentar/Descomentar  | `Ctrl + /`             | `Cmd + /`           |
| Format Code           | `Ctrl + Alt + L`       | `Cmd + Option + L`  |
| Navegar para Classe   | `Ctrl + N`             | `Cmd + O`           |

## Exemplo de codigo:

```Java
package Saudacao;
import javax.swing.JOptionPane;


public class Swing {
     public static  void main (String[] args){
         String Nome = JOptionPane.showInputDialog("Qual é seu Nome do Aluno? ");
         String Turma = JOptionPane.showInputDialog("Turma: ");
         String idade = JOptionPane.showInputDialog("Idade: ");
         int id = Integer.parseInt(idade);
         JOptionPane.showMessageDialog(
           null,
           " Ola " + Nome+ " Turma "+ Turma + " Idade " + id ,
                 "Boas vindas ",
                 JOptionPane.INFORMATION_MESSAGE
         );

     }
}
```

## Exemplo de codigo Java:

```Java
import p.Pessoa; // Importando a classe p do pacote pessoa;

public class Main {
    public static void main(String[] args) {
        System.out.printf("================================================================= \n");
        Pessoa p1 = new Pessoa("Kalleo",21,"SL",false);
        p1.VerificarNome();
        p1.VerificarIdade();
        p1.CidadePessoa();
        p1.Apresentacao();
        p1.Rei();
        System.out.printf("================================================================= \n");
        Pessoa p2 = new Pessoa("Arthur",22,"SP",false);
        p2.VerificarNome();
        p2.VerificarIdade();
        p2.CidadePessoa();
        p2.Apresentacao();
        p2.Rei();
        System.out.printf("================================================================= \n");
        Pessoa p3 = new Pessoa("Dalvano Prime",30,"SL",false);
        p3.Apresentacao();
        p3.CidadePessoa();
        p3.VerificarNome();
        p3.VerificarNome();
        p3.Rei();
        System.out.printf("================================================================= \n");
        Pessoa p4 = new Pessoa("Silveiro Lima",900,"SL",true);
        p4.Apresentacao();
        p4.CidadePessoa();
        p4.VerificarNome();
        p4.VerificarNome();
        p4.Rei();
        }
    }
```

``` Java
package p; // Pacote P para mandar pra main

public class Pessoa {

    String NomePessoa;
    int IdadePessoa;
    String cidadePessoa;
    boolean isKing;
    public Pessoa(String NomePessoa, int IdadePessoa,String cidadePessoa,boolean isKing){
        this.cidadePessoa = cidadePessoa;
        this.NomePessoa = NomePessoa;
        this.IdadePessoa = IdadePessoa;
    }

    public void VerificarNome(){
        if(NomePessoa.equals("Kalleo")){
            System.out.println("Nome Prime");
        }else{
            System.out.println("Ta sem Nome");
        }
    }
    public void VerificarIdade(){
        if(IdadePessoa>=18){
            System.out.println("Maior de Idade " + IdadePessoa);
        }else{
            System.out.println("Menor de Idade "+ IdadePessoa);
        }
    }
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
                break;
        }
    }

    public void Apresentacao(){
        System.out.println("Nome " +NomePessoa+ " idade "+IdadePessoa +" cidade "+cidadePessoa);
    }

    public void Rei(){
          if(isKing==true){
              System.out.printf("È rei");
          }else{
              System.out.printf("Not King");
          }
    }
}

```

# Java Swing - intellij

```Java

package Saudacao;

import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class Aula02 {
    private JTextField txt_altura;
    private JTextField txt_peso;
    private JButton calculadoraButton;
    private JLabel saida1;


    public Aula02() {
        calculadoraButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String end1 = txt_altura.getText();
                String end2 = txt_peso.getText();

                double entrada1 = Double.parseDouble(end1);
                double entrada2 = Double.parseDouble(end2);


                double imc = entrada2/(entrada1*entrada1);

                if (imc < 18.5) {
                    saida1.setText(String.format("Abaixo do peso 🥳 %.2f", imc));
                } else if (imc < 25) {
                    saida1.setText(String.format("Peso normal 👍🏻 %.2f", imc));
                } else if (imc < 30) {
                    saida1.setText(String.format("Sobrepeso 🐍 %.2f", imc));
                } else if (imc < 35) {
                    saida1.setText(String.format("Obesidade grau I🐍🐍 %.2f", imc));
                } else if (imc < 40) {
                    saida1.setText(String.format("Obesidade grau II🐍🐍🐍 %.2f", imc));
                } else {
                    saida1.setText(String.format("Obesidade grau III🐍🐍🐍🐍 %.2f", imc));
                }

            }
        });
    }
    public static void main(String[] args) {
        Aula02 aula = new Aula02();

        // Painel para colocar todos os componentes
        JPanel panel = new JPanel();
        panel.setLayout(new BoxLayout(panel, BoxLayout.Y_AXIS));
        panel.setBorder(BorderFactory.createEmptyBorder(10, 10, 10, 10));

        panel.add(new JLabel("Altura (m):"));
        panel.add(aula.txt_altura);
        panel.add(new JLabel("Peso (kg):"));
        panel.add(aula.txt_peso);
        panel.add(aula.calculadoraButton);
        panel.add(aula.saida1);

        // Criando o frame principal
        JFrame frame = new JFrame("Calculadora de IMC");
        frame.setContentPane(panel);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.pack(); // Ajusta tamanho automático
        frame.setLocationRelativeTo(null); // Centraliza
        frame.setVisible(true);


    }
}

```

## Problemas Comuns no IntelliJ IDEA:

JDK não encontrado:
Se o IntelliJ não encontrar o JDK, vá até File > Project Structure > Project e configure o caminho do JDK.

Erro ao compilar "java: invalid source release: 11":
Certifique-se de que a versão do JDK que você configurou é compatível com o código que você está tentando rodar



