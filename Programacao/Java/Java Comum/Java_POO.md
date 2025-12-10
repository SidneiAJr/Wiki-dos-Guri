# Tutorial Java - Classes, Interfaces e Herança

```java
package com.mycompany.teste;

// Classe principal com método main
public class Teste {

    public static void main(String[] args) {
        // Criação de usuários
        Usuario usuario1 = new Usuario("Pedro", true, "1234");
        usuario1.VerificarUsuario();      // Chama método que verifica o usuário
        usuario1.VerificarPermissao();    // Chama método que verifica permissão
        
        Usuario usuario2 = new Usuario("Daniel", true, "1234");
        usuario2.VerificarUsuario();
        usuario2.VerificarPermissao();
        
        Usuario usuario3 = new Usuario("Daniel", false, "1234");
        usuario3.VerificarUsuario();
        usuario3.VerificarPermissao();
        
        // Criação de entidade
        entidade entidade1 = new entidade("Pessoa", 16);
        entidade1.VerificarEntidade();    // Verifica a entidade e idade
    }
}

// Interface para verificação de usuários
interface Verificar{
    void VerificarInfoUser();   // Método genérico para verificar informações do usuário
    void VerificarUsuario();    // Método para verificar o nome do usuário
    void VerificarPermissao();  // Método para verificar permissões
    void Verificasenha();       // Método para verificar senha
}

// Interface para verificação de entidade
interface VerificarEntidade{
    void VerificarEntidade();   // Método para verificar entidade
}

// Classe abstrata que implementa a interface Verificar
abstract class InfoUsuario implements Verificar{
    public String NomeUsuario;  // Nome do usuário
    public boolean eadmin;      // Flag se é admin
    public String senha;        // Senha do usuário
    
    // Construtor
    InfoUsuario(String NomeUsuario, boolean eadmin, String senha){
        this.NomeUsuario = NomeUsuario;
        this.eadmin = eadmin;
        this.senha = senha;
    }
    
    // Implementações vazias dos métodos da interface
    public void VerificarInfoUser(){}
    public void VerificarUsuario(){}
    public void VerificarPermissao(){}
    public void Verificasenha(){}
}

// Classe para entidades, implementa VerificarEntidade
class entidade implements VerificarEntidade{
    public String Entidade;       // Nome da entidade
    public int IdadeEntidade;     // Idade da entidade
    
    // Construtor
    entidade(String Entidade, int IdadeEntidade){
        this.Entidade = Entidade;
        this.IdadeEntidade = IdadeEntidade;
    }
    
    // Método que verifica o tipo e idade da entidade
    public void VerificarEntidade(){
        if(Entidade == "Pessoa"){  // <- Comparação de string incorreta (usar .equals)
            System.out.println("Olá " + Entidade);
            if(IdadeEntidade <= 18){
                System.out.println("Idade da entidade: " + IdadeEntidade);
            } else {
                System.out.println("Entidade não pode entrar: " + IdadeEntidade);
            }
        } else {
            System.out.println("Olá " + Entidade);
        }
    }
}

// Classe Usuario que herda de InfoUsuario
class Usuario extends InfoUsuario{
   
    // Construtor
    Usuario(String NomeUsuario, boolean eadmin, String senha) {
        super(NomeUsuario, eadmin, senha);
    }

    // Verifica informações do usuário
    public void VerificarInfoUser(){
        if(NomeUsuario == "Pedro"){       // <- Comparação incorreta, usar .equals
            System.out.println("Olá " + NomeUsuario);
        } else if(NomeUsuario == "Daniel"){
            System.out.println("Olá! " + NomeUsuario);
        }
    }

    // Verifica usuário (nome)
    public void VerificarUsuario(){
        if(NomeUsuario == "Pedro"){       // <- Comparação incorreta, usar .equals
            System.out.println("Olá " + NomeUsuario);
        } else if(NomeUsuario == "Daniel"){
            System.out.println("Olá! " + NomeUsuario);
        }
    }

    // Verifica se é admin
    public void VerificarPermissao(){
        if(eadmin == true){
            System.out.println("Olá! Bem-vindo ao sistema " + NomeUsuario);
        } else {
            System.out.println("Não tem permissão");
        }
    }

    // Verifica senha
    public void Verificasenha(){
        if(senha == "1234"){               // <- Comparação incorreta, usar .equals
            System.out.println("A senha tem que ter caracter especial");
        } else {
            System.out.println("A senha está correta");
        }
    }
}
